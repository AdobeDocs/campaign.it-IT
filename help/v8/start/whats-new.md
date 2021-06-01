---
product: Adobe Campaign
title: Novità di Campaign v8
description: Ulteriori informazioni sulle funzionalità principali
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 62%

---

# Novità di Adobe Campaign v8 {#ac-gs-what-is-new}

Adobe Campaign v8 offre notevoli miglioramenti a livello di infrastruttura, sicurezza, recapito messaggi e monitoraggio. Sfruttando [[!DNL Snowflake]](https://www.snowflake.com/), una tecnologia di database cloud, Adobe Campaign ne migliora notevolmente la scala e la velocità, con la possibilità di gestire un numero più significativo di profili cliente, oltre a tassi di consegna e transazioni all’ora molto più elevati.

Le funzionalità principali includono:

* **Velocità e scalabilità**. Adobe Campaign v8 sfrutta Cloud Database Manager, consentendo l’esecuzione di query fino a 200 volte più veloci, con scalabilità multi-petabyte, un numero maggiore di messaggi all’ora, messaggi transazionali fino a 20M/ora o 1M/ora e con la gestione di fino a 200M profili attivi, con il potenziale per raggiungerne 1B.

* **Connessioni ad Adobe Experience Platform**. Adobe Campaign v8 supporta i connettori dati con Adobe Experience Platform/RT-CDP, il profilo cliente unificato e l’integrazione nativa con Journey Orchestration. Questi investimenti ottimizzano la customer experience di Adobe Campaign e consentono nuovi casi d’uso, come la possibilità di aggiungere percorsi del cliente personalizzati in tempo reale alle campagne.

* **Cloud Services gestiti**. Adobe Campaign v8 è disponibile come Cloud Services gestito best-in-class; fornisce supervisione proattiva, avvisi tempestivi e governance dei servizi. Il valore per l’addetto al marketing è una gestione delle campagne cross-channel più agile e scalabile.

>[!CAUTION]
>
>Per il momento, Campaign v8 è **disponibile solo** come Cloud Service gestito e non può essere distribuito in ambienti on-premise o ibridi.
>
>La migrazione da un ambiente Campaign Classic v7 esistente non è ancora disponibile.
>
>Se non sei sicuro del modello di distribuzione o hai domande, contatta il team del tuo account.


## Scalabilità

Campaign v8 porta la scala end-to-end in qualsiasi fase del processo, dal targeting al reporting finale:

* Scalabilità del volume di dati gestibile (fino a 8 TB)
* Scalabilità delle prestazioni delle query per la segmentazione e il targeting, oltre che per l’acquisizione e l’uscita dei dati
* Scala la preparazione della consegna (da ore a minuti)

## Semplificazione e aumento delle prestazioni

Campaign v8 introduce il concetto di **Federated Data Access (FDA) completo**: adesso tutti i dati sono remoti, nel Cloud Database.

Con questa nuova architettura, Campaign v8 semplifica la gestione dei dati: sul database cloud non è richiesto alcun indice. È sufficiente creare le tabelle, copiare i dati e iniziare.

[!DNL Snowflake] è il database di Campaign Cloud, ti porterà velocità e resistenza: nessun sovraccarico dei picchi di attività del sistema.

La tecnologia del database Cloud non richiede una manutenzione specifica per garantire la qualità del servizio.

## Ecosistema integrato

Puoi integrare Campaign con una serie di potenti soluzioni di Adobe, quali: Adobe Analytics, Workfront, Journey Orchestration, Real-Time CDP e altro ancora.

Inoltre puoi configurare l’ottimizzazione del tempo di invio e il punteggio di engagement predittivi con IA per la gestione dei percorsi cliente, nonché aumentare i tassi di apertura, i clic e i ricavi.

[!DNL :bulb:] [Ulteriori informazioni sulle integrazioni di Campaign](../connect/integration.md)

