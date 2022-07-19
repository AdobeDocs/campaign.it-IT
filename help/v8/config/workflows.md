---
title: Gestire e automatizzare i processi con i flussi di lavoro Adobe Campaign
description: Introduzione ai flussi di lavoro
feature: Workflows
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 59046a11c3e057cf41c322f190a9d8aef310c356
workflow-type: tm+mt
source-wordcount: '1574'
ht-degree: 1%

---

# Gestire e automatizzare i processi

Configura Campaign per sfruttare le potenti funzionalità di automazione delle campagne di marketing.

Puoi impostare:

* Flussi di lavoro
* Campagne ricorrenti
* Ciclo di convalida end-to-end
* Avvisi
* Invio automatico di rapporti
* Eventi attivati

## Progettazione e utilizzo dei flussi di lavoro{#gs-ac-wf}

Utilizza i flussi di lavoro Adobe Campaign per migliorare la velocità e la scala di ogni aspetto delle campagne di marketing, dalla creazione di segmenti alla preparazione dei messaggi alla consegna.

Scopri come progettare flussi di lavoro in questi [casi d’uso end-to-end](#end-to-end-uc).

Scopri di più sull’interfaccia utente e l’esecuzione dei flussi di lavoro in queste pagine:

* [Introduzione ai flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html)

* [Best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html)

* [Flussi di lavoro tecnici incorporati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html)

* [Monitorare l’esecuzione dei flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html)

* [Creare un pubblico in un flusso di lavoro di una campagna di marketing](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html)

## Attività del flusso di lavoro {#wf-activities}

Ulteriori informazioni sulle attività del flusso di lavoro disponibili in [questa sezione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html)

Le attività del flusso di lavoro sono raggruppate per categoria. Sono disponibili le quattro categorie di attività seguenti:

* [Attività di targeting](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html): Query, Elenco di lettura, Arricchimento, Unione e altro ancora
* [Attività di controllo del flusso](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html): Scheduler, Fork, Alert, Segnale esterno e altro ancora
* [Attività azione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html): Consegne cross-channel, codice JavaScript, attività CRM, aggiornamento aggregato e altro ancora
* [Attività evento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html): Trasferimento file, download web e altro ancora

### Modificare l’attività dell’origine dati {#change-data-source-activity}

La **[!UICONTROL Change data source]** consente di modificare l’origine dati di un flusso di lavoro **[!UICONTROL Working table]**. Questo offre maggiore flessibilità per gestire i dati tra diverse origini dati, come FDA, FFDA e database locale.

La **[!UICONTROL Working table]** consente al flusso di lavoro Adobe Campaign di gestire i dati e condividerli con le attività del flusso di lavoro.
Per impostazione predefinita, la **[!UICONTROL Working table]** viene creato nello stesso database dell&#39;origine dei dati su cui eseguiamo la query.

Ad esempio, quando si esegue una query sul **[!UICONTROL Profiles]** nella tabella, memorizzata nel database Cloud, verrà creato un **[!UICONTROL Working table]** sullo stesso database Cloud.
Per modificare questa impostazione, puoi aggiungere la **[!UICONTROL Change Data Source]** per scegliere un’origine dati diversa per la **[!UICONTROL Working table]**.

Tieni presente che quando utilizzi **[!UICONTROL Change Data Source]** per continuare l’esecuzione del flusso di lavoro, dovrai tornare al database Cloud .

Per utilizzare **[!UICONTROL Change Data Source]** attività:

1. Creare un flusso di lavoro.

1. Invia una query ai destinatari con un **[!UICONTROL Query]** attività.

   Per ulteriori informazioni sulla **[!UICONTROL Query]** attività, fai riferimento a [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html).

1. Da **[!UICONTROL Targeting]** aggiungi una scheda **[!UICONTROL Change data source]** attività e fai doppio clic su di essa per selezionarla **[!UICONTROL Default data source]**.

   La tabella di lavoro, che contiene il risultato della query, viene quindi spostata nel database PostgreSQL predefinito.

1. Da **[!UICONTROL Actions]** trascinare un **[!UICONTROL JavaScript code]** attività per eseguire operazioni unitarie sul tavolo di lavoro.

   Per ulteriori informazioni sulla **[!UICONTROL JavaScript code]** attività, fai riferimento a [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html).

1. Aggiungi un altro **[!UICONTROL Change data source]** attività per tornare al database Cloud.

   Fai doppio clic sull’attività e seleziona **[!UICONTROL Active FDA external account]** quindi il corrispondente account esterno.

1. Ora puoi avviare il flusso di lavoro.

## Gestire i magazzini virtuali {#warehouse}

Dopo aver creato il flusso di lavoro, puoi accedere alle opzioni aggiuntive con la **[!UICONTROL Properties]** per ulteriori configurazioni.

Ulteriori informazioni **Proprietà del flusso di lavoro** in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html).

Da **[!UICONTROL Execution]** scheda del flusso di lavoro **[!UICONTROL Properties]**, puoi scegliere di collegare il flusso di lavoro a diversi magazzini e ottimizzare la gestione del carico di lavoro. Per ulteriori informazioni su **Magazzini**, fare riferimento alla [Documentazione del Snowflake](https://docs.snowflake.com/en/user-guide/warehouses-overview.html).

![](assets/warehouse.png)

A seconda dello scopo del flusso di lavoro, puoi scegliere tra i tre magazzini seguenti dalla sezione **[!UICONTROL Warehouse]** a discesa:

* **[!UICONTROL Default]** / **[!UICONTROL Campaign]**: impostato per impostazione predefinita durante la creazione di un nuovo flusso di lavoro.

* **[!UICONTROL Import / Export]**: devono essere impostati con flussi di lavoro di importazione o esportazione per ottimizzare le prestazioni delle attività.

* **[!UICONTROL Campaign Burst]**: devono essere impostati con flussi di lavoro per campagne o consegne per ottimizzare il tempo di elaborazione delle consegne.

>[!NOTE]
>
>La **[!UICONTROL System]** warehouse è impostato solo per i flussi di lavoro incorporati.

## Configurare campagne ricorrenti

Progetta un flusso di lavoro ricorrente e crea una nuova istanza di consegna ogni volta che il flusso di lavoro viene eseguito. Ad esempio, se il flusso di lavoro è progettato per essere eseguito una volta alla settimana, si otterranno 52 consegne dopo un anno. Ciò significa anche che i registri saranno separati da ogni istanza di consegna.

Scopri come creare una campagna ricorrente in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html)


## Sfruttare gli eventi trigger

Utilizza la messaggistica transazionale di Campaign per automatizzare i messaggi generati dagli eventi attivati dai sistemi di informazioni. Questi messaggi transazionali possono essere fatture, conferma dell&#39;ordine, conferma della spedizione, modifica della password, notifica di indisponibilità del prodotto, dichiarazione dell&#39;account o creazione dell&#39;account del sito web, ad esempio. Questi messaggi possono essere inviati singolarmente o in batch tramite e-mail, SMS o notifiche push.

![](../assets/do-not-localize/glass.png) Ulteriori informazioni sulle funzionalità di messaggistica transazionale in [questa sezione](../send/transactional.md).

Collega Adobe Campaign e Adobe Analytics per recuperare le azioni degli utenti e inviare messaggi personalizzati in tempo reale.

![](../assets/do-not-localize/glass.png) Scopri come integrare Campaign con altre soluzioni in [questa sezione](../start/connect.md)


## Casi d’uso end-to-end del flusso di lavoro{#end-to-end-uc}

In questa sezione troverai vari casi d’uso che sfruttano le funzionalità dei flussi di lavoro di Campaign.

### Consegne {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">


* [Inviare un’e-mail di compleanno](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html)

   Questo caso d’uso illustra come pianificare l’invio di un’e-mail ricorrente a un elenco di destinatari il giorno del loro compleanno.

* [Caricare contenuto di consegna](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html)
Quando il contenuto della consegna è disponibile in un file HTML presente su un server remoto, puoi facilmente caricarlo nelle consegne Adobe Campaign.

* [Flusso di lavoro di consegna cross-channel](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/cross-channel-delivery-workflow.html)
Scopri come creare un flusso di lavoro di consegna cross-channel. L’obiettivo è quello di segmentare un pubblico dai destinatari del database in gruppi diversi e inviare un’e-mail al primo gruppo e un SMS all’altro.

* [Arricchimento delle e-mail con campi data personalizzati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html)
Scopri come inviare un’e-mail con campi dati personalizzati ai profili che festeggiano i loro compleanni questo mese. L&#39;e-mail includerà un coupon valido una settimana prima e dopo il loro compleanno.

E queste pagine nella documentazione di Campaign v7:

* [Creazione, edizione e pubblicazione automatica dei contenuti](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html){target=&quot;_blank&quot;} Scopri come automatizzare la creazione e la consegna di un blocco di contenuto con il componente aggiuntivo Gestione dei contenuti di Campaign.

* [Test A/B](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html){target=&quot;_blank&quot;} Scopri come confrontare due contenuti di consegna e-mail tramite un flusso di lavoro di targeting. Il messaggio e il testo sono identici in entrambe le consegne: cambia solo il layout. La popolazione mirata è divisa in tre parti: due gruppi di test e la popolazione rimanente. A ogni gruppo di test viene inviata una versione diversa della consegna.

### Monitoraggio {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Inviare un rapporto a un elenco](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-a-report-to-a-list.html)
Scopri come generare un rapporto mensile integrato degli indicatori di tracciamento in formato PDF e inviarlo a un elenco di operatori Campaign.

* [Superare i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/workflow-supervision.html)
Scopri come creare un flusso di lavoro che ti consente di monitorare lo stato di un set di flussi di lavoro che sono &quot;in pausa&quot;, &quot;interrotto&quot; o &quot;con errori&quot;.

* [Inviare avvisi personalizzati agli operatori](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators.html)
Scopri come inviare un avviso a un operatore che conterrà il nome dei profili che hanno aperto una newsletter ma non hanno fatto clic sul collegamento in essa contenuto.

### Gestione dei dati {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Coordinare gli aggiornamenti dei dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/coordinate-data-updates.html)
Scopri come verificare che il processo di aggiornamento sia terminato prima di eseguire un’altra operazione di aggiornamento. A questo scopo, imposteremo una variabile di istanza e lasceremo che il flusso di lavoro verifichi se l’istanza è in esecuzione per decidere se continuare l’esecuzione del flusso di lavoro ed eseguire l’aggiornamento.

* [Creare un elenco di riepilogo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/create-a-summary-list.html)
Scopri come creare un flusso di lavoro che, dopo la raccolta dei file e dopo diversi arricchimenti, ti consente di creare un elenco di riepilogo. L&#39;esempio si basa su un elenco di contatti che hanno effettuato acquisti in un negozio.

* [Arricchire i dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/enrich-data.html)
Scopri come inviare consegne personalizzate ai profili che hanno partecipato all’ultimo concorso a seconda del punteggio.

* [Utilizzare gli aggregati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html)
Scopri come identificare gli ultimi destinatari aggiunti al database.

* [Aggiornamento dell’elenco trimestrale tramite una query incrementale](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/quarterly-list-update.html)
Scopri come utilizzare una query incrementale per aggiornare automaticamente un elenco di destinatari.

* [Configurare un flusso di lavoro di importazione ricorrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html)
Scopri come progettare un flusso di lavoro che può essere riutilizzato per importare profili provenienti da un sistema di gestione delle relazioni con i clienti nel database Adobe Campaign.

### Targeting {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Eseguire una query sulla tabella dei destinatari](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/querying-recipient-table.html)
Scopri come recuperare i nomi e le e-mail dei destinatari il cui dominio e-mail è &quot;orange.co.uk&quot; e che non vivono a Londra.

* [Informazioni sulla consegna delle query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-delivery-info.html)
Scopri come definire query sulle informazioni di consegna per recuperare il comportamento del profilo.

* [Calcolare gli aggregati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/compute-aggregates.html)
Scopri come contare il numero di profili che vivono a Londra, in base al sesso.

* [Query tramite una relazione molti-a-molti](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html)
Scopri come trovare profili non contattati negli ultimi 7 giorni.

* [Chiamare una variabile di istanza in una query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/javascript-scripts-and-templates.html)
Scopri come utilizzare una variabile di istanza per calcolare dinamicamente la percentuale di suddivisione da applicare a un gruppo.

<!--
### Change data source activity {#data-source-uc}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. 

In this use case, learn how to use the **[!UICONTROL Change data source]** activity to perform unitary operations to insert or update information to the recipient table.

![](assets/wf_data_source_uc.png)

1. Create a workflow and add a **[!UICONTROL Start]** activity.

1. Query your targeted recipients from the NmsRecipient table with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to the [Query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html#creating-a-query) page in Campaign Classic V7 documentation.

1. 

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

1. Add another **[!UICONTROL Change data source]** activity to revert back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. Add an **[!UICONTROL End]** activity and start your workflow.
-->

