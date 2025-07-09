---
title: Note sulla versione di Campaign v8 (console) 2023
description: Elenco di funzioni e miglioramenti introdotti con le versioni di Campaign v8 2023
feature: Release Notes
role: User
level: Beginner
exl-id: b860c843-155e-4abb-bdd6-b68dc7eaa0ee
source-git-commit: b52308bcbe68a7c382918fe28f8166e3bfcb6cde
workflow-type: tm+mt
source-wordcount: '1518'
ht-degree: 56%

---

# Note sulle versioni 2023 {#2023-rn}

In questa pagina sono elencate le nuove funzionalità, i miglioramenti e le correzioni inclusi nelle **versioni di Campaign v8 2023**. Per la versione più recente, consulta [questa pagina](release-notes.md).

Per qualsiasi nuova implementazione o aggiornamento a un ambiente esistente, installa [la versione più recente](release-notes.md).


>[!BEGINSHADEBOX]

**In questa pagina**

* Campaign v8.5 - [Versione 8.5.1](#release-8-5-1) | [Versione 8.5.2](#release-8-5-2)
* Campaign v8.4 - [Versione 8.4.3](#release-8-4-3) | [Versione 8.4.4](#release-8-4-4) | [Versione 8.4.5](#release-8-4-5)

>[!ENDSHADEBOX]

## Versione 8.5.2 {#release-8-5-2}

_2 agosto 2023_

È stato risolto un problema di sicurezza che poteva verificarsi durante l’aggiornamento a 8.5.1. (NEO-64767)

## Versione 8.5.1 {#release-8-5}

_sabato 30 giugno 2023_


**Servizio di notifica push avanzato**

Campaign v8.5.1 introduce il servizio di notifica push più recente, basato su un solido framework basato su una tecnologia all’avanguardia. Questo servizio è progettato per sbloccare nuovi livelli di scalabilità, garantendo che le notifiche possano raggiungere un pubblico più ampio con una perfetta efficienza. Con la nostra infrastruttura migliorata e i nostri processi ottimizzati, puoi aspettarti maggiore scalabilità e affidabilità, consentendoti di interagire e connettersi con gli utenti delle app mobili come mai prima d’ora. Questa funzionalità è disponibile solo per un gruppo selezionato di clienti (disponibilità limitata).

Per ulteriori informazioni, consulta la [documentazione dettagliata](../send/push-data-collection.md).


<table style="table-layout:fixed" text-align="bottom"><tr style="border: 0;">
<td>
<br/><img alt="Miglioramenti della velocità effettiva" src="../start/assets/do-not-localize/improvements.jpeg">
<p>
</td>
<td>
<div>
<p><strong>Throughput aumentato del canale mobile</strong></p>
<p>Il nuovo servizio di notifica push mostra miglioramenti significativi nella velocità effettiva sia per Android push che per iOS push rispetto alla versione precedente (v8.4). Gli utenti potranno beneficiare di prestazioni notevolmente migliorate grazie al servizio aggiornato nella versione più recente (v8.5). </p>
<ul>
<li>Notifiche push (Android): fino a <strong>5x</strong> più veloce </li>
<li>Notifiche push (iOS): fino a <strong>2.2x</strong> più veloce</li>
</ul>
<p>La velocità effettiva degli SMS è stata notevolmente migliorata grazie a una serie di ottimizzazioni, con conseguenti notevoli miglioramenti in termini di velocità ed efficienza per le comunicazioni SMS. Questi aggiornamenti hanno aumentato la velocità effettiva dalla versione precedente (v8.4) alla versione più recente (v8.5), includendo sia gli aggiornamenti di invio che quelli di feedback. Gli utenti possono ora usufruire dei vantaggi di questo servizio SMS avanzato.</p>
<ul>
<li>Throughput SMS: fino a <strong>5x</strong> più veloce</li>
</ul>
<p><em>Queste prestazioni di throughput massime sono state misurate dai team di test di Adobe, in condizioni di laboratorio.</em></p>
</div>
<p></p>
</td>
</tr></table>


**Miglioramenti generali**

* Ora puoi sfruttare la connessione di destinazione Adobe Experience Platform per sincronizzare gli attributi del profilo, ad esempio i dati di rinuncia, tra Adobe Experience Platform e il database di Campaign v8.
* La preparazione della consegna è stata ottimizzata su tutti i canali.
* È stata aggiunta una nuova opzione di autenticazione basata su chiave per l’account esterno SFTP, insieme al metodo di autenticazione utente/password esistente. Ora gli utenti possono eseguire l’autenticazione in modo sicuro utilizzando una chiave privata, migliorando la sicurezza e fornendo un meccanismo di autenticazione alternativo per l’accesso SFTP. Per ulteriori informazioni, consulta [questa sezione](../config/external-accounts.md).

**Miglioramenti di sicurezza**

* Con Campaign v8.5.1, il processo di autenticazione per Campaign v8 è stato migliorato e protetto. Gli operatori tecnici devono ora utilizzare Adobe Identity Management System (IMS) per connettersi a Campaign. Scopri come eseguire la migrazione degli account tecnici esistenti in [questa nota tecnica](../../technotes/upgrades/ims-migration.md).
* A partire dalla versione v8.6 in arrivo, non ti sarà più consentito creare operatori dalla console client di Campaign. Se utilizzi l’autenticazione nativa per login/password, devi migrare gli operatori ad Adobe Identity Management System (IMS). Scopri come effettuare la migrazione degli operatori in [questa nota tecnica](../../technotes/upgrades/migrate-users-to-ims.md).
* Diversi strumenti di terze parti sono stati aggiornati per ottimizzare la sicurezza.

**Aggiornamenti della compatibilità**

* La versione a 32 bit della console client è ora obsoleta. A partire dalla versione 8.6, la console client sarà disponibile solo a 64 bit. L’aggiornamento alla versione a 64 bit della console client è semplice. Per ulteriori informazioni su come aggiornare il sistema operativo, consulta questa [nota tecnica](../../technotes/upgrades/console.md).
* Ora puoi collegare la tua istanza di Campaign v8 al database esterno di Azure Synapse. Questa connessione viene gestita tramite un nuovo account esterno. Ulteriori informazioni nella [Matrice di compatibilità di Campaign](../start/compatibility-matrix.md#federated-data-access-fdafederateddataaccessfda).


**Correzioni**

* È stato risolto un problema che poteva causare la codifica errata in diversi browser dei caratteri speciali nel contenuto HTML di una consegna. (NEO-60081)
* È stato risolto un problema che poteva impedire il salvataggio di un rapporto su una distribuzione Campaign v8 Enterprise (FFDA). (NEO-56836)
* È stato risolto un problema che si verificava durante l’inserimento o l’aggiornamento di dati in uno schema FFDA personalizzato tramite un’attività del flusso di lavoro Update Data (Aggiorna dati). (NEO-54708)
* È stato risolto un problema che impediva al flusso di lavoro di pulizia del database di rimuovere gli indirizzi nella tabella nms:address in FFDA. (NEO-54460)
* È stato risolto un problema relativo al flusso di lavoro di fatturazione che poteva non riuscire con un errore di tipo &quot;Memoria di compilazione esaurita&quot;. (NEO-51137)
* È stato risolto un problema che poteva impedire il corretto funzionamento della decrittografia GPG nell’attività del flusso di lavoro Caricamento dati (file). (NEO-50257)
* È stato risolto un problema che impediva l’utilizzo della funzione `JSPContext.sqlExecWithOneParam`. (NEO-50066)
* È stato risolto un problema che causava errori di consegna durante l’utilizzo di caratteri non stampabili nei campi di personalizzazione. (NEO-48588)
* È stato risolto un problema che poteva causare errori di consegna durante l’inserimento di immagini dinamiche Adobe Target. (NEO-62689)
* È stato risolto un problema che impediva ai browser di aggiungere spazi aggiuntivi durante l’utilizzo di contenuto condizionale in una consegna. (NEO-62132)
* È stato risolto un problema che causava l’apertura di una finestra a comparsa quando si faceva clic su un’immagine nell’editor dei contenuti e-mail. (NEO-60752)
* È stato risolto un problema che poteva causare un errore e impedire lo scorrimento durante la modifica del contenuto di una consegna. (NEO-61364)
* Il connettore Adobe Analytics ora esporta le metriche con il tipo di canale corretto. In precedenza era sempre impostato come canale &quot;e-mail&quot;. (NEO-26340)
* È stato risolto un problema che poteva causare errori durante l’utilizzo del connettore Big Query con campi datetime. (NEO-49768)


## Versione 8.4.5 {#release-8-4-5}

_3 aprile 2023_

**Correzioni**

* È stato risolto un problema che poteva causare un errore di duplicazione di vincolo chiave se diversi flussi di lavoro di approvazione venivano impostati sulla stessa pianificazione. (NEO-48968)
* È stato risolto un problema di regressione introdotto da NEO-54474 (8.4.4) che causava la modifica dell’attributo di stile del corpo del tag durante il caricamento di un’immagine dell’editor di contenuti digitali (DCE). (NEO-57697)
* È stato risolto un problema che poteva causare un errore durante l’esportazione dei dati tramite un connettore CRM se la tabella temporanea aveva una chiave primaria definita come lunga invece di UUID. (NEO-54153)
* È stato risolto un problema di regressione introdotto in 8.4.1 che poteva causare errori nell’esportazione di pacchetti, nel FDA su HTTP e nella reportistica. (NEO-57731)
* È stato risolto un problema di regressione introdotto nella versione 8.3.8 che poteva impedire che lo stato di consegna venisse aggiornato correttamente per le consegne con ID negativi. (NEO-54675)
* È stato risolto un problema relativo ai campi booleani durante l’importazione di dati tramite il connettore Big Query (NEO-49181)


## Versione 8.4.4 {#release-8-4-4}

_8 marzo 2023_

**Miglioramento della sicurezza**

* Per migliorare la sicurezza, Tomcat è stato aggiornato dalla versione 8.5.81 alla versione 8.5.85. (NEO-50530)

**Correzioni**

* È stato risolto un problema che poteva impedire lo scorrimento nella scheda **Modifica** dell’editor di contenuti digitali (DCE). (NEO-54474)
* È stato risolto un problema che poteva causare un arresto anomalo del server web durante la replica. (NEO-53670)


## Versione 8.4.3 {#release-8-4-3}


_27 gennaio 2023_

**Correzioni**

* È stato risolto un problema di sincronizzazione dell’indicatore di consegna tra il server di marketing e il server di mid-sourcing . (NEO-50724) <!--OKKKK-->
* È stato risolto un problema che poteva causare un errore durante l’esportazione di un flusso di lavoro. (NEO-50555) <!--OKKKK-->
* È stato risolto un problema che si verificava durante l’estensione di uno schema già esteso in precedenza. (NEO-49118) <!--OKKKK-->
* È stato risolto un problema che si verificava durante l’utilizzo di due attività di arricchimento con lo stesso identificatore nella definizione del collegamento. (NEO-48851)
* Sono stati risolti due problemi di preparazione della consegna. La preparazione della consegna poteva non riuscire quando il numero delle potenziali offerte manipolate era troppo alto. Il secondo problema si verificava quando gli URL dell’immagine venivano definiti come URL da monitorare in una consegna in formato testo. (NEO-48807) <!--OKKKK-->
* È stato risolto un problema che poteva causare un errore del flusso di lavoro, che si verificava quando un flusso di lavoro sovrascriveva il nome del data warehouse definito nell’account esterno per gli account non FFDA. (NEO-43209) <!--OKKKK-->
* Maggiore sicurezza sulle applicazioni web per prevenire attacchi DDoS. (NEO-50757) <!--OKKKK-->
* La gestione dei dati di tracciamento consolidati è stata migliorata nella tabella FFDA **[!UICONTROL Consolidated tracking]** (nms:trackingStats) per evitare duplicati. (NEO-46409)
* È stato risolto un problema relativo all’operatore logico nelle query del flusso di lavoro quando si utilizza `enableIf` in una condizione di operatore logico. La condizione logica precedente veniva ovrascritta. (NEO-45815)  <!--OKKKK-->
* La generazione di profili attivi è stata ottimizzata nel flusso di lavoro di fatturazione per migliorare le prestazioni. (NEO-47658) <!--OKKKK-->
* È stato risolto un problema relativo all’importazione di file HTML quando i nodi immagine (img) contenevano URL con campi di personalizzazione. (NEO-48396)
* È stato risolto un problema relativo a Snowflake (tutte le distribuzioni) durante l’utilizzo del parametro di ordinamento in un’attività del flusso di lavoro di **Divisione**. (NEO-45899) <!--OKKKK-->
* È stato risolto un problema che causava un errore quando un utente con diritti di accesso in lettura nella cartella nmsDeliveryMapping tentava di eseguire una campagna o un flusso di lavoro. (NEO-48230)
* È stato risolto un problema di prestazioni nella scheda HTML di una consegna che poteva verificarsi in caso di un codice HTML di grandi dimensioni. (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* È stato risolto un problema che impediva l’utilizzo dell’opzione del flusso di lavoro **Unisci righe selezionate**. (NEO-48488)
* È stato risolto un problema del connettore Snowflake FDA che causava la perdita di record durante l’utilizzo di “unione semplice a 0 o 1 cardinalità” durante l’arricchimento. (NEO-48737)
* I riferimenti rimanenti alla libreria log4j sono stati rimossi dall’installazione di Campaign su Windows. (NEO-44851)
* È stato risolto un problema che poteva causare un errore durante l’aggiunta dell’indicatore **Destinatari che hanno aperto** (estimatedRecipientOpen) nei dati aggiuntivi di un’attività del flusso di lavoro **Query**. (NEO-46665)
* La gestione degli URL di tracciamento è stata migliorata nei flussi di lavoro con più consegne per migliorare le prestazioni. (NEO-50894) <!--OKKKK-->
* È stato risolto un problema che poteva impedire la replica degli schemi che utilizzano Xtkfolder. (NEO-46787) <!--OKKKK-->
* È stato risolto un problema che poteva causare l’eliminazione della colonna personalizzata “lastModified” nella tabella NmsSubscription. (NEO-48402)
