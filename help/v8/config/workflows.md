---
title: Gestire e automatizzare i processi con i flussi di lavoro Adobe Campaign
description: Introduzione ai flussi di lavoro
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 780a29dab99ad2bda554134ca95c435b9e76b494
workflow-type: tm+mt
source-wordcount: '1545'
ht-degree: 2%

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

Ulteriori informazioni sull’interfaccia utente e l’esecuzione dei flussi di lavoro nella documentazione di Campaign Classic v7:

* [Introduzione ai flussi di lavoro](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows){target=&quot;_blank&quot;}

* [Best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html){target=&quot;_blank&quot;}

* [Flussi di lavoro tecnici incorporati](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html){target=&quot;_blank&quot;}

* [Monitorare l&#39;esecuzione](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html) dei flussi di lavoro{target=&quot;_blank&quot;}

* [Creare un pubblico in un flusso di lavoro della campagna di marketing](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow){target=&quot;_blank&quot;}

## Attività del flusso di lavoro {#wf-activities}

![](../assets/do-not-localize/book.png) Ulteriori informazioni sulle attività del flusso di lavoro disponibili  [Campaign Classic v7 documentazione](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-activities.html){target=&quot;_blank&quot;}

Le attività del flusso di lavoro sono raggruppate per categoria. Sono disponibili le quattro categorie di attività seguenti:

* [Attività](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html) di targeting {target=&quot;_blank&quot;}: Query, Elenco di lettura, Arricchimento, Unione e altro ancora
* [Attività](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html) di controllo del flusso {target=&quot;_blank&quot;}: Scheduler, Fork, Alert, Segnale esterno e altro ancora
* [Attività](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html) azione {target=&quot;_blank&quot;}: Consegne cross-channel, codice JavaScript, attività CRM, aggiornamento aggregato e altro ancora
* [Attività](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html) evento {target=&quot;_blank&quot;}: Trasferimento file, download web e altro ancora

### Modificare l’attività dell’origine dati {#change-data-source-activity}

L’attività **[!UICONTROL Change data source]** ti consente di modificare l’origine dati di un flusso di lavoro **[!UICONTROL Working table]**. Questo offre maggiore flessibilità per gestire i dati tra diverse origini dati, come FDA, FFDA e database locale.

Il **[!UICONTROL Working table]** consente al flusso di lavoro Adobe Campaign di gestire i dati e condividerli con le attività del flusso di lavoro.
Per impostazione predefinita, il **[!UICONTROL Working table]** viene creato nello stesso database dell&#39;origine dei dati su cui eseguiamo la query.

Ad esempio, quando esegui una query sulla tabella **[!UICONTROL Profiles]** memorizzata nel database Cloud, creerai un elemento **[!UICONTROL Working table]** nello stesso database Cloud.
Per modificare questa impostazione, puoi aggiungere l’attività **[!UICONTROL Change Data Source]** per scegliere una diversa origine dati per il tuo **[!UICONTROL Working table]**.

Tieni presente che quando utilizzi l’attività **[!UICONTROL Change Data Source]** , dovrai tornare al database Cloud per continuare l’esecuzione del flusso di lavoro.

Per utilizzare l&#39;attività **[!UICONTROL Change Data Source]**:

1. Creare un flusso di lavoro.

1. Esegui una query sui destinatari con un’attività **[!UICONTROL Query]** .

   Per ulteriori informazioni sull’attività **[!UICONTROL Query]**, consulta la pagina [Query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html#creating-a-query) nella documentazione di Campaign Classic V7.

1. Dalla scheda **[!UICONTROL Targeting]** , aggiungi un’attività **[!UICONTROL Change data source]** e fai doppio clic su di essa per selezionare **[!UICONTROL Default data source]**.

   La tabella di lavoro, che contiene il risultato della query, viene quindi spostata nel database PostgreSQL predefinito.

1. Dalla scheda **[!UICONTROL Actions]** , trascina e rilascia un’attività **[!UICONTROL JavaScript code]** per eseguire operazioni unitarie sulla tabella di lavoro.

   Per ulteriori informazioni sull&#39;attività **[!UICONTROL JavaScript code]**, consulta la pagina [Codice JavaScript e codice JavaScript avanzato](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/sql-code-and-javascript-code.html#javascript-code) nella documentazione di Campaign Classic V7 .

1. Aggiungi un’altra attività **[!UICONTROL Change data source]** per tornare al database Cloud.

   Fai doppio clic sull’attività e seleziona **[!UICONTROL Active FDA external account]** , quindi l’account esterno corrispondente.

1. Ora puoi avviare il flusso di lavoro.

## Configurare campagne ricorrenti

Progetta un flusso di lavoro ricorrente e crea una nuova istanza di consegna ogni volta che il flusso di lavoro viene eseguito. Ad esempio, se il flusso di lavoro è progettato per essere eseguito una volta alla settimana, si otterranno 52 consegne dopo un anno. Ciò significa anche che i registri saranno separati da ogni istanza di consegna.

![](../assets/do-not-localize/book.png) Scopri come creare una campagna ricorrente nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns){target=&quot;_blank&quot;}


## Sfruttare gli eventi trigger

Utilizza la messaggistica transazionale di Campaign per automatizzare i messaggi generati dagli eventi attivati dai sistemi di informazioni. Questi messaggi transazionali possono essere fatture, conferma dell&#39;ordine, conferma della spedizione, modifica della password, notifica di indisponibilità del prodotto, dichiarazione dell&#39;account o creazione dell&#39;account del sito web, ad esempio. Questi messaggi possono essere inviati singolarmente o in batch tramite e-mail, SMS o notifiche push.

![](../assets/do-not-localize/glass.png) Ulteriori informazioni sulle funzionalità di messaggistica transazionale in  [questa sezione](../send/transactional.md).

Collega Adobe Campaign e Adobe Analytics per recuperare le azioni degli utenti e inviare messaggi personalizzati in tempo reale.

![](../assets/do-not-localize/glass.png) Scopri come integrare Campaign con altre soluzioni in  [questa sezione](../start/connect.md)


## Casi d’uso end-to-end del flusso di lavoro{#end-to-end-uc}

In questa sezione troverai vari casi d’uso che sfruttano le funzionalità dei flussi di lavoro di Campaign. Questi casi d’uso sono generati in Adobe Campaign Classic v7 e si applicano ad Adobe Campaign v8.

### Consegne {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

* [Test A/B](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html){target=&quot;_blank&quot;}

   Scopri come confrontare due contenuti di consegna e-mail tramite un flusso di lavoro di targeting. Il messaggio e il testo sono identici in entrambe le consegne: cambia solo il layout. La popolazione mirata è divisa in tre parti: due gruppi di test e la popolazione rimanente. A ogni gruppo di test viene inviata una versione diversa della consegna.

* [Invio di un&#39;e-mail di compleanno](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html){target=&quot;_blank&quot;}

   Questo caso d’uso illustra come pianificare l’invio di un’e-mail ricorrente a un elenco di destinatari il giorno del loro compleanno.

* [Caricamento del contenuto](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html) di consegna{target=&quot;_blank&quot;} Quando il contenuto di consegna è disponibile in un file HTML presente su un server remoto, puoi facilmente caricare tale contenuto nelle consegne di Adobe Campaign.

* [Flusso di lavoro di consegna cross-channel](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/cross-channel-delivery-workflow.html){target=&quot;_blank&quot;}

   Scopri come creare un flusso di lavoro di consegna cross-channel. L’obiettivo è quello di segmentare un pubblico dai destinatari del database in gruppi diversi e inviare un’e-mail al primo gruppo e un SMS all’altro.

* [Arricchimento delle e-mail con campi data personalizzati](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html){target=&quot;_blank&quot;}

   Scopri come inviare un’e-mail con campi dati personalizzati ai profili che festeggiano i loro compleanni questo mese. L&#39;e-mail includerà un coupon valido una settimana prima e dopo il loro compleanno.

* [Automazione della creazione, della modifica e della pubblicazione dei contenuti](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html){target=&quot;_blank&quot;}

   Scopri come automatizzare la creazione e la consegna di un blocco di contenuto con il componente aggiuntivo Gestione dei contenuti di Campaign.


### Monitoraggio {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Invia un report a un elenco](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html){target=&quot;_blank&quot;}

   Scopri come generare un rapporto mensile integrato degli indicatori di tracciamento in formato PDF e inviarlo a un elenco di operatori Campaign.

* [Supera i tuoi flussi di lavoro](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html){target=&quot;_blank&quot;}

   Scopri come creare un flusso di lavoro che ti consente di monitorare lo stato di un set di flussi di lavoro che sono &quot;in pausa&quot;, &quot;interrotto&quot; o &quot;con errori&quot;.

* [Inviare avvisi personalizzati agli operatori](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-personalized-alerts-to-operators.html){target=&quot;_blank&quot;}

   Scopri come inviare un avviso a un operatore che conterrà il nome dei profili che hanno aperto una newsletter ma non hanno fatto clic sul collegamento in essa contenuto.

### Gestione dati {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Aggiornamenti dei dati di coordinate](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/coordinating-data-updates.html){target=&quot;_blank&quot;}

   Scopri come verificare che il processo di aggiornamento sia terminato prima di eseguire un’altra operazione di aggiornamento. A questo scopo, imposteremo una variabile di istanza e lasceremo che il flusso di lavoro verifichi se l’istanza è in esecuzione per decidere se continuare o meno l’esecuzione del flusso di lavoro ed eseguire l’aggiornamento.

* [Crea un elenco](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/creating-a-summary-list.html) di riepilogo {target=&quot;_blank&quot;}

   Scopri come creare un flusso di lavoro che, dopo la raccolta dei file e dopo diversi arricchimenti, ti consente di creare un elenco di riepilogo. L&#39;esempio si basa su un elenco di contatti che hanno effettuato acquisti in un negozio.

* [Arricchisci i dati](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html){target=&quot;_blank&quot;}

   Scopri come inviare consegne personalizzate ai profili che hanno partecipato all’ultimo concorso a seconda del punteggio.

* [Usa aggregati](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/using-aggregates.html){target=&quot;_blank&quot;}

   Scopri come identificare gli ultimi destinatari aggiunti al database.

* [Aggiornamento dell&#39;elenco trimestrale utilizzando una query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/quarterly-list-update.html) incrementale{target=&quot;_blank&quot;}

   Scopri come utilizzare una query incrementale per aggiornare automaticamente un elenco di destinatari.

* [Imposta un flusso di lavoro](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/recurring-import-workflow.html) di importazione ricorrente{target=&quot;_blank&quot;}

   Scopri come progettare un flusso di lavoro che può essere riutilizzato per importare profili provenienti da un sistema di gestione delle relazioni con i clienti nel database Adobe Campaign.

### Targeting {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Esegui query sulla tabella](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-recipient-table.html) dei destinatari {target=&quot;_blank&quot;}

   Scopri come recuperare i nomi e le e-mail dei destinatari il cui dominio e-mail è &quot;orange.co.uk&quot; e che non vivono a Londra.

* [Informazioni sulla consegna delle query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-delivery-information.html){target=&quot;_blank&quot;}

   Scopri come definire query sulle informazioni di consegna per recuperare il comportamento del profilo.

* [Calcola aggregati](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/performing-aggregate-computing.html){target=&quot;_blank&quot;}

   Scopri come contare il numero di profili che vivono a Londra, in base al sesso.

* [Query tramite una relazione molti-a-molti](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-using-many-to-many-relationship.html){target=&quot;_blank&quot;}

   Scopri come trovare profili non contattati negli ultimi 7 giorni.

* [Chiama una variabile di istanza in una query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/javascript-scripts-and-templates.html?lang=en#example){target=&quot;_blank&quot;}

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

