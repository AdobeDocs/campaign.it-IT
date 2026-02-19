---
title: Componente aggiuntivo di sicurezza avanzato di Campaign
description: Linee guida per la configurazione sicura per il componente aggiuntivo di sicurezza avanzato di Campaign
feature: Configuration
role: Developer
level: Experienced
exl-id: 7c586836-82e1-45fb-9c28-18361572e1fa
source-git-commit: 925f8152d28f60f876c5ef4420064fa0d71cdb9d
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 2%

---


# Componente aggiuntivo Sicurezza avanzata di Campaign {#enhanced-security}

Questa pagina fa parte delle [linee guida per la configurazione protetta consigliata](security.md#public-guidance) da Adobe per Campaign v8, disponibili pubblicamente.

Per rendere più sicura la connessione di rete e migliorare la sicurezza delle risorse, [!DNL Adobe Campaign] offre un nuovo componente aggiuntivo **Protezione avanzata**.

Questo componente aggiuntivo include due caratteristiche dell’ecosistema:

* [Integrazione Secure Customer-Managed Key (CMK)](#secure-cmk-integration)

* [Tunneling VPN (Virtual Private Network) sicuro](#secure-vpn-tunneling)

Queste funzioni sono descritte di seguito.

In questa pagina sono elencati alcuni guardrail e limitazioni relativi alle funzioni di sicurezza avanzate. Inoltre, è necessario assicurarsi che tutti i casi di utilizzo dell’integrazione CMK sicura/tunneling VPN sicuro funzionino.

Una volta implementate queste funzionalità, Adobe monitora:

* Disponibilità dell’istanza e avvisa se la chiave non è disponibile.

* I tunnel VPN e procedere con l’avviso in caso di problemi.

## Integrazione sicura delle chiavi gestite dal cliente {#secure-cmk-integration}

L&#39;integrazione di **Secure Customer-Managed Key (CMK)** ti consente di crittografare i dati inattivi utilizzando la tua chiave tramite il tuo account Amazon Web Services (AWS).

Le chiavi gestite dal cliente sono chiavi del servizio di gestione delle chiavi nell’account AWS che crei, possiedi e gestisci. Queste chiavi KMS sono completamente controllate e utilizzate per crittografare e decrittografare i dati. Questa capacità, che rende responsabili della generazione e della gestione delle chiavi di crittografia, consente di avere un maggiore controllo su di esse, inclusa la revoca di una chiave.

>[!CAUTION]
>
>In caso di revoca di una chiave, è necessario essere consapevoli degli effetti. [Ulteriori informazioni](#cmk-callouts)

Per abilitare l’integrazione della CMK con Campaign, effettua le seguenti operazioni:

1. Connettiti al tuo account [Amazon Web Services (AWS)](https://aws.amazon.com/){target="_blank"}.

1. Genera una chiave con rotazione automatica quando utilizzi AWS Key Management Service (KMS). [Scopri come](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}.

1. Applica la policy fornita da Adobe al tuo account AWS per concedere l’accesso alle tue risorse. [Ulteriori informazioni](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"}. <!--link TBC-->

1. Condividi [Amazon Resource Name (ARN chiave)](https://docs.aws.amazon.com/kms/latest/developerguide/find-cmk-id-arn.html){target="_blank"} con [!DNL Adobe Campaign]. A questo scopo, contatta il tuo rappresentante Adobe. <!--or Adobe transition manager?-->

1. Crea e verifica le regole di Amazon EventBridge per abilitare il monitoraggio delle chiavi da parte di Adobe&#x200B; [Ulteriori informazioni](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}.


### Guardrail e limitazioni {#cmk-callouts}

Le seguenti protezioni e limitazioni si applicano all’integrazione della CMK con Adobe Campaign v8:

* Adobe non fornisce un account [Amazon Web Services (AWS)](https://aws.amazon.com/){target="_blank"}. Devi disporre di un tuo account AWS e configurarlo per generare e condividere la tua chiave con Adobe.

* Sono supportate solo [chiavi del servizio di gestione delle chiavi di AWS](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"} (KMS). Non è possibile utilizzare chiavi generate dal cliente al di fuori di KMS&#x200B;

* Durante la prima configurazione è previsto un tempo di inattività. &#x200B;La durata del tempo di inattività dipende dalle dimensioni del database.

* In qualità di cliente, possiedi e gestisci la chiave. Devi contattare Adobe in caso di modifiche alla chiave. &#x200B;

* Puoi controllare la tua chiave utilizzando [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"} e revocarla, se necessario&#x200B;

* In caso di revoca, disabilitazione o eliminazione della chiave, le risorse e l’istanza crittografate diventano inaccessibili fino a quando non viene ripristinata l’azione corrispondente.

  >[!CAUTION]
  >
  >Se si disattiva la chiave e non si ripristina questa azione entro 7 giorni, il database può essere ripristinato solo dal backup.
  >
  >Se elimini la chiave e non ripristini questa azione entro 30 giorni, tutti i dati verranno eliminati definitivamente e andranno persi&#x200B;

## Tunneling Secure Virtual Private Network {#secure-vpn-tunneling}

Il tunneling **VPN (Secure Virtual Private Network)** è una VPN da sito a sito che fornisce accesso sicuro ai dati in transito su una rete privata, dalla sede all&#39;istanza [!DNL Adobe Campaign].

<!--As it connects two networks together, it is a site-to-site VPN.-->

Per garantire l&#39;elevata disponibilità (HA), utilizza due tunnel per evitare interruzioni nel caso in cui si verifichi un problema su un singolo tunnel.

Sono supportati tre casi d’uso:

* Federated Data Access (FDA) tramite VPN, per accedere al database locale dall’istanza Campaign tramite VPN

* Accesso all’istanza tramite VPN da un client spesso

* Accesso SFTP dell’istanza tramite VPN

>[!CAUTION]
>
>Sono supportati i database locali e cloud. [Ulteriori informazioni](#vpn-databases)

Per garantire un utilizzo corretto di questa funzione, attieniti alle linee guida seguenti:

* Configura la tua VPN laterale in base alla configurazione della VPN lato Adobe.

* Mantenere entrambi i tunnel aggiornati per un&#39;elevata disponibilità.

* Monitorare il tunnel laterale.

* L&#39;utente deve essere l&#39;iniziatore del tunnel e deve essere allineato per riavviare la connessione in caso di interruzione del tunnel.

* Imposta un meccanismo di esecuzione di un nuovo tentativo alla tua estremità in caso di errori di connessione.

### Database e dispositivi supportati {#vpn-databases}

Sono supportati i seguenti database locali:

* MySQL
* Netezza
* Oracle
* SAP HANA
* SQL Server
* Sybase
* Teradata
* Hadoop tramite HiveSQL
* PostgreSQL

I database cloud sono supportati. Consulta la [matrice di compatibilità](../start/compatibility-matrix.md#FederatedDataAccessFDA).

>[!NOTE]
>
>* La connettività VPN a terze parti o a fornitori esterni non è supportata.
>
>* Non sono incluse le VPN aggiuntive gestite da Adobe per i database cloud privati.
