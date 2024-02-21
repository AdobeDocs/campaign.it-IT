---
audience: user
user-guide-title: Guida all’automazione di Campaign
user-guide-description: Guida all’automazione di Campaign
source-git-commit: c3f4ad0b56dd45d19eebaa4d2f06551c8fecac1d
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 81%

---


# Guide all’automazione di Campaign {#automation}

+ [Guida all’automazione di Campaign](home.md)
+ Automatizzare con i flussi di lavoro {#workflows}
   + Introduzione ai flussi di lavoro {#introduction}
      + [Informazioni sui flussi di lavoro](workflow/about-workflows.md)
      + Tipi di flussi di lavoro {#wf-type}
         + [Flussi di lavoro di targeting](workflow/targeting-workflows.md)
         + [Flussi di lavoro della campagna](workflow/campaign-workflows.md)
         + [Flussi di lavoro tecnici](workflow/technical-workflows.md)
      + [Creare un flusso di lavoro](workflow/build-a-workflow.md)
      + [Best practice](workflow/workflow-best-practices.md)
      + [Utilizzare i dati del flusso di lavoro](workflow/use-workflow-data.md)
   + Eseguire un flusso di lavoro {#executing-a-workflow}
      + [Avviare un flusso di lavoro](workflow/start-a-workflow.md)
      + [Ciclo di vita di un flusso di lavoro](workflow/workflow-life-cycle.md)
      + [Impostare le approvazioni](workflow/define-approvals.md)
   + Monitorare i flussi di lavoro {#monitoring-workflows}
      + [Monitorare l’esecuzione di un flusso di lavoro](workflow/monitor-workflow-execution.md)
      + [Monitorare i flussi di lavoro tecnici](workflow/monitor-technical-workflows.md)
      + [Flusso di lavoro HeatMap](workflow/heatmap.md)
   + Attività del flusso di lavoro {#wf-activities}
      + [Introduzione alle attività](workflow/activities.md)
      + Attività di targeting {#targeting-activities}
         + [Elenco delle attività di targeting](workflow/targeting-activities.md)
         + [Celle](workflow/cells.md)
         + [Modificare l’origine dati](workflow/change-data-source.md)
         + [Cambiare dimensione](workflow/change-dimension.md)
         + [Connettore per sistema CRM](workflow/crm-connector.md)
         + [Deduplica](workflow/deduplication.md)
         + [Profilo di consegna](workflow/delivery-outline.md)
         + [Modifica di uno schema](workflow/edit-schema.md)
         + [Arricchimento](workflow/enrichment.md)
         + [Esclusione](workflow/exclusion.md)
         + [Query incrementale](workflow/incremental-query.md)
         + [Intersezione ](workflow/intersection.md)
         + [Aggiornare un elenco](workflow/list-update.md)
         + [Offerte per cella](workflow/offers-by-cell.md)
         + [Motore di offerta](workflow/offer-engine.md)
         + [Query](workflow/query.md)
         + [Lettura di un elenco](workflow/read-list.md)
         + [Dividi](workflow/split.md)
         + [Attività Subscription services](workflow/subscription-services.md)
         + [Unione](workflow/union.md)
         + [Aggiornare i dati](workflow/update-data.md)
      + Attività di controllo del flusso {#flow-control-activities}
         + [Elenco delle attività di controllo del flusso](workflow/flow-control-activities.md)
         + [Attività Alert](workflow/alert.md)
         + [AND-join](workflow/and-join.md)
         + [Approvazione](workflow/approval.md)
         + [Attività External signal](workflow/external-signal.md)
         + [Fork](workflow/fork.md)
         + [Oggetti Jump (punto iniziale e punto finale)](workflow/jump-start-point-and-end-point.md)
         + [Attività Start e End](workflow/start-and-end.md)
         + [Modulo di pianificazione](workflow/scheduler.md)
         + [Flusso di lavoro secondario](workflow/sub-workflow.md)
         + [Attività Test](workflow/test.md)
         + [Attività Time constraint](workflow/time-constraint.md)
         + [Attendi](workflow/wait.md)
      + Attività di azione {#action-activities}
         + [Elenco delle attività di azione](workflow/action-activities.md)
         + [Gestione dei contenuti](workflow/content-management.md)
         + [Consegna continua](workflow/continuous-delivery.md)
         + [Consegne cross-channel](workflow/cross-channel-deliveries.md)
         + [Estrazione dati (file)](workflow/extraction-file.md)
         + [Caricamento dati (file)](workflow/data-loading-file.md)
         + [Caricamento dati (RDBMS)](workflow/data-loading-rdbms.md)
         + [Consegna](workflow/delivery.md)
         + [Controllo della consegna](workflow/delivery-control.md)
         + [Approvazione locale](workflow/local-approval.md)
         + [Caricamento (SOAP)](workflow/loading-soap.md)
         + [Modulo Nlserver](workflow/nlserver-module.md)
         + [Consegna ricorrente](workflow/recurring-delivery.md)
         + [Codice SQL e codice JavaScript](workflow/sql-code-and-javascript-code.md)
         + [Gestione dati SQL](workflow/sql-data-management.md)
         + [Aggregato di aggiornamento](workflow/update-aggregate.md)
      + Attività di eventi {#event-activities}
         + [Elenco delle attività evento](workflow/event-activities.md)
         + [Raccolta file](workflow/file-collector.md)
         + [Trasferimento file](workflow/file-transfer.md)
         + [E-mail in entrata](workflow/inbound-emails.md)
         + [SMS in entrata](workflow/inbound-sms.md)
         + [Download web](workflow/web-download.md)
   + Casi d’uso {#use-cases}
      + [Informazioni sui casi d’uso dei flussi di lavoro](workflow/workflow-use-cases.md)
      + Consegne {#deliveries}
         + [Utilizzare l’attività di approvazione locale](workflow/local-approval-activity.md)
         + [Inviare un’e-mail di compleanno](workflow/send-a-birthday-email.md)
         + [Caricare i contenuti della consegna](workflow/load-delivery-content.md)
         + [Flusso di lavoro di consegna cross-channel](workflow/cross-channel-delivery-workflow.md)
         + [Arricchimento delle e-mail con campi data personalizzati](workflow/email-enrichment-with-custom-date-fields.md)
      + Monitoraggio {#monitoring}
         + [Inviare un rapporto a un elenco](workflow/send-a-report-to-a-list.md)
         + [Supervisionare i flussi di lavoro](workflow/workflow-supervision.md)
         + [Inviare avvisi personalizzati agli operatori](workflow/send-alerts-to-operators.md)
      + Gestione dei dati {#data-management}
         + [Coordinare gli aggiornamenti dei dati](workflow/coordinate-data-updates.md)
         + [Creare un elenco di riepilogo](workflow/create-a-summary-list.md)
         + [Arricchire i dati](workflow/enrich-data.md)
         + [Utilizzare gli aggregati](workflow/using-aggregates.md)
         + [Utilizzare la funzionalità di unione dell’attività Deduplicazione](workflow/deduplication-merge.md)
         + [Impostare un flusso di lavoro di importazione ricorrente](workflow/recurring-import-workflow.md)
      + Progettare le query {#designing-queries}
         + [Aggiornamento dell’elenco trimestrale tramite una query incrementale](workflow/quarterly-list-update.md)
      + Query e filtro {#designing-queries}
         + [Eseguire una query sulla tabella dei destinatari](workflow/querying-recipient-table.md)
         + [Eseguire una query sulle informazioni di consegna](workflow/query-delivery-info.md)
         + [Calcola aggregati](workflow/compute-aggregates.md)
         + [Eseguire query tramite gestione dei raggruppamenti](workflow/query-grouping-management.md)
         + [Eseguire una query tramite una relazione molti-a-molti](workflow/query-many-to-many-relationship.md)
         + [Aggiungere un campo calcolato di tipo enumerazione](workflow/adding-enumeration-type-calculated-field.md)
         + [Creare un filtro](workflow/create-a-filter.md)
         + [Filtrare i destinatari duplicati](workflow/filter-duplicated-recipients.md)
   + Impostazioni avanzate {#advanced-management}
      + [Proprietà del flusso di lavoro](workflow/workflow-properties.md)
      + [Parametri avanzati](workflow/advanced-parameters.md)
      + [Script e modelli JavaScript](workflow/javascript-scripts-and-templates.md)
      + [Esempi di codice JavaScript nei flussi di lavoro](workflow/javascript-in-workflows.md)
      + [Accedere a un database esterno](workflow/accessing-an-external-database-fda.md)
      + [Gestire le autorizzazioni](workflow/managing-rights.md)
      + [Modificare le immagini dell’attività](workflow/change-activity-images.md)
      + [Gestire i fusi orari](workflow/managing-time-zones.md)
+ Orchestrazione campagna {#campaign-orchestration}
   + [Introduzione alle campagne di marketing](campaigns/set-up-campaigns.md)
   + [Creare programmi e campagne](campaigns/marketing-campaign-create.md)
   + [Creare e configurare i modelli](campaigns/marketing-campaign-templates.md)
   + [Aggiungere consegne](campaigns/marketing-campaign-deliveries.md)
   + [Selezionare il pubblico](campaigns/marketing-campaign-target.md)
   + [Gestire documenti e risorse](campaigns/marketing-campaign-assets.md)
   + [Impostare e gestire le approvazioni](campaigns/marketing-campaign-approval.md)
   + [Campagne ricorrenti e periodiche](campaigns/recurring-periodic-campaigns.md)
   + [Monitorare le campagne](campaigns/marketing-campaign-monitoring.md)
   + [Fornitori, scorte e budget](campaigns/providers-stocks-and-budgets.md)
+ Ottimizzazione di Campaign (componente aggiuntivo){#campaign-optimization}
   + [Introduzione alle tipologie di campagne](campaign-opt/campaign-typologies.md)
   + [Regole di filtro](campaign-opt/filtering-rules.md)
   + [Regole di controllo](campaign-opt/control-rules.md)
   + [Regole di pressione](campaign-opt/pressure-rules.md)
   + [Regole di coerenza](campaign-opt/consistency-rules.md)
   + [Applicare le regole](campaign-opt/apply-rules.md)
   + [Simulazioni delle campagne](campaign-opt/campaign-simulations.md)
+ Gestione delle risorse marketing (componente aggiuntivo){#mrm}
   + [Introduzione alla gestione delle risorse di marketing](mrm/about-marketing-resource-management.md)
   + [Creare e gestire le attività](mrm/creating-and-managing-tasks.md)
   + [Controllare i costi](mrm/controlling-costs.md)
   + [Gestire le risorse di marketing](mrm/managing-marketing-resources.md)
   + [Forum di discussione](mrm/discussion-forums.md)
+ Marketing distribuito (componente aggiuntivo) {#distributed-marketing}
   + [Introduzione al marketing distribuito](distributed-marketing/about-distributed-marketing.md)
   + [Creare una campagna locale](distributed-marketing/creating-a-local-campaign.md)
   + [Creare una campagna collaborativa](distributed-marketing/creating-a-collaborative-campaign.md)
   + [Pubblicare il pacchetto della campagna](distributed-marketing/publishing-the-campaign-package.md)
   + [Accedere alle campagne](distributed-marketing/accessing-campaigns.md)
   + [Tracciare una campagna](distributed-marketing/tracking-a-campaign.md)
   + [Casi d’uso](distributed-marketing/examples.md)
+ [Documentazione di Campaign v8](https://experienceleague.adobe.com/docs/campaign/campaign-v8/campaign-home.html?lang=it)