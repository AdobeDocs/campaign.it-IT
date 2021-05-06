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
source-git-commit: 0e0cd6eb9fcf656c9ba6c72cd1a782098f9399fe
workflow-type: tm+mt
source-wordcount: '312'
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

## Replica dati{#data-replication}

Le tabelle vengono replicate dal database Campaign al database [!DNL Snowflake] Cloud tramite flussi di lavoro dedicati descritti in precedenza.

I criteri di replica si basano sulle dimensioni della tabella. Alcune tabelle verranno replicate. Alcune tabelle verranno replicate in tempo reale, altri verranno replicate su base oraria. Alcune tabelle avranno aggiornamenti incrementali quando altre verranno sostituite.

**DOVREMMO ELENCARE TUTTE LE TABELLE?**

CONTROLLO

**Argomenti correlati**

:arrow_Upper_right: Scopri come iniziare a utilizzare i flussi di lavoro nella [documentazione di Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)

:lampadina: Accedi ai periodi di conservazione dei dati in [questa sezione](../dev/datamodel-best-practices.md#data-retention)
