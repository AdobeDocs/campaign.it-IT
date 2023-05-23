---
title: Introduzione ai rapporti di Adobe Campaign Analytics
description: Scopri come creare i cubi
feature: Reporting
role: Data Engineer
level: Beginner
exl-id: f57f3074-981f-4bcf-9274-7908cd00a4a2
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 13%

---

# Introduzione ai rapporti di analisi di Campaign {#gs-cube}

Adobe Campaign viene fornito con uno strumento di esplorazione dei dati intuitivo per la creazione di rapporti dinamici.

Utilizza le funzionalità di analisi marketing per analizzare e misurare i dati, calcolare le statistiche, semplificare e ottimizzare la creazione e il calcolo dei rapporti. Puoi creare rapporti e creare popolazioni target e memorizzarle in elenchi che possono essere utilizzati in Adobe Campaign per attività di targeting o segmentazione.

Puoi estendere le capacità di esplorazione e di analisi del database e semplificare la configurazione di rapporti e tabelle da parte dell’utente finale: per elaborare calcoli, misure e statistiche, sarà sufficiente selezionare un cubo esistente (completamente configurato) durante la creazione del rapporto o della tabella .

I cubi vengono utilizzati per generare determinati rapporti incorporati, tra cui [rapporti di consegna](delivery-reports.md) (tracciamento della consegna, clic, aperture, ecc.).

Una volta creati e configurati, i cubi vengono utilizzati nelle caselle di query dei report e nelle applicazioni web. Possono essere utilizzati e manipolati all’interno di tabelle pivot.

Utilizza il modulo Marketing Analytics di Campaign per:

1. Creare cubi e indicatori

   * aggregare e memorizzare i dati in una tabella di lavoro per precalcolare gli indicatori in base alle esigenze degli utenti,
   * ridurre il volume dei dati coinvolti nei vari calcoli utilizzati per le relazioni e le query, ottimizzando in modo significativo i tempi di calcolo degli indicatori,
   * semplifica l’accesso ai dati, consentendo agli utenti di manipolarli (preaggregati o meno) a seconda delle varie dimensioni.

   Per ulteriori informazioni, consulta [Creare indicatori](cube-indicators.md).

1. Creare tabelle pivot ed esplorare i dati

   * esplorare i dati calcolati, le misure configurate,
   * selezionare i dati da visualizzare e la relativa modalità di visualizzazione,
   * personalizzare le misure e gli indicatori utilizzati,
   * offre strumenti di analisi interattiva agli utenti con background non tecnico.

   Per ulteriori informazioni, consulta [Utilizzare i cubi per esplorare i dati](cube-tables.md).

1. Creare una query utilizzando i dati calcolati e aggregati in un cubo.
1. Identificare le popolazioni e farvi riferimento negli elenchi.

## Terminologia {#terminology}

Di seguito sono elencati i termini specifici per l&#39;utilizzo dei cubi.

* **Cubo** - Un cubo è una rappresentazione di informazioni multidimensionali: fornisce agli utenti finali strutture progettate per l&#39;analisi interattiva dei dati.

* **Tabella dei fatti/schema** - La fact table (o schema dei fatti) contiene i dati grezzi o elementari su cui verranno basate le analisi. Si tratta principalmente di tabelle di volumi di grandi dimensioni (eventualmente con tabelle collegate) con calcoli potenzialmente lunghi. Ad esempio, una fact table può essere: la tabella broadlog, la tabella purchase e così via.

* **Dimension** - I Dimension consentono di segmentare i dati in gruppi: una volta creati, le dimensioni fungono da assi di analisi. Nella maggior parte dei casi, per una determinata dimensione, vengono definiti diversi livelli. Ad esempio, per una dimensione temporale, i livelli saranno mesi, giorni, ore, minuti e così via. Questo set di livelli rappresenta la gerarchia delle dimensioni e abilita vari livelli di analisi dei dati.

* **Binning** - In alcuni campi è possibile definire il binning per raggruppare i valori e semplificare la lettura delle informazioni. Binning applicato ai livelli. Si consiglia di definire il binning quando esiste la possibilità di molti valori diversi.

* **Misura** - Le misure più frequenti sono somma, media, massima, minima, deviazione standard, ecc. Le misure possono essere calcolate: ad esempio, il tasso di accettazione di un’offerta è il rapporto tra il numero di volte in cui è stata presentata e il numero di volte in cui è stata accettata.
