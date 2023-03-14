---
title: Introduzione all’architettura di Campaign
description: Scopri gli ambienti e le nozioni di base sull’implementazione, incluso come creare rapporti su un ambiente di Campaign.
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 618e45b6948070c6b791d2bcefa8296b297bf25e
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 9%

---

# Introduzione all’architettura di Campaign{#gs-ac-archi}

## Ambienti {#environments}

Campaign è disponibile come istanza singola, dove ogni istanza rappresenta un ambiente Campaign completo.

Sono disponibili due tipi di ambienti:

* **Ambiente di produzione**: ospita le applicazioni per gli utenti business.

* **Ambiente non di produzione**: utilizzato per vari test di prestazioni e qualità prima che le modifiche all’applicazione vengano inviate all’ambiente di produzione.

Puoi esportare e importare pacchetti da un ambiente a un altro.

![](../assets/do-not-localize/book.png) Ulteriori informazioni sui pacchetti in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html){target="_blank"}

## Modelli di distribuzione{#ac-deployment}

Sono disponibili due modelli di distribuzione:

* **FDA campagna [!DNL Snowflake] distribuzione**

   Nel suo [[!DNL Snowflake] Distribuzione FDA](fda-deployment.md), [!DNL Adobe Campaign] v8 è connesso a [!DNL Snowflake] per accedere ai dati tramite la funzionalità Federated Data Access: puoi accedere ed elaborare dati e informazioni esterni memorizzati nel tuo [!DNL Snowflake] senza modificare la struttura dei dati di Adobe Campaign. PostgreSQL è il database primario e Snowflake è il database secondario. Puoi estendere il modello dati e archiviare i dati sul Snowflake. Successivamente, puoi eseguire ETL, segmentazione e rapporti su un set di dati di grandi dimensioni con prestazioni eccezionali.

* **Distribuzione di Campaign Enterprise (FFDA)**

   Nell&#39;ambito di una [Distribuzione aziendale (FFDA)](enterprise-deployment.md), [!DNL Adobe Campaign] v8 funziona con due database: uno locale [!DNL Campaign] database per la messaggistica in tempo reale, le query unitarie dell’interfaccia utente, le operazioni di scrittura tramite API e un cloud [!DNL Snowflake] database per l’esecuzione della campagna, le query batch e l’esecuzione dei flussi di lavoro.

   Campaign v8 Enterprise introduce il concetto di **Full Federated Data Access** (FFDA): adesso tutti i dati sono remoti, nel database cloud. Con questa nuova architettura, l’implementazione di Campaign v8 Enterprise (FFDA) semplifica la gestione dei dati, in quanto nel database cloud non è richiesto alcun indice. È sufficiente creare le tabelle, copiare i dati e iniziare. La tecnologia del database cloud non richiede una manutenzione specifica per garantire la qualità del servizio.

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
>Per impostazione predefinita, la modalità di routing diviso è abilitata per l’account &quot;Consegna divisa - E-mail&quot;. Per tutti gli altri account esterni dei canali, contatta l’Assistenza clienti per far sì che l’opzione sia abilitata.
>
>Per impostazione predefinita, il valore della dimensione di soglia per suddividere una consegna tra più mid è 100.000. È possibile modificare questo valore nell’opzione &quot;NmsDelivery_MultiMidSplitThreshold&quot; in **[!UICONTROL Administration]** / **[!UICONTROL Platform]** / **[!UICONTROL Options]** menu.

Per impostare gli account esterni suddivisi come account predefinito per l’invio delle consegne, devi cambiare il provider di indirizzamento nei modelli di consegna. Per farlo, esegui questi passaggi:

1. Accedi a **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Delivery templates]** e apri il modello di consegna desiderato. In questo esempio, desideri modificare il modello di consegna e-mail.

   ![](assets/split-default-list.png)

1. Fai clic su **[!UICONTROL Properties]** e cambia il provider di indirizzamento con l’account esterno di consegna frazionata corrispondente.

   ![](assets/split-default-delivery.png)

1. Salva le modifiche. Tutte le consegne inviate utilizzando il modello ora utilizzano la modalità di routing diviso per impostazione predefinita.

<!--In addition, you can select split external accounts as the default routing provider for all future delivery templates. To do this, change the value of the **[!UICONTROL xtkoption NmsBroadcast_DefaultProvider]** option to the name of the split account.

![](assets/split-default-options.png) -->

## Architettura del Centro messaggi{#transac-msg-archi}

La messaggistica transazionale (Message Center) è il modulo di Campaign progettato per la gestione dei messaggi di attivazione.

![](../assets/do-not-localize/glass.png) Scopri come inviare messaggi transazionali in [questa sezione](../send/transactional.md).

In risposta a un’azione di un cliente su un sito web, un evento viene inviato a Campaign tramite un’API REST, il modello del messaggio viene compilato con le informazioni o i dati forniti tramite la chiamata API e un messaggio transazionale viene inviato in tempo reale al cliente. Questi messaggi possono essere inviati singolarmente o in batch tramite e-mail, SMS o notifiche push.

In questa architettura specifica, la cella di esecuzione è separata dall’istanza di controllo per garantire un’elevata disponibilità e la gestione del carico.

* Il **Istanza di controllo** (o istanza Marketing) viene utilizzato dagli addetti al marketing e dai team IT per creare, configurare e pubblicare modelli di messaggio. Questa istanza centralizza anche il monitoraggio e la cronologia degli eventi.

   ![](../assets/do-not-localize/glass.png) Scopri come creare e pubblicare modelli di messaggio in [questa sezione](../send/transactional.md).

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

![](../assets/do-not-localize/book.png) Ulteriori informazioni sugli eventi di messaggistica transazionale in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html#about-transactional-messaging-datamodel){target="_blank"}
