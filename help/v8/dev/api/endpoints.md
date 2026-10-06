---
title: Endpoint
description: Ulteriori informazioni sugli endpoint API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
TQID: 'https://experienceleague.adobe.com/1ajh28ZpUsuyTh-qHnto3GsH4J25WSsyK7TqTjlhHfg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
    internal-label: REST API
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 9%
---
# Endpoint {#endpoints}

Gli endpoint disponibili per l’API REST di Adobe Campaign:

* **/profileAndServices**: interagire con campi predefiniti. I campi estesi non sono accessibili con questo endpoint.
* **/profileAndServicesExt**: interagire con i campi personalizzati aggiunti durante l&#39;estensione della risorsa personalizzata Profile o Services. Per ulteriori informazioni sulle risorse personalizzate, consulta [questa sezione](custom-resources.md).
* **/&lt;transactionalAPI>**: interagire con l&#39;API dei messaggi transazionali (il nome dell&#39;endpoint dell&#39;API dei messaggi transazionali dipende dalla configurazione dell&#39;istanza). Per ulteriori informazioni al riguardo, consulta [questa sezione](managing-transactional-messages.md).
* **/workflow/execution**: interagire con i flussi di lavoro. Per ulteriori informazioni al riguardo, consulta [questa sezione](controlling-a-workflow.md).

Per impostazione predefinita, le risorse principali disponibili per le API **profileAndServices** e **profileAndServicesExt** sono:

* **/profile**: interagire con i profili dal database di Campaign. Per aggiungere profili a un servizio, utilizzare l&#39;endpoint **/servizio**. Per ulteriori informazioni sui profili in Campaign, consulta la [documentazione di Campaign](https://helpx.adobe.com/it/campaign/standard/audiences/using/about-profiles.html).
* **/servizio**: gestisci i servizi di abbonamento. Per ulteriori informazioni sui servizi in Campaign, consulta la [documentazione di Campaign](https://helpx.adobe.com/it/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Tutte le altre risorse estese o create sono disponibili solo tramite API **ProfileAndServicesExt**. Per essere accessibili, devono essere collegati alla risorsa **Profilo**.
