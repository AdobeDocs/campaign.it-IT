---
solution: Campaign
product: Adobe Campaign
title: Introduzione all’automazione delle campagne
description: Introduzione all’automazione delle campagne
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
translation-type: tm+mt
source-git-commit: 2ea953145b645d376d5ea88b89350b45f024ea7d
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 0%

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

Ulteriori informazioni sui flussi di lavoro nelle seguenti sezioni:

* [Guida introduttiva ai flussi di lavoro](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)
* Attività del flusso di lavoro
   * [Attività](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html) di targeting: query, elenco di lettura, arricchimento, unione e altro ancora
   * [Attività](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html) di controllo del flusso: scheduler, fork, alert, segnale esterno e altro ancora
   * [Attività](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html) azione: consegne cross-channel, codice JavaScript, attività CRM, aggiornamento aggregato e altro ancora
   * [Attività](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html) evento: trasferimento file, download web e altro ancora
* [Scopri i casi d’uso end-to-end](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/about-workflow-use-cases.html)
* [Creare un pubblico in un flusso di lavoro di una campagna di marketing](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)
* [Best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html)
* [Flussi di lavoro tecnici incorporati](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)
* [Monitorare l’esecuzione dei flussi di lavoro](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html)

## Configurare campagne ricorrenti

Progetta ricorrenti e crea una nuova istanza di consegna ogni volta che viene eseguita. Ad esempio, se il flusso di lavoro è progettato per essere eseguito una volta alla settimana, si otterranno 52 consegne dopo un anno. Ciò significa anche che i registri saranno separati da ogni istanza di consegna.

:arrow_Upper_right: Scopri come creare una campagna ricorrente nella [documentazione di Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns).

## Configurare il ciclo di convalida end-to-end

Imposta il processo di approvazione per ogni fase delle consegne e assicurati il monitoraggio e il controllo completi dei vari processi delle campagne di marketing: targeting, contenuto, budget, estrazione e invio di una bozza.

Le notifiche vengono inviate agli operatori Adobe Campaign impostati come revisori per informarli di una richiesta di approvazione.

:arrow_Upper_right: Scopri come impostare e gestire il processo di approvazione nella [documentazione Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html).


## Inviare avvisi

In qualità di operatore Campaign, puoi ricevere avvisi in caso di errore.

Puoi creare un flusso di lavoro che ti consenta di monitorare lo stato di un set di flussi di lavoro e inviare messaggi ricorrenti alle autorità di vigilanza.

:arrow_Upper_right: Scopri come creare un flusso di lavoro per monitorare lo stato di altri flussi di lavoro nella [documentazione di Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html?lang=en#step-1--creating-the-monitoring-workflow).

È inoltre possibile ricevere un avviso quando si verifica un errore

## Invia rapporti automatici

:arrow_Upper_right: Scopri come inviare automaticamente un rapporto a un elenco di operatori [documentazione Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html?lang=en#step-1--creating-the-recipient-list).


## Sfruttare gli eventi trigger

Utilizza la messaggistica transazionale di Campaign per automatizzare i messaggi generati dagli eventi attivati dai sistemi di informazioni. Questi messaggi transazionali possono essere fatture, conferma dell&#39;ordine, conferma della spedizione, modifica della password, notifica di indisponibilità del prodotto, dichiarazione dell&#39;account o creazione dell&#39;account del sito web, ad esempio. Questi messaggi possono essere inviati singolarmente o in batch tramite e-mail, SMS o notifiche push).

:arrow_Upper_right: Ulteriori informazioni sulle funzionalità di messaggistica transazionale nella [documentazione di Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=en#transactional-messaging).


Collega Adobe Campaign e Adobe Analytics per recuperare le azioni degli utenti e inviare messaggi personalizzati in tempo reale.

:arrow_Upper_right: Scopri come integrare Campaign con i trigger di Analytics nella [documentazione di Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en#integrating-with-adobe-experience-cloud).

:lampadina: Scopri come integrare Campaign con altre soluzioni in [questa sezione](../start/connect.md)
