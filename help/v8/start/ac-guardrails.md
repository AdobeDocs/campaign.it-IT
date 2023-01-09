---
title: Guardrail di Campaign v8
description: Guardrail di Campaign v8
feature: Overview
role: User
level: Beginner, Intermediate, Experienced
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: 58fff46ba12f5c6221bbcd88a40fa0806a6c98b9
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 95%

---

# Guardrail del prodotto{#guardrails}

I diritti, le limitazioni del prodotto e i guardrail relativi alle prestazioni sono elencati nella [pagina di descrizione del prodotto Adobe Campaign Managed Cloud Services](https://helpx.adobe.com/it/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target=&quot;_blank&quot;}.

Di seguito sono riportati ulteriori guardrail e limitazioni relativi all’utilizzo di [!DNL Adobe Campaign].

I guardrail e le limitazioni identificano le funzionalità, l’architettura o i processi non supportati dall’attuale versione del prodotto o che non vi interagiscono correttamente. Esamina attentamente queste limitazioni.

* Adobe Campaign v8 non è disponibile per le implementazioni on-premise o ibride; questa versione è rilasciata solo come Managed Cloud Service, gestito da Adobe.
* Per i clienti esistenti non è disponibile alcuna migrazione automatica ad Adobe Campaign v8
* Nel contesto di un’[implementazione Enterprise (FFDA)](../architecture/enterprise-deployment.md), non viene fornita alcuna replica bidirezionale dei dati: la replica viene eseguita solo dal database locale di Campaign al database cloud.
* Le funzionalità elencate in [questa sezione](v7-to-v8.md#gs-unavailable-features) non sono disponibili nella build corrente di Campaign v8.
* Alcune funzioni non disponibili o rimosse risultano ancora visibili nell’interfaccia utente.
* Nel contesto di un’[implementazione Enterprise (FFDA)](../architecture/enterprise-deployment.md) i meccanismi di abbonamento (opt-in), annullamento dell’abbonamento (opt-out) e registrazione mobile sono processi asincroni. Le richieste vengono elaborate ogni ora, mediante un flusso di lavoro tecnico specifico. [Ulteriori informazioni](../architecture/replication.md#tech-wf)
* I duplicati devono essere gestiti manualmente dagli utenti finali. [Ulteriori informazioni](../architecture/keys.md)
* Adobe Campaign v8 non supporta la velocità di elaborazione estesa nelle applicazioni API e web; in caso di esigenze specifiche, contatta Adobe per ottenere assistenza
* Il modulo di ottimizzazione delle campagne di Adobe Campaign non tiene conto delle consegne pianificate nelle regole di tipologia di pressione. Per ulteriori informazioni, consulta [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/pressure-rules.html?lang=it)