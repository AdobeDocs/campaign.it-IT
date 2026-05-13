---
title: Recupero di abbonamenti
description: Scopri come recuperare gli abbonamenti con le API
role: Developer
level: Experienced
exl-id: 6d935074-3196-45c5-97cd-ccb7c80bbba8
TQID: https://experienceleague.adobe.com/PxFql-omcIMizY-oMBl75gfo2UmmLTanrhQqw5te--A
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
subfeature_v2: id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 200
ht-degree: 1%

---

# Recupero di abbonamenti con API {#retrieving-subscriptions-api}

## Recupero dei profili abbonati a un servizio

Questa è una procedura in due fasi.

1. Recupera l’URL degli abbonamenti per il servizio desiderato.
1. Esegui una richiesta GET sull’URL degli abbonamenti. Restituisce l’elenco degli abbonamenti al servizio, con ogni profilo associato.

>[!CAUTION]
>
>L’API REST restituisce la proprietà &quot;href&quot;, che contiene l’URL da utilizzare. <b>Utilizza sempre l&#39;URL contenuto nella risposta per effettuare la richiesta API successiva</b>.

<br/>

***Richiesta di esempio***

Esegui una richiesta GET per recuperare il servizio.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l’URL degli abbonamenti per il servizio.

```
  {
    ...
    "messageType": "email",
    "name": "SVC1",
    "subscriptions": {
                "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/"
    },
    ...
  },
```

Esegui una richiesta GET sull’URL degli abbonamenti.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Viene visualizzato l’elenco degli abbonamenti al servizio, con ogni profilo associato.

```
  {
    ...
    "service": ...,
    "serviceName": "SVC3",
    "subscriber": {
        "PKey": "<PKEY>",
        "email": "",
        "firstName": "John",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
        "lastName": "Doe",
    },
  }
```

## Recupero dei servizi a cui è abbonato un profilo

Questa è una procedura in due fasi.

1. Recupera l’URL delle sottoscrizioni per un determinato profilo.
1. Esegui una richiesta GET sull’URL. Restituisce l’elenco delle sottoscrizioni per il profilo, con ogni servizio associato.

<br/>

***Richiesta di esempio***

Esegui una richiesta GET per recuperare il profilo.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l’URL delle sottoscrizioni per il profilo.

```
  {
    ...
    "postalAddress":...,
    "preferredLanguage": "none",
    "subscriptions": {
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions/"
    },
    ...
  }
```

Esegui una richiesta GET sull’URL degli abbonamenti.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l’elenco dei servizi a cui il profilo si è abbonato.

```
  {
    ...
    "PKey": "<PKEY>",
    "created": "2017-03-03 10:54:00.363Z",
    "service": {
      "PKey": "<PKEY>",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
      "label": "Sport Newsletter",
      "name": "SVC1",
      "title": "Sport Newsletter (SVC1)"
    },
    ...
  }
```
