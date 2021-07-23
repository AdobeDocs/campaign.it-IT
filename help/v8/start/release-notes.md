---
product: Adobe Campaign
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Panoramica
role: Data Engineer
level: Beginner
hidefromtoc: true
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 9e745f7fb8fd20f35025c06ff621a9da5002190e
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 7%

---

# Ultima versione{#latest-release}

In questa pagina sono elencate nuove funzionalità, miglioramenti e correzioni apportati con la **versione più recente di Campaign v8**.

## Versione 8.1.14 {#release-8-1-14}

_23 luglio 2021_

**Novità**

<table>
<thead>
<tr>
<th><strong>Nuova attività del flusso di lavoro: Cambia origine dati</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>La nuova attività del flusso di lavoro <b>Cambia origine dati</b> ti consente di modificare l’origine dati della tabella di lavoro di un flusso di lavoro. Ciò offre una maggiore flessibilità nella gestione dei dati tra diverse origini dati (FDA, FFDA e database locale).</p>
<p>Nei flussi di lavoro Adobe Campaign, i dati vengono gestiti utilizzando tabelle di lavoro (o temporanee). Durante l’esecuzione del flusso di lavoro, le tabelle di lavoro condividono i dati tra le attività del flusso di lavoro. Per impostazione predefinita, le tabelle di lavoro vengono create sullo stesso database dell'origine dei dati su cui eseguiamo la query.</p>
<p>Con Campaign v8, la tabella dei profili principali viene memorizzata direttamente nel database cloud. Quindi, eseguire una query sulla tabella Profili creerà una tabella di lavoro anche sul database cloud. In alcuni casi, può essere utile spostare la tabella di lavoro in un’altra origine dati per eseguire operazioni specifiche.</p>
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
<td> <p>Il canale LINE è ora disponibile con Campaign v8. Sono stati apportati i seguenti miglioramenti quando si utilizza LINE con Message Center (Centro messaggi):
</p>
<ul> 
<li><p>È stato risolto un problema che poteva impedire ai visitatori di essere oggetto di targeting in una consegna LINE. 
</p></li>
<li><p>È stato risolto un problema che poteva causare errori durante il recupero dei visitatori dall’istanza di esecuzione all’istanza di marketing.
</p></li>
<li><p>Sono stati risolti dei problemi durante l’elaborazione di eventi in tempo reale nel contesto delle consegne LINE che utilizzano Message Center (Centro messaggi).</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**Altri miglioramenti**

* È stato risolto un problema che poteva impedire la visualizzazione del rapporto **Hot click** per consegne specifiche.
* È stato risolto un problema relativo all&#39;attività del flusso di lavoro **Deduplication** che poteva causare un conteggio duplicato non accurato.
* È stato risolto un problema che si verificava durante l’utilizzo di una query del flusso di lavoro con il filtro &quot;ID non vuoto&quot; e che poteva causare la visualizzazione di un elemento vuoto nella popolazione di transizione.
* È stato risolto un problema che impediva la creazione di campi aggiuntivi in una nuova mappatura di destinazione.
