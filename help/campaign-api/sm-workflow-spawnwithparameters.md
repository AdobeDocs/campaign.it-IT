---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 2%
---
# SpawnWithParameters

Crea un&#39;istanza del flusso di lavoro da un modello, quindi richiama il metodo [StartWithParameters](sm-workflow-startwithparameters.md) su questa istanza.

```text
Number instanceId = SpawnWithParameters ( String workflowId, XML parameters )
```

## Parametri

**workflowId** Identificatore o nome interno del modello di workflow.

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

**instanceId** Identificatore dell&#39;istanza creata dal modello.

## Osservazioni

Il comando viene eseguito in modalità asincrona e non ha un effetto immediato dopo il ritorno del metodo. Il flusso di lavoro viene avviato con l’account degli operatori chiamanti, a meno che un accesso specifico non sia collegato al modello nella tabella di accesso del flusso di lavoro, nel qual caso viene utilizzato questo accesso.

## Funzioni

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Statico:**

Sì
