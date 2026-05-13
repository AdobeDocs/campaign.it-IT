---
title: Interazione con risorse personalizzate
description: Ulteriori informazioni sulla gestione delle risorse personalizzate con API/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
TQID: https://experienceleague.adobe.com/w8FCKOzUXzquVrDL2R6BJkkKWN-S1BaXZ4-sKl93iRI
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 146
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
