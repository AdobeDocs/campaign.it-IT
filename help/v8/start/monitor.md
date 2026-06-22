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
source-git-commit: 6cf587ecc9cc1e4cf9b3de0d2067e0c4562afe01
workflow-type: tm+mt
source-wordcount: 2206
ht-degree: 1%

---

# Panoramica sul monitoraggio di Campaign {#monitor-campaign}

Adobe Campaign offre visibilità a tutti i livelli, dalla consegna di un singolo messaggio, al motivo dell’errore di un flusso di lavoro, alla capacità del database rimasta nell’istanza. Questa pagina mappa tutte le funzionalità di monitoraggio per consentirti di sapere dove trovare qualcosa che richiede attenzione.

>[!NOTE]
>
>In qualità di amministratore di Campaign, puoi anche utilizzare [Pannello di controllo Campaign Campaign](#control-panel) per monitorare le istanze, gestire le prestazioni e configurare le impostazioni con funzionalità self-service.

>[!TIP]
>
>**Non sei sicuro di dove iniziare?**
>
>- Esperto di marketing che controlla una campagna → [Monitora le consegne](#monitor-deliveries)
>- Risoluzione dei problemi relativi a un flusso di lavoro → [Monitorare i flussi di lavoro](#monitor-workflows)
>- L&#39;amministratore sta controllando l&#39;integrità dell&#39;istanza → [Monitorare l&#39;istanza](#monitor-instance)

## Monitorare le consegne {#monitor-deliveries}

Il monitoraggio delle consegne dopo l’invio è un passaggio chiave per garantire l’efficienza delle campagne di marketing e l’effettivo raggiungimento dei clienti. Dopo aver inviato una consegna, puoi monitorarne lo stato e tracciare le metriche chiave nel dashboard di consegna. La dashboard consente di accedere ai registri di consegna, ai registri di esclusione, ai registri di tracciamento e ad altre funzionalità di monitoraggio per analizzare le prestazioni di consegna su tutti i canali.

>[!NOTE]
>
>**Ti avvicini ora a Campaign?** Il dashboard di consegna è la schermata principale della tua giornata. Apri una consegna inviata, fai clic sulla scheda **Registri** per vedere quali destinatari hanno ricevuto il messaggio, quali sono stati esclusi e perché, e chi ha fatto clic o aperto.

**Consegne e-mail** - Monitora lo stato della consegna e-mail, tieni traccia delle metriche chiave e accedi ai registri dettagliati. Ulteriori informazioni su [monitoraggio delle consegne nell&#39;interfaccia utente di Campaign](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/monitor/delivery-dashboard), [stati di consegna](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/monitor/delivery-statuses) e [monitoraggio della consegna e-mail](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/emails/send#email-monitoring).

**Consegne SMS** - Tieni traccia dello stato di consegna SMS e monitora le metriche chiave nel dashboard di consegna SMS. Ulteriori informazioni sul monitoraggio di [SMS](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/sms/sms-monitor).

**Notifiche push** - Monitora le consegne delle notifiche push per garantire che raggiungano gli utenti dell&#39;app mobile in modo efficace. Ulteriori informazioni sul [monitoraggio delle notifiche push](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/push/push#push-test).

**Messaggi transazionali** - Per i messaggi attivati dagli eventi, controlla lo stato di elaborazione degli eventi, l&#39;esecuzione dei messaggi e lo stato di consegna. Ulteriori informazioni sul [monitoraggio dei messaggi transazionali](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/real-time/event/delivery-execution#monitor-messages).

**Errori di recapito** - Per mantenere un database pulito e garantire tassi di recapito validi è fondamentale comprendere il motivo per cui una consegna non è riuscita. Gli errori di consegna sono classificati in tre tipi: comprendere la differenza ti aiuta a decidere quale azione intraprendere:

| Tipo di errore | Che cosa significa | Funzionamento di Campaign |
| --- | --- | --- |
| **Mancato recapito permanente** | Indirizzo non valido in modo permanente (inesistente, dominio sconosciuto) | Il contatto viene messo in quarantena automaticamente; non verrà impostato come destinazione nelle consegne future |
| **Mancato recapito non permanente** | Un problema temporaneo (cassetta postale completa, server temporaneamente non disponibile) | Nuovi tentativi di Campaign automatici per un periodo configurato |
| **Ignorato** | L’indirizzo era già stato messo in quarantena o in un elenco Bloccati di prima dell’invio | Nessun tentativo effettuato; conteggiato separatamente dai mancati recapiti |

Ulteriori informazioni su [errori di consegna e quarantena](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/monitor/delivery-failures).

## Monitorare il recapito messaggi {#monitor-deliverability}

>[!NOTE]
>
>Un messaggio conteggiato come &quot;recapitato&quot; significa che è stato accettato dal server ricevente e non garantisce il posizionamento della casella in entrata. Il monitoraggio del recapito messaggi indica se l’autenticazione del dominio di invio, la reputazione IP e il contenuto delle e-mail soddisfano gli standard del provider della casella in entrata.

Il monitoraggio del recapito messaggi ti aiuta a garantire che i messaggi raggiungano le caselle in entrata dei destinatari ed eviti i filtri anti-spam. Adobe Campaign fornisce diversi strumenti incorporati per monitorare e migliorare il recapito messaggi, tra cui rapporti di consegna, rendering della casella in entrata, test SpamAssassin e statistiche di broadcast. Per mantenere tassi di consegna ottimali, è fondamentale seguire le best practice per la consegna dei messaggi, ad esempio mantenere un elenco e-mail pulito, monitorare la reputazione del mittente e autenticare i domini di invio.

Ulteriori informazioni sugli [strumenti di monitoraggio del recapito messaggi](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/deliverability-management/monitoring-deliverability) e sulle [best practice per il recapito messaggi](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/deliverability-management/about-deliverability).

## Monitorare i flussi di lavoro {#monitor-workflows}

I flussi di lavoro sono essenziali per automatizzare le campagne di marketing e l’elaborazione dei dati. Il monitoraggio dell’esecuzione dei flussi di lavoro consente di:

- Completare i flussi di lavoro
- Identificare e risolvere gli errori
- Ottimizzare le prestazioni del flusso di lavoro

>[!TIP]
>
>Se un flusso di lavoro mostra uno stato **Non riuscito**, aprilo, fai clic con il pulsante destro del mouse sull&#39;attività rossa e seleziona **Visualizza registri**. Il messaggio di errore identifica esattamente cosa è andato storto e su quale record.

### Funzionalità di monitoraggio del flusso di lavoro {#workflow-monitoring}

**Monitora i seguenti elementi del flusso di lavoro:**

**Stato esecuzione flusso di lavoro** - Monitora se i flussi di lavoro sono in esecuzione, in pausa, non riusciti o completati. [Ulteriori informazioni sull&#39;esecuzione del flusso di lavoro](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#_blank)

**Registri di esecuzione attività** - Accedi ai registri dettagliati per ogni attività del flusso di lavoro per risolvere i problemi e ottimizzare le prestazioni.

**Workflow HeatMap**: panoramica visiva di tutti i flussi di lavoro in esecuzione simultaneamente nell&#39;istanza. Utilizzalo per identificare i periodi di carico di picco, i flussi di lavoro a pronti che consumano risorse sproporzionate e pianificare la pianificazione per evitare conflitti di esecuzione. Disponibile solo per gli amministratori di Campaign. [Ulteriori informazioni sulla mappa di calore del flusso di lavoro](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/heatmap#_blank)

**Cronologia flusso di lavoro** - Monitora tutte le esecuzioni e le modifiche del flusso di lavoro nel tempo per comprenderne il comportamento e le prestazioni.

## Monitorare l’istanza {#monitor-instance}

Il monitoraggio delle istanze consente di garantire lo stato e le prestazioni dell’ambiente Adobe Campaign. Per Campaign v8 Managed Cloud Services, Adobe monitora e gestisce anche l’infrastruttura per tuo conto. Ulteriori informazioni sul [monitoraggio gestito da Adobe](#adobe-cloud-monitoring).

### Audit trail {#audit-trail}

L’interfaccia self-service di Audit trail consente di monitorare le modifiche apportate all’interno dell’istanza Adobe Campaign. Audit trail acquisisce in tempo reale un elenco completo delle azioni e degli eventi che si verificano all’interno dell’istanza.

**Utilizza Audit trail per:**

- **Rileva modifiche componenti**: controlla cosa è successo ai tuoi flussi di lavoro, schemi, opzioni e altri componenti
- **Identificare chi ha apportato modifiche**: vedere chi ha aggiornato per ultimo un elemento specifico e quando
- **Comprendere le azioni dell&#39;utente**: verificare le operazioni eseguite dagli utenti nell&#39;istanza per la risoluzione dei problemi o il controllo
- **Mantieni conformità**: tieni traccia di tutte le modifiche alla configurazione per motivi di conformità e sicurezza

L’Audit trail è accessibile tramite la console client di Campaign e fornisce informazioni dettagliate sulle azioni eseguite dagli utenti.

Ulteriori informazioni su [Audit trail](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/audit-trail)

### Monitoraggio delle prestazioni {#performance-monitoring}

Campaign v8 fornisce diverse funzionalità di monitoraggio per monitorare le prestazioni dell’istanza e garantire il funzionamento ottimale:

**Monitoraggio del database** - Monitora l&#39;utilizzo e la capacità del database tramite il Pannello di controllo Campaign per garantire prestazioni e gestione dello storage ottimali. [Ulteriori informazioni sul monitoraggio del database](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/database-monitoring/database-monitoring#_blank)

**Monitoraggio profili attivi** - Monitora l&#39;utilizzo dei profili attivi in base ai limiti contrattuali, per mantenere la conformità e ottimizzare l&#39;allocazione delle risorse. [Ulteriori informazioni sui profili attivi](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/active-profiles-monitoring#_blank)

**Monitoraggio del flusso di lavoro** - Monitora lo stato di esecuzione del flusso di lavoro per identificare i flussi di lavoro con tempi di esecuzione lunghi e garantire il corretto funzionamento di tutti i flussi di lavoro tecnici. [Ulteriori informazioni sui flussi di lavoro tecnici](#technical-workflows)

**Velocità effettiva e latenza di consegna** - Monitoraggio della velocità effettiva di consegna (messaggi inviati all&#39;ora) e della latenza per le comunicazioni transazionali tramite il Pannello di controllo Campaign. [Ulteriori informazioni sul monitoraggio della velocità effettiva](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/throughputs-latencies#_blank)

>[!NOTE]
>
>Per Campaign v8 Managed Cloud Services, l’infrastruttura del server (CPU, memoria, disco) è monitorata e gestita da Adobe. Ulteriori informazioni sul [monitoraggio gestito da Adobe](#adobe-cloud-monitoring).

### Monitoraggio gestito da Adobe {#adobe-cloud-monitoring}

I servizi cloud di Adobe Campaign forniscono supporto mission-critical per le esigenze di consegna della customer experience complesse tramite un’infrastruttura cloud flessibile. Questo consente alle organizzazioni di avviare, monitorare e ottimizzare le esperienze dei clienti senza dover gestire o gestire direttamente l’infrastruttura di Campaign.

Adobe monitora gli ambienti Campaign Cloud Services per gestire vari problemi e ridurre al minimo le interruzioni rilevando i problemi tecnici e fornendo feedback continuo sulle prestazioni e sui progetti in corso.

**Risposta di Adobe**

Adobe monitora tutte le apparecchiature di rete critiche sulla rete Campaign 24 ore su 24, 7 giorni su 7 e riceve notifiche dai sistemi di monitoraggio quando sono necessarie correzioni o escalation. Quando viene rilevato un problema, il sistema utilizza meccanismi di riavvio automatico e di avvio automatico per tentare di porvi rimedio. Se il sistema non si risolve autonomamente, il team tecnico di Adobe On-Call interviene per eseguire la risoluzione dei problemi in base a manuali di avvisi predefiniti.

>[!NOTE]
>
>Alcune azioni di monitoraggio eseguite da Adobe vengono visualizzate nei registri di Campaign sotto l&#39;utente **campaign-loginmonitor**.

Oltre al monitoraggio interno di Adobe, puoi accedere alle funzionalità di monitoraggio direttamente tramite la console client di Campaign o il [Pannello di controllo Campaign Campaign](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/permissions/self-service). Con il Pannello di controllo Campaign, puoi abbonarti agli avvisi in tempo reale sulle tue istanze e ricevere i passaggi correttivi consigliati per gli incidenti identificati (ad esempio, i certificati SSL in scadenza).

**Tassonomia di monitoraggio**

Adobe monitora l’ambiente su tre livelli:

| Livello | Gruppo | Potenziale impatto sull&#39;azienda |
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
>Adobe Campaign Cloud Services è basato su una strategia multi-cloud e offre implementazioni su AWS e Azure. A causa delle differenze tra i fornitori, le funzionalità di monitoraggio differiscono tra le implementazioni di AWS, Azure e altri centri dati. La tabella precedente si applica ai clienti di Campaign Cloud Services ospitati su AWS, se non diversamente indicato. Inoltre, al momento Adobe Campaign non espone ai clienti tutti i dati di monitoraggio utilizzati dai tecnici di On-Call.

### Flussi di lavoro tecnici {#technical-workflows}

I flussi di lavoro tecnici sono processi essenziali che vengono eseguiti in background per mantenere l’istanza Campaign.

**Monitora flussi di lavoro tecnici:**

- In esecuzione secondo programma
- Completamento completato senza errori
- Elaborazione corretta dei dati

**Flussi di lavoro tecnici chiave da monitorare:**

| Flusso di lavoro | Scopo | Se non riesce |
| --- | --- | --- |
| **Tracking** | Elabora il tracciamento dei dati dalle consegne e-mail | Fai clic e apri le metriche; interrompi l’aggiornamento nei rapporti |
| **Pulizia** | Rimuove i vecchi dati e registri per mantenere le prestazioni del database | Crescita del database non controllata, con riduzione delle prestazioni di query e consegna |
| **Aggiornamento del recapito messaggi** | Aggiorna le regole di recapito messaggi e i modelli di filtro anti-spam | Le regole diventano obsolete; la precisione di filtraggio potrebbe peggiorare |
| **Pulizia database** | Elimina i vecchi registri di consegna e tracciamento | L’accumulo di registri rallenta le query e i rapporti nel tempo |

Ulteriori informazioni sui [flussi di lavoro tecnici](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows#_blank)

### Pannello di controllo Campaign {#control-panel}

Campaign Pannelli di controllo Campaign offre agli amministratori funzionalità self-service per monitorare e gestire le istanze di Campaign.

| Tipo di monitoraggio | Funzionalità |
| --- | --- |
| **Prestazioni** | Monitorare l’utilizzo del profilo attivo, monitorare l’utilizzo e la capacità del database, visualizzare lo stato di esecuzione del flusso di lavoro, monitorare la velocità effettiva di consegna e la latenza |
| **Infrastruttura** | Monitorare la capacità di archiviazione SFTP, tenere traccia della configurazione dei sottodomini, monitorare la scadenza dei certificati SSL, gestire l’inserimento di IP nell’elenco Consentiti |
| **Istanza** | Visualizzare la versione di build e i pacchetti installati, monitorare la configurazione del sistema, gestire i domini esterni autorizzati |

Ulteriori informazioni sul monitoraggio delle prestazioni di [Pannello di controllo Campaign](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/permissions/self-service) e [Pannello di controllo Campaign](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/about-performance-monitoring#_blank)

>[!NOTE]
>
>Per Campaign v8 Managed Cloud Services, Adobe monitora e gestisce l’infrastruttura del server, il sistema operativo e il livello di applicazione. Ulteriori informazioni sul [monitoraggio gestito da Adobe](#adobe-cloud-monitoring). Puoi utilizzare le funzionalità di monitoraggio descritte in questa pagina e in questo Pannello di controllo Campaign per monitorare le prestazioni, i flussi di lavoro e le consegne dell’istanza.

## Tracciamento e reporting {#tracking-reporting}

### Tracciamento dei messaggi {#message-tracking}

Tieni traccia del comportamento dei destinatari e misura l’efficacia delle campagne:

- **Aperture**: tieni traccia di quando i destinatari aprono le e-mail
- **Clic**: controlla quali collegamenti fanno clic i destinatari
- **Annullamenti iscrizione**: tieni traccia delle richieste di rinuncia
- **Visualizzazioni pagina mirror**: verifica il numero di destinatari che visualizzano il messaggio e-mail in un browser

Ulteriori informazioni sul [tracciamento dei messaggi](https://experienceleague.adobe.com/it/docs/campaign/campaign-v8/analytics/tracking/tracking)

### Rapporti di consegna {#delivery-reports}

Adobe Campaign fornisce un set completo di rapporti per analizzare le prestazioni di consegna:

- **Riepilogo consegne**: panoramica di invii, consegne ed errori
- **Indicatori di tracciamento**: aperture, clic e percentuali di click-through
- **URL e flussi di clic**: collegamenti più popolari nelle consegne
- **Hot click**: rappresentazione visiva di dove i destinatari hanno fatto clic nell&#39;e-mail

Ulteriori informazioni sui [report di consegna](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/reports/ac-reports/delivery-reports)

### Rapporti globali {#global-reports}

Accedi ai rapporti globali per analizzare le prestazioni in tutte le campagne e le consegne:

- **Velocità effettiva di consegna**: messaggi inviati nel tempo
- **Messaggi non recapitati e non recapitati**: analisi delle consegne non riuscite
- **Attività utente**: apre, fa clic e annulla l&#39;iscrizione in tutte le campagne

Ulteriori informazioni sui [report globali](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/reports/ac-reports/global-reports)

## Argomenti correlati {#related-topics}

- [Best practice per la consegna](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/delivery-best-practices)
- [Gestione della quarantena](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/monitor/quarantines)
- [Configurare e inviare consegne](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/validate/configure-and-send)
- [Introduzione al reporting](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/reports/gs-reporting)
