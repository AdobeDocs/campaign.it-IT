---
product: Adobe Campaign
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 5b81c8e9e391ea1a9ad1825e5102b66c7926c204
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 43%

---

# Ultima versione{#latest-release}

In questa pagina sono elencate nuove funzionalità, miglioramenti e correzioni introdotti con l’**ultima versione di Campaign v8**.

## Versione 8.1.20 {#release-8-1-20}

_7 settembre 2021_

**Miglioramenti della sicurezza**

* È stato risolto un problema di sicurezza per rafforzare la protezione contro gli attacchi di navigazione nelle directory. (NEO-28547)

**Miglioramenti**

* Al termine del suo ciclo di vita, il Flash è stato rimosso da tutte le funzioni e i componenti di Campaign correlati e sostituito con HTML5. Il tipo di grafico **Gage** è stato rimosso. (NEO-30330) [Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html)
* Durante l&#39;installazione della console client su Windows, il programma di installazione controlla ora se è presente un nodo del Registro di sistema padre e ne crea uno se è mancante. Questo evita potenziali problemi durante l’avvio della console. (NEO-34854)
* La funzione di firma di tracciamento è stata migliorata per evitare errori collegati al modo in cui strumenti di terze parti (client e-mail, browser Internet, ecc.) gestire caratteri speciali. I parametri URL sono ora codificati.

**Altre modifiche**

* I connettori di Microsoft CRM precedentemente obsoleti (distribuzioni Office 365 e on-premise) sono stati rimossi dall’interfaccia. [Leggi tutto](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html#configure-acc-for-microsoft)
* In seguito alla migrazione a Tomcat 8, lo script di installazione di IIS è stato aggiornato per risolvere i problemi di integrazione di IIS. (NEO-31019)
* È stata aggiunta una guardrail per consentire solo l’esecuzione del [flusso di lavoro tecnico di fatturazione](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html#billing-report) sull’istanza di marketing.
* L’identificazione dell’origine dati è stata migliorata nelle schede dati e schema della finestra **Visualizza popolazione** delle transizioni del flusso di lavoro.
* Gli indici di database mancanti sono stati aggiunti ai seguenti schemi per evitare problemi di aggiornamento del database: xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**Patch**

* È stato risolto un problema che impediva il funzionamento del rapporto **Hot click** quando le offerte erano collegate alla consegna. (NEO-26295)
* È stato risolto un problema relativo all&#39;attività **Sub-worfklow** quando l&#39;esecuzione non generava una tabella di output. (NEO-36242)
* Sono stati risolti diversi problemi durante l’esportazione del rapporto **Analisi descrittiva** in PDF. (NEO-25847)
* È stato risolto un problema che poteva causare un errore nelle consegne durante l’utilizzo di una consegna e-mail esterna. (NEO-37435)
* È stato corretto un errore che si verificava durante la connessione a Microsoft CRM tramite API Web. Il messaggio di errore è stato rimosso perché le funzionalità non erano interessate.
* È stato risolto un problema di deduplicazione del registro di tracciamento quando il server mid veniva impostato come relay tra i server di tracciamento e di marketing. (NEO-36285)
* È stata corretta una regressione che impediva l&#39;utilizzo di Vault come archivio di codice specifico.
* È stato risolto un problema che impediva l&#39;utilizzo di variabili in un&#39;attività del flusso di lavoro **Enrichment** quando la transizione in ingresso proveniva da un&#39;origine dati FDA.
* È stato risolto un problema relativo a FFDA che impediva la corretta replica dei gruppi di operatori e dei diritti.
* È stato risolto un problema che poteva causare l’invio di un collegamento di annullamento dell’abbonamento errato tramite la consegna.
* È stato risolto un problema nella gestione della replica che influisce sulla durata del post aggiornamento.
* È stato risolto un problema che poteva impedire la visualizzazione di **Hot click**.
* È stato risolto un problema che poteva causare il blocco degli URL nei messaggi e-mail.

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
