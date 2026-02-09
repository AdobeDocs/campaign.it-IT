---
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: f25b0a0fea5f32dd509d8b78e6f6a010d9598a9f
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 17%

---

# Versioni più recenti {#latest-release}

In questa pagina sono elencate le nuove funzionalità, i miglioramenti e le correzioni introdotte con le **versioni più recenti** di Campaign v8 (console). Ulteriori informazioni sulle versioni e gli aggiornamenti di Campaign sono disponibili in [questa pagina](upgrades.md). Altre versioni sono elencate nella sezione Versioni precedenti di questa documentazione.

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

* Gli account esterni di Snowflake ora supportano l’autenticazione OAuth2, fornendo metodi di autenticazione moderni e sicuri per le connessioni federate di accesso ai dati. (NEO-87013)
* Sono state corrette le vulnerabilità di accesso ai file del flusso di lavoro limitando le operazioni alle directory autorizzate, impedendo l’accesso non autorizzato e la potenziale esecuzione di codice remoto. (NEO-88460)
* È stato aggiunto l’URL FTP, che consente di inserire nell&#39;elenco Consentiti controlli alle attività del codice JavaScript del flusso di lavoro, limitando le connessioni FTP in uscita solo agli indirizzi autorizzati. (NEO-89083)

### Altre modifiche {#changes-8-9-1}

* È stata migliorata la gestione della memoria contenitore implementando la limitazione automatica del flusso di lavoro in condizioni di memoria elevata, con funzionalità di riavvio intelligente del flusso di lavoro e guardrail di memoria per i processi non critici. (NEO-89041)
* È stato aggiunto il supporto per funzioni di crittografia e decrittografia asimmetriche nei flussi di lavoro di Campaign. (NEO-80257)
* Prestazioni migliorate dell’agente di replica e resilienza della memoria per caricamenti di dati di grandi dimensioni nelle implementazioni FFDA. (NEO-88430)


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