---
title: Guardrail di Campaign v8
description: Guardrail di Campaign v8
feature: Configuration
role: User
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
TQID: https://experienceleague.adobe.com/4FF81xd4CiMT3fusDRU32n0-ap16O1RVUEhGIbz33Os
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 265
ht-degree: 78%

---

# Guardrail del prodotto{#guardrails}

I diritti, le limitazioni del prodotto e i guardrail relativi alle prestazioni sono elencati nella [pagina di descrizione del prodotto Adobe Campaign Managed Cloud Services](https://helpx.adobe.com/it/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Di seguito sono riportati ulteriori guardrail e limitazioni relativi all’utilizzo di [!DNL Adobe Campaign].

I guardrail e le limitazioni identificano le funzionalità, l’architettura o i processi non supportati dall’attuale versione del prodotto o che non vi interagiscono correttamente. Esamina attentamente queste limitazioni.

* Adobe Campaign v8 non è disponibile per le implementazioni on-premise o ibride; questa versione è rilasciata solo come Managed Cloud Service, gestito da Adobe.
* Per i clienti attuali non è disponibile la migrazione automatica ad Adobe Campaign v8
* Nel contesto di un’[implementazione Enterprise (FFDA)](../../v8/architecture/enterprise-deployment.md), non viene fornita alcuna replica bidirezionale dei dati: la replica viene eseguita solo dal database locale di Campaign al database cloud.
* Le funzionalità elencate in [questa sezione](v7-to-v8.md#gs-unavailable-features) non sono disponibili nella build corrente di Campaign v8.
* Alcune funzioni non disponibili o rimosse risultano ancora visibili nell’interfaccia utente.
* Nel contesto di un’[implementazione Enterprise (FFDA)](../architecture/enterprise-deployment.md) i meccanismi di abbonamento (opt-in), annullamento dell’abbonamento (opt-out) e registrazione mobile sono processi asincroni. Le richieste vengono elaborate ogni ora, mediante un flusso di lavoro tecnico specifico. [Ulteriori informazioni](../architecture/replication.md#tech-wf)
* Nel contesto di una distribuzione [Enterprise (FFDA)](../architecture/enterprise-deployment.md), i duplicati devono essere gestiti manualmente dagli utenti finali. [Ulteriori informazioni](../architecture/keys.md)
* Adobe Campaign v8 non supporta la velocità di elaborazione estesa nelle applicazioni API e web; in caso di esigenze specifiche, contatta Adobe per ottenere assistenza
* Nel contesto di una distribuzione [Enterprise (FFDA)](../architecture/enterprise-deployment.md), il modulo di ottimizzazione di Adobe Campaign Campaign non tiene conto delle consegne pianificate nelle regole di tipologia di pressione. Per ulteriori informazioni, consulta [questa pagina](../../automation/campaign-opt/pressure-rules.md)