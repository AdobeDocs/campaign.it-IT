---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 23%
---
# StoreMirrorPageInfo

Aggiunge informazioni per generare pagine mirror per un set di parti di consegna.

```text
[ Number fatalError, String fatalErrorMsg ] = StoreMirrorPageInfo ( Number deliveryId, Number partsCount, Number firstPartId, Number lastPartId )
```

## Parametri

**deliveryId** Identificatore di consegna

**partsCount** Numero di parti

**firstPartId** Identificatore prima parte

**lastPartId** Identificatore ultima parte

## Valore/i restituito/i

**fatalError** Restituisce un codice di errore che impedisce al chiamante di eseguire nuovi tentativi. In caso contrario, l’errore può essere temporaneo.

**fatalErrorMsg** Messaggio di errore associato al codice di errore &#39;fatalError&#39;.

## Funzioni

**Schema:** [nms:delivery](s-nms-delivery.md)

**Statico:**

Sì
