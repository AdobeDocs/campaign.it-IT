---
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: c1a5dd3fcad5d377acb2f9df3a090897ed3b533e
workflow-type: tm+mt
source-wordcount: '2754'
ht-degree: 79%

---

# Ultima versione{#latest-release}

In questa pagina sono elencate nuove funzionalità, miglioramenti e correzioni introdotti con l’**ultima versione di Campaign v8**.

## Versione 8.4.1 {#release-8-4-1}

_30 settembre 2022_

**Novità**

<table> 
<thead>
<tr> 
<th> <strong>Integrazione di Adobe Campaign con Adobe Experience Platform</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>Sono ora disponibili nuovi connettori di destinazione e sorgente per consentire un’integrazione diretta tra Adobe Campaign e Adobe Experience Platform:</p>
<ul><li>Utilizza il connettore Adobe Campaign Managed Cloud Sources per inviare i segmenti di Experience Platform ad Adobe Campaign per l’attivazione,</li>
<li>Utilizza il connettore di destinazione Adobe Campaign Managed Cloud per inviare i registri di consegna e tracciamento di Adobe Campaign a Adobe Experience Platform.</li>
</ul>
<p>Per ulteriori informazioni, consulta la <a href="../connect/ac-aep.md">documentazione dettagliata</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Disponibilità dei canali twitter</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>La <a href="../send/twitter.md">Canale social twitter</a> è ora disponibile con Campaign v8. Puoi:</p>
<ul> 
<li><p>Invia messaggi su Twitter: Adobe Campaign ti consente di inviare messaggi direttamente al tuo account twitter. Puoi anche inviare messaggi diretti a tutti i tuoi follower.
</p></li>
<li><p>Raccogli nuovi contatti: Adobe Campaign può ripristinare automaticamente i dati del profilo, consentendo di eseguire campagne di targeting e implementare strategie cross-channel.
</p></li>
</ul>
<p>Scopri come collegare Campaign e Twitter nel <a href="../connect/ac-tw.md">documentazione dettagliata</a>.</p>
<p>Scopri come pubblicare tweet e inviare messaggi diretti con Campaign in <a href="../connect/ac-tw.md">questa pagina</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Miglioramenti**

* Dopo la fine del ciclo di vita di Microsoft Internet Explorer 11, il motore di rendering HTML nella console sta ora utilizzando **Cromo bordo Microsoft**. Inoltre, l&#39;installazione di **WebView Microsoft Edge 2** runtime è ora necessario per qualsiasi installazione della console client.
* È stata migliorata l’esecuzione del flusso di lavoro con l’elevata disponibilità del flusso di lavoro, che consente di eseguire flussi di lavoro simultanei tra contenitori diversi per evitare la perdita del servizio del flusso di lavoro ed evitare i relativi errori di esecuzione. **Nota**: Questa nuova funzionalità viene rilasciata solo in Disponibilità limitata a un set di clienti.
* Le richieste di privacy vengono ora eseguite in batch per uno specifico spazio dei nomi di privacy. Questo miglioramento aumenta il tempo di esecuzione per le richieste di cancellazione RGPD/privacy.

**Aggiornamenti della compatibilità**

* L’SDK di Campaign v8 supporta ora iOS 16 per le notifiche push.

Consulta la [Matrice di compatibilità di Campaign](compatibility-matrix.md).

**Patch**

* È stato risolto un problema che influenzava gli aggiornamenti dello stato del registro di consegna sull’istanza MID, quando l’opzione FeatureFlag_GZIP_Compression era abilitata. (NEO-49183)
* È stato risolto un problema che poteva causare il blocco delle consegne in **In sospeso** stato anche se è stata raggiunta la data di contatto. (NEO-48079)
* È stato risolto un problema nei flussi di lavoro che poteva impedire l’aggiornamento dei file sul server quando si utilizzava **Caricamento dati (file)** attività. Il processo si è interrotto al 100% ma non è mai terminato. (NEO-47269)
* È stato risolto un problema durante l’aggiornamento successivo negli ambienti giapponesi. (NEO-46640)
* È stato risolto un problema che poteva verificarsi se una consegna raggiungeva una dimensione precisa durante il processo MTA. (NEO-46097)
* È stato risolto un problema che impediva ai registri di tracciamento di restituire i dati relativi al browser del destinatario. (NEO-46612)
* È stato risolto un problema che causava problemi di personalizzazione durante l’invio di messaggi SMS utilizzando una modalità di consegna esterna. (NEO-46415)
* È stato risolto un problema che poteva generare duplicati nei registri di tracciamento. (NEO-46409)
* È stato risolto un problema che impediva la **[!UICONTROL Replicate Staging data]** Il flusso di lavoro tecnico (ffdaReplicateStagingData) non viene interrotto anche quando si è verificato un errore durante la relativa esecuzione. (NEO-46280)
* È stato risolto un problema che poteva verificarsi se una consegna raggiungeva una dimensione precisa durante il processo MTA. (NEO-46097)
* Per evitare la lentezza durante l’invio di prove agli indirizzi di seed, tutte le repliche consecutive dei membri di seed ora sono raggruppate in un’unica richiesta di replica. (NEO-44844)
* È stato risolto un problema che causava la visualizzazione di un errore durante il tentativo di visualizzare l’anteprima di una consegna in qualsiasi evento archiviato del Centro messaggi . (NEO-43620)
* È stato risolto un problema che si verificava durante l’inserimento di dati nel database cloud di Snowflake con una campagna **Query** attività e **Cambia origine dati** attività: il processo non riusciva quando nei dati è presente un carattere barra rovesciata. La stringa di origine non è preceduta dall&#39;escape e i dati non sono stati elaborati correttamente sul Snowflake. (NEO-45549)
* È stato risolto un problema che si verificava con l’utilizzo di **Query** attività e filtraggio di una tabella. Quando un nome di colonna conteneva la parola &quot;Update&quot;, si verificava un errore di compilazione con un identificatore non valido e il seguente messaggio: &quot;numero di righe aggiornate&quot;. (NEO-46485)


## Versione 8.3.8 {#release-8-3-8}

_18 maggio 2022_

**Novità**

<table> 
<thead>
<tr> 
<th> <strong>Notifiche sensibili al tempo</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Con iOS 15, Apple ha aggiunto il concetto di “notifiche urgenti” che permette allo sviluppatore dell’app di ignorare la modalità di attivazione quando una notifica è considerata urgente e deve quindi raggiungere l’utente in tempo reale.</p>
<p>Per ulteriori informazioni, consulta la <a href="../send/push.md#send-notifications-on-ios">documentazione dettagliata</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Integrazione core Privacy Service</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Campaign v8 ora si integra con Adobe Privacy Core Service. Le richieste di accesso a dati personali inviate dal servizio core per la privacy a tutte le soluzioni Experience Cloud vengono gestite automaticamente da Campaign tramite un flusso di lavoro dedicato.</p>
<p>Per ulteriori informazioni, consulta la <a href="privacy.md">documentazione dettagliata</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table>
<thead>
<tr>
<th><strong>Gestione della risposta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Gestione della risposta di Campaign consente di misurare il successo e il ROI delle campagne di marketing o delle proposte di offerta su tutti i canali: e-mail, dispositivi mobili, direct mailing, ecc.</p>
<p>Per ulteriori informazioni, consulta la <a href="../start/campaigns.md#response-manager-add-on">documentazione dettagliata</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Marketing distribuito</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Marketing distribuito di Campaign consente di implementare campagne di collaborazione tra entità centrali (sedi centrali, dipartimenti di marketing, ecc.) e gli enti locali (punti vendita, agenzie regionali, ecc.). Tramite un’area di lavoro condivisa (pacchetti di campagne), puoi creare modelli di campagna e proporli alle entità locali.</p>
<p>Per ulteriori informazioni, consulta la <a href="../start/campaigns.md#distributed-marketing-add-on">documentazione dettagliata</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Aggiornamenti della compatibilità**

* L’SDK di Campaign v8 supporta ora Android 12 e iOS 15 per le notifiche push.
* Campaign v8 è ora compatibile con Windows 11.

Consulta la [Matrice di compatibilità di Campaign](compatibility-matrix.md).

**Miglioramenti**

* L’autenticazione di Microsoft Exchange Online OAuth 2.0 per POP3 è ora supportata in Campaign. [Maggiori informazioni](../config/external-accounts.md#bounce-mails-external-account)
* Sono state applicate correzioni critiche relative all’API web di Microsoft Dynamics Connector.
* È stato aggiunto il nuovo diritto di scrittura dello schema di operatore e gruppo (operatorWrite) denominato per consentire agli utenti di inserire, aggiornare ed eliminare gli schemi Operatori (xtk:operator) e Gruppi di operatori (xtk:group).

<!--* You can now enable the Email BCC (blind carbon copy) capability to store emails sent by Campaign at the delivery level, through the dedicated option in the delivery properties. [Read more](../config/email-settings.md#email-bcc)-->
<!--* To ensure better performances, a new "Split" option is now activated by default in the Routing external account. This option allows messages to be automatically split across your mid-sourcing instances in order to be delivered faster to the recipients.-->
* È ora possibile configurare più account attivi LINE su un singolo mid-sourcing.
* Il numero di connessioni predefinite per il processo web è stato aumentato da 50 a 150.
* Campaign viene fornito con un set di nuove protezioni per impedire l’inserimento di chiavi duplicate nel database di Snowflake. [Maggiori informazioni](../architecture/keys.md)

**Patch**

* È stato risolto un problema che si verificava durante l’utilizzo di seed e gruppi di controllo nella stessa consegna ricorrente. (NEO-41197)
* È stato risolto un problema su FFDA che causava il blocco dell’invio di e-mail per tutti i destinatari appartenenti alla stessa deliveryPart durante il processo di invio (fino a 256) quando i blocchi di personalizzazione contenevano uno dei seguenti caratteri: `' & < > "`. Questi caratteri ora sono supportati nei blocchi di personalizzazione (ad esempio: nome=“Brian O&#39;Neil”). (NEO-43184)
* È stato risolto un problema che poteva causare un errore nel flusso di lavoro di tracciamento quando si utilizzava uno schema personalizzato come mappatura di destinazione. Ora assicuriamo che il tipo di collegamento esterno a uno schema di targeting personalizzato sia corretto durante la generazione dello schema broadLog tramite la procedura guidata di mappatura di destinazione. (NEO-43506)
* È stato risolto un problema che poteva causare il mancato funzionamento dei flussi di lavoro di distribuzione FFDA per lingue diverse dall’inglese. (NEO-44561)

## Versione 8.2.10 {#release-8-2-10}

_2 febbraio 2022_

**Patch**

* È stato risolto un problema che causava un errore nella preparazione della consegna se veniva raggiunto il numero massimo di messaggi, definito nella regola di tipologia.
* È stato risolto un problema che si verificava durante la configurazione del connettore Adobe Analytics se l’indirizzo e-mail conteneva un carattere “s”.
* È stato risolto un problema che si verificava durante il post aggiornamento e poteva causare la perdita di dati della tabella deliveryMapping da una mappatura di consegna personalizzata.
* È stato risolto un problema a causa del quale i destinatari potevano ricevere lo stesso messaggio più volte per la stessa consegna se l’indirizzo e-mail conteneva una virgoletta singola (&#39;). Questo carattere ora viene preceduto da un carattere di escape. (NEO-41198)
* È stato risolto un problema di generazione ID che si verificava durante l’invio di bozze con indirizzi seed o sostitutivi. (NEO-42637)
* È stato risolto un problema che poteva impedire l’invio di bozze utilizzando il metodo di sostituzione dell’indirizzo. (NEO-40417)
* È stato risolto un problema che impediva l’installazione del pacchetto LINE. (NEO-42503)

## Versione 8.2.8 {#release-8-2-8}

_28 ottobre 2021_

<table>
<thead>
<tr>
<th><strong>Interazione in entrata</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Real-time Interaction Management è ora disponibile per i canali in entrata. Utilizza il modulo di interazione in entrata di Campaign per presentare l’offerta migliore ai clienti quando visitano il sito web o contattano il call center. Questa funzionalità include Campaign v8 come opzione e richiede una configurazione specifica sull’istanza. Per avere accesso al modulo di interazione in entrata, rivolgiti al tuo rappresentante Adobe.</p>
<p>Per ulteriori informazioni, consulta la <a href="../interaction/interaction-architecture.md">documentazione dettagliata</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Ottimizzazione delle campagne</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>È ora disponibile il modulo di ottimizzazione delle campagne. Questo modulo consente di controllare, filtrare e monitorare l’invio delle consegne. Per evitare conflitti tra campagne, Adobe Campaign può sottoporre a test diverse combinazioni applicando specifiche regole di vincolo. Ciò garantisce che i messaggi inviati soddisfino le esigenze e le aspettative dei clienti, in linea con le politiche di comunicazione aziendali.</p>
<p>Per ulteriori informazioni, consulta la <a href="https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=it#campaign-optimization">documentazione dettagliata</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Servizio Unicity</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Il servizio Unicity è un nuovo componente Cloud Database Manager. Consente agli utenti di preservare e monitorare l’integrità dei vincoli di chiave univoca all’interno delle tabelle del database cloud. Questo consente di ridurre il rischio di inserimento di chiavi duplicate.
<p>Poiché il database cloud non applica vincoli di unicità, il servizio Unicity introduce a livello applicativo <b>una serie di nuovi guardrail</b> per ridurre il rischio di inserimento di duplicati durante la gestione dei dati con Adobe Campaign.</p> 
<p>Il servizio Unicity avvia un nuovo flusso di lavoro integrato denominato <b>ffdaUnicity</b> per monitorare i vincoli di unicità e avvisare quando vengono rilevati duplicati.</p>
<p>Per ulteriori informazioni, consulta la <a href="../architecture/keys.md">documentazione dettagliata</a>.</p>
</td> </tr> 
</tbody> 
</table>


**Miglioramenti**

* Il connettore Snowflake è stato migliorato in termini di prestazioni.
* Ai fini del monitoraggio e del testing, i registri di audit dei **[!UICONTROL Replicate Staging data]** ora includono il numero di record inviati al database FFDA (Full Federated Data Access).
* L’attività codice SQL consente ora di scegliere in quale database verrà memorizzato lo script SQL: l’origine dati predefinita o un account esterno FDA attivo prescelto.
* È ora disponibile un set di warehouse predefiniti che può essere utilizzato per eseguire varie query in parallelo, ad esempio segmentazione, ETL o picchi. [Leggi tutto](../config/workflows.md)

**Altre modifiche**

* Il campo **[!UICONTROL Encrypted identifier]** è stato aggiunto allo schema visitatore (`nms:visitor`). Questo campo viene calcolato e deve essere utilizzato per le applicazioni web.
* È stato risolto un problema che causava un errore di analisi della consegna se alcune affinità IP esistevano in alcuni contenitori di mid-sourcing, ma non in tutti. Ora le affinità IP sono tutte memorizzate nel database, in modo che qualsiasi contenitore possa accedere alle affinità presenti in tutti gli altri contenitori. (NEO-37564)
* Ora puoi importare un pacchetto con più schemi e nodi della struttura di navigazione.

**Patch**

* Se, uno schema di dati, veniva rimosso l’attributo `<autoStg>` di un elemento di definizione di tabella oppure veniva modificato il suo valore da `true` a `false`, la relativa tabella di staging non veniva eliminata. Questo problema è stato risolto.
* È stato risolto un problema che causava un errore durante la creazione di record con un modulo dedicato a causa della gestione degli ID con un’origine dati FFDA.
* È stato risolto un problema che poteva impedire l’inserimento di offerte in una consegna se queste erano gestite da un’attività di arricchimento in un flusso di lavoro.
* È stato risolto un problema che poteva rallentare l’importazione dei pacchetti.
* È stato risolto un problema che poteva impedire l’invio di consegne e-mail con indirizzi di seed.
* È stato risolto un problema che poteva impedire il salvataggio delle proposte nella tabella delle proposte di offerta.
* È stato risolto un problema che causava la registrazione errata dei problemi di timeout: questi non venivano registrati come errori di rete, ma come problemi di interruzione dello script. Questo problema si verificava nel caso di richieste HTTP incluse nelle attività JavaScript.
* È stato risolto un problema che impediva la replica delle offerte nell’ambiente delle offerte live su Snowflake.
* È stato risolto un problema a causa del quale veniva ignorato l’attributo “autoStg” per gli schemi incorporati non estesi.
* È stato risolto un problema che impediva agli utenti di selezionare il collegamento **[!UICONTROL Country/Region]** durante l’anteprima di un profilo.
* È stato risolto un problema che causava un errore di script nella visualizzazione del selettore di data nei report personalizzati. (NEO-36345)
* È stato risolto un problema che causava l’arresto anomalo del sistema durante la rigenerazione della configurazione in caso di file di configurazione non validi.
* È stato risolto un problema che impediva l’aggiornamento corretto delle istanze di marketing e controllo.
* È stato risolto un problema che poteva causare l’arresto anomalo del flusso di lavoro di fatturazione sulle istanze di marketing.
* È stato risolto un problema che poteva causare la duplicazione delle chiavi nelle tabelle predefinite di Snowflake FFDA. (NEO-38583)
* È stato risolto un problema che poteva causare la perdita di schemi temporanei del flusso di lavoro durante la modifica di due attività di deduplica una dopo l’altra. (NEO-34063)
* È stato risolto un problema a causa del quale venivano restituiti risultati errati nell’esecuzione delle funzioni Amazon Redshift HoursDiff e MinutesDiff durante il tentativo di estrarre il componente “time”.(NEO-31673)
* È stato risolto un problema che poteva impedire agli utenti di accedere alla console a causa di un problema di configurazione proxy. (NEO-38388)
* È stato risolto un problema di regressione che impediva il funzionamento corretto della funzionalità **Purge folder** (Svuota cartella). (NEO-37459)
* È stato risolto un problema che poteva impedire la visualizzazione in anteprima delle consegne mobili collegate a un flusso di lavoro.
* È stato risolto un problema che poteva impedire il funzionamento dell’attività del flusso di lavoro **Read list** (Leggi elenco) se l’elenco era stato identificato nel database con un ID negativo. (NEO-39607)

## Versione 8.1.20 {#release-8-1-20}

_7 settembre 2021_

**Miglioramenti di sicurezza**

* È stato risolto un problema di sicurezza per rafforzare la protezione contro gli attacchi di navigazione nelle directory. (NEO-28547)

**Miglioramenti**

* Al termine del suo ciclo di vita, Flash è stato rimosso da tutte le funzioni e i componenti di Campaign correlati e sostituito con HTML5. Il tipo di grafico **Misuratore** è stato rimosso. (NEO-30330) [Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html?lang=it)
* Durante l’installazione della console client su Windows, il programma di installazione ora controlla se è presente un nodo del registro principale e, se necessario, ne crea uno. Questo evita potenziali problemi durante l’avvio della console. (NEO-34854)
* La funzione di firma di tracciamento è stata migliorata per evitare errori collegati al modo in cui strumenti di terze parti (client e-mail, browser Internet, ecc.) gestiscono i caratteri speciali. I parametri URL sono ora codificati.

**Altre modifiche**

* I connettori Microsoft CRM precedentemente dichiarati obsoleti (per implementazioni Office 365 e on-premise) sono stati rimossi dall’interfaccia. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=it#configure-acc-for-microsoft)
* In seguito alla migrazione a Tomcat 8, lo script di installazione di IIS è stato aggiornato per risolvere i problemi di integrazione di IIS. (NEO-31019)
* È stata aggiunto un guardrail per consentire solo l’esecuzione del [flusso di lavoro tecnico di fatturazione](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html?lang=it#billing-report) sull’istanza di marketing.
* L’identificazione dell’origine dati è stata migliorata nelle schede dati e schema della finestra **Visualizza popolazione** delle transizioni del flusso di lavoro.
* Gli indici di database mancanti sono stati aggiunti ai seguenti schemi per evitare problemi di aggiornamento del database: xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**Patch**

* È stato risolto un problema che impediva il funzionamento del rapporto **Hot click** quando le offerte erano collegate alla consegna. (NEO-26295)
* È stato risolto un problema a causa del quale l’attività **Flusso di lavoro secondario** non generava una tabella di output. (NEO-36242)
* Sono stati risolti diversi problemi riguardanti l’esportazione PDF del rapporto **Analisi descrittiva**. (NEO-25847)
* È stato risolto un problema che poteva causare un errore nelle consegne durante l’utilizzo di una consegna e-mail esterna. (NEO-37435)
* È stato corretto un errore che si verificava durante la connessione a Microsoft CRM tramite API web. Il messaggio di errore è stato rimosso perché le funzionalità non erano interessate.
* È stato risolto un problema di deduplica del registro di tracciamento quando il server mid veniva impostato come relay tra i server di tracciamento e di marketing. (NEO-36285)
* È stata corretta una regressione che impediva l’utilizzo di Vault come archivio di codice specifico.
* È stato risolto un problema che impediva l’utilizzo di variabili in un’attività del flusso di lavoro **Arricchimento** quando la transizione in ingresso proveniva da un’origine dati FDA.
* È stato risolto un problema relativo a FFDA che impediva la corretta replica dei gruppi di operatori e dei diritti.
* È stato risolto un problema che poteva causare l’invio di un collegamento di annullamento dell’abbonamento errato tramite la consegna.
* È stato risolto un problema nella gestione della replica che influiva sulla durata del post aggiornamento.
* È stato risolto un problema che poteva impedire la visualizzazione di **Hot click**.
* È stato risolto un problema che poteva causare il malfunzionamento degli URL nei messaggi e-mail.

## Versione 8.1.14 {#release-8-1-14}

_23 luglio 2021_

**Novità**

<table>
<thead>
<tr>
<th><strong>Nuova attività per flusso di lavoro: cambiare l’origine dati</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>La nuova attività <b>Change Data Source</b> consente di cambiare l’origine dati della tabella di lavoro di un flusso di lavoro. Questa possibilità offre maggiore flessibilità nella gestione dei dati tra diverse origini dati (FDA, FFDA e database locale).</p>
<p>Nei flussi di lavoro di Adobe Campaign, i dati vengono gestiti utilizzando tabelle di lavoro (o temporanee). Durante l’esecuzione del flusso di lavoro, le tabelle di lavoro condividono i dati tra le varie attività del flusso di lavoro. Per impostazione predefinita, le tabelle di lavoro vengono create sullo stesso database dell’origine dei dati su cui si eseguono le query.</p>
<p>Con Campaign v8, la tabella dei profili principali viene memorizzata direttamente nel database cloud. Pertanto, quando si esegue una query sulla tabella dei profili, viene creata una tabella di lavoro sul database cloud. In alcuni casi, può essere utile spostarla in un’altra origine dati, per eseguire operazioni specifiche.</p>
<p>Per ulteriori informazioni, consulta la <a href="../config/workflows.md#change-data-source-activity">documentazione dettagliata</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Disponibilità del canale LINE</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Il <a href="../send/line.md">canale LINE</a> è ora disponibile con Campaign v8, inclusi i seguenti miglioramenti se combinati con il modulo di <a href="../send/transactional.md">messaggistica transazionale</a>:
<ul> 
<li><p>È stato risolto un problema a causa del quale non era possibile indirizzare i visitatori in una consegna LINE. 
</p></li>
<li><p>È stato risolto un problema che poteva causare errori durante il recupero dei visitatori dall’istanza di esecuzione all’istanza di marketing.
</p></li>
<li><p>Sono stati risolti alcuni problemi che si verificavano durante l’elaborazione di eventi in tempo reale.</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>


**Altri miglioramenti**

* È stato risolto un problema che poteva impedire la visualizzazione del rapporto **Hot clicks** per consegne specifiche.
* È stato risolto un problema relativo all’attività di **deduplicazione** dei flussi di lavoro, che poteva causare un conteggio non accurato dei duplicati.
* È stato risolto un problema che si verificava durante l’utilizzo di una query del flusso di lavoro con il filtro “ID is not empty” e che poteva causare la visualizzazione di un elemento vuoto nella popolazione di transizione.
* È stato risolto un problema che impediva la creazione di campi aggiuntivi in una nuova mappatura di destinazione.
