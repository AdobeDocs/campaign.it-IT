---
title: Paginazione
description: Scopri come eseguire le operazioni di impaginazione.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: d6ebce3c-1e84-4b3b-a68d-90df4680af64
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 1%
---
# Paginazione

Per impostazione predefinita, 25 risorse vengono caricate in un elenco.

Il parametro **_lineCount** ti consente di limitare il numero di risorse elencate nella risposta.  Puoi quindi utilizzare il nodo **next** per visualizzare i risultati successivi.

>[!NOTE]
>
>Utilizza sempre il valore URL restituito nel nodo **next** per eseguire una richiesta di impaginazione.
>
>La richiesta **_lineStart** è calcolata e deve essere sempre utilizzata all&#39;interno dell&#39;URL restituito nel nodo **next**.

<br/>

***Richiesta di esempio***

Richiesta GET di esempio per visualizzare 1 record della risorsa profilo.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Risposta alla richiesta, con il nodo **next** per eseguire la paginazione.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "John",
            "lastName":"Doe",
            "birthDate": "1980-10-24",
            ...
        }
    ],
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
        lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
    }
    ...
}
```

Per impostazione predefinita, il nodo **next** non è disponibile quando si interagisce con tabelle con grandi quantità di dati. Per poter eseguire l&#39;impaginazione, devi aggiungere il parametro **_forcePagination=true** all&#39;URL della chiamata.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>Il numero di record al di sopra dei quali una tabella viene considerata grande è definito nell&#39;opzione **XtkBigTableThreshold** di Campaign Standard. Il valore predefinito è 100.000 record.
