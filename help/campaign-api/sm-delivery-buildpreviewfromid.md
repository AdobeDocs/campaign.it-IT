---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 33%
---
# BuildPreviewFromId

Crea l’anteprima di un contenuto da consegnare o di una riga del file di output (in modalità esterna).

```text
[ XML preview, XML queryResult ] = BuildPreviewFromId ( Number deliveryId, XML params ) const
```

## Parametri

**deliveryId** ID consegna.

**parametri** Condizione filtro destinatario (@filter = &#39;@id = 5673&#39;), identificatore contenuto (@content = &#39;html&#39;, &#39;text&#39;, &#39;sms&#39;, &#39;webContent1&#39;, &#39;outputFile&#39;...), @targetPart = 1345686...

## Valore/i restituito/i

**preview** Restituisce tutti i parametri dell&#39;anteprima generata.

**queryResult** Restituisce i dati caricati per calcolare l&#39;anteprima.

## Esempio

```javascript
var res = nms.delivery.BuildPreviewFromId(
                           deliveryId,
                           {params: {content: "html", filter: "@id=1234"}})
var preview     = res[0]
var queryResult = res[1]
```

## Funzioni

**Schema:** [nms:delivery](s-nms-delivery.md)

**Statico:**

Sì
