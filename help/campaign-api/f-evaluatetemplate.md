---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '27'
ht-degree: 14%
---
# evaluateTemplate

Valuta un modello di JavaScript (&lt;%= ... %>).

```text
evaluateTemplate (template)
```

## Parametri

**modello** Il modello da valutare.

## Valore restituito

La stringa dopo la sostituzione delle espressioni tra &lt;% e %>.

## Osservazioni

Esempio:

```javascript
      vars.filename = evaluateTemplate(activity.filename)
```

## Funzioni

**Disponibile in:**

* Flusso di lavoro
