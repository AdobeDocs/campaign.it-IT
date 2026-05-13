---
title: Risorse personalizzate
description: Ulteriori informazioni sulla gestione delle risorse personalizzate con API/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: d7b2231d-46ff-4966-9ea7-27a775e5236b
TQID: https://experienceleague.adobe.com/T-CLyTlNyyuckhraPX-rAU7TOrMfMbcZdrDcneiflg0
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 177
ht-degree: 2%

---

# Risorse personalizzate {#custom-resources}

Adobe Campaign viene fornito con un modello dati predefinito, in cui i dati vengono definiti tramite risorse diverse. Puoi arricchire il modello dati fornito estendendo le risorse per aggiungere campi personalizzati o tabelle personalizzate, ad esempio tabelle di acquisto o di prodotti.

Le risorse personalizzate sono accessibili tramite API utilizzando l&#39;endpoint **/profileAndServicesExt** e il nome della risorsa personalizzata.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>Per le risorse che non sono pronte all&#39;uso, utilizza sempre il prefisso <b>&quot;cus&quot;</b> prima del nome della risorsa.

Puoi eseguire qualsiasi operazione con risorse personalizzate, purché siano collegate alla tabella Profilo. Ad esempio, consideriamo la struttura delle tabelle seguente:

![testo alternativo](assets/cusresources.png)

In tal caso, tutte le risorse delle tabelle **Transaction**, **TransactionDetails** e **Product** sono disponibili purché siano collegate alla tabella **Profile**.

<br/>

***Richiesta di esempio***

Richiesta GET di esempio per accedere alla risorsa profileAndServicesExt estesa.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

Restituisce l’elenco di tutte le risorse personalizzate collegate. Puoi quindi utilizzare gli URL delle risorse per eseguire qualsiasi attività API descritta in questa documentazione.

```
{
"apiName": "resourceType",
"cusProduct": {
        "content": ...,
        "data": "/profileAndServicesExt/cusProduct/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusProduct/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
"cusTransaction": {
        "content": ...,
        "data": "/profileAndServicesExt/cusTransaction/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusTransaction/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
    ...
}
```
