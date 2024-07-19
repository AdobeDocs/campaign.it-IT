---
title: Workflow tecnici e replica dei dati
description: Workflow tecnici e replica dei dati
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 2%

---

# Workflow tecnici e replica dei dati {#wf-data-replication}

## Flussi di lavoro tecnici {#tech-wf}

Nel contesto di una distribuzione [Enterprise (FFDA)](enterprise-deployment.md), Adobe Campaign viene fornito con un set di flussi di lavoro tecnici incorporati. I flussi di lavoro tecnici eseguono processi o processi, pianificati regolarmente sul server.

Questi flussi di lavoro eseguono operazioni di manutenzione sul database, sfruttano le informazioni di tracciamento nei registri di consegna, creano campagne ricorrenti e altro ancora.

L&#39;elenco completo dei flussi di lavoro tecnici è descritto in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}.

Oltre a questi flussi di lavoro tecnici, Campaign v8 si basa su flussi di lavoro tecnici specifici per gestire la [replica dei dati](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Questo flusso di lavoro esegue la replica automatica delle tabelle incorporate che devono essere presenti nel database locale di Campaign (Postgres) e nel database cloud ([!DNL Snowflake]). È pianificata per l&#39;esecuzione ogni ora, ogni giorno. Se il campo **lastModified** esiste, la replica viene eseguita in modo incrementale, altrimenti viene replicata l&#39;intera tabella. L’ordine delle tabelle nell’array seguente è quello utilizzato dal flusso di lavoro di replica.
* **[!UICONTROL Replicate Staging data]**
Questo flusso di lavoro replica i dati di staging per le chiamate unitarie. È pianificata per l&#39;esecuzione ogni ora, ogni giorno.
* **[!UICONTROL Deploy FFDA immediately]**\
  Questo flusso di lavoro esegue una distribuzione immediata nel database cloud.
* **[!UICONTROL Replicate FFDA data immediately]**
Questo flusso di lavoro replica i dati XS per un determinato account esterno.

Questi flussi di lavoro tecnici sono disponibili dal nodo **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]** di Campaign Explorer. **Non devono essere modificati.**

Se necessario, puoi avviare manualmente la sincronizzazione dei dati. Per eseguire questa operazione, fare clic con il pulsante destro del mouse sull&#39;attività **Scheduler** e selezionare **Esegui attività in sospeso ora**.

## Replica dei dati {#data-replication}

Alcune tabelle integrate vengono replicate dal database locale di Campaign al database cloud [!DNL Snowflake] tramite i flussi di lavoro dedicati descritti in precedenza.

Scopri quali database utilizza Adobe Campaign v8, perché i dati vengono replicati, quali dati vengono replicati e come funziona il processo di replica.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### Criteri di replica dei dati {#data-replication-policies}

I criteri di replica si basano sulle dimensioni delle tabelle. Alcune tabelle vengono replicate in tempo reale, altre su base oraria. Alcune tabelle avranno aggiornamenti incrementali quando altre verranno sostituite.

Oltre al flusso di lavoro tecnico integrato **Replica tabelle di riferimento**, puoi forzare la replica dei dati nei flussi di lavoro.

Puoi eseguire le seguenti azioni:

* aggiungi un&#39;attività **codice JavaScript** specifica con il codice seguente:

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* aggiungi un&#39;attività **nlmodule** specifica con il comando seguente:

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)


**Argomenti correlati**

* [Scopri come iniziare a utilizzare i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=it){target="_blank"}

* [Periodi di conservazione dei dati](../dev/datamodel-best-practices.md#data-retention)
