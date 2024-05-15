---
title: Introduzione all’architettura di Campaign
description: Scopri nozioni di base su ambienti e distribuzione, incluso come creare rapporti su un ambiente di Campaign.
feature: Architecture, Deployment
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 10%

---

# Introduzione all’architettura di Campaign{#gs-ac-archi}

## Ambienti {#environments}

Campaign è disponibile come istanza singola, dove ogni istanza rappresenta un ambiente Campaign completo.

Sono disponibili due tipi di ambienti:

* **Ambiente di produzione**: ospita le applicazioni per gli utenti business.

* **Ambiente non di produzione**: utilizzato per vari test di prestazioni e qualità prima che le modifiche all’applicazione vengano inviate all’ambiente di produzione.

Puoi esportare e importare pacchetti da un ambiente a un altro.

Ulteriori informazioni sui pacchetti in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html){target="_blank"}

## Modelli di distribuzione {#ac-deployment}

Sono disponibili due modelli di distribuzione: **Distribuzione FDA di Campaign** (P1-P3) e **Distribuzione di Campaign Enterprise (FFDA)** (P4).

### Distribuzione FDA di Campaign {#ac-deployment-fda}

Nel suo [Distribuzione FDA](fda-deployment.md), [!DNL Adobe Campaign] v8 può essere connesso a [!DNL Snowflake] per accedere ai dati tramite la funzionalità Federated Data Access: puoi accedere ed elaborare dati e informazioni esterni memorizzati nel tuo [!DNL Snowflake] senza modificare la struttura dei dati di Adobe Campaign. PostgreSQL è il database primario ed è possibile utilizzare Snowflake come database secondario per estendere quindi il modello dati e archiviare i dati nel Snowflake. Successivamente, puoi eseguire ETL, segmentazione e rapporti su un set di dati di grandi dimensioni con prestazioni eccezionali.


![](assets/P1-P3-architecture.png){zoomable=&quot;yes&quot;}

>[!NOTE]
>
>In questo modello di distribuzione, il [!DNL Snowflake] database secondario disponibile solo su richiesta. Per aggiornare la distribuzione con [!DNL Snowflake], contatta il tuo Adobe Transition Manager.
>

### Distribuzione di Campaign Enterprise (FFDA) {#ac-deployment-ffda}

Nell&#39;ambito di una [Distribuzione aziendale (FFDA)](enterprise-deployment.md), [!DNL Adobe Campaign] v8 funziona con due database: uno locale [!DNL Campaign] database per la messaggistica in tempo reale, le query unitarie dell’interfaccia utente, le operazioni di scrittura tramite API e un cloud [!DNL Snowflake] database per l’esecuzione della campagna, le query batch e l’esecuzione dei flussi di lavoro.

Campaign v8 Enterprise introduce il concetto di **Full Federated Data Access** (FFDA): adesso tutti i dati sono remoti, nel database cloud. Con questa nuova architettura, l’implementazione di Campaign v8 Enterprise (FFDA) semplifica la gestione dei dati, in quanto nel database cloud non è richiesto alcun indice. È sufficiente creare le tabelle, copiare i dati e iniziare. La tecnologia del database Cloud non richiede una manutenzione specifica per garantire le prestazioni del servizio.

![](assets/P4-architecture.png){zoomable=&quot;yes&quot;}


## Esecuzione della consegna divisa {#split}

>[!AVAILABILITY]
>
>Questa funzione è disponibile solo per i clienti con più configurazioni di istanze MID.

A seconda del pacchetto Campaign v8, ti viene fornito un numero specifico di istanze di mid-sourcing responsabili dell’esecuzione delle consegne.

Per impostazione predefinita, gli account esterni di tutti i canali utilizzano un **[!UICONTROL Alternate]** modalità di routing, che indica che una consegna viene inviata da ogni istanza mid alla volta in modo alternativo.

Per garantire prestazioni migliori in termini di velocità e scalabilità, puoi consentire la suddivisione automatica delle consegne tra le istanze di mid-sourcing in modo che vengano consegnate più rapidamente ai destinatari. Questa operazione è trasparente durante l’esecuzione della consegna dall’istanza di marketing: una volta inviata la consegna, tutti i registri vengono consolidati insieme, prima di essere rimandati all’istanza di marketing in un singolo oggetto di consegna.

A questo scopo, è necessario disporre di ulteriori account esterni con **[!UICONTROL Split]** la modalità di routing viene creata al momento del provisioning per ogni canale:

* Consegna divisa - E-mail (splitDeliveryEmail)
* Consegna divisa - SMS (splitDeliverySMS)
* Consegna divisa - iOS (splitDeliveryIOS)
* Consegna divisa - Android (splitDeliveryAndroid)

![](assets/splitted-delivery.png)

>[!IMPORTANT]
>
>Per impostazione predefinita, la modalità di routing diviso è abilitata per l’account &quot;Consegna divisa - E-mail&quot;. Per tutti gli altri account esterni dei canali, contatta l’Adobe Transition Manager per abilitare l’opzione.
>
>Per impostazione predefinita, il valore di dimensione della soglia per suddividere una consegna tra più mid è 100.000. È possibile modificare questo valore nell’opzione &quot;NmsDelivery_MultiMidSplitThreshold&quot; in **[!UICONTROL Administration]** / **[!UICONTROL Platform]** / **[!UICONTROL Options]** menu.

Per impostare gli account esterni suddivisi come account predefinito per l’invio delle consegne, devi cambiare il provider di indirizzamento nei modelli di consegna. Per farlo, segui questi passaggi:

1. Accedi a **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Delivery templates]** e apri il modello di consegna desiderato. In questo esempio, desideri modificare il modello di consegna e-mail.

   ![](assets/split-default-list.png)

1. Fai clic su **[!UICONTROL Properties]** e cambia il provider di indirizzamento con l’account esterno di consegna frazionata corrispondente.

   ![](assets/split-default-delivery.png)

1. Salva le modifiche. Tutte le consegne inviate utilizzando il modello ora utilizzano la modalità di routing diviso per impostazione predefinita.

<!--In addition, you can select split external accounts as the default routing provider for all future delivery templates. To do this, change the value of the **[!UICONTROL xtkoption NmsBroadcast_DefaultProvider]** option to the name of the split account.

![](assets/split-default-options.png) -->

## Architettura del Centro messaggi{#transac-msg-archi}

La messaggistica transazionale (Message Center) è il modulo di Campaign progettato per la gestione dei messaggi di attivazione.

Scopri come inviare messaggi transazionali in [questa sezione](../send/transactional.md).

In risposta a un’azione di un cliente su un sito web, un evento viene inviato a Campaign tramite un’API REST, il modello del messaggio viene compilato con le informazioni o i dati forniti tramite la chiamata API e un messaggio transazionale viene inviato in tempo reale al cliente. Questi messaggi possono essere inviati singolarmente o in batch tramite e-mail, SMS o notifiche push.

In questa architettura specifica, la cella di esecuzione è separata dall’istanza di controllo per garantire un’elevata disponibilità e la gestione del carico.

* Il **Istanza di controllo** (o istanza Marketing) viene utilizzato dagli addetti al marketing e dai team IT per creare, configurare e pubblicare modelli di messaggio. Questa istanza centralizza anche il monitoraggio e la cronologia degli eventi.

  Scopri come creare e pubblicare modelli di messaggio in [questa sezione](../send/transactional.md).

* Il **Istanza di esecuzione** archivia gli eventi in arrivo (ad esempio, reimpostazione della password o ordini da un sito web) e invia messaggi personalizzati. Possono essere presenti più istanze di esecuzione per elaborare i messaggi tramite il load-balancer e scalare il numero di eventi da eseguire per ottenere la massima disponibilità.

>[!CAUTION]
>
>L&#39;istanza di controllo e le istanze di esecuzione devono essere installate su computer diversi. Non possono condividere la stessa istanza di Campaign.

![](assets/messagecenter_diagram.png)

### Autenticazione

Per utilizzare queste funzionalità, gli utenti di Adobe Campaign accedono all’istanza di controllo per creare modelli di messaggi transazionali, generare l’anteprima dei messaggi utilizzando un elenco di seed, visualizzare i rapporti e monitorare le istanze di esecuzione.

* Istanza di esecuzione singola Quando si interagisce con un’istanza di esecuzione del Centro messaggi ospitata da un Adobe, un sistema esterno può prima recuperare un token di sessione (che per impostazione predefinita scade tra 24 ore), effettuando una chiamata API al metodo di accesso alla sessione, utilizzando un account di accesso e una password forniti.
Quindi, con il sessionToken fornito dall’istanza di esecuzione in risposta alla chiamata di cui sopra, l’applicazione esterna può effettuare chiamate API SOAP (rtEvents o batchEvents) per inviare comunicazioni, senza dover includere in ogni chiamata SOAP l’accesso e la password dell’account.

* Più istanze di esecuzione In un’architettura di esecuzione a più celle con più istanze di esecuzione dietro un load balancer, il metodo di accesso richiamato dall’applicazione esterna passa attraverso il load balancer: per questo motivo, non è possibile utilizzare un’autenticazione basata su token. È necessaria un&#39;autenticazione basata su utente/password.

Ulteriori informazioni sugli eventi di messaggistica transazionale in [questa pagina](../send/event-processing.md).
