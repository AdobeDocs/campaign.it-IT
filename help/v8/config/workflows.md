---
product: Adobe Campaign
title: Gestire e automatizzare i processi con i flussi di lavoro Adobe Campaign
description: Introduzione ai flussi di lavoro
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 41ea85bc3c616ed7cdd0718ff3368aab971a5352
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 9%

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

[!DNL :arrow_upper_right:]  [Introduzione ai flussi di lavoro](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)
* Attività del flusso di lavoro:
   * [Attività](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html) di targeting: Query, Elenco di lettura, Arricchimento, Unione e altro ancora
   * [Attività](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html) di controllo del flusso: Scheduler, Fork, Alert, Segnale esterno e altro ancora
   * [Attività](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html) azione: Consegne cross-channel, codice JavaScript, attività CRM, aggiornamento aggregato e altro ancora
   * [Attività](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html) evento: Trasferimento file, download web e altro ancora
      [!DNL :arrow_upper_right:]  [Creare un pubblico in un flusso di lavoro di una campagna di marketing](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)

      [!DNL :arrow_upper_right:]  [Best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html)
      [!DNL :arrow_upper_right:] [Flussi di lavoro tecnici incorporati](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)
      [!DNL :arrow_upper_right:] [Monitorare l’esecuzione dei flussi di lavoro](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html)


## Configurare campagne ricorrenti

Progetta un flusso di lavoro ricorrente e crea una nuova istanza di consegna ogni volta che il flusso di lavoro viene eseguito. Ad esempio, se il flusso di lavoro è progettato per essere eseguito una volta alla settimana, si otterranno 52 consegne dopo un anno. Ciò significa anche che i registri saranno separati da ogni istanza di consegna.

[!DNL :arrow_upper_right:] Scopri come creare una campagna ricorrente nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns).


## Sfruttare gli eventi trigger

Utilizza la messaggistica transazionale di Campaign per automatizzare i messaggi generati dagli eventi attivati dai sistemi di informazioni. Questi messaggi transazionali possono essere fatture, conferma dell&#39;ordine, conferma della spedizione, modifica della password, notifica di indisponibilità del prodotto, dichiarazione dell&#39;account o creazione dell&#39;account del sito web, ad esempio. Questi messaggi possono essere inviati singolarmente o in batch tramite e-mail, SMS o notifiche push.

[!DNL :bulb:] Ulteriori informazioni sulle funzionalità di messaggistica transazionale in  [questa sezione](../send/transactional.md).

Collega Adobe Campaign e Adobe Analytics per recuperare le azioni degli utenti e inviare messaggi personalizzati in tempo reale.

[!DNL :bulb:] Scopri come integrare Campaign con altre soluzioni in  [questa sezione](../start/connect.md)


## Casi di utilizzo end-to-end del flusso di lavoro{#end-to-end-uc}

In questa sezione troverai vari casi d’uso che sfruttano le funzionalità dei flussi di lavoro di Campaign. Questi casi d’uso sono generati in Adobe Campaign Classic v7 e si applicano ad Adobe Campaign v8.

### Consegne {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

* [Test A/B](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html)

   Scopri come confrontare due contenuti di consegna e-mail tramite un flusso di lavoro di targeting. Il messaggio e il testo sono identici in entrambe le consegne: cambia solo il layout. La popolazione mirata è divisa in tre parti: due gruppi di test e la popolazione rimanente. A ogni gruppo di test viene inviata una versione diversa della consegna.

* [Invio di un’e-mail di compleanno](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html)

   Questo caso d’uso illustra come pianificare l’invio di un’e-mail ricorrente a un elenco di destinatari il giorno del loro compleanno.

* [Caricamento del contenuto di una consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)

   Quando il contenuto della consegna è disponibile in un file HTML presente su un server remoto, puoi facilmente caricarlo nelle consegne di Adobe Campaign.

* [Flusso di lavoro di consegna cross-channel](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/cross-channel-delivery-workflow.html)

   Scopri come creare un flusso di lavoro di consegna cross-channel. L’obiettivo è quello di segmentare un pubblico dai destinatari del database in gruppi diversi e inviare un’e-mail al primo gruppo e un SMS all’altro.

* [Arricchimento delle e-mail con campi data personalizzati](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html)

   Scopri come inviare un’e-mail con campi dati personalizzati ai profili che festeggiano i loro compleanni questo mese. L&#39;e-mail includerà un coupon valido una settimana prima e dopo il loro compleanno.

* [Automazione di creazione, edizione e pubblicazione di contenuti](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html)

   Scopri come automatizzare la creazione e la consegna di un blocco di contenuto con il componente aggiuntivo Gestione dei contenuti di Campaign.


### Monitoraggio {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Inviare un rapporto a un elenco](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html)

   Scopri come generare un rapporto mensile integrato di indicatori di tracciamento in formato PDF e inviarlo a un elenco di operatori Campaign.

* [Supervisionare i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html)

   Scopri come creare un flusso di lavoro che ti consente di monitorare lo stato di un set di flussi di lavoro che sono &quot;in pausa&quot;, &quot;interrotto&quot; o &quot;con errori&quot;.

* [Inviare avvisi personalizzati agli operatori](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-personalized-alerts-to-operators.html)

   Scopri come inviare un avviso a un operatore che conterrà il nome dei profili che hanno aperto una newsletter ma non hanno fatto clic sul collegamento in essa contenuto.

### Gestione dei dati {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Coordinare gli aggiornamenti dei dati](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/coordinating-data-updates.html)

   Scopri come verificare che il processo di aggiornamento sia terminato prima di eseguire un’altra operazione di aggiornamento. A questo scopo, imposteremo una variabile di istanza e lasceremo che il flusso di lavoro verifichi se l’istanza è in esecuzione per decidere se continuare o meno l’esecuzione del flusso di lavoro ed eseguire l’aggiornamento.

* [Creare un elenco di riepilogo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/creating-a-summary-list.html)

   Scopri come creare un flusso di lavoro che, dopo la raccolta dei file e dopo diversi arricchimenti, ti consente di creare un elenco di riepilogo. L&#39;esempio si basa su un elenco di contatti che hanno effettuato acquisti in un negozio.

* [Arricchire i dati](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html)

   Scopri come inviare consegne personalizzate ai profili che hanno partecipato all’ultimo concorso a seconda del punteggio.

* [Utilizzare gli aggregati](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/using-aggregates.html)

   Scopri come identificare gli ultimi destinatari aggiunti al database.

* [Aggiornamento dell’elenco trimestrale tramite una query incrementale](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/quarterly-list-update.html)

   Scopri come utilizzare una query incrementale per aggiornare automaticamente un elenco di destinatari.

* [Impostare un flusso di lavoro di importazione ricorrente](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/recurring-import-workflow.html)

   Scopri come progettare un flusso di lavoro che può essere riutilizzato per importare profili provenienti da un sistema di gestione delle relazioni con i clienti nel database Adobe Campaign.

### Targeting {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Eseguire una query sulla tabella dei destinatari](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-recipient-table.html)

   Scopri come recuperare i nomi e le e-mail dei destinatari il cui dominio e-mail è &quot;orange.co.uk&quot; e che non vivono a Londra.

* [Eseguire una query sulle informazioni di consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-delivery-information.html)

   Scopri come definire query sulle informazioni di consegna per recuperare il comportamento del profilo.

* [Calcolare gli aggregati](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/performing-aggregate-computing.html)

   Scopri come contare il numero di profili che vivono a Londra, in base al sesso.

* [Eseguire una query tramite una relazione molti-a-molti](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-using-many-to-many-relationship.html)

   Scopri come trovare profili non contattati negli ultimi 7 giorni.

* [Chiamare una variabile di istanza in una query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/javascript-scripts-and-templates.html?lang=en#example)

   Scopri come utilizzare una variabile di istanza per calcolare dinamicamente la percentuale di suddivisione da applicare a un gruppo.

