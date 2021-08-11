---
product: Adobe Campaign
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Panoramica
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 328f1bca11f8554def6ad4ccb741a86695481e98
workflow-type: ht
source-wordcount: '312'
ht-degree: 100%

---

# Ultima versione{#latest-release}

In questa pagina sono elencate nuove funzionalità, miglioramenti e correzioni introdotti con l’**ultima versione di Campaign v8**.

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
