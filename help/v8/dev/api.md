---
title: 'Introduzione alle API di Campaign '
description: 'Introduzione alle API di Campaign '
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 94fc2739c538f3aa8b11e0ea69d08f1bfffb5d32
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 12%

---

# Introduzione a [!DNL Campaign] API{#gs-ac-api}

[!DNL Adobe Campaign] viene fornito con un set di funzioni Javascript che è possibile utilizzare:

* in Script - in [!DNL Adobe Campaign] workflow
* tramite API - da sistemi esterni

Puoi utilizzare le API JavaScript per scrivere nel database cloud di Campaign o leggere dal database:

* API specifiche per le aziende che consentono di agire su ogni oggetto: consegne, flussi di lavoro, abbonamenti e così via. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html).
* API di accesso ai dati generiche per la query dei dati del modello dati. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html).

Campaign v8 funziona con due database: un database locale per la messaggistica in tempo reale e le query unitarie dell’interfaccia utente e la scrittura tramite API e un database Cloud per l’esecuzione di campagne, il reporting, l’inserimento di dati, le query batch e l’esecuzione di flussi di lavoro.

>[!CAUTION]
>
>[!DNL Adobe Campaign] v8 viene fornito con un limite sul throughput (TPS) del nostro livello API. Se si supera il limite, si verifica un errore HTTP standard (429). In qualità di utente di Cloud Services gestiti, puoi contattare Adobe per adattare la limitazione per ogni API.

## Prerequisiti

Prima di utilizzare [!DNL Adobe Campaign] API, devi avere familiarità con i seguenti argomenti:

* JavaScript
* Protocollo SOAP
* [!DNL Adobe Campaign] modello dati

Per utilizzare le API e interagire con [!DNL Adobe Campaign], devi anche avere familiarità con il modello dati.

>[!NOTE]
>Puoi generare una descrizione completa del modello dati. Per ulteriori informazioni, consulta [questa pagina](datamodel.md).

## [!DNL Campaign] Meccanismo di staging per le API

Con [!DNL Campaign] Database cloud, le chiamate unitarie di esplosione non sono raccomandate a causa delle prestazioni (latenza e concorrenza). L&#39;operazione batch è sempre preferita. Per garantire prestazioni ottimali delle API, Campaign continua a gestire le chiamate API a livello di database locale.

![](../assets/do-not-localize/glass.png) [Il meccanismo di staging API è descritto in questa pagina](staging.md)

## Nuove API

Sono disponibili nuove API per gestire la sincronizzazione dati tra [!DNL Campaign] database locale e database cloud. È stato inoltre introdotto un nuovo meccanismo per gestire le chiamate API a livello di database locale per evitare la latenza e migliorare le prestazioni complessive.

![](../assets/do-not-localize/glass.png) [Le nuove API sono descritte in dettaglio in questa pagina](new-apis.md)

**Argomenti correlati**

* [Best practice per i modelli di dati](datamodel-best-practices.md)
