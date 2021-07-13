---
product: Adobe Campaign
title: Novità di Campaign v8
description: Scopri le funzionalità chiave in Campaign v8
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 100%

---

# Novità di Adobe Campaign v8 {#ac-gs-what-is-new}

Adobe Campaign v8 offre notevoli miglioramenti a livello di infrastruttura, sicurezza, recapito messaggi e monitoraggio. L’utilizzo di [[!DNL Snowflake]](https://www.snowflake.com/), una tecnologia di database cloud, migliora notevolmente la scalabilità e la velocità di Adobe Campaign, con la possibilità di gestire un numero più significativo di profili cliente e garantendo inoltre tassi di consegna e transazioni all’ora più elevati.

Le funzionalità principali includono:

* **Velocità e scalabilità**. Adobe Campaign v8 sfrutta Cloud Database Manager e offre miglioramenti quali: esecuzione delle query fino a 200 volte più veloce; scalabilità multi-petabyte; un numero maggiore di messaggi all’ora, fino a 20 mln/ora o 1 mln/ora per i messaggi transazionali; e capacità di gestire fino a 200 milioni di profili attivi, con il potenziale per raggiungerne 1 miliardo.

* **Connessioni ad Adobe Experience Platform**. Adobe Campaign v8 supporta i connettori dati con Adobe Experience Platform/RT-CDP, il profilo cliente unificato e l’integrazione nativa con Journey Orchestration. Questi investimenti ottimizzano la customer experience di Adobe Campaign e consentono nuovi casi d’uso, come la possibilità di aggiungere percorsi del cliente personalizzati in tempo reale alle campagne.

* **Cloud Services gestiti**. Adobe Campaign v8 è disponibile come Cloud Services gestito best-in-class; fornisce supervisione proattiva, avvisi tempestivi e governance dei servizi. Tutto questo offre all’addetto marketing la capacità di gestire le campagne cross-channel in modo più agile e scalabile.

>[!CAUTION]
>
>Per il momento, Campaign v8 è disponibile **solo** come Cloud Service gestito e non può essere implementato in ambienti locali o ibridi.
>
>La migrazione da un ambiente esistente di Campaign Classic v7 non è ancora disponibile.
>
>Se hai dubbi sul modello di implementazione o hai altre domande, contatta il team del tuo account.

![](assets/home-page.png)

## Scalabilità

Campaign v8 offre una scalabilità end-to-end in qualsiasi fase del processo, dal targeting alla generazione di report finale:

* Scalabilità del volume di dati gestibile (fino a 8 TB)
* Scalabilità delle prestazioni delle query per la segmentazione e il targeting, oltre che per l’acquisizione e l’uscita dei dati
* Scalabilità della preparazione della consegna (da ore a minuti)

## Semplificazione e aumento delle prestazioni

Campaign v8 introduce il concetto di **Federated Data Access (FDA) completo**: adesso tutti i dati sono remoti, nel Cloud Database.

Con questa nuova architettura, Campaign v8 semplifica la gestione dati: nel database cloud non è richiesto alcun indice. È sufficiente creare le tabelle, copiare i dati e iniziare.

[!DNL Snowflake] è il datanase cloud di Campaign che ti offre velocità e resistenza, senza il rischio di sovraccarichi per picchi di attività del sistema.

La tecnologia del database Cloud non richiede una manutenzione specifica per garantire la qualità del servizio.

## Ecosistema integrato

Puoi integrare Campaign con una serie di potenti soluzioni Adobe, quali: Adobe Analytics, Adobe Journey Orchestration, Real-Time CDP e altre ancora.

Inoltre puoi configurare l’ottimizzazione del tempo di invio e il valore di engagement, entrambi in modalità predittiva, con il servizio IA gestione percorsi, per aumentare i tassi di apertura, i clic e i ricavi.

💡 [Ulteriori informazioni sulle integrazioni di Campaign](../connect/integration.md)

