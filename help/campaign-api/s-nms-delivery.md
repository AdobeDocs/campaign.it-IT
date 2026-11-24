---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 77%
---
# consegna

Questo schema rappresenta un’azione o un modello di consegna.

Un modello è un modello di consegna che include tutti i parametri necessari. Un modello di consegna può essere eseguito manualmente dalla console client o quando si verifica un evento (avviato dal modulo di pianificazione o in modo programmatico da una chiamata SOAP).

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [AppendDeliveryPart](sm-delivery-appenddeliverypart.md) | Aggiunge una parte a una consegna in fase di preparazione. |
| [BuildForward](sm-delivery-buildforward.md) | Genera la pagina HTML. |
| [BuildMirror](sm-delivery-buildmirror.md) | Crea la pagina mirror HTML. |
| [BuildMirrorEx](sm-delivery-buildmirrorex.md) | Crea la pagina mirror HTML. |
| [BuildPreview](sm-delivery-buildpreview.md) | Crea l’anteprima di un contenuto da consegnare o di una riga del file di output (in modalità esterna). |
| [BuildPreviewFromId](sm-delivery-buildpreviewfromid.md) | Crea l’anteprima di un contenuto da consegnare o di una riga del file di output (in modalità esterna). |
| [BuildTargetDataSchema](sm-delivery-buildtargetdataschema.md) |  |
| [CleanupDeliveries](sm-delivery-cleanupdeliveries.md) | Specifica che il server di mid-sourcing deve eliminare alcune consegne. |
| [RaccogliRegistri](sm-delivery-collectlogs.md) | Crea una tabella con tutti i messaggi del registro di consegna per un elenco di consegne |
| [CreaDaModello](sm-delivery-createfrommodel.md) | Creazione di una consegna da un modello (dal suo nome interno). |
| [DistribuisciMessaggioTrigger](sm-delivery-deploytriggermessagesingle.md) | Pubblica il messaggio transazionale sulle istanze di esecuzione. Restituisce true se la pubblicazione ha esito positivo e false in caso contrario. |
| [DeployTriggerMessages](sm-delivery-deploytriggermessages.md) | Pubblica i messaggi transazionali selezionati sulle istanze di esecuzione |
| [DiagnosiHTML](sm-delivery-diagnosehtml.md) | Avvia la diagnostica dei contenuti HTML |
| [DispatchImages](sm-delivery-dispatchimages.md) | Indica al server dell’applicazione di inviare le immagini al server mid-sourcing. |
| [ExecCommand](sm-delivery-execcommand.md) | Esegue un comando su una consegna. |
| [ExecuteJob](sm-delivery-executejob.md) | Esegue un processo sincrono su una consegna. |
| [FinalizeMidPreparation](sm-delivery-finalizemidpreparation.md) | Completa l’analisi di una consegna in modalità mid-sourcing. |
| [GetDeviceList](sm-delivery-getdevicelist.md) |  |
| [GetDlStatusAndLogs](sm-delivery-getdlstatusandlogs.md) | Recupera gli ultimi registri dal giornale di registrazione e lo stato di consegna. |
| [GetFilesToDownload](sm-delivery-getfilestodownload.md) | Restituisce l’elenco dei file trovati sul server associato alla consegna. |
| [GetMidBroadLogs](sm-delivery-getmidbroadlogs.md) | Recupera i registri di consegna modificati per ultimi in modalità mid-sourcing. |
| [GetMidDeliveries](sm-delivery-getmiddeliveries.md) | Recupera lo stato delle consegne modificate per ultime in modalità mid-sourcing. |
| [GetMidXtkKey](sm-delivery-getmidxtkkey.md) | Restituisce la chiave Xtk del server mid |
| [GetMirrorURL](sm-delivery-getmirrorurl.md) | Ottiene l’URL di una pagina mirror HTML. |
| [GetSeedList](sm-delivery-getseedlist.md) |  |
| [HtmlToText](sm-delivery-htmltotext.md) | Converte il contenuto HTML in testo semplice |
| [Pubblicazione immagine](sm-delivery-imagepublishing.md) | Esegue la post-elaborazione: sposta l’immagine in una cartella specificata e la rende disponibile online |
| [MessaggioTransazionale](sm-delivery-installtransactionalmessage.md) | Installa un modello per messaggi transazionali sull’istanza di esecuzione. |
| [InvalidateDeliveryCache](sm-delivery-invalidatedeliverycache.md) | Deve essere chiamato alla fine della preparazione del messaggio, ad eccezione del mid-sourcing (metodo privato). |
| [LaunchFCP](sm-delivery-launchfcp.md) | Avvia una copia Bozza per una consegna |
| [LoadExpandedContents](sm-delivery-loadexpandedcontents.md) | Carica un elenco di componenti per la preelaborazione con dipendenze (blocchi di personalizzazione, opzioni, oggetti script aggiuntivi, ecc.). |
| [Pausa](sm-delivery-pause.md) | Sospende una consegna. |
| [Riproduci](sm-delivery-play.md) | Inizia una consegna. |
| [Prepara](sm-delivery-prepare.md) | Analisi della consegna: targeting e personalizzazione |
| [PreparaEInizia](sm-delivery-prepareandstart.md) | Analizza la consegna e la esegue subito se non si verificano errori |
| [PrepareFromId](sm-delivery-preparefromid.md) | Analizza una consegna. |
| [PreparaMessaggio](sm-delivery-preparemessage.md) | Personalizzazione dei messaggi |
| [PrepareMessageImpl](sm-delivery-preparemessageimpl.md) | Personalizzazione dei messaggi |
| [PreparaMultipartRelated](sm-delivery-preparemultipartrelated.md) | Salva nel database le immagini da includere nell’e-mail |
| [PrepareNotification](sm-delivery-preparenotification.md) | Analisi di una notifica aggiunta a un’azione di consegna esistente |
| [PreparaBozza](sm-delivery-prepareproof.md) | Analisi della consegna a fronte della generazione di una bozza |
| [PreparaTarget](sm-delivery-preparetarget.md) | Conteggio e arbitrato del target della consegna |
| [PrepareTargetImpl](sm-delivery-preparetargetimpl.md) | Conteggio e arbitrato del target della consegna |
| [AnteprimaEstrazione](sm-delivery-previewextraction.md) | Anteprima del file di estrazione |
| [Registri con priorità](sm-delivery-prioritizelogs.md) | Assegna la priorità al registro di consegna per un elenco di consegne |
| [Destinazione prioritaria](sm-delivery-prioritizetarget.md) | Arbitrato del target di consegna |
| [NotificaCoda](sm-delivery-queuenotification.md) | Richiesta di mettere in coda una notifica con riferimento a un modello di consegna. |
| [RicalcolaStatistiche](sm-delivery-recomputestats.md) | Ricalcola le statistiche di consegna e tracciamento di un’azione di consegna. |
| [SalvaUrlInfo](sm-delivery-saveurlinfo.md) | Salva gli URL di questa consegna come modelli URL. |
| [Interrompi](sm-delivery-stop.md) | Interruzione di una consegna in corso. |
| [InformazioniPaginaMirrorStore](sm-delivery-storemirrorpageinfo.md) | Aggiunge informazioni per generare pagine mirror per un set di parti di consegna. |
| [StoreMirrorPageInfoEx](sm-delivery-storemirrorpageinfoex.md) | Aggiunge informazioni per generare pagine mirror per un set di parti di consegna. |
| [InviaConsegna](sm-delivery-submitdelivery.md) | Creazione e invio di una consegna da uno scenario (dal relativo nome interno). |
| [SubmitDeliveryById](sm-delivery-submitdeliverybyid.md) | Crea e invia una consegna da uno scenario (identificato dal relativo nome interno). |
| [InviaProcesso](sm-delivery-submitjob.md) | Invia un processo per l’elaborazione asincrona di una consegna |
| [SubmitMidSourcing](sm-delivery-submitmidsourcing.md) | Invia una consegna in modalità mid-sourcing. |
| [InviaNotifica](sm-delivery-submitnotification.md) | Crea e invia una notifica da uno scenario. |
| [UpdateBroadLogs](sm-delivery-updatebroadlogs.md) | Aggiorna lo stato dei registri di consegna, effettua la gestione degli errori e aggiorna i contatori di consegna. |
| [UpdateCachedDelivery](sm-delivery-updatecacheddelivery.md) | Deve essere chiamato ogni volta che la consegna viene modificata nella memoria in modo che altri thread abbiano accesso a una versione aggiornata (metodo privato). |
| [AggiornaConfigurazioneImmagine](sm-delivery-updateimageconfig.md) | Modifica il nodo imageConfig per tenere conto delle immagini già presenti nel server. |
| [ConvalidaDefinizioneOnde](sm-delivery-validatewavesdefinition.md) | Verifica la coerenza delle informazioni utilizzate nella definizione degli scaglioni. |

## Metodi generici

| Elemento “method” | Descrizione |
| --- | --- |
| [crea](f-create.md) | Crea una nuova entità corrispondente a uno schema specificato. |
| [carica](f-load.md) | Carica e restituisce un&#39;entità corrispondente a uno schema e a una chiave specifici. |
| [salva](m-entity-save.md) | Salva un&#39;entità nel database. |
