---
audience: end-user
user-guide-title: Campaign v8
description: Documentazione di Campaign v8
breadcrumb-title: Panoramica di Campaign
title: Documenti su Campaign v8
source-git-commit: b9928cc3bda0c0a1a0d5a43b2604615d7472b419
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 93%

---


# Documentazione di Adobe Campaign v8 {#campaign-v8}

+ [Documentazione di Campaign v8](campaign-home.md)
+ Versioni e aggiornamenti più recenti {#releases}
   + [Note preliminari sulla versione](start/e-release-notes.md)
   + [Note sulla versione](start/release-notes.md)
   + [Guardrail](start/ac-guardrails.md)
   + [Problemi noti](start/known-issues.md)
   + [Matrice di compatibilità](start/compatibility-matrix.md)
+ Introduzione {#new}
   + [Introduzione ad Adobe Campaign](start/get-started.md)
   + [Funzionalità principali](start/whats-new.md)
   + [Componenti e processi](start/ac-components.md)
   + [Connessione a Campaign](start/connect.md)
   + Interfaccia utente di Campaign {#ac-ui}
      + [Scoprire l’interfaccia di Campaign](start/campaign-ui.md)
      + [Personalizzare l’interfaccia di Campaign](start/customize-ui.md)
      + [Gestire le cartelle e le visualizzazioni](audiences/folders-and-views.md)
   + [Da Classic v7 a v8](start/v7-to-v8.md)
   + [Domande frequenti](start/campaign-faq.md)
+ Gestione delle campagne {#campaigns}
   + [Introduzione alle campagne](start/campaigns.md)
   + [Documentazione sull’orchestrazione delle campagne](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=it)
   + Inviare messaggi{#send}
      + [Introduzione ai messaggi](start/create-message.md)
      + E-mail {#emails}
         + [Progettare e convalidare le e-mail](send/email.md)
         + [Inviare e monitorare le e-mail](send/send.md)
      + [SMS](send/sms.md)
      + [Notifiche push](send/push.md)
      + [Messaggistica LINE](send/line.md)
      + [Direct mail](send/direct-mail.md)
      + [Twitter](send/twitter.md)
      + [Messaggi transazionali](send/transactional.md)
      + Errori, mancati recapiti e quarantene{#failures}
         + [Quarantene](send/quarantines.md)
         + [Errori di consegna](send/delivery-failures.md)
      + [Ottimizzazione dell’ora di invio](send/predictive.md)
      + [Gestire le iscrizioni](start/subscriptions.md)
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
   + Creare tipi di pubblico {#create-audiences}
      + [Creare un elenco di contatti](audiences/create-audiences.md)
      + [Creare e gestire i filtri](audiences/create-filters.md)
   + [Condividere tipi di pubblico con le soluzioni Adobe](start/shared-audiences.md)
   + [Best practice](audiences/audiences-best-practices.md)
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
      + [Guida introduttiva ai rapporti](reporting/gs-reporting.md)
      + Creazione di cubi{#cubes}
         + [Introduzione ai cubi](reporting/gs-cubes.md)
         + [Creare un cubo](reporting/cube-indicators.md)
         + [Utilizzare i cubi per creare rapporti](reporting/cube-tables.md)
         + [Personalizzare i cubi](reporting/cube-best-practices.md)
      + Report incorporati{#ac-reports}
         + [Elenco dei report incorporati](reporting/built-in-reports.md)
         + [Rapporti globali](reporting/global-reports.md)
         + [Rapporti di consegna](reporting/delivery-reports.md)
         + [Calcolo delle metriche incorporate](reporting/metrics-calculation.md)
      + [Report personalizzati](reporting/custom-reports.md)
+ Gestione dei dati {#data}
   + [Introduzione ai flussi di lavoro](config/workflows.md)
   + [Importare i dati](start/import.md)
   + [Documentazione del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=it)
+ Integrazioni {#connect}
   + [Connettere Campaign con altre soluzioni](connect/integration.md)
   + [Campaign + Experience Platform](connect/ac-aep.md)
   + [Campaign + Journey Optimizer](connect/ac-ajo.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign + trigger di Experience Cloud](connect/ac-triggers.md)
   + [Campaign + Twitter](connect/ac-tw.md)
   + [Campaign + database esterno](connect/fda.md)
   + Campaign + CRM {#ac-crm}
      + [Introduzione ai connettori CRM](connect/crm.md)
      + [Utilizzare Campaign e SFDC](connect/ac-sfdc.md)
      + [Utilizzare Campaign e Microsoft Dynamics](connect/ac-ms-dyn.md)
      + [Sincronizzare i dati](connect/crm-data-sync.md)
+ Amministrazione {#admin}
   + [Autorizzazioni](start/permissions.md)
   + [Pannello di controllo](config/self-service.md)
+ Architettura e configurazione {#config}
   + Architettura {#architecture}
      + [Principi globali](architecture/general-architecture.md)
      + [Architettura](architecture/architecture.md)
      + Distribuzione di Snowflake FDA {#fda}
         + [Cos’è Snowflake FDA?](architecture/fda-deployment.md)
      + Distribuzione aziendale (FFDA) {#ffda}
         + [Cos’è Campaign FFDA?](architecture/enterprise-deployment.md)
         + Caratteristiche {#ffda-characteristics}
            + [Gestione delle chiavi e unicità](architecture/keys.md)
            + [Nuove API](architecture/new-apis.md)
            + [Meccanismo di staging API](architecture/staging.md)
            + [Meccanismo di replica](architecture/replication.md)
   + Implementazione {#implement}
      + [Passaggi di implementazione](start/implement.md)
      + [Personalizzare l’istanza](dev/customize.md)
      + [Best practice per i modelli di dati](dev/datamodel-best-practices.md)
   + Configurazione {#configuration}
      + [Impostazioni e-mail](config/email-settings.md)
      + [Impostazioni dei messaggi transazionali](config/transactional-msg-settings.md)
      + [Integrare gli SDK di Campaign con la tua app](config/push-config.md)
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
+ [Pannello di controllo](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it)
+ [Guida all’automazione di Campaign](https://experienceleague.adobe.com/docs/campaign/automation/home.html?lang=it)
