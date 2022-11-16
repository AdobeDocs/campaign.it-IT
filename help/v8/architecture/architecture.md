---
title: Guida introduttiva all’architettura di Campaign
description: Scopri ambienti e nozioni di base sulla distribuzione, inclusa la modalità di creazione di rapporti su un ambiente campagna.
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 507f30d16eecf5400ee88a4d29913e4cdaca9cba
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 12%

---

# Guida introduttiva all’architettura di Campaign{#gs-ac-archi}

## Ambienti {#environments}

Campaign è reso disponibile come istanze individuali con ogni istanza che rappresenta un ambiente completo per Campaign.

Sono disponibili due tipi di ambienti:

* **Ambiente di produzione**: ospita le applicazioni per i professionisti del business.

* **Ambiente non di produzione**: utilizzati per vari test di prestazioni e qualità prima che le modifiche all’applicazione vengano inviate all’ambiente di produzione.

Puoi esportare e importare i pacchetti da un ambiente all’altro.

![](../assets/do-not-localize/book.png) Ulteriori informazioni sui pacchetti in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html){target=&quot;_blank&quot;}

## Modelli di distribuzione{#ac-deployment}

Sono disponibili due modelli di distribuzione:

* **FDA campagna [!DNL Snowflake] distribuzione**

   Nella [[!DNL Snowflake] Distribuzione FDA](fda-deployment.md), [!DNL Adobe Campaign] v8 è collegato a [!DNL Snowflake] per accedere ai dati tramite la funzionalità Federated Data Access: puoi accedere ed elaborare dati e informazioni esterni memorizzati nel tuo [!DNL Snowflake] senza modificare la struttura dei dati di Adobe Campaign. PostgreSQL è il database principale e il Snowflake è il database secondario. Puoi estendere il modello dati e memorizzare i dati sul Snowflake. Successivamente, puoi eseguire ETL, segmentazione e rapporti su un set di dati di grandi dimensioni con prestazioni eccezionali.

* **Distribuzione di Campaign Enterprise (FFDA)**

   Nel contesto di un [Distribuzione aziendale (FFDA)](enterprise-deployment.md), [!DNL Adobe Campaign] v8 funziona con due database: locale [!DNL Campaign] database per la messaggistica in tempo reale e le query unitarie dell’interfaccia utente e per la scrittura tramite API e un cloud [!DNL Snowflake] database per l’esecuzione della campagna, le query batch e l’esecuzione del flusso di lavoro.

   Campaign v8 Enterprise introduce il concetto di **Full Federated Data Access** (FFDA): adesso tutti i dati sono remoti, nel database cloud. Con questa nuova architettura, l’implementazione di Campaign v8 Enterprise (FFDA) semplifica la gestione dei dati, in quanto nel database cloud non è richiesto alcun indice. È sufficiente creare le tabelle, copiare i dati e iniziare. La tecnologia del database cloud non richiede una manutenzione specifica per garantire la qualità del servizio.


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

![](../assets/do-not-localize/book.png) Ulteriori informazioni sugli eventi di messaggistica transazionale in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html#about-transactional-messaging-datamodel){target=&quot;_blank&quot;}
