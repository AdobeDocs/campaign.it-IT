---
title: Guida introduttiva all’architettura di Campaign
description: Scopri gli ambienti e nozioni di base sull’implementazione
feature: Overview
role: Data Engineer
level: Beginner
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 7%

---

# Guida introduttiva all’architettura di Campaign{#gs-ac-archi}

## Ambienti {#environments}

Campaign è reso disponibile come istanze individuali con ogni istanza che rappresenta un ambiente completo per Campaign.

Due tipi di ambienti disponibili con Cloud Service Campaign:

* **Ambiente di produzione**: ospita le applicazioni per i professionisti del business.

* **Ambiente non di produzione**: utilizzati per vari test di prestazioni e qualità prima che le modifiche all’applicazione vengano inviate all’ambiente di produzione.

Puoi esportare e importare i pacchetti da un ambiente all’altro.

![](../assets/do-not-localize/book.png) Ulteriori informazioni sui pacchetti in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html)

## Modello di distribuzione{#ac-deployment}

Nella [Distribuzione aziendale (FFDA)](enterprise-deployment.md), [!DNL Adobe Campaign] v8 funziona con due database: locale [!DNL Campaign] database per la messaggistica in tempo reale e le query unitarie dell’interfaccia utente e per la scrittura tramite API e un cloud [!DNL Snowflake] database per l’esecuzione della campagna, le query batch e l’esecuzione del flusso di lavoro.

Campaign v8 Enterprise introduce il concetto di **Accesso completo ai dati federati** (FFDA): tutti i dati sono ora remoti nel database cloud. Con questa nuova architettura, la distribuzione Campaign v8 Enterprise (FFDA) semplifica la gestione dei dati: sul database cloud non è richiesto alcun indice. È sufficiente creare le tabelle, copiare i dati e iniziare. La tecnologia del database Cloud non richiede una manutenzione specifica per garantire la qualità del servizio.



<!--Two deployment models are available:

* **Campaign FDA [!DNL Snowflake] deployment**

In its [[!DNL Snowflake] FDA deployment](fda-deployment.md), [!DNL Adobe Campaign] v8 is connected to [!DNL Snowflake] to access data through Federated Data Access capability: you can access and process external data and information stored in your [!DNL Snowflake] database without changing the structure of Adobe Campaign data. PostgreSQL is the primary database, and Snowflake is the secondary database. You can extend your data model and store your data on Snowflake. Subsequently, you can run ETL, segmentation and reports on a large data set with outstanding performances.

* **Campaign Enterprise (FFDA) deployment**

-->

## Architettura del Centro messaggi{#transac-msg-archi}

La messaggistica transazionale (Message Center) è il modulo di Campaign progettato per la gestione dei messaggi di attivazione.

![](../assets/do-not-localize/glass.png) Scopri come inviare messaggi transazionali in [questa sezione](../send/transactional.md).

In risposta a un’azione di un cliente su un sito web, viene inviato un evento Campaign tramite un’API REST e il modello di messaggio viene compilato con le informazioni o i dati forniti tramite la chiamata API e viene inviato al cliente un messaggio transazionale in tempo reale. Questi messaggi possono essere inviati singolarmente o in batch tramite e-mail, SMS o notifiche push.

In questa architettura specifica, la cella di esecuzione è separata dall’istanza di controllo per garantire un’elevata disponibilità e gestione del carico.

* La **Istanza di controllo** (o istanza di marketing) viene utilizzata dagli esperti di marketing e dai team IT per creare, configurare e pubblicare modelli di messaggio. Questa istanza centralizza anche il monitoraggio e la cronologia degli eventi.

   ![](../assets/do-not-localize/glass.png) Scopri come creare e pubblicare modelli di messaggio in [questa sezione](../send/transactional.md).

* La **Istanza di esecuzione** recupera gli eventi in arrivo (ad esempio, reimpostazione della password o ordini da un sito web) e invia messaggi personalizzati. Ci può essere più di un&#39;istanza di esecuzione per elaborare i messaggi tramite il load-balancer e scalare il numero di eventi da elaborare per la massima disponibilità.

>[!CAUTION]
>
>L&#39;istanza di controllo e le istanze di esecuzione devono essere installate su computer diversi. Non possono condividere la stessa istanza Campaign.

![](assets/messagecenter_diagram.png)

### Autenticazione

Per utilizzare queste funzionalità, gli utenti di Adobe Campaign accedono all’istanza di controllo per creare modelli di messaggi transazionali, generare l’anteprima del messaggio utilizzando un elenco di seed, visualizzare i rapporti e monitorare le istanze di esecuzione.

* Istanza di esecuzione singola Quando interagisci con un&#39;istanza di esecuzione del Centro messaggi ospitata da un Adobe, un sistema esterno può prima recuperare un token di sessione (che per impostazione predefinita scade tra 24 ore), effettuando una chiamata api al metodo di accesso alla sessione, utilizzando un login e una password dell&#39;account specificati.
Quindi, con sessionToken fornito dall&#39;istanza di esecuzione in risposta alla chiamata precedente, l&#39;applicazione esterna può effettuare chiamate API SOAP (rtEvents o batchEvents) per inviare comunicazioni, senza la necessità di includere in ogni chiamata SOAP il login e la password dell&#39;account.

* Più istanze di esecuzione In un&#39;architettura di esecuzione a più celle con più istanze di esecuzione dietro un load balancer, il metodo di accesso richiamato dall&#39;applicazione esterna sta passando attraverso il load balancer: per questo motivo non è possibile utilizzare un’autenticazione basata su token. È necessaria un’autenticazione basata su utente/password.

![](../assets/do-not-localize/book.png) Ulteriori informazioni sugli eventi di messaggistica transazionale in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html#about-transactional-messaging-datamodel)