---
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 4a3e6cf15b1877e6eb4e13fdee056356eab267c5
workflow-type: tm+mt
source-wordcount: '1747'
ht-degree: 6%

---

# Versioni più recenti {#latest-release}

In questa pagina sono elencate le nuove funzionalità, i miglioramenti e le correzioni introdotte con le **versioni più recenti** di Campaign v8 (console). Ulteriori informazioni sulle versioni e gli aggiornamenti di Campaign sono disponibili in [questa pagina](upgrades.md). Altre versioni sono elencate nella sezione Versioni precedenti di questa documentazione.

## Versione 8.9.2 {#release-8-9-2}

>[!CAUTION]
>
> L’aggiornamento della console client è obbligatorio. Scopri come aggiornare la console client in questa [pagina](../start/connect.md#upgrade-ac-console).

_3 maggio 2026_

### Miglioramenti di sicurezza {#security-8-9-2}

* Per mantenere la sicurezza, la stabilità e la conformità ottimali, tutte le istanze sono state aggiornate a Debian 13 e PostgreSQL 17.

### Correzioni {#fixes-8-9-2}

>[!NOTE]
>
> Le correzioni elencate di seguito sono state implementate progressivamente nelle build 8.9.2 successive. Passa al **[!UICONTROL Help > About...]** [menu](upgrades.md#version) per verificare di disporre della build 8.9.2 (11d1c68) più recente. Per ulteriori informazioni, contatta il rappresentante Adobe.

* È stato risolto un problema che impediva la corretta impostazione delle date degli eventi negli eventi transazionali a causa di un problema di conversione del tipo di dati, causando date errate nel reporting dinamico. (NEO-93923)
* È stato risolto un problema a causa del quale le notifiche push silenziose di Android e iOS non riuscivano durante la preparazione della consegna quando i campi titolo e corpo erano vuoti. (NEO-93739)
* È stato risolto un problema che impediva l’acquisizione del campo della lingua per i token di registrazione dell’app Android a causa di chiavi di riconciliazione errate. (NEO-93100)
* È stato risolto un problema che impediva la preparazione della consegna durante l’applicazione di regole di tipologia personalizzate con regole di pressione. (NEO-94457)
* È stato risolto un problema che causava errori di elaborazione delle richieste HTTP nella console client. (NEO-94071)

<!-- BUILD 8.9.2.9829.9669833 -->

* Il monitoraggio FDA ora è disabilitato per impostazione predefinita per evitare errori di inserimento del registro connessioni. (NEO-94841)
* È stato risolto un problema a causa del quale le chiamate di Interaction SOAP utilizzate per il rimborso dell’offerta potevano non riuscire e generare un errore di risoluzione dello spazio dei nomi. (NEO-94787)
<!-- infra * Fixed an issue where Snowflake connections using private key authentication could fail on ARM64 architectures. (NEO-94350) -->
* È stato risolto un problema a causa del quale i campi stringa con lunghezza 1 potevano causare errori SQL nelle tabelle temporanee del flusso di lavoro in PostgreSQL 17. (NEO-94487)
<!-- linked to previous build * Fixed an issue where the server could fail to restart after a Debian 13 build upgrade due to a missing dependency. (NEO-94598) -->

<!-- BUILD 8.9.2.9829.c90aa36 -->

* È stato risolto un problema a causa del quale l&#39;opzione **Visualizza pagina mirror** nella console client e nell&#39;interfaccia utente Web poteva restituire un errore di tipo &quot;Pagina mirror errata&quot;. (NEO-93303)

<!-- BUILD 8.9.2.9830.4a6f868 -->

* È stato risolto un problema che poteva causare un errore nel flusso di lavoro tecnico predefinito **Tracking** dopo l’installazione di un pacchetto multivariante nelle distribuzioni FFDA. (NEO-94972)
* È stato risolto un problema che impediva alla preparazione della consegna di aggiungere destinatari al target quando il modello di consegna utilizzava una formula di rilevanza che faceva riferimento alla consegna corrente. (NEO-94892)
<!-- hotfix -->
* È stato risolto un problema a causa del quale l’arricchimento dei flussi di lavoro tramite join tra due collegamenti 1-N consecutivi poteva non riuscire e causare errori SQL dopo un aggiornamento. (NEO-94893)

<!-- BUILD 8.9.2.9831.f53d3d2 -->

* È stato risolto un problema nella pipeline e-mail che poteva causare un consumo eccessivo di memoria nel tempo. (NEO-95088)
* È stato risolto un problema a causa del quale la regola di tipologia e-mail in conflitto poteva erroneamente escludere destinatari non duplicati da un target di consegna quando venivano utilizzati indirizzi seed o di bozza. (NEO-95026)
* È stato risolto un problema che causava un errore del flusso di lavoro tecnico predefinito **Notifica offerta** dopo un aggiornamento. (NEO-95064)
* Il processo di installazione del pacchetto multivariato è stato migliorato per evitare errori del flusso di lavoro di tracciamento durante gli aggiornamenti della build. (NEO-95018)

<!-- BUILD 8.9.2.9831.11d1c68 -->

* È stato risolto un problema che poteva causare l’arresto anomalo ripetuto del server, con conseguente interruzione dell’istanza. (NEO-95304)
* È stato risolto un problema che impediva il caricamento delle consegne da parte dei collegamenti di tracciamento e pagina speculare. (NEO-95239)
* È stato risolto un problema che poteva causare un loop di reindirizzamento durante l’accesso alle applicazioni web Campaign protette dal Single Sign-On IMS. (NEO-95188)
* È stato risolto un problema a causa del quale la data di creazione della consegna mancava dai file di estrazione della consegna dopo il salvataggio della consegna. (NEO-95010)
* È stato risolto un problema a causa del quale i flussi di lavoro secondari generati in un volume elevato potevano rimanere bloccati nello stato **In corso di modifica**, riducendo la capacità del flusso di lavoro transazionale. (NEO-95131)
* È stato risolto un problema a causa del quale l&#39;attività **Read List** poteva sovrascrivere modelli di elenco predefiniti con strutture di elenco generate dal flusso di lavoro, causando errori nei flussi di lavoro a valle. (NEO-95103)
* È stato risolto un problema a causa del quale la gestione del feedback delle notifiche push poteva causare l’arresto anomalo del server durante l’elaborazione di consegne di volumi elevati. (NEO-95150)
* È stato risolto un problema che causava l&#39;attivazione di un messaggio di errore quando si apriva la scheda **Dati** nello schema `xtk:workflow` in Esplora schemi. (NEO-94923)
<!-- hotfixes -->
* È stato risolto un problema che impediva all&#39;attività **Enrichment** di recuperare gli attributi di output dalle attività **Subworkflow** a monte, causando un errore dei flussi di lavoro. (NEO-95151)
* È stato risolto un problema di acquisizione dei dati di tracciamento che poteva impedire gli aggiornamenti dello stato di consegna e bloccare l’elaborazione dei messaggi a valle. (NEO-94666)
* È stato risolto un problema a causa del quale alcune azioni della console client relative alle proposte di offerta potevano attivare query con tempi di esecuzione lunghi sui database di Snowflake, causando blocchi e lentezza. (NEO-92936)
* È stato risolto un problema che impediva la configurazione di opzioni personalizzate per l’archiviazione di chiavi crittografate negli account esterni di Snowflake. (NEO-93302)

<!-- 
Internal/non-customer-facing:
* Internal test automation task added to cover NEO-94893. (NEO-94990) — autotest only
Customer-specific hotfixes:
* Fixed an issue affecting WhatsApp delivery preparation. (NEO-92480) — HeroMotoCorp only
* Added a feature-flagged optimization to use dynamic shared memory in Customer Targeting Audience (CTA) processing. (NEO-93542) — DerTour only
* Fixed an issue where the delivery alerting workflow could fire incorrect "long start pending" notifications even when deliveries were sent within the configured threshold. (NEO-93434) — non-ZDT hotfix, NORC only
* Added a new parameter in the mobile SDK to allow identification of the source instance for push notifications. (NEO-94650) — ICICI only
* Fixed an issue with the custom send time feature on the Web UI where deliveries waited until the contact date and time to execute instead of executing at the equivalent local time per recipient timezone, breaking parity with Campaign Standard behavior. (NEO-94762) — H&M only (in progress at time of writing)
-->

## Versione 8.9.1 {#release-8-9-1}

_27 gennaio 2026_

>[!CAUTION]
>
> L’aggiornamento della console client è obbligatorio. Scopri come aggiornare la console client in questa [pagina](../start/connect.md#upgrade-ac-console).

### Nuove funzioni {#new-8-9-1}

Il **nuovo connettore di invio SMS** è ora disponibile per tutti i clienti (GA). Consulta la [documentazione dettagliata](../send/sms/sms.md).

Questa versione include una serie di funzionalità disponibili con l’interfaccia utente di Campaign Web:

* [Funzionalità di consegna multilingue (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html?lang=it){target="_blank"}
* [Arricchimento profilo nei messaggi transazionali (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html?lang=it){target="_blank"}
* [Adobe Experience Manager Live e copie per lingua](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html?lang=it){target="_blank"}
* [Esperimenti di contenuto - Test A/B](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html?lang=it){target="_blank"}
* [Attività di consegna continua](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html?lang=it){target="_blank"}
* [Gestione approvazione campagna](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html?lang=it){target="_blank"}

Consulta le [note sulla versione](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=it){target="_blank"} dell’interfaccia utente di Campaign Web

### Miglioramenti di sicurezza {#security-8-9-1}

* Gli account esterni di Snowflake ora supportano l’autenticazione OAuth2, fornendo metodi di autenticazione moderni e sicuri per le connessioni federate di accesso ai dati. (NEO-87013) [Ulteriori informazioni](../config/external-accounts.md#snowflake-external-accounts)
* Gli account esterni Databricks ora supportano l’autenticazione OAuth2 tramite l’entità principale del servizio (flusso di credenziali client non interattive), fornendo metodi di autenticazione sicuri per le connessioni federate di accesso ai dati. L’autenticazione interattiva OAuth2 sarà disponibile in una versione futura. (NEO-87422) [Ulteriori informazioni](../config/external-accounts.md#databricks-external-accounts)
* Sono state corrette le vulnerabilità di accesso ai file del flusso di lavoro limitando le operazioni alle directory autorizzate, impedendo l’accesso non autorizzato e la potenziale esecuzione di codice remoto. (NEO-88460)
* È stato aggiunto l’URL FTP inserire nell&#39;elenco Consentiti controlli alle attività del codice JavaScript del flusso di lavoro, limitando le connessioni FTP in uscita solo agli indirizzi autorizzati. (NEO-89083)

### Altre modifiche {#changes-8-9-1}

* È stata migliorata la gestione della memoria contenitore implementando la limitazione automatica del flusso di lavoro in condizioni di memoria elevata, con funzionalità di riavvio intelligente del flusso di lavoro e guardrail di memoria per i processi non critici. (NEO-89041)
* È stato aggiunto il supporto per funzioni di crittografia e decrittografia asimmetriche nei flussi di lavoro di Campaign. (NEO-80257)
* Prestazioni migliorate dell’agente di replica e resilienza della memoria per caricamenti di dati di grandi dimensioni nelle implementazioni FFDA. (NEO-88430)
* Le attività del flusso di lavoro **[!UICONTROL SQL code]** e **[!UICONTROL SQL Data Management]** sono state migliorate per proteggere meglio i database PostgreSQL e mantenere i flussi di lavoro in esecuzione senza problemi quando SQL personalizzato viene eseguito da Campaign. Per ulteriori informazioni e best practice, consultare [Gestione dati SQL](../../automation/workflow/sql-data-management.md#important-notes) e [Codice SQL](../../automation/workflow/sql-code-and-javascript-code.md#important-notes). (NEO-86540)


### Correzioni {#fixes-8-9-1}

* È stato risolto un problema che impediva l’aggiornamento della struttura del database in seguito alle modifiche apportate a sysFilter. (NEO-93306)
* È stato risolto un problema a causa del quale mancavano i dati del report dinamico dopo la migrazione. (NEO-92962)
* È stato risolto un problema che impediva l’aggiornamento corretto dello stato di consegna. (NEO-92908)
* È stato risolto un problema relativo alla restrizione FDA Use Catalog per Databricks. (NEO-92900)
* È stato risolto un problema che poteva causare errori di layout di HTML nel desktop di Outlook Windows. (NEO-92611)
* È stato risolto un problema di integrità dei dati a causa del quale le chiavi primarie di consegna venivano duplicate sull’istanza mid dopo un aggiornamento. (NEO-92424)
* È stato risolto un problema che impediva la disattivazione dei collegamenti nella finestra di dialogo Tracciamento e immagini in una consegna. (NEO-92381)
* È stato risolto un problema che impediva il funzionamento della funzione nms.subscribtion.RecipientSubscribe() per l’abbonamento in blocco. (NEO-92308)
* È stato risolto un problema che causava errori di consegna a causa di parti di consegna mancanti dopo un aggiornamento. (NEO-92278)
* È stato risolto un problema nel flusso di lavoro di tracciamento a causa del quale errori di stato duplicati ed errori di sintassi SQL impedivano l’aggiornamento degli indicatori di tracciamento. (NEO-92239)
* È stato risolto un problema a causa del quale le etichette dei campi di enumerazione risultavano mancanti o non venivano visualizzate correttamente negli elenchi creati tramite il flusso di lavoro quando si utilizzavano campi dbEnum. (NEO-91158)
* È stato risolto un problema che impediva la chiusura e il congelamento della finestra di dialogo RT Publish/Unpublish. (NEO-91038)
* È stato risolto un problema che si verificava per i destinatari con lo stato &quot;Preso in considerazione dal provider di servizi&quot;. (NEO-90927)
* È stato risolto un problema che causava l’assenza dell’origine (non) dell’abbonamento per i collegamenti di rinuncia. (NEO-90714)
* È stato risolto un problema che impediva l’aggiunta di coupon per la preparazione della consegna. (NEO-90547)
* È stato risolto un problema a causa del quale l’opzione Inserisci conteggio rifiuti non veniva riflessa in modo accurato nella scheda Audit. (NEO-90318)
* È stato risolto un problema di sicurezza che poteva causare il rifiuto del servizio da parte dell’applicazione. (NEO-89984)
* È stato risolto un problema che causava il mancato funzionamento del PDF scaricato del rapporto Hotclick. (NEO-89954)
* È stato risolto un errore SSL che si verificava dopo un aggiornamento, causando un errore EOF imprevisto durante la lettura degli errori. (NEO-89108)
* È stato risolto un problema che impediva l’esecuzione di query sui dati in uno schema di dati dopo un aggiornamento. (NEO-88663)
* È stato corretto un errore che si verificava durante la concatenazione di un campo &quot;char&quot; in PostgreSQL 15. (NEO-88028)
* È stato risolto un problema che causava la modifica dell’ordine delle variabili del modello di consegna durante il salvataggio o la duplicazione del modello. (NEO-87845)
* È stato risolto un problema che causava l’arresto anomalo dell’interfaccia web a causa della creazione di un nuovo schema della libreria dati. (NEO-87816)
* È stato risolto un problema relativo ai set di complementi nell’attività Deduplication. (NEO-87711)
* È stata corretta una richiesta di pacchetto di installazione senza dipendenza X11. (NEO-87471)
* È stato risolto un problema che impediva l’utilizzo dei codici di segmento nei report dinamici. (NEO-87276)
* È stato risolto un problema che bloccava i flussi di lavoro nell’attività Update Data (Aggiorna dati). (NEO-87252)
* È stato risolto un problema a causa del quale BigQuery utilizzava un fuso orario errato. (NEO-86622)
* È stato corretto un errore di JavaScript che si verificava durante la valutazione dello script &quot;mcSynch_mcExec1/jsReplicateUrl&quot;. (NEO-86553)
* È stato risolto un problema che causava la visualizzazione di eventi duplicati nella tabella eventHisto a causa di un metodo di calcolo dell’identificatore errato. (NEO-86544)
* È stato risolto un problema che impediva la visualizzazione della scheda Avanzate per Push al momento della copia in iOS. (NEO-86231)
* È stato risolto un problema che impediva al flusso di lavoro replica tabelle di riferimento di replicare lo schema nms:delivery. (NEO-85884)
* È stato risolto un problema che causava la visualizzazione di errori di dominio nulli corrispondenti a indirizzi MXIP nei registri di errore durante l’invio delle consegne. (NEO-85238)
* È stato risolto un problema a causa del quale i modelli di consegna tecnica non venivano aggiornati dopo le modifiche apportate alle opzioni. (NEO-84149)
* È stato corretto un errore nel flusso di lavoro di fatturazione preconfigurato. (NEO-83624)
* È stato risolto un problema di esclusione dei duplicati basati solo sulla chiave primaria dei record di destinazione. (NEO-82910)
* Sono state corrette le discrepanze nei rapporti dell’interfaccia utente web di Campaign a causa delle quali le statistiche di tracciamento mostravano valori diversi rispetto alla console. (NEO-82339)
* È stato risolto un problema che causava la modifica della data dell’ultima modifica anche se il record non doveva essere aggiornato nell’attività Aggiorna dati. (NEO-82002)
* È stato risolto un problema che impediva l’aggiunta di nuovi attributi in un elenco a causa del quale i flussi di lavoro che leggevano l’elenco non riuscivano. (NEO-80258)
* È stato risolto un problema che causava la visualizzazione di valori errati nel rapporto Tracking Indicators (Indicatori di tracciamento) per aperture distinte. (NEO-79466)