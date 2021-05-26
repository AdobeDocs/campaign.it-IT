---
solution: Campaign v8
product: Adobe Campaign
title: Flussi di lavoro tecnici e replica dei dati
description: Flussi di lavoro tecnici e replica dei dati
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 1%

---

# Flussi di lavoro tecnici e replica dei dati

## Flussi di lavoro tecnici{#tech-wf}

Adobe Campaign viene fornito con un set di flussi di lavoro tecnici integrati. I flussi di lavoro tecnici eseguono processi o processi, pianificati regolarmente sul server.

Questi flussi di lavoro eseguono operazioni di manutenzione sul database, sfruttano le informazioni di tracciamento nei registri di consegna, creano campagne ricorrenti e altro ancora.

[!DNL :arrow_upper_right:] L’elenco completo dei flussi di lavoro tecnici è descritto in dettaglio nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)


Oltre a questi flussi di lavoro tecnici, Campaign v8 si basa su flussi di lavoro tecnici specifici per gestire la [replica dei dati](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Questo flusso di lavoro esegue la replica automatica delle tabelle integrate che devono essere presenti nel database locale di Campaign (Postgres) e nel database cloud ([!DNL Snowflake]). È prevista l’esecuzione ogni ora, ogni giorno. Se esiste un campo **lastModified**, la replica avviene in modo incrementale, altrimenti l&#39;intera tabella viene replicata. L&#39;ordine delle tabelle nell&#39;array sottostante è l&#39;ordine utilizzato dal flusso di lavoro di replica.
* **[!UICONTROL Replicate Staging data]**
Questo flusso di lavoro replica i dati di staging per le chiamate unitarie. È prevista l’esecuzione ogni ora, ogni giorno.
* **[!UICONTROL Deploy FFDA immediately]**\
   Questo flusso di lavoro esegue un’implementazione immediata nel database Cloud.
* **[!UICONTROL Replicate FFDA data immediately]**
Questo flusso di lavoro replica i dati XS per un dato account esterno.

Questi flussi di lavoro tecnici sono disponibili dal nodo **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** di Campaign Explorer. **Non devono essere modificati.**

Se necessario, puoi avviare manualmente la sincronizzazione dati. Per eseguire questa operazione, fai clic con il pulsante destro del mouse sull&#39;attività **Scheduler** e seleziona **Esegui attività in sospeso**.

## Replica dati{#data-replication}

Alcune tabelle incorporate vengono replicate dal database locale di Campaign al database [!DNL Snowflake] Cloud tramite flussi di lavoro dedicati descritti in precedenza.

I criteri di replica si basano sulle dimensioni delle tabelle. Alcune tabelle verranno replicate in tempo reale, altre verranno replicate su base oraria. Alcune tabelle avranno aggiornamenti incrementali quando altre verranno sostituite.

Oltre al flusso di lavoro tecnico integrato **Replica tabelle di riferimento**, puoi forzare la replica dei dati nei flussi di lavoro.

Puoi:

* aggiungi una specifica attività **Codice JavaScript** con il seguente codice:

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* aggiungi un&#39;attività **nlmodule** specifica con il seguente comando:

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)

**Argomenti correlati**

[!DNL :arrow_upper_right:] Scopri come iniziare a utilizzare i flussi di lavoro nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)

[!DNL :bulb:] Accedere ai periodi di conservazione dei dati in  [questa sezione](../dev/datamodel-best-practices.md#data-retention)
