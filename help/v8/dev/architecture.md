---
solution: Campaign
product: Adobe Campaign
title: Guida introduttiva all’architettura di Campaign
description: Guida introduttiva all’architettura di Campaign
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# Guida introduttiva all’architettura di Campaign{#gs-ac-archi}

## Ambienti

Campaign è reso disponibile come istanze individuali con ogni istanza che rappresenta un ambiente completo per Campaign.

Tre tipi di ambienti disponibili con Cloud Service Campaign:

* Ambiente di produzione: ospita le applicazioni per i professionisti del business.

* Ambiente stage: utilizzati per vari test di prestazioni e qualità prima che le modifiche all’applicazione vengano inviate all’ambiente di produzione.

* Ambiente di sviluppo: consente agli sviluppatori di implementare Campaign nelle stesse condizioni di runtime degli ambienti di stage e produzione.

Puoi esportare e importare i pacchetti da un ambiente all’altro.

:arrow_Upper_right: Ulteriori informazioni sui pacchetti nella documentazione di [Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html?lang=en#about-data-packages)

## Distribuzione mid-sourcing{#mid-sourcing-deployment}

La comunicazione generale tra server e processi viene eseguita secondo il seguente schema:

![](assets/architecture.png)

* I moduli di esecuzione e gestione dei messaggi non recapitati sono disabilitati nell’istanza.

* L’applicazione è configurata per eseguire l’esecuzione dei messaggi su un server remoto &quot;mid-sourced&quot;, gestito utilizzando chiamate SOAP (su HTTP o HTTPS).

>[!NOTE]
>
> Campaign v8 si basa su un’architettura ibrida. Se stai eseguendo la transizione da Campaign Classic v7, tieni presente che tutte le consegne passano attraverso il server di mid-sourcing .
> Di conseguenza, l’indirizzamento interno è **impossibile** in Campaign v8 e l’account esterno è stato disabilitato di conseguenza.


## Architettura del centro messaggi{#transac-msg-archi}

La messaggistica transazionale (Message Center, Centro messaggi) è il modulo Campaign progettato per la gestione dei messaggi di attivazione.

:lampadina: Scopri come inviare messaggi transazionali in [questa sezione](../send/transactional.md).

In risposta a un’azione di un cliente su un sito web, viene inviato un evento Campaign tramite un’API REST e il modello di messaggio viene compilato con le informazioni o i dati forniti tramite la chiamata API e viene inviato al cliente un messaggio transazionale in tempo reale. Questi messaggi possono essere inviati singolarmente o in batch tramite e-mail, SMS o notifiche push.

In questa architettura specifica, la cella di esecuzione è separata dall’istanza di controllo per garantire un’elevata disponibilità e gestione del carico.

* L’ **istanza di controllo** (o istanza di marketing) viene utilizzata dagli esperti di marketing e dai team IT per creare, configurare e pubblicare modelli di messaggio. Questa istanza centralizza anche il monitoraggio e la cronologia degli eventi.

   :arrow_Upper_right: Scopri come creare e pubblicare modelli di messaggio nella [documentazione Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/message-templates/introduction.html?lang=en#transactional-messaging)

* L’ **istanza di esecuzione** recupera gli eventi in arrivo (ad esempio, reimpostazione della password o ordini da un sito web) e invia messaggi personalizzati. Ci può essere più di un&#39;istanza di esecuzione per elaborare i messaggi tramite il load-balancer e scalare il numero di eventi da elaborare per la massima disponibilità.

>[!CAUTION]
>
>L&#39;istanza di controllo e le istanze di esecuzione devono essere installate su computer diversi. Non possono condividere la stessa istanza Campaign.

![](assets/messagecenter_diagram.png)

:arrow_Upper_right: L&#39;architettura del Centro messaggi è descritta nella [documentazione Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/transactional-messaging-architecture.html?lang=en#transactional-messaging)


### Autenticazione

Per utilizzare queste funzionalità, gli utenti di Adobe Campaign accedono all’istanza di controllo per creare modelli di messaggi transazionali, generare l’anteprima del messaggio utilizzando un elenco di seed, visualizzare i rapporti e monitorare le istanze di esecuzione.

* Istanza di esecuzione singola
Quando interagisci con un&#39;istanza di esecuzione del Centro messaggi ospitata da un Adobe, un sistema esterno può prima recuperare un token di sessione (che per impostazione predefinita scade tra 24 ore), effettuando una chiamata api al metodo di accesso alla sessione utilizzando un login e una password dell&#39;account specificati.
Quindi, con sessionToken fornito dall&#39;istanza di esecuzione in risposta alla chiamata precedente, l&#39;applicazione esterna può effettuare chiamate API SOAP (rtEvents o batchEvents) per inviare comunicazioni, senza la necessità di includere in ogni chiamata SOAP il login e la password dell&#39;account.

* Più istanze di esecuzione
In un’architettura di esecuzione a più celle con più istanze di esecuzione dietro un load balancer, il metodo di accesso richiamato dall’applicazione esterna passa attraverso il load balancer: per questo motivo non è possibile utilizzare un’autenticazione basata su token. È necessaria un’autenticazione basata su utente/password.

:arrow_Upper_right: Ulteriori informazioni sugli eventi di messaggistica transazionale nella [documentazione Campaign Classic](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/event-description.html?lang=en#about-transactional-messaging-datamodel)