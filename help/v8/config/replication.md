---
solution: Campaign Classic
product: campaign
title: Flussi di lavoro tecnici e replica dei dati
description: Flussi di lavoro tecnici e replica dei dati
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
translation-type: tm+mt
source-git-commit: 369ddafcc64fa418a479ab03092d3475f1c811b2
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 1%

---

# Flussi di lavoro tecnici e replica dei dati

## Flussi di lavoro tecnici

Adobe Campaign viene fornito con un set di flussi di lavoro tecnici integrati. I flussi di lavoro tecnici eseguono processi o processi, pianificati regolarmente sul server.

Questi flussi di lavoro eseguono operazioni di manutenzione sul database, sfruttano le informazioni di tracciamento nei registri di consegna, creano campagne ricorrenti e altro ancora.

:arrow_Upper_right: L&#39;elenco completo dei flussi di lavoro tecnici è descritto in [Documentazione Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=en#overview)

Oltre a questi flussi di lavoro tecnici, Campaign v8 si basa su flussi di lavoro tecnici specifici per gestire la [replica dei dati](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Questo flusso di lavoro esegue la replica automatica delle tabelle di riferimento che devono essere presenti nel database locale di Campaign (Postgres) e nel database Cloud ([!DNL Snowflake]). È prevista l’esecuzione ogni ora, ogni giorno. Se esiste un campo **lastModified**, la replica avviene in modo incrementale, altrimenti l&#39;intera tabella viene replicata. L&#39;ordine delle tabelle nell&#39;array sottostante è l&#39;ordine utilizzato dal flusso di lavoro di replica.
* **[!UICONTROL Replicate Staging data]**
Questo flusso di lavoro replica i dati di staging per le chiamate unitarie. È prevista l’esecuzione ogni ora, ogni giorno.
* **[!UICONTROL Deploy FFDA immediately]**\
   Questo flusso di lavoro esegue un’implementazione immediata nel database Cloud.
* **[!UICONTROL Replicate FFDA data immediately]**
Questo flusso di lavoro replica i dati XS per un dato account esterno.

Questi flussi di lavoro tecnici sono disponibili dal nodo **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** di Campaign Explorer.

**DOVREMMO AGGIUNGERE QUESTO? https://wiki.corp.adobe.com/display/neolane/Full+FDA+%3A%3A+Replication+strategy**


**Argomenti correlati**

:arrow_Upper_right: Scopri come iniziare a utilizzare i flussi di lavoro nella [documentazione di Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)

:lampadina: Accedi ai periodi di conservazione dei dati in [questa sezione](../dev/datamodel-best-practices.md#data-retention)


## Replica dati{#data-replication}

Le tabelle vengono replicate dal database Campaign al database [!DNL Snowflake] Cloud tramite flussi di lavoro dedicati descritti in precedenza.

I criteri di replica si basano sulle dimensioni della tabella. Alcune tabelle verranno replicate. Alcune tabelle verranno replicate in tempo reale, altri verranno replicate su base oraria. Alcune tabelle avranno aggiornamenti incrementali quando altre verranno sostituite.

| Namespace | Tabella | replica del flusso di lavoro | Replica in tempo reale |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- | --------------------- |
| **XTK** | xtk:enum<br>xtk:enumValue<br>xtk:enumAlias<br>xtk:folder<br>xtk:formRendering<br>xtk:operator<br>xtk:group<br>xtk:report<br>xtk:olapCube a8/>xtk:olapDimension<br>xtk:olapMeasure<br>xtk:tionaryString<br><br> | Sì (incrementale) | Sì |
| **XTK** | xtk:opsecurity<br>xtk:rights<br>xtk:operatorGroup<br>xtk:reportHistory<br>xtk:reportRights | Sì (completo) | Sì |
| **NMS** | nms:budget<br>nms:program<br>nms:operation<br>nms:plan<br>nms:typologyRule<br>nms:typology<br>nms:extAccount<br>nms:deliveryMapping<br>nms:delivery (replica immediata)<br>nms seedMember<br>nms:webApp<br>nms:trackingUrl (replica immediata)<br>nms:service<br>nms:offerEnv<br>nms:offerCategory<br>nms:offerSpace<br>nms:offerta a16/>nms:offerView<br>nms:recipient (incrementale?)<br><br>nms:<br>groupnms:<br>dlvExclusionnms:stock | Sì (incrementale) | Sì |
| **NMS** | nms:country<br>nms:localOrgUnit<br>nms:state<br>nms:suppressionAddress<br>nms:suppressionDomain<br>nms:category<br>nms:trackingUrlInfo<br>nms:webTrackingLog<br>nms:mobileApp&lt;a/>nms:budgetCategory<br>nms:costType<br>nms:costCenter<br>nms:costStructure<br>nms:stockLine<br>nms:spesaLine<br>nms:costLine<br> | Sì (completo) | Sì |
| **NMS** | nms:address<br>nms:userAgent<br>nms:userAgentReject<br>nms:userAgentStats<br>nms:wideLogMsg<br>nms:wideLog<br>nms:trackingLog<br>nms:deliveryLogStats<br>nms ms:appSubscription<br>nms:proposition<br>nms:rcpGrpRel<br>nms:wideLogRcp<br>nms:excludeLogRcp<br>nms:trackingLogRcp<br>nms:propositionRcp a14/>nms:localValidationRcp<br>nms:visitor<br>nms:wideLogVisitor<br>nms:trackingLogVisitor<br>nms:propositionVisitor<br>nms:webAppLogRcp&lt;a 20/>nms:appSubscriptionRcp<br>nms:wideLogAppSubRcp<br>nms:excludeLogAppSubRcp<br>nms:trackingLogAppSubRcp<br>nms:eventHisto<br>nms:wideLogEventHisto<br>nms:trackingLogEventHisto<br>nms:subscription<br>nms:subHisto<br>nms:trackingStats (solo utilizzo Snowflake)<br>nms:tmpBroadcast (utilizzo Snowflake) Solo)<br>nms:tmpBroadcastExclusion (solo utilizzo Snowflake)<br>nms:tmpBroadcastPaper (solo utilizzo Snowflake)<br><br> | No | No |

