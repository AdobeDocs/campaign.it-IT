---
title: Panoramica sul monitoraggio di Campaign
description: Scopri come monitorare consegne, flussi di lavoro e la tua istanza di Campaign
feature: Monitoring
role: User
level: Beginner
exl-id: 2ad585f2-19bc-4391-8a19-9e892dbe01a3
TQID: https://experienceleague.adobe.com/PjU1EFX5x4iB3yRsShGBWoR0k1D2-EI90-ss0FTcexE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: e8438b85eec144e83b2660f9d66444c1a01863ab
workflow-type: tm+mt
source-wordcount: 2101
ht-degree: 2%

---

# Panoramica sul monitoraggio di Campaign {#monitor-campaign}

Adobe Campaign offre visibilità a tutti i livelli, dalla consegna di un singolo messaggio, al motivo dell’errore di un flusso di lavoro, alla capacità del database rimasta nell’istanza. Questa pagina mappa tutte le funzionalità di monitoraggio per consentirti di sapere dove trovare qualcosa che richiede attenzione. In qualità di amministratore di Campaign, puoi anche utilizzare [Pannello di controllo Campaign Campaign](#control-panel) per monitorare le istanze, gestire le prestazioni e configurare le impostazioni con funzionalità self-service.

>[!TIP]
>
>**Non sei sicuro di dove iniziare?**
>
>- Esperto di marketing che controlla una campagna → [Monitora le consegne](#monitor-deliveries)
>- Risoluzione dei problemi relativi a un flusso di lavoro → [Monitorare i flussi di lavoro](#monitor-workflows)
>- L&#39;amministratore sta controllando l&#39;integrità dell&#39;istanza → [Monitorare l&#39;istanza](#monitor-instance)

## Monitorare le consegne {#monitor-deliveries}

Il monitoraggio delle consegne dopo l’invio è un passaggio chiave per garantire l’efficienza delle campagne di marketing e la possibilità di raggiungere i clienti. Dopo aver inviato una consegna, puoi tracciarne l’avanzamento e diagnosticare i problemi dal dashboard di consegna. La dashboard ti consente di accedere a registri di consegna, registri di esclusione, registri di tracciamento e altri dati per ogni canale utilizzato.

>[!NOTE]
>
>**Ti avvicini ora a Campaign?** Il dashboard di consegna è la schermata principale della tua giornata. Apri una consegna inviata, fai clic sulla scheda **Registri** per vedere quali destinatari hanno ricevuto il messaggio, quali sono stati esclusi e perché, e chi ha fatto clic o aperto.

**Consegne e-mail**: monitora lo stato di consegna delle e-mail, tieni traccia delle metriche chiave e accedi ai registri dettagliati. Ulteriori informazioni su [monitoraggio delle consegne nell&#39;interfaccia utente di Campaign](../send/delivery-dashboard.md), [stati di consegna](../send/delivery-statuses.md) e [monitoraggio della consegna e-mail](../send/send.md#email-monitoring).

**Consegne SMS**: tieni traccia dello stato di consegna degli SMS e monitora le metriche chiave nel dashboard di consegna degli SMS. Ulteriori informazioni sul monitoraggio di [SMS](../send/sms/sms-monitor.md).

**Notifiche push**: monitora le consegne delle notifiche push per garantire che raggiungano gli utenti dell&#39;app mobile in modo efficace. Ulteriori informazioni sul [monitoraggio delle notifiche push](../send/push.md#push-test).

**Messaggi transazionali**: per i messaggi attivati dagli eventi, monitorare lo stato di elaborazione degli eventi, la profondità della coda e i risultati dell&#39;esecuzione. Ulteriori informazioni sul [monitoraggio dei messaggi transazionali](../send/delivery-execution.md#monitor-messages).

**Errori di recapito**: per mantenere un database pulito e garantire tassi di recapito validi è fondamentale comprendere il motivo per cui una consegna non è riuscita. Gli errori di consegna sono classificati in tre tipi: comprendere la differenza ti aiuta a decidere quale azione intraprendere:

| Tipo di errore | Che cosa significa | Funzionamento di Campaign |
| --- | --- | --- |
| **Mancato recapito permanente** | Indirizzo non valido in modo permanente (inesistente, dominio sconosciuto) | Il contatto viene messo in quarantena automaticamente; non verrà impostato come destinazione nelle consegne future |
| **Mancato recapito non permanente** | Un problema temporaneo (cassetta postale completa, server temporaneamente non disponibile) | Nuovi tentativi di Campaign automatici per un periodo configurato |
| **Ignorato** | L’indirizzo era già stato messo in quarantena o in un elenco Bloccati di prima dell’invio | Nessun tentativo effettuato; conteggiato separatamente dai mancati recapiti |

Ulteriori informazioni su [errori di consegna e quarantena](../send/delivery-failures.md).

## Monitorare il recapito messaggi {#monitor-deliverability}

Il recapito messaggi misura con quale successo i messaggi raggiungono le caselle in entrata dei destinatari, anziché essere filtrati per spam o rifiutati. Adobe Campaign fornisce diversi strumenti incorporati per comprendere e migliorare le percentuali di posizionamento nella casella in entrata.

>[!NOTE]
>
>Un messaggio conteggiato come &quot;recapitato&quot; significa che è stato accettato dal server ricevente e non garantisce il posizionamento della casella in entrata. Il monitoraggio del recapito messaggi indica se l’autenticazione del dominio di invio, la reputazione IP e il contenuto delle e-mail soddisfano gli standard del provider della casella in entrata.

Adobe Campaign fornisce i seguenti strumenti integrati per il recapito dei messaggi:

- **Rapporti di consegna** — Rapporti incorporati che mostrano il volume di invio, le percentuali di mancato recapito e gli annullamenti dell&#39;abbonamento nel tempo.
- **Rendering della casella in entrata** - Anteprima della visualizzazione del messaggio e-mail tra i client principali (Gmail, Outlook, Apple Mail) prima o dopo l&#39;invio.
- **Test SpamAssassin**: assegna un punteggio al contenuto delle e-mail in base alle regole comuni del filtro anti-spam per rilevare eventuali problemi prima della consegna.
- **Statistiche di trasmissione**: aggrega i dati di consegna tra i volumi di invio e la reputazione IP.

Seguire le best practice per la consegna dei messaggi, ad esempio mantenere un elenco di e-mail pulito, monitorare la reputazione del mittente e autenticare i domini di invio, è fondamentale per mantenere tassi di consegna ottimali.

Ulteriori informazioni sugli [strumenti di monitoraggio del recapito messaggi](../send/monitoring-deliverability.md) e sulle [best practice per il recapito messaggi](../send/about-deliverability.md).

## Monitorare i flussi di lavoro {#monitor-workflows}

I flussi di lavoro sono il motore delle automazioni di marketing e dell’elaborazione dei dati. Il loro monitoraggio garantisce che le attività pianificate vengano completate come previsto e che gli errori vengano rilevati prima che influiscano sulle consegne o sulla qualità dei dati.

>[!TIP]
>
>Se un flusso di lavoro mostra uno stato **Non riuscito**, aprilo, fai clic con il pulsante destro del mouse sull&#39;attività rossa e seleziona **Visualizza registri**. Il messaggio di errore identifica esattamente cosa è andato storto e su quale record.

### Funzionalità di monitoraggio del flusso di lavoro {#workflow-monitoring}

**Monitora i seguenti elementi del flusso di lavoro:**

**Stato esecuzione flusso di lavoro** - Controllare se i flussi di lavoro sono in esecuzione, in pausa, non riusciti o completati. Visualizza subito i flussi di lavoro bloccati o con tempi di esecuzione lunghi. [Ulteriori informazioni sull&#39;esecuzione del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

**Registri di esecuzione attività**. Eseguire l&#39;espansione nei registri per attività per capire cosa è successo in ogni passaggio. Ciò è utile per risolvere eventuali transizioni non riuscite o output di dati imprevisti.

**Workflow HeatMap**: panoramica visiva di tutti i flussi di lavoro in esecuzione simultaneamente nell&#39;istanza. Utilizzalo per identificare i periodi di carico di picco, i flussi di lavoro a pronti che consumano risorse sproporzionate e pianificare la pianificazione per evitare conflitti di esecuzione. Disponibile solo per gli amministratori di Campaign. [Ulteriori informazioni sulla mappa di calore del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/heatmap.html?lang=it){target="_blank"}

**Cronologia flusso di lavoro**: tieni traccia di tutte le esecuzioni e modifiche del flusso di lavoro nel tempo per comprenderne il comportamento e i modelli di prestazioni.

## Monitorare l’istanza {#monitor-instance}

Il monitoraggio delle istanze riguarda lo stato dell’ambiente Campaign: capacità del database, utilizzo del profilo, velocità effettiva e infrastruttura. Per Campaign v8 Managed Cloud Services, Adobe monitora e gestisce l’infrastruttura sottostante per tuo conto, ma puoi mantenere la piena visibilità tramite la console client e il Pannello di controllo Campaign. Ulteriori informazioni sul [monitoraggio gestito da Adobe](#adobe-cloud-monitoring).

### Audit trail {#audit-trail}

L’interfaccia self-service di Audit trail consente di monitorare ogni modifica significativa apportata all’interno dell’istanza Adobe Campaign. Audit trail acquisisce in tempo reale un elenco completo delle azioni e degli eventi che si verificano all’interno dell’istanza.

**Utilizza Audit trail per:**

- **Rileva modifiche componenti** — Controlla cosa è successo ai tuoi flussi di lavoro, schemi, opzioni e altri componenti
- **Identificare chi ha apportato una modifica** — Vedere quale utente ha modificato l&#39;ultima volta un elemento e a che ora
- **Risolvere i problemi di un comportamento imprevisto** — Trace back through user actions per individuare quando e come è stato introdotto un problema
- **Conformità e controlli di supporto** - Mantenere un record completo ed evidente di manomissione di tutte le modifiche alla configurazione

L’Audit trail è accessibile tramite la console client di Campaign e fornisce informazioni dettagliate sulle azioni eseguite dagli utenti.

Ulteriori informazioni su [Audit trail](../reporting/audit-trail.md)

### Monitoraggio delle prestazioni {#performance-monitoring}

Campaign v8 fornisce diverse funzionalità di monitoraggio per monitorare le prestazioni dell’istanza e garantire il funzionamento ottimale:

**Monitoraggio del database**: consente di monitorare l&#39;utilizzo e la capacità del database tramite il Pannello di controllo Campaign per garantire prestazioni ottimali e la gestione dello storage. [Ulteriori informazioni sul monitoraggio del database](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html){target="_blank"}

**Monitoraggio dei profili attivi**: tieni traccia dell&#39;utilizzo dei profili attivi rispetto ai limiti contrattuali, per mantenere la conformità e ottimizzare l&#39;allocazione delle risorse. [Ulteriori informazioni sui profili attivi](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}

**Monitoraggio del flusso di lavoro**: controlla lo stato di esecuzione del flusso di lavoro per identificare i flussi di lavoro con tempi di esecuzione lunghi e garantire il corretto funzionamento di tutti i flussi di lavoro tecnici. [Ulteriori informazioni sui flussi di lavoro tecnici](#technical-workflows)

**Velocità effettiva e latenza di consegna**: tieni traccia della velocità effettiva di consegna (messaggi inviati all&#39;ora) e della latenza per le comunicazioni transazionali tramite il Pannello di controllo Campaign. [Ulteriori informazioni sul monitoraggio della velocità effettiva](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html){target="_blank"}

>[!NOTE]
>
>Per Campaign v8 Managed Cloud Services, l’infrastruttura del server (CPU, memoria, disco) è monitorata e gestita da Adobe. Le funzionalità di monitoraggio descritte in questa pagina e in Pannello di controllo Campaign sono complementari e forniscono visibilità ai dati e alla configurazione senza richiedere l&#39;accesso all&#39;infrastruttura. Alcune azioni eseguite da Adobe vengono visualizzate nei registri di Campaign sotto l&#39;utente **campaign-loginmonitor**. Ulteriori informazioni sul [monitoraggio gestito da Adobe](#adobe-cloud-monitoring).

### Monitoraggio gestito da Adobe {#adobe-cloud-monitoring}

I servizi cloud di Adobe Campaign forniscono supporto mission-critical per le esigenze di consegna della customer experience complesse tramite un’infrastruttura cloud flessibile. Questo consente alle organizzazioni di avviare, monitorare e ottimizzare le esperienze dei clienti senza dover gestire o gestire direttamente l’infrastruttura di Campaign.

Adobe monitora gli ambienti Campaign Cloud Services 24 ore su 24, 7 giorni su 7 per rilevare i problemi tecnici e ridurre al minimo le interruzioni. Quando viene rilevato un problema, il sistema utilizza meccanismi di riavvio automatico e di avvio automatico per tentare di porvi rimedio. Se il sistema non si risolve autonomamente, il team ingegneristico Adobe On-Call interviene in base a manuali di avvisi predefiniti.

>[!TIP]
>
>È possibile abbonarsi agli avvisi delle istanze in tempo reale tramite [Pannello di controllo Campaign Campaign](#control-panel) e ricevere i passaggi di correzione consigliati per i problemi rilevati, ad esempio i certificati SSL prossimi alla scadenza.

**Livelli di monitoraggio**

Adobe monitora l’ambiente su tre livelli. I problemi di livello 1 hanno il maggiore impatto e ricevono la risposta più rapida:

| Livello | Gruppo | Esperienze possibili |
| --- | --- | --- |
| **Livello 1: infrastruttura** | Esaurimento dello spazio del database | Problemi di prestazioni, inclusa l’impossibilità di accedere, eseguire consegne batch o eseguire query |
| **Livello 1: infrastruttura** | Disponibilità del database | Gli utenti e i servizi potrebbero non essere in grado di utilizzare il sistema |
| **Livello 1: infrastruttura** | Sovraccarico del database (bilanciamento burst) | Problemi di prestazioni, inclusa l’impossibilità di accedere, eseguire consegne batch o eseguire query |
| **Livello 1: infrastruttura** | Sequenza di database e esaurimento ID transazione | Impossibile creare nuovi flussi di lavoro, consegne o inviare e-mail batch |
| **Livello 1: infrastruttura** | Archiviazione SFTP | Impossibile aggiornare o recuperare dati sui server SFTP |
| **Livello 2: piattaforma e Web** | Accesso | Gli utenti potrebbero non essere in grado di accedere; le attività e i flussi di lavoro pianificati potrebbero non essere eseguiti |
| **Livello 2: piattaforma e Web** | Blocco API | Gli utenti o i servizi potrebbero non essere in grado di autenticare o eseguire operazioni |
| **Livello 2: piattaforma e Web** | Web | Impossibile creare nuove connessioni a Campaign |
| **Livello 2: piattaforma e Web** | Rete del centro dati | Problemi di prestazioni o totale indisponibilità per gli utenti del centro dati |
| **Livello 3: software** | Tracciamento della consegna | L’elaborazione dei registri di tracciamento non è disponibile |
| **Livello 3: software** | inMail | Nessun feedback su errori e mancati recapiti delle consegne e-mail |
| **Livello 3: software** | Stato del Centro messaggi | Impossibile inviare consegne transazionali |
| **Livello 3: software** | MTA | Impossibile inviare consegne e-mail pianificate e ad hoc |
| **Livello 3: software** | Stato del server del flusso di lavoro | Impossibile eseguire i flussi di lavoro |
| **Livello 3: software** | Disponibilità API web | Impossibile elaborare richieste HTTP o eseguire chiamate API |
| **Livello 3: software** | Interazioni in entrata | Impossibile elaborare le interazioni in entrata |

>[!NOTE]
>
>Adobe Campaign Cloud Services è basato su una strategia multi-cloud con implementazioni su AWS e Azure. Le funzionalità di monitoraggio differiscono tra le diverse implementazioni di AWS, Azure e altri centri dati. La tabella precedente si applica ai clienti di Campaign Cloud Services ospitati su AWS, se non diversamente indicato. Al momento Adobe Campaign non espone ai clienti tutti i dati di monitoraggio utilizzati dai tecnici On-Call.

### Flussi di lavoro tecnici {#technical-workflows}

I flussi di lavoro tecnici vengono eseguiti in background senza interruzioni per mantenere l’istanza Campaign. Non vengono create dagli utenti, vengono fornite con il prodotto. Se un flusso di lavoro tecnico non riesce, può influire direttamente sulle consegne e sulla qualità dei dati.

Verifica che ogni flusso di lavoro tecnico sia in esecuzione secondo la pianificazione, che venga completato senza errori e che i dati vengano elaborati correttamente.

| Flusso di lavoro | Scopo | Se non riesce |
| --- | --- | --- |
| **Tracking** | Elabora il tracciamento dei dati dalle consegne e-mail | Fai clic e apri le metriche; interrompi l’aggiornamento nei rapporti |
| **Pulizia** | Rimuove i vecchi dati e registri per mantenere le prestazioni del database | Crescita del database non controllata, con riduzione delle prestazioni di query e consegna |
| **Aggiornamento del recapito messaggi** | Aggiorna le regole di recapito messaggi e i modelli di filtro anti-spam | Le regole diventano obsolete; la precisione di filtraggio potrebbe peggiorare |
| **Pulizia database** | Elimina i vecchi registri di consegna e tracciamento | L’accumulo di registri rallenta le query e i rapporti nel tempo |

Ulteriori informazioni sui [flussi di lavoro tecnici](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}

### Pannello di controllo Campaign {#control-panel}

Campaign Pannelli di controllo Campaign offre agli amministratori funzionalità self-service per monitorare e gestire le istanze di Campaign, senza richiedere un ticket di supporto.

| Tipo di monitoraggio | Funzionalità |
| --- | --- |
| **Prestazioni** | Utilizzo del profilo attivo rispetto al limite del contratto, utilizzo e capacità del database, stato di esecuzione del flusso di lavoro, velocità effettiva di consegna e latenza |
| **Infrastruttura** | Capacità di archiviazione SFTP, configurazione dei sottodomini, avvisi di scadenza dei certificati SSL, inserimento di IP nell’elenco Consentiti |
| **Istanza** | Versione della build e pacchetti installati, panoramica della configurazione del sistema, domini esterni autorizzati |

Ulteriori informazioni sul monitoraggio delle prestazioni di [Pannello di controllo Campaign](../config/self-service.md) e [Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=it){target="_blank"}

>[!NOTE]
>
>Per Campaign v8 Managed Cloud Services, Adobe monitora e gestisce l’infrastruttura del server, il sistema operativo e il livello di applicazione. Le funzionalità di monitoraggio descritte in questa pagina e nel Pannello di controllo Campaign sono complementari e forniscono visibilità ai dati e alla configurazione senza richiedere l&#39;accesso all&#39;infrastruttura.

## Tracciamento e reporting {#tracking-reporting}

### Tracciamento dei messaggi {#message-tracking}

Il tracciamento registra il modo in cui i destinatari interagiscono con i messaggi dopo la consegna. Tutti gli eventi tracciati vengono memorizzati nei registri di tracciamento e visualizzati nei rapporti di consegna.

- **Aperture** — Registrato al caricamento del pixel di tracciamento (solo e-mail)
- **Clic** — Registrati per ogni collegamento tracciato nel messaggio
- **Annullamenti iscrizione** — richieste di rinuncia tramite il collegamento di annullamento iscrizione
- **Visualizzazioni pagina mirror**: destinatari che hanno visualizzato l&#39;e-mail in un browser

Ulteriori informazioni sul [tracciamento dei messaggi](../send/tracking.md)

### Rapporti di consegna {#delivery-reports}

Adobe Campaign fornisce un set completo di rapporti per analizzare le prestazioni di consegna:

- **Riepilogo consegne**: panoramica di invii, consegne ed errori per una singola consegna
- **Indicatori di tracciamento** — aperture, clic e tassi di click-through con tendenza nel tempo
- **URL e flussi di clic** — Classificazione dei collegamenti più selezionati, con conteggi e percentuali
- **Hot click** — Sovrapposizione visiva che mostra dove i destinatari hanno fatto clic all&#39;interno del corpo dell&#39;e-mail

Ulteriori informazioni sui [report di consegna](../reporting/delivery-reports.md)

### Rapporti globali {#global-reports}

Accedi ai rapporti globali per analizzare le prestazioni in tutte le campagne e le consegne:

- **Velocità effettiva di consegna** — Messaggi inviati all&#39;ora in tutte le consegne in un periodo di tempo
- **Messaggi non recapitati e mancati recapiti** — Raggruppamento delle consegne non riuscite per tipo e motivo di errore
- **Attività utente** - Aperture, clic e annullamenti di abbonamenti aggregati in tutte le campagne

Ulteriori informazioni sui [report globali](../reporting/global-reports.md)

## Argomenti correlati {#related-topics}

- [Best practice per la consegna](delivery-best-practices.md)
- [Gestione della quarantena](../send/quarantines.md)
- [Configurare e inviare consegne](../send/configure-and-send.md)
- [Introduzione al reporting](../reporting/gs-reporting.md)
