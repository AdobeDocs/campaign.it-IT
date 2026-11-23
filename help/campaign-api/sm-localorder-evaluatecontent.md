---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 3%
---
# ValutaContenuto

Valuta il contenuto di una consegna collegata a un ordine. Questa valutazione verrà eseguita quando si ordinano i diritti dell’operatore e prima della creazione della campagna locale.

```text
XML result = EvaluateContent ( XML order, Number deliveryId, String contentType, Number seedMemberId )
```

## Parametri

**order** elemento contenente informazioni sull&#39;ordine.

**deliveryId** ID di consegna da valutare.

**contentType** Tipo di contenuto da restituire (html o testo per un&#39;e-mail; stringa vuota per altri canali).

**seedMemberId** ID indirizzo di seed utilizzato per la personalizzazione del contenuto.

## Valore/i restituito/i

**risultato** Contenuto valutato.

## Funzioni

**Schema:** [nms:localOrder](s-nms-localorder.md)

**Statico:**

Sì
