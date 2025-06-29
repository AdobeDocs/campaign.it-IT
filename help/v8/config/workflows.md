---
title: Gestire e automatizzare i processi con i flussi di lavoro Adobe Campaign
description: Introduzione ai flussi di lavoro
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 8e1401ef0aada30d941905936b45c6c1819c83a7
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 2%

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
>L’interfaccia utente web di Adobe Campaign viene fornita con un’area di lavoro riprogettata per i flussi di lavoro, che consente di creare percorsi di clienti più dinamici e personalizzati. Per ulteriori informazioni sui flussi di lavoro per l&#39;interfaccia utente Web, consulta la [documentazione dell&#39;interfaccia utente Web di Adobe Campaign](https://experienceleague.adobe.com/it/docs/campaign-web/v8/wf/gs-workflows){target=_blank}.


## Progettare e utilizzare flussi di lavoro {#gs-ac-wf}

Utilizza i flussi di lavoro di Adobe Campaign per migliorare la velocità e la scalabilità di ogni aspetto delle campagne di marketing, dalla creazione di segmenti e preparazione dei messaggi alla consegna.

Scopri come progettare flussi di lavoro in questi [casi d&#39;uso end-to-end](#end-to-end-uc).

Per ulteriori informazioni sull’interfaccia utente e l’esecuzione dei flussi di lavoro, consulta queste pagine:

* [Introduzione ai flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=it){target="_blank"}

* [Best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=it){target="_blank"}

* [Flussi di lavoro tecnici incorporati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=it){target="_blank"}

* [Monitorare l&#39;esecuzione dei flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=it){target="_blank"}

* [Crea un pubblico in un flusso di lavoro per una campagna di marketing](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=it){target="_blank"}

## Attività del flussi di lavoro {#wf-activities}

Ulteriori informazioni sulle attività del flusso di lavoro disponibili in [questa sezione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html?lang=it){target="_blank"}

Le attività del flusso di lavoro sono raggruppate per categoria. Sono disponibili le quattro categorie di attività seguenti:

* [Attività di targeting](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=it){target="_blank"}: Query, Leggi elenco, Arricchimento, Unione e altro ancora
* [Attività di controllo del flusso](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=it){target="_blank"}: modulo di pianificazione, fork, avviso, segnale esterno e altro ancora
* [Attività azione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=it){target="_blank"}: consegne cross-channel, codice JavaScript, attività di gestione delle relazioni con i clienti, aggregazione aggiornamenti e altro ancora
* [Attività evento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html?lang=it){target="_blank"}: trasferimento file, download Web e altro ancora

### Modificare l’attività dell’origine dati {#change-data-source-activity}

L&#39;attività **[!UICONTROL Change data source]** consente di modificare l&#39;origine dati di un flusso di lavoro **[!UICONTROL Working table]**. Questo offre maggiore flessibilità per gestire i dati tra diverse origini dati, come FDA, FFDA e database locale.

**[!UICONTROL Working table]** consente al flusso di lavoro di Adobe Campaign di gestire i dati e condividerli con le attività del flusso di lavoro.
Per impostazione predefinita, **[!UICONTROL Working table]** viene creato nello stesso database dell&#39;origine dei dati su cui viene eseguita la query.

Ad esempio, quando si esegue una query sulla tabella **[!UICONTROL Profiles]**, memorizzata nel database Cloud, verrà creato un **[!UICONTROL Working table]** sullo stesso database Cloud.
Per modificare questa impostazione, è possibile aggiungere l&#39;attività **[!UICONTROL Change Data Source]** per scegliere un&#39;origine dati diversa per **[!UICONTROL Working table]**.

Quando si utilizza l&#39;attività **[!UICONTROL Change Data Source]**, è necessario tornare al database cloud per continuare l&#39;esecuzione del flusso di lavoro.

Per utilizzare l&#39;attività **[!UICONTROL Change Data Source]**:

1. Crea un flusso di lavoro.

1. Eseguire una query sui destinatari con un&#39;attività **[!UICONTROL Query]**.

   Per ulteriori informazioni sull&#39;attività **[!UICONTROL Query]**, vedere [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=it){target="_blank"}.

1. Dalla scheda **[!UICONTROL Targeting]**, aggiungere un&#39;attività **[!UICONTROL Change data source]** e fare doppio clic su di essa per selezionare **[!UICONTROL Default data source]**.

   La tabella di lavoro, che contiene il risultato della query, viene quindi spostata nel database PostgreSQL predefinito.

1. Dalla scheda **[!UICONTROL Actions]**, trascina e rilascia un&#39;attività **[!UICONTROL JavaScript code]** per eseguire operazioni unitarie sulla tabella di lavoro.

   Per ulteriori informazioni sull&#39;attività **[!UICONTROL JavaScript code]**, vedere [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html?lang=it){target="_blank"}.

1. Aggiungi un&#39;altra attività **[!UICONTROL Change data source]** per tornare al database cloud.

   Fai doppio clic sull&#39;attività e seleziona **[!UICONTROL Active FDA external account]**, quindi l&#39;account esterno corrispondente.

1. Ora puoi avviare il flusso di lavoro.

## Gestire i magazzini virtuali {#warehouse}

Dopo aver creato il flusso di lavoro, è possibile accedere alle opzioni aggiuntive con il pulsante **[!UICONTROL Properties]** per ulteriori configurazioni.

Ulteriori informazioni sulle **proprietà del flusso di lavoro** in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html?lang=it){target="_blank"}.

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

In questa sezione troverai diversi casi d’uso che sfruttano le funzionalità dei flussi di lavoro di Campaign.

### Consegne {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">


* [Inviare un’e-mail di compleanno](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=it){target="_blank"}

  Questo caso d’uso illustra come pianificare l’invio di un’e-mail ricorrente a un elenco di destinatari il giorno del loro compleanno.

* [Carica contenuto consegna](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html?lang=it){target="_blank"}
Quando il contenuto della consegna è disponibile in un file HTML che si trova su un server remoto, puoi facilmente caricarlo nelle consegne Adobe Campaign.

* [Flusso di lavoro di consegna cross-channel](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/cross-channel-delivery-workflow.html?lang=it){target="_blank"}
Scopri come creare un flusso di lavoro di consegna cross-channel. L’obiettivo è segmentare un pubblico dai destinatari del database in gruppi diversi e inviare un’e-mail al primo gruppo e un SMS all’altro.

* [Arricchimento delle e-mail con campi data personalizzati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html?lang=it){target="_blank"}
Scopri come inviare un’e-mail con campi dati personalizzati ai profili che festeggiano il loro compleanno questo mese. L’e-mail includerà un coupon valido una settimana prima e dopo il compleanno.

E queste pagine nella documentazione di Campaign v7:

* [Creazione, edizione e pubblicazione automatizzate dei contenuti](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html?lang=it){target="_blank"}
Scopri come automatizzare la creazione e la distribuzione di un blocco di contenuto con il componente aggiuntivo Gestione dei contenuti di Campaign.

* [Test A/B](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html?lang=it){target="_blank"}
Scopri come confrontare due contenuti di consegna e-mail tramite un flusso di lavoro di targeting. Il messaggio e il testo sono identici in entrambe le consegne: cambia solo il layout. La popolazione interessata è suddivisa in tre gruppi: due gruppi sperimentali e la popolazione rimanente. A ogni gruppo di test viene inviata una versione diversa della consegna.

### Monitoraggio {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Invia un report a un elenco](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-a-report-to-a-list.html?lang=it){target="_blank"}
Scopri come generare un rapporto mensile integrato sugli indicatori di tracciamento in formato PDF e inviarlo a un elenco di operatori di Campaign.

* [Supervisionare i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/workflow-supervision.html?lang=it){target="_blank"}
Scopri come creare un flusso di lavoro che consenta di monitorare lo stato di un set di flussi di lavoro &quot;in pausa&quot;, &quot;interrotti&quot; o &quot;con errori&quot;.

* [Inviare avvisi personalizzati agli operatori](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators.html?lang=it){target="_blank"}
Scopri come inviare un avviso a un operatore che conterrà il nome dei profili che hanno aperto una newsletter ma non hanno fatto clic sul collegamento in essa contenuto.

### Gestione dati {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Coordinare gli aggiornamenti dei dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/coordinate-data-updates.html?lang=it){target="_blank"}
Scopri come verificare che il processo di aggiornamento sia terminato prima di eseguire un’altra operazione di aggiornamento. A questo scopo, verrà impostata una variabile di istanza e verrà eseguito un test del flusso di lavoro se l’istanza è in esecuzione per decidere se continuare l’esecuzione del flusso di lavoro ed eseguire l’aggiornamento.

* [Creare un elenco di riepilogo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/create-a-summary-list.html?lang=it){target="_blank"}
Scopri come creare un flusso di lavoro che, dopo aver raccolto i file e aver seguito diversi arricchimenti, ti consenta di creare un elenco di riepilogo. L&#39;esempio si basa su un elenco di contatti che hanno effettuato acquisti in un negozio.

* [Arricchire i dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/enrich-data.html?lang=it){target="_blank"}
Scopri come inviare consegne personalizzate ai profili che hanno partecipato all’ultimo concorso a seconda del punteggio ottenuto.

* [Usa aggregati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=it){target="_blank"}
Scopri come identificare gli ultimi destinatari aggiunti al database.

* [Aggiornamento elenco trimestrale tramite una query incrementale](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/quarterly-list-update.html?lang=it){target="_blank"}
Scopri come utilizzare una query incrementale per aggiornare automaticamente un elenco di destinatari.

* [Imposta un flusso di lavoro di importazione ricorrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=it){target="_blank"}
Scopri come progettare un flusso di lavoro che possa essere riutilizzato per importare nel database di Adobe Campaign i profili provenienti da un sistema di gestione delle relazioni con i clienti.

### Targeting {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Eseguire una query sulla tabella dei destinatari](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/querying-recipient-table.html?lang=it){target="_blank"}
Scopri come recuperare i nomi e le e-mail dei destinatari il cui dominio e-mail è &quot;orange.co.uk&quot; e che non vivono a Londra.

* [Eseguire una query sulle informazioni di consegna](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-delivery-info.html?lang=it){target="_blank"}
Scopri come definire query sulle informazioni di consegna per recuperare il comportamento del profilo.

* [Calcola aggregati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/compute-aggregates.html?lang=it){target="_blank"}
Scopri come contare il numero di profili che vivono a Londra, in base al sesso.

* [Eseguire una query tramite una relazione molti-a-molti](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html?lang=it){target="_blank"}
Scopri come trovare profili non contattati negli ultimi 7 giorni.

* [Chiamare una variabile di istanza in una query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/javascript-scripts-and-templates.html?lang=it){target="_blank"}
Scopri come utilizzare una variabile di istanza per calcolare dinamicamente la percentuale divisa da applicare a una popolazione.

<!--
### Change data source activity {#data-source-uc}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. 

In this use case, learn how to use the **[!UICONTROL Change data source]** activity to perform unitary operations to insert or update information to the recipient table.

![](assets/wf_data_source_uc.png)

1. Create a workflow and add a **[!UICONTROL Start]** activity.

1. Query your targeted recipients from the NmsRecipient table with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to the [Query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html?lang=it#creating-a-query) page in Campaign Classic V7 documentation.

1. 

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

1. Add another **[!UICONTROL Change data source]** activity to revert back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. Add an **[!UICONTROL End]** activity and start your workflow.
-->

