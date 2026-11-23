---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 4%
---
# SimulateWithParameters

Avvia un flusso di lavoro in modalità simulazione e gli fornisce i parametri.

```text
SimulateWithParameters ( String workflowId, XML parameters )
```

## Parametri

**workflowId** Identificatore o nome interno del workflow.

**parametri** Parametri da passare all&#39;istanza. Questi parametri diventeranno le variabili di istanza del flusso di lavoro. Questo argomento è un elemento XML il cui nome deve essere di tipo Variable e può includere solo attributi. Esempio:

```xml
<variables foo="abc" bar="def">
```

Gli script JavaScript all’interno del flusso di lavoro possono accedere a queste variabili dall’oggetto instance.vars:

```javascript
    var foo = instance.vars.foo   // "abc"
    var bar = instance.vars.bar   // "def"
            
```

## Valore/i restituito/i

Nessuno.

## Osservazioni

Il comando viene eseguito in modo asincrono e non ha effetto immediato dopo il ritorno del metodo.

## Funzioni

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Statico:**

Sì
