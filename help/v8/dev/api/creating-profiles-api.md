---
title: Creazione di profili con API
description: Scopri come creare profili con le API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
TQID: https://experienceleague.adobe.com/ufHL-Vr8NjFpJVES61uhuTl8Xh3DqUsKmwyDkvm7J-g
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 112
ht-degree: 0%

---

# Creazione di profili con API {#creating-profiles-api}

La creazione dei profili viene eseguita con una richiesta **POST** nella risorsa profilo.

>[!CAUTION]
>
>Se si desidera associare una <b>orgUnit</b> al profilo creato, è necessario estendere la risorsa profilo a questo campo e, dopo la pubblicazione dell&#39;estensione, eseguire una richiesta POST sull&#39;endpoint <b>ProfileAndServicesExt</b>.
>
>Per ulteriori informazioni sull&#39;estensione della risorsa del profilo, consulta la <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">documentazione di Campaign</a>.

<br/>

***Richiesta di esempio***

Esempio di richiesta POST per creare un profilo con l’e-mail &quot;john.doe@mail.com&quot;.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

Restituisce il nuovo profilo creato, con l’indirizzo e-mail &quot;john.doe@mail.com&quot;.

```
{
    "PKey": "<PKEY>",
    "firstName": "John",
    "lastName":"Doe",
    "birthDate": "1980-10-24",
    "email": "john.doe@mail.com",
    ...
}
```
