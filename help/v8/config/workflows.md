---
title: Gestire e automatizzare i processi con i flussi di lavoro Adobe Campaign
description: Introduzione ai flussi di lavoro
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 95c944963feee746a2bb83a85f075134c91059d1
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 4%

---

# Introduzione ai flussi di lavoro{#gs-with-workflows}

Configura Campaign per sfruttare le potenti funzionalità di automazione delle campagne di marketing.

Puoi impostare:

* Flussi di lavoro
* Campagne ricorrenti
* Ciclo di convalida completo
* Avvisi
* Invio automatico di rapporti
* Eventi attivati

>[!NOTE]
>
>L’interfaccia utente web di Adobe Campaign viene fornita con un’area di lavoro riprogettata per i flussi di lavoro, che consente di creare percorsi di clienti più dinamici e personalizzati. Per ulteriori informazioni sui flussi di lavoro per l&#39;interfaccia utente Web, consulta la [documentazione dell&#39;interfaccia utente Web di Adobe Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/wf/gs-workflows){target=_blank}.


## Progettare e utilizzare flussi di lavoro {#gs-ac-wf}

Utilizza i flussi di lavoro di Adobe Campaign per migliorare la velocità e la scalabilità di ogni aspetto delle campagne di marketing, dalla creazione di segmenti e preparazione dei messaggi alla consegna.

Per ulteriori informazioni sull’interfaccia utente e l’esecuzione dei flussi di lavoro, consulta queste pagine:

* [Introduzione ai flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=it){target="_blank"}

* [Best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}

* [Flussi di lavoro tecnici incorporati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}

* [Monitorare l&#39;esecuzione dei flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

* [Crea un pubblico in un flusso di lavoro per una campagna di marketing](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=it){target="_blank"}

## Attività del flussi di lavoro {#wf-activities}

Ulteriori informazioni sulle attività del flusso di lavoro disponibili in [questa sezione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html?lang=it){target="_blank"}

Le attività del flusso di lavoro sono raggruppate per categoria. Sono disponibili le quattro categorie di attività seguenti:

* [Attività di targeting](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"}: Query, Leggi elenco, Arricchimento, Unione e altro ancora
* [Attività di controllo del flusso](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"}: modulo di pianificazione, fork, avviso, segnale esterno e altro ancora
* [Attività azione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html){target="_blank"}: consegne cross-channel, codice JavaScript, attività di gestione delle relazioni con i clienti, aggregazione aggiornamenti e altro ancora
* [Attività evento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html){target="_blank"}: trasferimento file, download Web e altro ancora

<!--
### Change data source activity {#change-data-source-activity}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. This provides more flexibility to manage data across different data sources such as FDA, FFDA and local database.

The **[!UICONTROL Working table]** allows Adobe Campaign workflow to handle data and share data with the workflow activities.
By default, the **[!UICONTROL Working table]** is created in the same database as the source of the data we query on.

For example, when querying the **[!UICONTROL Profiles]** table, stored on the Cloud database, you will create a **[!UICONTROL Working table]** on the same Cloud database.
To change this, you can add the **[!UICONTROL Change Data Source]** activity to choose a different data source for your **[!UICONTROL Working table]**.

Note that when using the **[!UICONTROL Change Data Source]** activity, you will need to switch back to the Cloud database to continue the workflow execution.

To use the **[!UICONTROL Change Data Source]** activity:

1. Create a workflow.

1. Query your targeted recipients with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}.

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

    For more information on the **[!UICONTROL JavaScript code]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html){target="_blank"}.

1. Add another **[!UICONTROL Change data source]** activity to switch back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. You can now start your workflow.
-->

## Gestire i magazzini virtuali {#warehouse}

Dopo aver creato il flusso di lavoro, è possibile accedere alle opzioni aggiuntive con il pulsante **[!UICONTROL Properties]** per ulteriori configurazioni.

Ulteriori informazioni sulle **proprietà del flusso di lavoro** in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html){target="_blank"}.

Dalla scheda **[!UICONTROL Execution]** di **[!UICONTROL Properties]** del flusso di lavoro, puoi scegliere di collegare il flusso di lavoro a warehouse diversi e ottimizzare la gestione del carico di lavoro. Per ulteriori informazioni su **Warehouse**, consulta la [documentazione di Snowflake](https://docs.snowflake.com/en/user-guide/warehouses-overview.html){target="_blank"}.

![](assets/warehouse.png)

A seconda dello scopo del flusso di lavoro, è possibile scegliere tra i tre warehouse seguenti dall&#39;elenco a discesa **[!UICONTROL Warehouse]**:

* **[!UICONTROL Default]** / **[!UICONTROL Campaign]**: impostazione predefinita per la creazione di un nuovo flusso di lavoro.

* **[!UICONTROL Import / Export]**: deve essere impostato con flussi di lavoro di importazione o esportazione per ottimizzare le prestazioni delle attività.

* **[!UICONTROL Campaign Burst]**: deve essere impostato con i flussi di lavoro campagna o consegne per ottimizzare il tempo di elaborazione delle consegne.

>[!NOTE]
>
>Il data warehouse **[!UICONTROL System]** è impostato solo per i flussi di lavoro incorporati.

## Configurare campagne ricorrenti

Progetta un flusso di lavoro ricorrente e crea una nuova istanza di consegna ogni volta che il flusso di lavoro viene eseguito. Ad esempio, se il flusso di lavoro è progettato per essere eseguito una volta alla settimana, in un anno si otterranno 52 consegne. Ciò significa anche che i registri saranno separati da ogni istanza di consegna.

Scopri come creare una campagna ricorrente in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html?lang=it){target="_blank"}.


## Sfruttare gli eventi trigger

Utilizza la messaggistica transazionale di Campaign per automatizzare i messaggi generati dagli eventi attivati dai sistemi di informazione. Questi messaggi transazionali possono essere, ad esempio, fatture, conferme di ordini, conferme di spedizione, modifiche della password, notifiche di non disponibilità del prodotto, rendiconti dei conti o creazione di account sul sito web. Questi messaggi possono essere inviati singolarmente o in batch tramite e-mail, SMS o notifiche push.

Ulteriori informazioni sulle funzionalità di messaggistica transazionale in in [questa sezione](../send/transactional.md).

Connetti Adobe Campaign e Adobe Analytics per recuperare le azioni degli utenti e inviare messaggi personalizzati in tempo reale.

Scopri come integrare Campaign con altre soluzioni in [questa sezione](../start/connect.md)


## Casi d’uso end-to-end del flusso di lavoro{#end-to-end-uc}

Scopri i casi d&#39;uso che sfruttano le funzionalità dei flussi di lavoro di Campaign [in questa sezione](../../automation/workflow/workflow-use-cases.md).
