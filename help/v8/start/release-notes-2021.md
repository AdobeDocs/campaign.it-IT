---
title: Note sulla versione di Campaign v8 2021
description: Elenco delle funzioni e dei miglioramenti introdotti con le versioni v8 di Campaign 2021
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 5ac6bda9-86c8-4200-b285-6fee2a29039d
source-git-commit: d6160d927601f66f450553a6dd6f91d74b0b1104
workflow-type: tm+mt
source-wordcount: '1581'
ht-degree: 100%

---

# Note sulla versione 2021{#2021-release}

In questa pagina sono elencate le nuove funzionalità, i miglioramenti e correzioni introdotte con le **versioni di Campaign v8 2021**.

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
* Ai fini del monitoraggio e del testing, i registri di audit del flusso di lavoro **[!UICONTROL Replicate Staging data]** ora includono il numero di record inviati al database FFDA (Full Federated Data Access).
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
