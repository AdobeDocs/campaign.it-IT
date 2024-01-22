---
audience: end-user
user-guide-title: Campaign v8
user-guide-description: Documentazione del prodotto per Adobe Campaign v8.
title: Documentazione di Adobe Campaign v8
description: Documentazione di Campaign v8
breadcrumb-title: Documentazione di Campaign v8
source-git-commit: f04db53bee75c935bc8737eef93fa05ec6868ebc
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 86%

---


# Documentazione di Adobe Campaign v8 {#campaign-v8}

+ [Documentazione di Campaign v8](campaign-home.md)
+ Versioni e aggiornamenti più recenti {#releases}
   + [Aggiornamenti della documentazione](start/documentation-updates.md)
   + [Note preliminari sulla versione](start/e-release-notes.md)
   + [Note sulla versione](start/release-notes.md)
   + Note sulla versione precedente {#previous-rn}
      + [2022](start/release-notes-2022.md)
      + [2021](start/release-notes-2021.md)
   + [Guardrail](start/ac-guardrails.md)
   + [Problemi noti](start/known-issues.md)
   + [Matrice di compatibilità](start/compatibility-matrix.md)
+ Introduzione {#new}
   + [Introduzione ad Adobe Campaign](start/get-started.md)
   + [Funzionalità principali](start/whats-new.md)
   + [Componenti e processi](start/ac-components.md)
   + [Connessione a Campaign](start/connect.md)
   + [Interfaccia di Campaign](start/campaign-ui.md)
   + [Da Classic v7 a v8](start/v7-to-v8.md)
   + [Domande frequenti](start/campaign-faq.md)
+ Gestione delle campagne {#campaigns}
   + [Introduzione alle campagne](start/campaigns.md)
   + [Orchestrazione campagna >](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=it)
+ Inviare messaggi{#send}
   + [Introduzione ai messaggi](start/create-message.md)
   + E-mail {#emails}
      + [Progettare e convalidare le e-mail](send/email.md)
      + [Collegamento a una pagina mirror](send/mirror-page.md)
      + [Definire parametri e-mail aggiuntivi](send/email-parameters.md)
      + [Inviare e monitorare le e-mail](send/send.md)
   + [SMS](send/sms.md)
   + Notifiche push {#push}
      + [Creare e inviare notifiche push](send/push.md)
      + [Configurare il canale di notifica push](send/push-settings.md)
      + [Configurare le notifiche push con Raccolta dati](send/push-data-collection.md)
   + [Messaggistica LINE](send/line.md)
   + [Direct mail](send/direct-mail.md)
   + [X (Twitter)](send/twitter.md)
   + Personalizzazione dei contenuti {#personalize}
      + [Introduzione alla personalizzazione](send/personalize.md)
      + [Dati di personalizzazione](send/personalization-data.md)
      + [Aggiungere campi di personalizzazione](send/personalization-fields.md)
      + [Utilizzare i blocchi di personalizzazione](send/personalization-blocks.md)
      + [Creare condizioni](send/conditions.md)
   + Convalidare e inviare la consegna {#validate}
   + [Anteprima e bozze](send/preview-and-proof.md)
   + [Analisi della consegna](send/delivery-analysis.md)
   + [Configurare e inviare la consegna](send/configure-and-send.md)
   + [Ottimizzazione dell’ora di invio](send/predictive.md)
   + Errori, mancati recapiti e quarantene{#failures}
      + [Quarantene](send/quarantines.md)
      + [Errori di consegna](send/delivery-failures.md)
   + [Utilizzare i modelli di consegna](send/create-templates.md)
   + Messaggi transazionali {#real-time}
      + [Introduzione ai messaggi transazionali](send/transactional.md)
      + [Creare e pubblicare il modello](send/transactional-template.md)
      + Gestione degli eventi {#event}
         + [Raccogliere ed elaborare gli eventi](send/event-processing.md)
         + [Informazioni sulla descrizione dell’evento](send/event-description.md)
         + [Inviare e monitorare i messaggi](send/delivery-execution.md)
+ Gestione di profili e pubblico {#audience}
   + [Guida introduttiva a profili e tipi di pubblico](audiences/gs-audiences.md)
   + [Utilizzare i tipi di pubblico](start/audiences.md)
   + [Accedere ai profili](audiences/view-profiles.md)
   + Aggiungere profili {#add-profiles}
      + [Creare i profili manualmente](audiences/create-profiles.md)
      + [Importare i profili da un file](audiences/import-profiles.md)
      + [Utilizzare i profili esterni](audiences/external-profiles.md)
      + [Raccogliere i dati del profilo nei moduli web](audiences/collect-profiles.md)
      + [Utilizzare le mappature target](audiences/target-mappings.md)
      + [Creare profili di test](audiences/test-profiles.md)
   + Creare tipi di pubblico {#create-audiences}
      + [Creare un elenco di contatti](audiences/create-audiences.md)
      + [Creare e gestire i filtri](audiences/create-filters.md)
      + [Condividere tipi di pubblico con le soluzioni Adobe](start/shared-audiences.md)
   + [Best practice](audiences/audiences-best-practices.md)
   + [Gestire le iscrizioni](start/subscriptions.md)
+ Gestione dei contenuti {#content}
   + [Progettare applicazioni web e moduli](dev/webapps.md)
+ Gestione della privacy e della sicurezza {#privacy}
   + [Gestire le richieste di accesso ai dati personali](start/privacy.md)
   + [Linee guida sulla sicurezza](config/security.md)
+ Gestione delle decisioni {#offers}
   + [Introduzione all’interazione in tempo reale](interaction/interaction.md)
   + [Ambienti e architettura](interaction/interaction-architecture.md)
   + [Best practice](interaction/interaction-best-practices.md)
   + Definire le impostazioni{#interaction-settings}
      + [Creare operatori](interaction/interaction-operators.md)
      + [Creare ambienti](interaction/interaction-env.md)
      + [Creare filtri predefiniti](interaction/interaction-predefined-filters.md)
      + [Creare spazi dell’offerta](interaction/interaction-offer-spaces.md)
   + [Creare un catalogo di offerte](interaction/interaction-offer-catalog.md)
   + [Creare un’offerta](interaction/interaction-offer.md)
   + [Inviare un’offerta (in uscita)](interaction/interaction-send-offers.md)
   + Presentare un’offerta (in entrata){#inbound}
      + [Contesto](interaction/interaction-present-offers.md)
      + [Chiamare un’offerta in una pagina web](interaction/interaction-integration.md)
      + [Gestire le interazioni anonime](interaction/anonymous-interactions.md)
   + [Rapporti e cronologia](interaction/interaction-tracking.md)
   + [Casi d’uso](interaction/interaction-use-cases.md)
+ Reporting e analisi {#analytics}
   + [Tracciamento e monitoraggio](start/tracking.md)
   + Utilizzare i rapporti{#reports}
      + [Introduzione ai rapporti](reporting/gs-reporting.md)
      + Creare i cubi{#cubes}
         + [Introduzione ai cubi](reporting/gs-cubes.md)
         + [Creare un cubo](reporting/cube-indicators.md)
         + [Utilizzare i cubi per creare rapporti](reporting/cube-tables.md)
         + [Personalizzare i cubi](reporting/customize-cubes.md)
      + Rapporti incorporati{#ac-reports}
         + [Elenco dei rapporti incorporati](reporting/built-in-reports.md)
         + [Rapporti globali](reporting/global-reports.md)
         + [Rapporti di consegna](reporting/delivery-reports.md)
         + [Calcolo delle metriche incorporate](reporting/metrics-calculation.md)
      + [Rapporti personalizzati](reporting/custom-reports.md)
+ Gestione dei dati {#data}
   + [Introduzione ai flussi di lavoro](config/workflows.md)
   + [Importare i dati](start/import.md)
   + [Documentazione del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=it)
+ Integrazioni {#connect}
   + [Connettere Campaign con altre soluzioni](connect/integration.md)
   + Campaign + Experience Platform {#ac-aep}
      + [Tipi di pubblico e attributi di profilo](connect/ac-aep.md)
      + [Pagine di destinazione e attributi del profilo di Campaign](connect/ac-aep-landing-pages.md)
   + [Campaign + Journey Optimizer](connect/ac-ajo.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign + trigger di Experience Cloud](connect/ac-triggers.md)
   + [Campaign + X (Twitter)](connect/ac-tw.md)
   + [Campaign + database esterno](connect/fda.md)
   + Campaign + CRM {#ac-crm}
      + [Introduzione ai connettori CRM](connect/crm.md)
      + [Utilizzare Campaign e SFDC](connect/ac-sfdc.md)
      + [Utilizzare Campaign e Microsoft Dynamics](connect/ac-ms-dyn.md)
      + [Sincronizzare i dati](connect/crm-data-sync.md)
+ Amministrazione {#admin}
   + Utenti e autorizzazioni {#permissions}
      + [Introduzione alle autorizzazioni](start/gs-permissions.md)
      + [Gestire le autorizzazioni utente](start/manage-permissions.md)
      + [Aggiungere autorizzazioni sulle cartelle](start/folder-permissions.md)
   + [Pannello di controllo](config/self-service.md)
+ Architettura e configurazione {#config}
   + Architettura di Campaign v8 {#architecture}
      + [Principi globali](architecture/general-architecture.md)
      + [Modelli di architettura](architecture/architecture.md)
      + [Distribuzione FDA di Campaign](architecture/fda-deployment.md)
      + Distribuzione aziendale (FFDA) {#ffda}
         + [Cos’è Campaign FFDA?](architecture/enterprise-deployment.md)
         + [Gestione delle chiavi e unicità](architecture/keys.md)
         + [Nuove API](architecture/new-apis.md)
         + [Meccanismo di staging API](architecture/staging.md)
         + [Meccanismo di replica](architecture/replication.md)
   + Implementazione {#implement}
      + [Passaggi di implementazione](start/implement.md)
      + [Personalizzare l’istanza](dev/customize.md)
      + [Best practice per i modelli di dati](dev/datamodel-best-practices.md)
   + Impostazioni e configurazione {#configuration}
      + [Impostazioni dell’interfaccia utente](config/ui-settings.md)
      + [Gestire le cartelle e le visualizzazioni](audiences/folders-and-views.md)
      + [Impostazioni e-mail](config/email-settings.md)
      + [Impostazioni dei messaggi transazionali](config/transactional-msg-settings.md)
      + [Integrare gli SDK di Campaign con l’app - PAGINA OBSOLETA](config/push-config.md)
      + [Account esterni](config/external-accounts.md)
+ Risorse per sviluppatori {#developer}
   + [Modello dati di Campaign](dev/datamodel.md)
   + Schemi e moduli {#shemas-forms}
      + [Utilizzare gli schemi](dev/schemas.md)
      + [Creare gli schemi](dev/create-schema.md)
      + [Estendere gli schemi](dev/extend-schema.md)
      + [Filtrare gli schemi](dev/filter-schema.md)
      + [Struttura dello schema](dev/schema-structure.md)
      + [Mappatura del database](dev/database-mapping.md)
      + [Limitare la visualizzazione di dati personali](dev/restrict-pi-view.md)
      + [Utilizzare una tabella dei destinatari personalizzata](dev/custom-recipient.md)
      + [Aggiornare il database](dev/update-database-structure.md)
      + [Moduli di input](dev/forms.md)
   + [API di Campaign](dev/api.md)
+ [Pannello di controllo Campaign >](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it)
+ [Guida all’automazione di Campaign >](https://experienceleague.adobe.com/docs/campaign/automation/home.html?lang=it)
