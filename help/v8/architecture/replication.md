---
title: Replica dei dati
description: Workflow tecnici e replica dei dati
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: b8f774ce507cff67163064b6bd1341b31512c08f
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 2%

---


# Replica dei dati {#wf-data-replication}

## Principio

Nel contesto di una distribuzione di [Enterprise (FFDA)](enterprise-deployment.md), la replica dei dati garantisce che i due database, il database locale di Campaign (PostgreSQL) e il database cloud ([!DNL Snowflake]), siano operativi in parallelo e rimangano sincronizzati in tempo reale.

Il database cloud ([!DNL Snowflake]) è ottimizzato per la gestione di batch di dati di grandi dimensioni, ad esempio per l&#39;aggiornamento di 1 milione di indirizzi. Nel frattempo, il database locale di Campaign (PostgreSQL) è più adatto per operazioni singole o di volume ridotto, come l’aggiornamento di un singolo indirizzo di seed. La sincronizzazione viene eseguita in background in modo automatico e trasparente, garantendo la duplicazione in tempo reale dei dati nel database locale di Campaign (PostgreSQL) nel database cloud ([!DNL Snowflake]), mantenendo entrambi i database sincronizzati. La sincronizzazione dei dati coinvolge schemi, tabelle e dati.

➡️ [Scopri come funziona la replica dei dati nel video](#video)

## Modalità di replica {#modes}

La replica dei dati può avvenire in modalità diverse a seconda del caso d’uso.

* **Replica immediata** gestisce i casi in cui la duplicazione in tempo reale è essenziale. Si basa su thread tecnici specifici per replicare immediatamente i dati per casi d’uso come la creazione di una diffusione o l’aggiornamento di un indirizzo seed.
* **Viene utilizzata la replica pianificata** quando non è richiesta la sincronizzazione immediata. La replica pianificata utilizza [flussi di lavoro tecnici](#workflows) specifici che vengono eseguiti ogni ora per sincronizzare i dati, ad esempio le regole di tipologia.

## Criteri di replica

I criteri di replica definiscono la quantità di dati replicati da una tabella del database locale di Campaign (PostgreSQL). Questi criteri dipendono dalle dimensioni della tabella e dal caso d’uso specifico. Alcune tabelle avranno aggiornamenti incrementali quando altre saranno completamente replicate. Esistono tre tipi principali di criteri di replica:

* **XS**: questo criterio viene utilizzato per tabelle di dimensioni relativamente piccole. L&#39;intera tabella viene replicata in un&#39;unica schermata. La replica incrementale evita di replicare ripetutamente gli stessi dati utilizzando un puntatore timestamp per replicare solo le modifiche recenti.
* **RigaSingola**: questo criterio replica una sola riga alla volta. Viene generalmente utilizzato per la replica immediata che coinvolge gli oggetti Campaign correnti e gli oggetti correlati.
* **SomeRows**: questo criterio è progettato per replicare un sottoinsieme limitato di dati utilizzando definizioni di query o filtri. Viene utilizzato per tabelle più grandi in cui è necessaria la replica selettiva.

## Flussi di lavoro di replica {#workflows}

Campaign v8 si basa su flussi di lavoro tecnici specifici per gestire la replica pianificata dei dati. Questi flussi di lavoro tecnici sono disponibili dal nodo **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]** di Campaign Explorer. **Non devono essere modificati.**

I flussi di lavoro tecnici eseguono processi o processi, pianificati regolarmente sul server. L&#39;elenco completo dei flussi di lavoro tecnici è descritto in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=it){target="_blank"}.

I flussi di lavoro tecnici che garantiscono la replica dei dati sono i seguenti:

| Flusso di lavoro tecnico | Descrizione |
|------|-----------|
| **[!UICONTROL Replicate Reference tables]** (ffdaReplicateReferenceTables) | Esegue la replica automatica delle tabelle incorporate che devono essere presenti nel database locale di Campaign (PostgreSQL) e nel database cloud ([!DNL Snowflake]). È pianificata per l&#39;esecuzione ogni ora, ogni giorno. Se il campo **lastModified** esiste, la replica viene eseguita in modo incrementale, altrimenti viene replicata l&#39;intera tabella. |
| **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) | Replica i dati di staging per le chiamate unitarie. È pianificata per l&#39;esecuzione ogni ora, ogni giorno. |
| **[!UICONTROL Deploy FFDA immediately]** (ffdaDeploy) | Esegue una distribuzione immediata nel database cloud. |
| **[!UICONTROL Replicate FFDA data immediately]** (ffdaReplicate) | Replica i dati XS per un determinato account esterno. |

Se necessario, puoi avviare manualmente la sincronizzazione dei dati. A tale scopo, fare clic con il pulsante destro del mouse sull&#39;attività **Scheduler** e selezionare **Esegui attività in sospeso ora**.

Oltre al flusso di lavoro tecnico integrato **Replica tabelle di riferimento**, puoi forzare la replica dei dati nei flussi di lavoro utilizzando uno di questi metodi

+++Come forzare la replica dei dati

* Aggiungi un&#39;attività **Codice JavaScript** specifica con il codice seguente:

  ```
  nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
  ```

  ![](assets/jscode.png)

* Aggiungi un&#39;attività **nlmodule** specifica con il comando seguente:

  ```
  nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
  ```

  ![](assets/nlmodule.png)

+++

<br/>

>[!NOTE]
>
>La replica immediata viene gestita da thread tecnici specifici anziché da flussi di lavoro. La configurazione di questa modalità viene gestita nel file serverConf.xml. È possibile configurare serverConf.xml in modo che corrisponda a casi d&#39;uso specifici, ad esempio per richiedere la replica incrementale delle tabelle XS anziché la replica completa. Per ulteriori informazioni, contatta il rappresentante Adobe.

## API

Le API consentono la replica di dati personalizzati e predefiniti dal database locale di Campaign (PostgreSQL) al database cloud ([!DNL Snowflake]). Queste API ti consentono di ignorare flussi di lavoro predefiniti e personalizzare la replica per requisiti specifici, ad esempio la replica di tabelle personalizzate.

Esempio:

```
var dataSource = "nms:extAccount:ffda";
var xml = xtk.builder.CopyXxlData(
    <params dataSource={dataSource} policy="xs">
        <srcSchema name="cus:recipient"/>
    </params>
);
```

## Code di replica

Quando si verificano contemporaneamente elevati volumi di richieste di replica, è possibile che si verifichino problemi di prestazioni nel database cloud ([!DNL Snowflake]) a causa di blocchi a livello di tabella durante le operazioni MERGE. Per ovviare a questo problema, i flussi di lavoro di replica centralizzati raggruppano le richieste in code.

Ogni coda viene gestita da un flusso di lavoro tecnico, che gestisce la replica per una tabella specifica, eseguendo richieste in sospeso come una singola operazione MERGE. Questi flussi di lavoro vengono attivati ogni 20 secondi per elaborare nuove richieste di replica:

| Flusso di lavoro tecnico | Descrizione |
|------|-----------|
| **Replica coda nmsDelivery** (ffdaReplicateQueueDelivery) | Coda per la tabella `nms:delivery`. |
| **Replica coda nmsDlvExclusion** (ffdaReplicateQueueDlvExclusion) | Coda per la tabella `nms:dlvExclusion`. |
| **Replica coda nmsDlvMidRemoteIdRel** (ffdaReplicateQueueDlvMidRemoteIdRel) | Coda per la tabella `nms:dlvRemoteIdRel`. |
| **Replica coda nmsTrackingUrl** (ffdaReplicateQueueTrackingUrl)<br/>**Replica coda nmsTrackingUrl in concorrenza** (ffdaReplicateQueueTrackingUrl_2) | Code in concorrenza per la tabella `nms:trackingUrl`, utilizzando due flussi di lavoro per migliorare l&#39;efficienza elaborando le richieste in base a priorità diverse. |

## Tutorial {#video}

Questo video illustra i concetti chiave dei database utilizzati da Adobe Campaign v8, il motivo per cui i dati vengono replicati, quali dati vengono replicati e come funziona il processo di replica.

>[!VIDEO](https://video.tv.adobe.com/v/3416866?quality=12&captions=ita)

Ulteriori tutorial sulla console client di Campaign v8 sono disponibili [qui](https://experienceleague.adobe.com/it/docs/campaign-learn/tutorials/overview).
