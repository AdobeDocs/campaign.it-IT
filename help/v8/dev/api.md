---
title: Introduzione alle API di Campaign
description: Introduzione alle API di Campaign
feature: API
role: Developer
level: Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 14%

---

# Introduzione a [!DNL Campaign] API {#gs-ac-api}

[!DNL Adobe Campaign] viene fornito con un set di funzioni JavaScript che puoi utilizzare:

* negli script - nei flussi di lavoro [!DNL Adobe Campaign]
* tramite API - da sistemi esterni

Puoi utilizzare le API di JavaScript per scrivere nel database cloud di Campaign o leggere dal database:

* API specifiche per l’azienda che consentono di agire su ciascun oggetto: consegne, flussi di lavoro, abbonamenti e così via. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html){target="_blank"}.
* API di accesso ai dati generiche per l’esecuzione di query sui dati del modello di dati. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html){target="_blank"}.

Nella distribuzione [Enterprise (FFDA)](../architecture/enterprise-deployment.md), Campaign funziona con due database: un database locale per la messaggistica in tempo reale, le query unitarie dell&#39;interfaccia utente e le operazioni di scrittura tramite API; e un database cloud per l&#39;esecuzione della campagna, il reporting, l&#39;acquisizione dei dati, le query batch e l&#39;esecuzione dei flussi di lavoro.

>[!CAUTION]
>
>* In qualità di utente di Campaign che passa da Campaign Standard, puoi utilizzare le API REST con Campaign v8. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/get-started-apis){target="_blank"}.
>
>* A partire dalla versione 8.5.1 di Campaign, il processo di autenticazione è stato modificato in Campaign v8. Per connettersi a Campaign, gli operatori tecnici devono utilizzare Adobe Identity Management System (IMS). Scopri come eseguire la migrazione degli account tecnici esistenti in [questa nota tecnica](../../technotes/upgrades/ims-migration.md).
>
>* [!DNL Adobe Campaign] v8 viene fornito con un limite alla velocità effettiva (TPS) del livello API. Se si supera il limite, viene generato un errore HTTP standard (429). In qualità di utente di Managed Cloud Services, puoi contattare Adobe per adattare la limitazione per ogni API.
> 

## Prerequisiti {#ac-api-prerequisites}

Prima di utilizzare le API di [!DNL Adobe Campaign], è necessario avere familiarità con i seguenti argomenti:

* JavaScript
* Protocollo SOAP
* Modello dati [!DNL Adobe Campaign]

Per utilizzare le API e interagire con [!DNL Adobe Campaign], è inoltre necessario avere familiarità con il modello dati.

>[!NOTE]
>Puoi generare una descrizione completa del modello dati. Per ulteriori informazioni, consulta [questa pagina](datamodel.md).


**Argomenti correlati**

* [Best practice per i modelli di dati](datamodel-best-practices.md)
