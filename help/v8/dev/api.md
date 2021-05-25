---
solution: Campaign v8
product: Adobe Campaign
title: Guida introduttiva alle API di Campaign
description: Guida introduttiva alle API di Campaign
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 4%

---

# Guida introduttiva alle [!DNL Campaign] API{#gs-ac-api}

[!DNL Adobe Campaign] viene fornito con un set di funzioni Javascript che è possibile utilizzare:

* in Script - nei flussi di lavoro [!DNL Adobe Campaign]
* tramite API - da sistemi esterni

Puoi utilizzare le API JavaScript per scrivere nel database cloud di Campaign o leggere dal database:

* API specifiche per le aziende che consentono di agire su ogni oggetto: consegne, flussi di lavoro, abbonamenti, ecc. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html).
* API di accesso ai dati generici per la query dei dati del modello dati. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html).

Campaign v8 funziona con due database: un database locale per la messaggistica in tempo reale e le query unitarie dell’interfaccia utente e la scrittura tramite API e un database Cloud per l’esecuzione di campagne, il reporting, l’inserimento di dati, le query batch e l’esecuzione di flussi di lavoro.

>[!CAUTION]
>
>[!DNL Adobe Campaign] v8 viene fornito con un limite sul throughput (TPS) del nostro livello API. Se si supera il limite, si verifica un errore HTTP standard (429). In qualità di utente di Cloud Services gestiti, puoi contattare Adobe per adattare la limitazione per ogni API.


## Prerequisiti

Prima di utilizzare le API [!DNL Adobe Campaign] , è necessario avere familiarità con i seguenti argomenti:

* Javascript
* Protocollo SOAP
* [!DNL Adobe Campaign] modello dati

Per utilizzare le API e interagire con [!DNL Adobe Campaign], è necessario conoscere anche il modello dati.

>[!NOTE]
>Puoi generare una descrizione completa del modello dati. Ulteriori informazioni in [questa pagina](datamodel.md).

## [!DNL Campaign] Meccanismo di staging API

Con il database [!DNL Campaign] Cloud, le chiamate unitarie non sono consigliate a causa delle prestazioni (latenza e concorrenza). L&#39;operazione batch è sempre preferita. Per garantire prestazioni ottimali delle API, Campaign continua a gestire le chiamate API a livello di database locale.

:lampadina: [Il meccanismo di gestione temporanea API è descritto in questa pagina](staging.md)

## Nuove API

Sono disponibili nuove API per gestire la sincronizzazione dati tra il database locale [!DNL Campaign] e il database Cloud. È stato inoltre introdotto un nuovo meccanismo per gestire le chiamate API a livello di database locale per evitare la latenza e migliorare le prestazioni complessive

:lampadina: [Le nuove API sono descritte in dettaglio in questa pagina](new-apis.md)

**Argomenti correlati**

* [Best practice per i modelli di dati](datamodel-best-practices.md)
