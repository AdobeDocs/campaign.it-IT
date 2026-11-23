---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 5%
---
# EvaluateTarget

Valuta il targeting della campagna per ogni consegna di campagna collegata a un ordine. Questa valutazione verrà eseguita quando si ordinano i diritti dell’operatore e prima della creazione della campagna locale.

```text
XML result = EvaluateTarget ( XML order )
```

## Parametri

**order** elemento contenente informazioni sull&#39;ordine.

## Valore/i restituito/i

**risultato** Risultato dei conteggi per ciascuna consegna della campagna.

## Funzioni

**Schema:** [nms:localOrder](s-nms-localorder.md)

**Statico:**

Sì
