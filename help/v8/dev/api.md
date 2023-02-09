---
title: Introduzione alle API di Campaign
description: Introduzione alle API di Campaign
feature: API
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 15%

---

# Introduzione a [!DNL Campaign] API{#gs-ac-api}

[!DNL Adobe Campaign] viene fornito con un set di funzioni Javascript che è possibile utilizzare:

* in Script - in [!DNL Adobe Campaign] workflow
* tramite API - da sistemi esterni

Puoi utilizzare le API JavaScript per scrivere nel database cloud di Campaign o leggere dal database:

* API specifiche per le aziende che consentono di agire su ogni oggetto: consegne, flussi di lavoro, abbonamenti e così via. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html){target="_blank"}.
* API di accesso ai dati generiche per la query dei dati del modello dati. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html){target="_blank"}.

Tieni presente che [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), Campaign funziona con due database: un database locale per la messaggistica in tempo reale e le query unitarie dell’interfaccia utente e la scrittura tramite API e un database Cloud per l’esecuzione di campagne, il reporting, l’inserimento di dati, le query batch e l’esecuzione di flussi di lavoro.

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


**Argomenti correlati**

* [Best practice per i modelli di dati](datamodel-best-practices.md)
