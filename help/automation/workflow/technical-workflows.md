---
product: campaign
title: Flussi di lavoro tecnici
description: Ulteriori informazioni sui flussi di lavoro tecnici disponibili con Campaign
feature: Workflows
exl-id: 2693856c-80b2-4e35-be8e-2a9760f8311f
source-git-commit: 8d9b8d3e31362c2d69ec0fc6f16ab375538d7f10
workflow-type: tm+mt
source-wordcount: '1654'
ht-degree: 3%

---

# Flussi di lavoro tecnici{#about-technical-workflows}

Adobe Campaign viene fornito con un set di flussi di lavoro tecnici integrati. Gestiscono le operazioni e i processi pianificati per l&#39;esecuzione periodica sul server. Consentono di eseguire la manutenzione sul database, inoltrare le informazioni di tracciamento sulle consegne o impostare processi provvisori sulle consegne. I flussi di lavoro tecnici sono configurati tramite **[!UICONTROL Administration > Production > Technical workflows]** nodo.

![](assets/navtree.png)

Sono disponibili modelli nativi per la creazione di flussi di lavoro tecnici. Possono essere configurati in base alle tue esigenze.

La **[!UICONTROL Campaign process]** la sottocartella centralizza i flussi di lavoro necessari per l’esecuzione dei processi all’interno delle campagne: notifica delle attività, gestione delle scorte, calcolo dei costi, ecc.

![](assets/campaign-processes-wf.png)


>[!NOTE]
>
>L’elenco dei flussi di lavoro tecnici installati con ciascun modulo è disponibile in un [sezione dedicata](technical-workflows.md).

Puoi creare altri flussi di lavoro tecnici nella sezione **[!UICONTROL Administration > Production > Technical workflows]** nodo della struttura ad albero. Tuttavia, questo processo è riservato agli utenti esperti.

Le attività offerte sono le stesse dei flussi di lavoro di targeting. [Ulteriori informazioni](targeting-workflows.md)

I flussi di lavoro descritti in questa sezione vengono installati con i diversi pacchetti incorporati di Adobe Campaign. Questi pacchetti e i relativi flussi di lavoro tecnici dipendono dal contratto di licenza. I pacchetti incorporati sono descritti in .

Per impostazione predefinita, i flussi di lavoro tecnici sono disponibili in una sottocartella del nodo seguente: **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]**.

I flussi di lavoro tecnici possono essere avviati e modificati solo dagli operatori con autorizzazioni di amministrazione.

>[!NOTE]
>
>I flussi di lavoro tecnici relativi al componente aggiuntivo Centro messaggi sono disponibili per impostazione predefinita nel **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Message Center]** > **[!UICONTROL Technical workflows]** nodo.

Scopri come monitorare i flussi di lavoro tecnici in questo [sezione dedicata](monitor-technical-workflows.md).


## Elenco dei flussi di lavoro tecnici {#list-technical-workflows}

| Flusso di lavoro tecnico | Pacchetto | Descrizione |
|------|--------|-----------|
| **Pulizia degli alias** (aliasCleansing) | Installato per impostazione predefinita | Questo flusso di lavoro standardizza i valori di enumerazione. Viene attivato ogni giorno alle 3 per impostazione predefinita. |
| **Fatturazione** (fatturazione) | Installato per impostazione predefinita | Questo flusso di lavoro invia il rapporto sull’attività del sistema all’operatore di &quot;fatturazione&quot; tramite e-mail. Viene attivato il 25 di ogni mese sull’istanza Marketing. |
| **Processi campagna** (operationMgt) | Installato per impostazione predefinita | Questo flusso di lavoro gestisce i lavori per le campagne di marketing (targeting di lanci, estrazione file, ecc.). Crea inoltre flussi di lavoro relativi a campagne ricorrenti e periodiche. |
| **Raccolta di dati per il servizio HeatMap** (collectDataHeatMapService) | Installato per impostazione predefinita | Questo flusso di lavoro recupera i dati richiesti dal servizio HeatMap . |
| **Raccogli richieste di privacy** (collectPrivacyRequests) | Regolamento sulla protezione dei dati sulla privacy | Questo flusso di lavoro genera i dati del destinatario memorizzati in Adobe Campaign e li rende disponibili per il download nella schermata della richiesta di accesso a dati personali. |
| **Calcolo del costo** (budgetMgt) | Installato per impostazione predefinita | Questo flusso di lavoro avvia il calcolo delle linee di spesa e di costo relative a budget, piani, programmi, campagne, consegne e attività. |
| **Pulizia del database** (pulizia) | Installato per impostazione predefinita | Questo flusso di lavoro è il flusso di lavoro di manutenzione del database: effettua calcoli diversi dalle statistiche e dai processi ed elimina dati obsoleti dal database in base alla configurazione definita nell&#39;assistente alla distribuzione. Viene attivato ogni giorno alle 4 per impostazione predefinita. Per ulteriori informazioni, consulta . |
| **Elimina utenti LINE bloccati** (deleteBlockedLineUsersV2) | Canale LINE | Questo flusso di lavoro assicura che i dati degli utenti LINE V2 vengano cancellati dopo che hanno bloccato l&#39;account ufficiale LINE per 180 giorni. |
| **Eliminare i dati delle richieste di privacy** (deletePrivacyRequestsData) | Regolamento sulla protezione dei dati sulla privacy | Questo flusso di lavoro elimina i dati del destinatario memorizzati in Adobe Campaign. |
| **Indicatori di consegna** (deliveryIndicators) | Piattaforma di mid-sourcing | Questo flusso di lavoro aggiorna gli indicatori di tracciamento della consegna per una consegna. Questo flusso di lavoro viene attivato ogni ora per impostazione predefinita. |
| **Processi di marketing distribuiti** (centralLocalMgt) | Marketing centrale/locale (Marketing distribuito) | Questo flusso di lavoro avvia l’elaborazione correlata all’utilizzo del modulo marketing distribuito. Avvia la creazione di campagne locali e gestisce le notifiche relative agli ordini e alla disponibilità dei pacchetti delle campagne. |
| **Eliminazione eventi** (webAnalyticsPurgeWebEvents) | Connettori di Web Analytics | Questo flusso di lavoro ti consente di eliminare ogni evento dal campo del database in base al periodo configurato nel campo Durata . |
| **Esportare tipi di pubblico in Adobe Experience Cloud** (exportSharedAudience) | Integrazione con Adobe Experience Cloud | Questo flusso di lavoro esporta i tipi di pubblico come pubblici/segmenti condivisi. Questi tipi di pubblico possono essere utilizzati nelle diverse soluzioni Adobe Experience Cloud che utilizzi. |
| **Previsione** (previsioni) | Consegna | Questo flusso di lavoro analizza le consegne salvate nel calendario provvisorio (crea registri provvisori). Viene attivato ogni giorno all’1 per impostazione predefinita. |
| **Calcolo aggregato completo (cubo propositionrcp)** (agg_nmspropositionrcp_full) | Motore di offerta (interazione) | Questo flusso di lavoro aggiorna l’aggregato completo per il cubo delle proposte di offerta. Viene attivato ogni giorno alle 6 per impostazione predefinita. Questo aggregato acquisisce le seguenti dimensioni: Canale, consegna, offerta di marketing e data. Il cubo delle proposte di offerta viene quindi utilizzato per generare rapporti basati sulle offerte. Ulteriori informazioni sui cubi in  [questa sezione](../../v8/reporting/gs-cubes.md). |
| **Identificazione dei contatti convertiti** (webAnalyticsFindConverted) | Connettori di Web Analytics | Questo flusso di lavoro indicizza i visitatori del sito che hanno completato l’acquisto dopo una campagna di remarketing. I dati recuperati da questo flusso di lavoro sono accessibili nel rapporto sull’efficienza di remarketing (consulta questa pagina). |
| **Importare tipi di pubblico da Adobe Experience Cloud** (importSharedAudience) | Integrazione con Adobe Experience Cloud | Questo flusso di lavoro ti consente di importare tipi di pubblico/segmenti da diverse soluzioni Adobe Experience Cloud in Adobe Campaign. |
| **Processi sulle consegne nelle campagne** (deliveryMgt) | Installato per impostazione predefinita | Questo flusso di lavoro attiva le consegne approvate e avvia la post-elaborazione del provider di servizi per una consegna esterna. Invia inoltre notifiche e promemoria di approvazione. |
| **Processi dei fornitori di servizi** (fornitoreMgt) | Installato per impostazione predefinita | Questo flusso di lavoro avvia l&#39;elaborazione del provider (e-mail al router e post-elaborazione) una volta che le consegne sono state approvate. |
| **Migrazione da MID a LineUserID** (MIDToUserIDMigration) | Canale LINE | Questo flusso di lavoro genera l’ID degli utenti LINE V2 per la migrazione da LINE V1 a LINE V2. |
| **Centro messaggi &lt;external_account_name>** (mcSynch_&lt;external_account_name>) | Controllo dei messaggi transazionali (Centro messaggi - Controllo) | Questo flusso di lavoro: <ul><li>recupera l’elenco degli eventi elaborati dalle operazioni.</li><li>si sincronizza con la tabella NmsBroadLogMsg per recuperare i requisiti dei messaggi di consegna.</li><li>recupera i registri di consegna degli eventi non appena la sincronizzazione con la tabella NmsBroadLogMsg è stata completata.</li><li>si sincronizza con la tabella NmsTrackingUrl al fine di recuperare il tracciamento per gli URL di consegna.</li><li>recupera gli URL di tracciamento degli eventi non appena la sincronizzazione con la tabella NmsTrackingUrl è stata completata.</li><li>consente di recuperare tutti gli indirizzi e-mail messi in quarantena ogni tre ore dopo l’invio di una consegna.</li></ul> |
| **Calcolo aggregato completo MessageCenter** (agg_messageCenter_full) | Controllo dei messaggi transazionali (Centro messaggi - Controllo) | Questo flusso di lavoro aggiorna l’aggregato Completo per il cubo Centro messaggi . Viene attivato ogni giorno alle 3 per impostazione predefinita. Questo aggregato acquisisce le seguenti dimensioni: Canale, data, stato ed evento. Il cubo Centro messaggi viene quindi utilizzato per generare rapporti basati su eventi. Puoi saperne di più sui cubi in  |
| **Mid-sourcing (contatori di consegna)** (defaultMidSourcingDlv) | Trasferisci a mid-sourcing | Questo flusso di lavoro raccoglie le informazioni sul conteggio delle consegne sul server di mid-sourcing. Le informazioni sul conteggio includono indicatori generali di consegna come il numero di consegne inviate, ecc. Le informazioni di tracciamento come le aperture non sono incluse. Viene attivato ogni dieci minuti per impostazione predefinita. |
| **Mid-sourcing (registri di consegna)** (defaultMidSourcingLog) | Trasferisci a mid-sourcing | Questo flusso di lavoro raccoglie i registri di consegna sul server di mid-sourcing. Viene attivato ogni ora per impostazione predefinita. |
| **Gestione delle rinunce NMAC** (mobileAppOptOutMgt) | Canale app mobile (push) | Questo flusso di lavoro aggiorna le sottoscrizioni di notifiche sui dispositivi mobili. Viene attivato ogni 6 ore tra l’1 e mezzanotte. Per ulteriori informazioni, consulta . |
| **Notifica di offerta** (offerMgt) | Installato per impostazione predefinita | Questo flusso di lavoro distribuisce le offerte approvate nell’ambiente online, nonché in ogni categoria contenuta nel catalogo delle offerte. |
| **Pulizia dei flussi di lavoro in pausa** (cleanupPausedWorkflows) | Installato per impostazione predefinita | Questo flusso di lavoro analizza i flussi di lavoro in pausa con la gravità impostata su normale e attiva avvisi e notifiche quando sono stati messi in pausa per troppo tempo. Dopo un mese, i flussi di lavoro tecnici in pausa vengono interrotti incondizionatamente. Per impostazione predefinita viene attivato ogni lunedì alle 5. Per ulteriori informazioni, consulta [Gestione dei flussi di lavoro in pausa](monitor-workflow-execution.md#handling-of-paused-workflows). |
| **Pulizia delle richieste di privacy** (cleanupPrivacyRequests) | Regolamento sulla protezione dei dati sulla privacy | Questo flusso di lavoro cancella i file di richiesta di accesso che sono più vecchi di 90 giorni. |
| **Eventi batch di elaborazione** (batchEventsProcessing) | Esecuzione di messaggi transazionali (Centro messaggi - Esecuzione) | Questo flusso di lavoro consente di mettere gli eventi batch in una coda prima di associarli a un modello di messaggio. |
| **Elaborazione di eventi in tempo reale** (rtEventsProcessing) | Esecuzione di messaggi transazionali (Centro messaggi - Esecuzione) | Questo flusso di lavoro consente di mettere gli eventi in tempo reale in una coda prima di associarli a un modello di messaggio. |
| **Sincronizzazione delle proposte** (propositionSynch) | Controllo del motore di offerta con istanza di esecuzione | Questo flusso di lavoro sincronizza le proposizioni tra l’istanza di marketing e l’istanza di esecuzione utilizzata per le interazioni. |
| **Recupero di eventi web** (webAnalyticsGetWebEvents) | Connettori di Web Analytics | Ogni ora, questo flusso di lavoro scarica i segmenti sul comportamento degli utenti Internet su un dato sito, li inserisce nel database Adobe Campaign e avvia il flusso di lavoro di remarketing. |
| **Reporting aggregates** (reportingAggregates) | Consegna | Questo flusso di lavoro aggiorna gli aggregati utilizzati nei rapporti. Viene attivato ogni giorno alle 2 per impostazione predefinita. |
| **Invio di indicatori e attributi della campagna** (webAnalyticsSendMetrics) | Connettori di Web Analytics | Questo flusso di lavoro consente di inviare gli indicatori delle campagne e-mail da Adobe Campaign a Adobe Experience Cloud Suite tramite il connettore Adobe® Analytics. Gli indicatori interessati sono i seguenti: Inviato (Inviato), Numero totale di aperture (iTotalRecipientOpen), Numero totale di destinatari che hanno fatto clic su (iTotalRecipientClick), Errori (iError), Opt-Out (opt-out) (iOptOut). |
| **Stock: Ordini e avvisi** (stockMgt) | Installato per impostazione predefinita | Questo flusso di lavoro avvia il calcolo delle scorte sulle linee dell&#39;ordine e gestisce le soglie degli avvisi di avviso. |
| **Tracking** (tracciamento | Installato per impostazione predefinita | Questo flusso di lavoro esegue il ripristino e il consolidamento delle informazioni di tracciamento. Assicura inoltre il ricalcolo delle statistiche di tracciamento e consegna, in particolare quelle utilizzate dai flussi di lavoro di archiviazione Message Center. Per impostazione predefinita viene attivato una volta all’ora. |
| **Aggiorna stato evento** (updateEventsStatus) | Esecuzione di messaggi transazionali (Centro messaggi - Esecuzione) | Questo flusso di lavoro ti consente di assegnare uno stato a un evento. Gli stati dell’evento sono i seguenti:<ul><li>In sospeso: l’evento è in coda. Non è ancora stato associato alcun modello di messaggio.</li><li>Consegna in sospeso: l’evento è in coda, è stato associato un modello di messaggio ed è attualmente in fase di elaborazione da parte della consegna.</li><li>Inviato: questo stato viene copiato dai log di consegna. Significa che la consegna è stata inviata.</li><li>Ignorato dalla consegna: questo stato viene copiato dai log di consegna. Significa che la consegna è stata ignorata.</li><li>Errore di consegna: questo stato viene copiato dai log di consegna. Significa che la consegna non è riuscita.</li><li>Evento non trattato: impossibile associare l&#39;evento a un modello di messaggio. L’evento non verrà rielaborato.</li></ul> |
| **Aggiornamento per il recapito messaggi** (deliverabilityUpdate) | Installato per impostazione predefinita | Una volta installato il pacchetto di monitoraggio del recapito messaggi (recapito messaggi e-mail), questo flusso di lavoro viene eseguito di notte e gestisce le regole di qualificazione delle e-mail non recapitate, nonché l’elenco dei domini e delle MX. Questo richiede che la porta HTTPS sia aperta sulla piattaforma. |
