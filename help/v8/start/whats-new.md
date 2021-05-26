---
solution: Campaign v8
product: Adobe Campaign
title: Novità di Campaign v8
description: Ulteriori funzionalità chiave
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 0%

---

# Quali sono le novità di Adobe Campaign v8? {#ac-gs-what-is-new}

Adobe Campaign v8 offre notevoli miglioramenti a livello di infrastruttura, sicurezza, recapito messaggi e monitoraggio. Sfruttando [[!DNL Snowflake]](https://www.snowflake.com/), una tecnologia di database cloud, Adobe Campaign ne migliora notevolmente la scala e la velocità, con la possibilità di gestire un numero più significativo di profili cliente, oltre a tassi di consegna e transazioni all’ora molto più elevati.

Le funzionalità principali includono:

* **Velocità e scala**. Adobe Campaign v8 sfrutta Cloud Database Manager, consentendo l&#39;esecuzione di query fino a 200 volte più veloci, con scalabilità a più petabyte, un numero maggiore di messaggi all&#39;ora, fino a 20 M/ora o 1,5 M/ora per i messaggi transazionali e gestendo fino a 200 M profili attivi con il potenziale per raggiungere 1B.

* **Connessioni a Adobe Experience Platform**. Adobe Campaign v8 supporta i connettori dati con Adobe Experience Platform/RT-CDP, il profilo cliente unificato e l’integrazione nativa con il Journey Orchestration. Questi investimenti ottimizzeranno la customer experience di Adobe Campaign e sbloccheranno nuovi casi d’uso, come la possibilità di aggiungere percorsi di clienti in tempo reale personalizzati alle campagne.

* **Cloud Services gestiti**. Adobe Campaign v8 è disponibile come Cloud Services gestito all’avanguardia, fornendo una supervisione proattiva, avvisi tempestivi e governance dei servizi. Il valore per l’addetto al marketing è una gestione delle campagne cross-channel più agile e scalabile.

>[!CAUTION]
>
>Per il momento, Campaign v8 è **disponibile solo** come Cloud Service gestito e non può essere distribuito in ambienti on-premise o ibridi.
>
>La migrazione da un ambiente Campaign Classic v7 esistente non è ancora disponibile.


## Scala

Campaign v8 porta la scala end-to-end in qualsiasi fase del processo, dal targeting al reporting finale:

* Scala il volume di dati gestibile (fino a 8 TB)
* Scala le prestazioni delle query per la segmentazione e il targeting, ma anche l’acquisizione e l’uscita dei dati
* Scala la preparazione della consegna (da ore a minuti)

## Semplificazione e aumento delle prestazioni

Campaign v8 introduce il concetto di **Accesso completo ai dati federati** (FDA): tutti i dati sono ora remoti nel database cloud.

Con questa nuova architettura, Campaign v8 semplifica la gestione dei dati: sul database cloud non è richiesto alcun indice. È sufficiente creare le tabelle, copiare i dati e iniziare.

[!DNL Snowflake] è il database di Campaign Cloud, ti porterà velocità e resistenza: nessun sovraccarico dei picchi di attività del sistema.

La tecnologia del database Cloud non richiede una manutenzione specifica per garantire il livello di prestazioni.

## Ecosistema integrato

Puoi integrare Campaign con una serie di potenti soluzioni di Adobe, ad esempio: Adobe Analytics, Workfront, Journey Orchestration, Real-Time CDP e altro ancora.

Puoi anche configurare l’ottimizzazione predittiva del tempo di invio e il punteggio predittivo del coinvolgimento con Percorsi AI, nonché aumentare i tassi di apertura, i clic e i ricavi.

[!DNL :bulb:] [Ulteriori informazioni sulle integrazioni con Campaign](../connect/integration.md)

