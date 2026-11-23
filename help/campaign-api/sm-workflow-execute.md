---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 8%
---
# Esegui

Esegue immediatamente un flusso di lavoro e attende il suo completamento.

```text
XML workflow = Execute ( String workflowId, Boolean simulationMode, Boolean keepResult, Boolean logSQL )
```

## Parametri

**workflowId** Identificatore o nome interno del workflow.

**simulationMode** simulazione di esecuzione.

**keepResult** Mantieni risultati provvisori.

**logSQL** È necessario salvare una traccia degli ordini SQL?

## Valore/i restituito/i

**workflow** Il risultato dell&#39;esecuzione.

## Funzioni

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Statico:**

Sì
