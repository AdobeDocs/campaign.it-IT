---
title: Workflow tecnici e replica dei dati
description: Workflow tecnici e replica dei dati
feature: Workflows, FFDA
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 4%

---

# Workflow tecnici e replica dei dati

## Flussi di lavoro tecnici{#tech-wf}

Nell&#39;ambito di una [Distribuzione aziendale (FFDA)](enterprise-deployment.md), Adobe Campaign viene fornito con una serie di flussi di lavoro tecnici incorporati. I flussi di lavoro tecnici eseguono processi o processi, pianificati regolarmente sul server.

Questi flussi di lavoro eseguono operazioni di manutenzione sul database, sfruttano le informazioni di tracciamento nei registri di consegna, creano campagne ricorrenti e altro ancora.

![](../assets/do-not-localize/glass.png) L’elenco completo dei flussi di lavoro tecnici è descritto in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html).

Oltre a questi flussi di lavoro tecnici, Campaign v8 si basa su flussi di lavoro tecnici specifici per gestire [replica dei dati](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Questo flusso di lavoro esegue la replica automatica delle tabelle integrate che devono essere presenti nel database locale di Campaign (Postgres) e nel database cloud ([!DNL Snowflake]). È pianificata per l&#39;esecuzione ogni ora, ogni giorno. Se **lastModified** esiste, la replica avviene in modo incrementale, altrimenti l’intera tabella viene replicata. L’ordine delle tabelle nell’array seguente è quello utilizzato dal flusso di lavoro di replica.
* **[!UICONTROL Replicate Staging data]**
Questo flusso di lavoro replica i dati di staging per le chiamate unitarie. È pianificata per l&#39;esecuzione ogni ora, ogni giorno.
* **[!UICONTROL Deploy FFDA immediately]**\
   Questo flusso di lavoro esegue una distribuzione immediata nel database cloud.
* **[!UICONTROL Replicate FFDA data immediately]**
Questo flusso di lavoro replica i dati XS per un determinato account esterno.

Questi flussi di lavoro tecnici sono disponibili nella **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]** di Campaign Explorer. **Non devono essere modificati.**

Se necessario, puoi avviare manualmente la sincronizzazione dei dati. Per eseguire questa operazione, fare clic con il pulsante destro del mouse sulla **Scheduler** attività e selezione **Esegui attività in sospeso**.

## Replica dei dati{#data-replication}

Alcune tabelle integrate vengono replicate dal database locale di Campaign in [!DNL Snowflake] Database cloud tramite flussi di lavoro dedicati descritti in precedenza.

Scopri quali database utilizza Adobe Campaign v8, perché i dati vengono replicati, quali dati vengono replicati e come funziona il processo di replica.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### Criteri di replica dei dati{#data-replication-policies}

I criteri di replica si basano sulle dimensioni delle tabelle. Alcune tabelle saranno replicate in tempo reale, altre in base alle ore. Alcune tabelle avranno aggiornamenti incrementali quando altre verranno sostituite.

Oltre al **Replica tabelle di riferimento** del flusso di lavoro tecnico, puoi forzare la replica dei dati nei flussi di lavoro.

È possibile eseguire le seguenti operazioni:

* aggiungi uno specifico **Codice JavaScript** attività con il seguente codice:

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* aggiungi uno specifico **nlmodule** attività con il seguente comando:

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)


**Argomenti correlati**

* [Scopri come iniziare a utilizzare i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=it)

* [Periodi di conservazione dei dati](../dev/datamodel-best-practices.md#data-retention)
