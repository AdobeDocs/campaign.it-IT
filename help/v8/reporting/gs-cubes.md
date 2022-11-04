---
title: Guida introduttiva ai rapporti di Adobe Campaign Analytics
description: Scopri come creare cubi
feature: Reporting
role: Data Engineer
level: Beginner
source-git-commit: bd39a18178edec2730707f0323a19c9d1c80cd76
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 13%

---

# Guida introduttiva ai rapporti di Analytics per Campaign {#gs-cube}

Adobe Campaign è dotato di uno strumento intuitivo di esplorazione dei dati per creare rapporti dinamici.

Utilizza le funzionalità di analisi di marketing per analizzare e misurare i dati, calcolare le statistiche, semplificare e ottimizzare la creazione e il calcolo dei rapporti. Puoi creare rapporti e creare popolazioni target e memorizzarle in elenchi che possono essere utilizzati in Adobe Campaign per attività di targeting o segmentazione.

Puoi estendere le capacità di esplorazione e di analisi del database e semplificare la configurazione di report e tabelle da parte degli utenti finali: tutto ciò che devono fare è selezionare un cubo esistente (completamente configurato) durante la creazione del report o della tabella per elaborare calcoli, misure e statistiche.

I cubi vengono utilizzati per generare alcuni rapporti incorporati, tra cui [rapporti di consegna](delivery-reports.md) (tracciamento della consegna, clic, aperture, ecc.).

>[!CAUTION]
>
>In una [[!DNL Snowflake] Distribuzione FDA (predefinita)](../architecture/fda-deployment.md), i rapporti basati sui cubi possono essere utilizzati solo per volumi di dati inferiori a 5 milioni di linee di fatto.


Una volta creati e configurati, i cubi vengono utilizzati nelle caselle di query dei report e nelle applicazioni web. Possono essere utilizzati e manipolati all’interno di tabelle pivot.

Utilizza il modulo Campaign Marketing Analytics per:

1. Creazione di cubi e indicatori

   * aggregare e memorizzare i dati in una tabella di lavoro per precalcolare gli indicatori in base alle esigenze degli utenti,
   * ridurre il volume dei dati coinvolti nei vari calcoli utilizzati per i rapporti e le query, ottimizzando in modo significativo i tempi di calcolo degli indicatori,
   * semplifica l’accesso ai dati, consente agli utenti di manipolare i dati (preaggregati o meno) a seconda delle varie dimensioni.

   Per ulteriori informazioni, consulta [Creare indicatori](cube-indicators.md).

1. Creare tabelle pivot ed esplorare i dati

   * esplorare dati calcolati, misure configurate,
   * selezionare i dati da visualizzare e la relativa modalità di visualizzazione,
   * personalizzare le misure e gli indicatori utilizzati,
   * offrono strumenti di analisi interattivi agli utenti con background non tecnico.

   Per ulteriori informazioni, consulta [Utilizzare i cubi per esplorare i dati](cube-tables.md).

1. Crea una query utilizzando dati calcolati e aggregati in un cubo.
1. Identificare le popolazioni e farvi riferimento negli elenchi.

## Terminologia {#terminology}

Di seguito sono elencati i termini specifici quando si lavora con i cubi.

* **Cubo** - Un cubo è una rappresentazione di informazioni multidimensionali: fornisce agli utenti finali strutture progettate per l’analisi interattiva dei dati.

* **Tabella/schema dei fatti** - La tabella dei fatti (o schema dei fatti) contiene i dati grezzi o elementari su cui verranno basate le analisi. Si tratta principalmente di grandi tabelle di volumi (eventualmente con tabelle collegate) con calcoli potenzialmente lunghi. Ad esempio, una tabella dei fatti può essere: la tabella del registro di trasmissione, la tabella degli acquisti, ecc.

* **Dimension** - I Dimension ti consentono di segmentare i dati in gruppi: una volta create, le quote fungono da assi di analisi. Nella maggior parte dei casi, per una data dimensione, verranno definiti diversi livelli. Ad esempio, per una dimensione temporale, i livelli saranno mesi, giorni, ore, minuti, ecc. Questo insieme di livelli rappresenta la gerarchia delle dimensioni e consente diversi livelli di analisi dei dati.

* **Binning** - Per alcuni campi è possibile definire il binding ai valori dei gruppi e semplificare la lettura delle informazioni. Il binding viene applicato ai livelli. È consigliabile definire il binding quando è presente una possibilità di valori diversi.

* **Misura** - Le misure più frequenti sono la somma, la media, il massimo, il minimo, la deviazione standard, ecc. Le misure possono essere calcolate: ad esempio, il tasso di accettazione di un&#39;offerta è il rapporto tra il numero di volte in cui è stata presentata rispetto al numero di volte in cui è stata accettata.
