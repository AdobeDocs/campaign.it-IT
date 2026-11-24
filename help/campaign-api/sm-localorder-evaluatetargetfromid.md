---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 5%
---
# EvaluateTargetFromId

Valuta il targeting della campagna per ogni consegna di campagna collegata a un ordine. Questa valutazione verrà eseguita quando si ordinano i diritti dell’operatore e prima della creazione della campagna locale.

```text
XML result = EvaluateTargetFromId ( Number orderId )
```

## Parametri

**orderId** ID ordine.

## Valore/i restituito/i

**risultato** Risultato dei conteggi per ciascuna consegna della campagna.

## Funzioni

**Schema:** [nms:localOrder](s-nms-localorder.md)

**Statico:**

Sì
