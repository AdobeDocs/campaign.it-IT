---
title: Flussi di lavoro tecnici e replica dei dati
description: Flussi di lavoro tecnici e replica dei dati
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: 0fa0db62f45097755bebcbf434614c4c835d886a
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 2%

---

# Flussi di lavoro tecnici e replica dei dati

## Flussi di lavoro tecnici{#tech-wf}

Nel contesto di un [Distribuzione aziendale (FFDA)](enterprise-deployment.md), Adobe Campaign viene fornito con un set di flussi di lavoro tecnici incorporati. I flussi di lavoro tecnici eseguono processi o processi, pianificati regolarmente sul server.

Questi flussi di lavoro eseguono operazioni di manutenzione sul database, sfruttano le informazioni di tracciamento nei registri di consegna, creano campagne ricorrenti e altro ancora.

![](../assets/do-not-localize/book.png) L’elenco completo dei flussi di lavoro tecnici è descritto in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html){target=&quot;_blank&quot;}

Oltre a questi flussi di lavoro tecnici, Campaign v8 si basa su flussi di lavoro tecnici specifici per la gestione [replica dei dati](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Questo flusso di lavoro esegue la replica automatica delle tabelle integrate che devono essere presenti nel database locale di Campaign (Postgres) e nel database cloud ([!DNL Snowflake]). È prevista l’esecuzione ogni ora, ogni giorno. Se **lastModified** esiste, la replica avviene in modo incrementale, altrimenti l&#39;intera tabella viene replicata. L&#39;ordine delle tabelle nell&#39;array sottostante è l&#39;ordine utilizzato dal flusso di lavoro di replica.
* **[!UICONTROL Replicate Staging data]**
Questo flusso di lavoro replica i dati di staging per le chiamate unitarie. È prevista l’esecuzione ogni ora, ogni giorno.
* **[!UICONTROL Deploy FFDA immediately]**\
   Questo flusso di lavoro esegue un’implementazione immediata nel database Cloud.
* **[!UICONTROL Replicate FFDA data immediately]**
Questo flusso di lavoro replica i dati XS per un dato account esterno.

Questi flussi di lavoro tecnici sono disponibili dal **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]** nodo di Campaign Explorer. **Non devono essere modificati.**

Se necessario, puoi avviare manualmente la sincronizzazione dati. Per eseguire questa operazione, fai clic con il pulsante destro del mouse sul pulsante **Scheduler** e seleziona **Esegui subito le attività in sospeso**.

## Replica dei dati{#data-replication}

Alcune tabelle incorporate vengono replicate dal database locale di Campaign in [!DNL Snowflake] Database cloud tramite flussi di lavoro dedicati descritti in precedenza.

Comprendere i database utilizzati da Adobe Campaign v8, il motivo per cui i dati vengono replicati, quali dati vengono replicati e come funziona il processo di replica.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### Criteri di replica dei dati

I criteri di replica si basano sulle dimensioni delle tabelle. Alcune tabelle verranno replicate in tempo reale, altre verranno replicate su base oraria. Alcune tabelle avranno aggiornamenti incrementali quando altre verranno sostituite.

Oltre al **Replicare le tabelle di riferimento** flusso di lavoro tecnico, puoi forzare la replica dei dati nei flussi di lavoro.

Puoi:

* aggiungi un **Codice JavaScript** attività con il seguente codice:

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* aggiungi un **nlmodule** attività con il seguente comando:

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)


**Argomenti correlati**

![](../assets/do-not-localize/book.png) Scopri come iniziare a utilizzare i flussi di lavoro in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows){target=&quot;_blank&quot;}

![](../assets/do-not-localize/glass.png) Accedere ai periodi di conservazione dei dati in [questa sezione](../dev/datamodel-best-practices.md#data-retention)
