---
title: Componente aggiuntivo di sicurezza avanzato
description: Introduzione al componente aggiuntivo di sicurezza avanzato di Campaign
feature: Configuration
role: Developer
level: Experienced
hide: true
hidefromtoc: true
exl-id: 7c586836-82e1-45fb-9c28-18361572e1fa
source-git-commit: f9b064dffa0f8792e8653760cb2ac44cfdf43848
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 1%

---

# Componente aggiuntivo di sicurezza avanzato {#enhanced-security}

Per rendere più sicura la connessione di rete e migliorare la sicurezza delle risorse, [!DNL Adobe Campaign] offre una nuova **Sicurezza avanzata** componente aggiuntivo.

Questo componente aggiuntivo include due caratteristiche dell’ecosistema:

* [Integrazione sicura CMK](#secure-cmk-integration)

* [Tunneling VPN sicuro](#secure-vpn-tunneling)

Queste funzioni sono descritte di seguito.

## Integrazione sicura CMK {#secure-cmk-integration}

Il **Integrazione Secure Customer-Managed Key (CMK)** ti consente di crittografare l’istanza e i dati utilizzando la tua chiave tramite l’account Amazon Web Services (AWS).

Le chiavi gestite dal cliente sono chiavi del servizio di gestione delle chiavi nell’account AWS che crei, possiedi e gestisci. Queste chiavi KMS sono completamente controllate e utilizzate per crittografare e decrittografare i dati. Questa capacità, che rende responsabili della generazione e della gestione delle chiavi di crittografia, consente di avere un maggiore controllo su di esse, inclusa la revoca di una chiave.

>[!CAUTION]
>
>In caso di revoca di una chiave, è necessario essere consapevoli degli effetti. [Ulteriori informazioni](#cmk-callouts)

Per abilitare l’integrazione della CMK con Campaign, effettua le seguenti operazioni:

1. Connetti al tuo [Amazon Web Services (AWS)](https://aws.amazon.com/){target="_blank"} account.

1. Genera una chiave con rotazione automatica quando utilizzi AWS Key Management Service (KMS). [Scopri come](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}.

1. Applica la policy fornita da Adobe all’account AWS per concedere l’accesso alle risorse. [Ulteriori informazioni](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"}. <!--link TBC-->

1. Condividi [Nome risorsa Amazon (ARN chiave)](https://docs.aws.amazon.com/kms/latest/developerguide/find-cmk-id-arn.html){target="_blank"} con [!DNL Adobe Campaign]. Per farlo, contatta il rappresentante del tuo Adobe. <!--or Adobe transition manager?-->

1. Creare e testare le regole Amazon EventBridge per abilitare il monitoraggio delle chiavi per Adobe &#x200B; [Ulteriori informazioni](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}.

## Tunneling VPN sicuro {#secure-vpn-tunneling}

Il **Tunneling VPN (Virtual Private Network) sicuro** è una VPN da sito a sito che fornisce accesso sicuro ai tuoi dati in transito su una rete privata, dalla tua sede al [!DNL Adobe Campaign] dell&#39;istanza.

<!--As it connects two networks together, it is a site-to-site VPN.-->

Per garantire l&#39;elevata disponibilità (HA), utilizza due tunnel per evitare interruzioni nel caso in cui si verifichi un problema su un singolo tunnel.

Sono supportati tre casi d’uso:

* Federated Data Access (FDA) tramite VPN<!--to access your on-premise database from the Campaign instance over VPN-->

* Accesso all’istanza tramite VPN da un client spesso

* Accesso SFTP dell’istanza tramite VPN

>[!CAUTION]
>
>Sono supportati solo i database on-premise e i dispositivi VPN conformi a AWS. [Ulteriori informazioni](#vpn-callouts)

Per garantire un utilizzo corretto di questa funzione, attieniti alle linee guida seguenti:

* Imposta la tua VPN laterale in base alla configurazione della VPN lato Adobe.

* Mantenere entrambi i tunnel aggiornati per un&#39;elevata disponibilità.

* Monitorare il tunnel laterale.

* L&#39;utente deve essere l&#39;iniziatore del tunnel e deve essere allineato per riavviare la connessione in caso di interruzione del tunnel.

* Imposta un meccanismo di esecuzione di un nuovo tentativo alla tua estremità in caso di errori di connessione.

## Guardrail {#callouts}

Di seguito sono elencati alcuni guardrail e limitazioni relativi alle funzioni di sicurezza avanzate.

* Assicurati che tutti i casi di utilizzo dell’integrazione CMK sicura/tunneling VPN sicuro funzionino.

<!--* Adobe shall reach out to you or your technical team if any issue is found on your side.

* Currently, when using Enhanced security features, any communication with Adobe must be performed manually via email.-->

* Adobe di monitoraggio:

   * Disponibilità dell’istanza e avvisa se la chiave non è disponibile.

   * I tunnel VPN e procedere con l’avviso in caso di problemi.

### Guardrail di integrazione Secure CMK {#cmk-callouts}

* L’Adobe non fornisce un account AWS. Devi disporre di un tuo account AWS e configurarlo per generare e condividere la chiave con Adobe.

* Solo [Servizio di gestione delle chiavi AWS](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"} Sono supportate le chiavi (KMS). Non è possibile utilizzare chiavi generate dal cliente al di fuori di KMS&#x200B;

* Per la prima configurazione saranno necessari alcuni tempi di inattività. &#x200B;La durata del periodo di inattività dipenderà dalle dimensioni del database.

* Poiché possiedi e gestisci la chiave, devi contattare Adobe in caso di modifiche alla chiave&#x200B;

* Puoi controllare la tua chiave utilizzando [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"} e revocarla se necessario&#x200B;

* In caso di revoca, disabilitazione o eliminazione della chiave, le risorse e l’istanza crittografate diventano inaccessibili fino a quando non viene ripristinata l’azione corrispondente.

  >[!CAUTION]
  >
  >Se si disattiva la chiave e non si ripristina questa azione entro 7 giorni, il database può essere ripristinato solo dal backup.
  >
  >Se elimini la chiave e non ripristini questa azione entro 30 giorni, tutti i dati verranno eliminati definitivamente e andranno persi&#x200B;

### Guardrail di tunneling VPN sicuri {#vpn-callouts}

* Attualmente, sono supportati solo i database locali, ad esempio<!--Richa to check the list with PM-->:

   * MySQL
   * Netezza 
   * Oracle 
   * SAP HANA 
   * SQL Server 
   * Sybase 
   * Teradata 
   * Hadoop tramite HiveSQL

* Sono supportati solo i dispositivi VPN conformi ad AWS. Un elenco di dispositivi compatibili è disponibile su [questa pagina](https://docs.aws.amazon.com/vpn/latest/s2svpn/your-cgw.html#example-configuration-files){target="_blank"}<!--check which list should be communicated-->.

* La connettività VPN a terze parti o a fornitori esterni non è supportata.

* Non sono incluse VPN aggiuntive gestite da Adobi per database cloud privati.
