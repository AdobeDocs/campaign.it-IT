---
title: Panoramica sul monitoraggio di Campaign
description: Scopri come monitorare consegne, flussi di lavoro e la tua istanza di Campaign
feature: Monitoring
role: User
level: Beginner
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 2%

---

# Panoramica sul monitoraggio di Campaign {#monitor-campaign}

Adobe Campaign offre un set completo di funzionalità per monitorare i processi, le consegne e l’ambiente in modo da garantire prestazioni ottimali e risolvere proattivamente i problemi.

>[!NOTE]
>
>In qualità di amministratore di Campaign, puoi anche utilizzare [Pannello di controllo Campaign Campaign](#control-panel) per monitorare le istanze, gestire le prestazioni e configurare le impostazioni con funzionalità self-service.

## Monitorare le consegne {#monitor-deliveries}

Il monitoraggio delle consegne dopo l’invio è un passaggio chiave per garantire l’efficienza delle campagne di marketing e l’effettivo raggiungimento dei clienti. Dopo aver inviato una consegna, puoi monitorarne lo stato e tracciare le metriche chiave nel dashboard di consegna. La dashboard consente di accedere ai registri di consegna, ai registri di esclusione, ai registri di tracciamento e ad altre funzionalità di monitoraggio per analizzare le prestazioni di consegna su tutti i canali.

**Consegne e-mail** - Monitora lo stato della consegna e-mail, tieni traccia delle metriche chiave e accedi ai registri dettagliati. Ulteriori informazioni su [monitoraggio delle consegne nell&#39;interfaccia utente di Campaign](../send/delivery-dashboard.md), [stati di consegna](../send/delivery-statuses.md) e [monitoraggio della consegna e-mail](../send/send.md#email-monitoring).

**Consegne SMS** - Tieni traccia dello stato di consegna SMS e monitora le metriche chiave nel dashboard di consegna SMS. Ulteriori informazioni sul monitoraggio di [SMS](../send/sms/sms-monitor.md).

**Notifiche push** - Monitora le consegne delle notifiche push per garantire che raggiungano gli utenti dell&#39;app mobile in modo efficace. Ulteriori informazioni sul [monitoraggio delle notifiche push](../send/push.md#push-test).

**Messaggi transazionali** - Per i messaggi attivati dagli eventi, controlla lo stato di elaborazione degli eventi, l&#39;esecuzione dei messaggi e lo stato di consegna. Ulteriori informazioni sul [monitoraggio dei messaggi transazionali](../send/delivery-execution.md#monitor-messages).

**Errori di recapito** - Per mantenere un database pulito e garantire tassi di recapito validi è fondamentale comprendere il motivo per cui una consegna non è riuscita. Gli errori di consegna sono classificati in mancati recapiti permanenti, mancati recapiti non permanenti e messaggi ignorati. Ulteriori informazioni su [errori di consegna e quarantena](../send/delivery-failures.md).

## Monitorare il recapito messaggi {#monitor-deliverability}

Il monitoraggio del recapito messaggi ti aiuta a garantire che i messaggi raggiungano le caselle in entrata dei destinatari ed eviti i filtri anti-spam. Adobe Campaign fornisce diversi strumenti incorporati per monitorare e migliorare il recapito messaggi, tra cui rapporti di consegna, rendering della casella in entrata, test SpamAssassin e statistiche di broadcast. Per mantenere tassi di consegna ottimali, è fondamentale seguire le best practice per la consegna dei messaggi, ad esempio mantenere un elenco e-mail pulito, monitorare la reputazione del mittente e autenticare i domini di invio.

Ulteriori informazioni sugli [strumenti di monitoraggio del recapito messaggi](../send/monitoring-deliverability.md) e sulle [best practice per il recapito messaggi](../send/about-deliverability.md).

## Monitorare i flussi di lavoro {#monitor-workflows}

I flussi di lavoro sono essenziali per automatizzare le campagne di marketing e l’elaborazione dei dati. Il monitoraggio dell’esecuzione dei flussi di lavoro consente di:

* Completare i flussi di lavoro
* Identificare e risolvere gli errori
* Ottimizzare le prestazioni del flusso di lavoro

### Funzionalità di monitoraggio del flusso di lavoro {#workflow-monitoring}

**Monitora i seguenti elementi del flusso di lavoro:**

**Stato esecuzione flusso di lavoro** - Monitora se i flussi di lavoro sono in esecuzione, in pausa, non riusciti o completati. [Ulteriori informazioni sull&#39;esecuzione del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

**Registri di esecuzione attività** - Accedi ai registri dettagliati per ogni attività del flusso di lavoro per risolvere i problemi e ottimizzare le prestazioni.

**Workflow heatmap** - Visualizza i modelli di esecuzione del flusso di lavoro, identifica i colli di bottiglia e monitora i flussi di lavoro simultanei. La Workflow HeatMap è disponibile per gli amministratori di Campaign. [Ulteriori informazioni sulla mappa di calore del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/heatmap.html?lang=it){target="_blank"}

**Cronologia flusso di lavoro** - Monitora tutte le esecuzioni e le modifiche del flusso di lavoro nel tempo per comprenderne il comportamento e le prestazioni.

## Monitorare l’istanza {#monitor-instance}

Il monitoraggio delle istanze consente di garantire lo stato e le prestazioni dell’ambiente Adobe Campaign.

### Audit trail {#audit-trail}

L’interfaccia self-service di Audit trail consente di monitorare le modifiche apportate all’interno dell’istanza Adobe Campaign. Audit trail acquisisce in tempo reale un elenco completo delle azioni e degli eventi che si verificano all’interno dell’istanza.

**Utilizza Audit trail per:**

* **Rileva modifiche componenti**: controlla cosa è successo ai tuoi flussi di lavoro, schemi, opzioni e altri componenti
* **Identificare chi ha apportato modifiche**: vedere chi ha aggiornato per ultimo un elemento specifico e quando
* **Comprendere le azioni dell&#39;utente**: verificare le operazioni eseguite dagli utenti nell&#39;istanza per la risoluzione dei problemi o il controllo
* **Mantieni conformità**: tieni traccia di tutte le modifiche alla configurazione per motivi di conformità e sicurezza

L’Audit trail è accessibile tramite la console client di Campaign e fornisce informazioni dettagliate sulle azioni eseguite dagli utenti.

Ulteriori informazioni su [Audit trail](../reporting/audit-trail.md)

### Monitoraggio delle prestazioni {#performance-monitoring}

Campaign v8 fornisce diverse funzionalità di monitoraggio per monitorare le prestazioni dell’istanza e garantire il funzionamento ottimale:

**Monitoraggio del database** - Monitora l&#39;utilizzo e la capacità del database tramite il Pannello di controllo Campaign per garantire prestazioni e gestione dello storage ottimali. [Ulteriori informazioni sul monitoraggio del database](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html){target="_blank"}

**Monitoraggio profili attivi** - Monitora l&#39;utilizzo dei profili attivi in base ai limiti contrattuali, per mantenere la conformità e ottimizzare l&#39;allocazione delle risorse. [Ulteriori informazioni sui profili attivi](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}

**Monitoraggio del flusso di lavoro** - Monitora lo stato di esecuzione del flusso di lavoro per identificare i flussi di lavoro con tempi di esecuzione lunghi e garantire il corretto funzionamento di tutti i flussi di lavoro tecnici. [Ulteriori informazioni sui flussi di lavoro tecnici](#technical-workflows)

**Velocità effettiva e latenza di consegna** - Monitoraggio della velocità effettiva di consegna (messaggi inviati all&#39;ora) e della latenza per le comunicazioni transazionali tramite il Pannello di controllo Campaign. [Ulteriori informazioni sul monitoraggio della velocità effettiva](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html){target="_blank"}

>[!NOTE]
>
>Per Campaign v8 Managed Cloud Services, l’infrastruttura del server (CPU, memoria, disco) è monitorata e gestita da Adobe.

### Flussi di lavoro tecnici {#technical-workflows}

I flussi di lavoro tecnici sono processi essenziali che vengono eseguiti in background per mantenere l’istanza Campaign.

**Monitora flussi di lavoro tecnici:**

* In esecuzione secondo programma
* Completamento completato senza errori
* Elaborazione corretta dei dati

**Flussi di lavoro tecnici chiave da monitorare:**

| Flusso di lavoro | Scopo |
|----------|---------|
| **Tracking** | Elabora il tracciamento dei dati dalle consegne e-mail |
| **Pulizia** | Rimuove i vecchi dati e registri per mantenere le prestazioni del database |
| **Aggiornamento del recapito messaggi** | Aggiorna le regole di recapito messaggi e i modelli di filtro anti-spam |
| **Pulizia database** | Elimina i vecchi registri di consegna e tracciamento |

Ulteriori informazioni sui [flussi di lavoro tecnici](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}

### Pannello di controllo Campaign {#control-panel}

Campaign Pannelli di controllo Campaign offre agli amministratori funzionalità self-service per monitorare e gestire le istanze di Campaign.

| Tipo di monitoraggio | Funzionalità |
|-----------------|--------------|
| **Prestazioni** | Monitorare l’utilizzo del profilo attivo, monitorare l’utilizzo e la capacità del database, visualizzare lo stato di esecuzione del flusso di lavoro, monitorare la velocità effettiva di consegna e la latenza |
| **Infrastruttura** | Monitorare la capacità di archiviazione SFTP, tenere traccia della configurazione dei sottodomini, monitorare la scadenza dei certificati SSL, gestire l’inserimento di IP nell’elenco Consentiti |
| **Istanza** | Visualizzare la versione di build e i pacchetti installati, monitorare la configurazione del sistema, gestire i domini esterni autorizzati |

Ulteriori informazioni sul monitoraggio delle prestazioni di [Pannello di controllo Campaign](../config/self-service.md) e [Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=it){target="_blank"}

>[!NOTE]
>
>Per Campaign v8 Managed Cloud Services, Adobe monitora e gestisce l’infrastruttura del server, il sistema operativo e il livello di applicazione. Puoi utilizzare le funzionalità di monitoraggio descritte in questa pagina e in questo Pannello di controllo Campaign per monitorare le prestazioni, i flussi di lavoro e le consegne dell’istanza.

## Tracciamento e reporting {#tracking-reporting}

### Tracciamento dei messaggi {#message-tracking}

Tieni traccia del comportamento dei destinatari e misura l’efficacia delle campagne:

* **Aperture**: tieni traccia di quando i destinatari aprono le e-mail
* **Clic**: controlla quali collegamenti fanno clic i destinatari
* **Annullamenti iscrizione**: tieni traccia delle richieste di rinuncia
* **Visualizzazioni pagina mirror**: verifica il numero di destinatari che visualizzano il messaggio e-mail in un browser

Ulteriori informazioni sul [tracciamento dei messaggi](../send/tracking.md)

### Rapporti sulle consegne {#delivery-reports}

Adobe Campaign fornisce un set completo di rapporti per analizzare le prestazioni di consegna:

* **Riepilogo consegne**: panoramica di invii, consegne ed errori
* **Indicatori di tracciamento**: aperture, clic e percentuali di click-through
* **URL e flussi di clic**: collegamenti più popolari nelle consegne
* **Hot click**: rappresentazione visiva di dove i destinatari hanno fatto clic nell&#39;e-mail

Ulteriori informazioni sui [report di consegna](../reporting/delivery-reports.md)

### Rapporti globali {#global-reports}

Accedi ai rapporti globali per analizzare le prestazioni in tutte le campagne e le consegne:

* **Velocità effettiva di consegna**: messaggi inviati nel tempo
* **Messaggi non recapitati e non recapitati**: analisi delle consegne non riuscite
* **Attività utente**: apre, fa clic e annulla l&#39;iscrizione in tutte le campagne

Ulteriori informazioni sui [report globali](../reporting/global-reports.md)

## Argomenti correlati {#related-topics}

* [Best practice per la consegna](delivery-best-practices.md)
* [Gestione della quarantena](../send/quarantines.md)
* [Configurare e inviare consegne](../send/configure-and-send.md)
* [Introduzione al reporting](../reporting/gs-reporting.md)

