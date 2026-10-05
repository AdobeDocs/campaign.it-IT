---
title: Interazione con risorse personalizzate
description: Ulteriori informazioni sulla gestione delle risorse personalizzate con API/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
TQID: 'https://experienceleague.adobe.com/w8FCKOzUXzquVrDL2R6BJkkKWN-S1BaXZ4-sKl93iRI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
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
source-wordcount: '146'
ht-degree: 0%
---
# Interazione con risorse personalizzate {#interacting-with-custom-resources}

L&#39;endpoint **/customResources** consente di esporre le risorse personalizzate di Campaign in REST. In base a questa API, è disponibile un’integrazione tra entità personalizzate ed endpoint esterni.

L’endpoint /customResources ha esattamente lo stesso comportamento dell’endpoint /profileAndServices.

Le risorse personalizzate esposte all’interno di questa API sono:

* tutte le entità non esposte in /profileAndServicesExt
* tutte le entità non collegate al profilo e, per tali entità, i figli e i nipoti.
* per impostazione predefinita, tutte le entità non collegate a nulla, nonché i relativi figli e nipoti.

>[!NOTE]
>Le risorse personalizzate disponibili in /profileAndServicesExt non sono esposte nell’API /customResources.


Di seguito è riportato un esempio per recuperare i metadati da una risorsa personalizzata:

```
GET /customResources/resourceType/<customResourceName>
```

Per eseguire una creazione, un aggiornamento o un’eliminazione, vengono utilizzati GET, POST, PATCH, DELETE.

```
POST /customResources/<customResourceName>
```
