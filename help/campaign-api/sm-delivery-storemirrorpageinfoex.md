---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 22%
---
# StoreMirrorPageInfoEx

Aggiunge informazioni per generare pagine mirror per un set di parti di consegna.

```text
[ Number fatalError, String fatalErrorMsg ] = StoreMirrorPageInfoEx ( Number deliveryId, Boolean notification, Number partsCount, Number firstPartId, Number notificationId )
```

## Parametri

**deliveryId** Identificatore di consegna

**notifica** È una notifica?

**partsCount** Numero di parti

**firstPartId** Identificatore prima parte

**notificationId** Identificatore di notifica

## Valore/i restituito/i

**fatalError** Restituisce un codice di errore che impedisce al chiamante di eseguire nuovi tentativi. In caso contrario, l’errore può essere temporaneo.

**fatalErrorMsg** Messaggio di errore associato al codice di errore &#39;fatalError&#39;.

## Funzioni

**Schema:** [nms:delivery](s-nms-delivery.md)

**Statico:**

Sì
