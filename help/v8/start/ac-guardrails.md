---
title: Garanzie per Campaign v8
description: Garanzie per Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: cda523168525c24ec1c976850bc336f273276ac9
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 42%

---

# Guardrail di prodotto{#guardrails}

Le autorizzazioni, le limitazioni dei prodotti e le protezioni delle prestazioni sono elencate in [Pagina di descrizione del prodotto Adobe Campaign Managed Cloud Services](https://helpx.adobe.com/it/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target=&quot;_blank&quot;}.

Di seguito sono riportate ulteriori protezioni e limitazioni durante l’utilizzo [!DNL Adobe Campaign].

Guardrail e limitazioni identificano funzionalità, architettura o processi non supportati da questa versione del prodotto o che non interagiscono correttamente con esso. Esamina attentamente queste limitazioni.

* Adobe Campaign v8 non è disponibile per le implementazioni locali o ibride; questa versione è rilasciata solo come Cloud Service gestito da Adobe
* I clienti attuali non possono eseguire la migrazione da un ambiente Adobe Campaign esistente ad Adobe Campaign v8.
* Nel contesto di un [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), non viene fornita alcuna replica bidirezionale dei dati: la replica viene eseguita solo dal database locale di Campaign al database Cloud
* Le funzionalità elencate in [questa sezione](v7-to-v8.md#gs-unavailable-features) non sono disponibili nella build corrente di Campaign v8.
* Alcune funzioni non disponibili o rimosse risultano ancora visibili nell’interfaccia utente.
* Nel contesto di un [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md)I meccanismi di abbonamento , di annullamento dell’abbonamento (opt-in) e di registrazione mobile sono processi asincroni. Le richieste vengono elaborate ogni ora, mediante un flusso di lavoro tecnico specifico. [Ulteriori informazioni](../architecture/replication.md#tech-wf)
* I duplicati devono essere gestiti manualmente dagli utenti finali. [Ulteriori informazioni](../architecture/keys.md)
* Adobe Campaign v8 non supporta la velocità effettiva estesa sulle applicazioni API e web - in caso di esigenze specifiche, contatta l’Adobe per ottenere assistenza
* Il modulo di ottimizzazione di Adobe Campaign Campaign non tiene conto delle consegne pianificate nelle regole di tipologia della pressione. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/pressure-rules.html?lang=it#setting-the-period){target=&quot;_blank&quot;}