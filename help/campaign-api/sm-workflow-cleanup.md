---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 5%
---
# Pulizia

Cancella la cronologia del flusso di lavoro.

```text
Cleanup ( String workflowId )
```

## Parametri

**workflowId** Identificatore o nome interno del workflow.

## Valore/i restituito/i

Nessuno.

## Osservazioni

Elimina tutti gli eventi elaborati, le attività completate, le attività non riuscite e i messaggi di registro. Se il flusso di lavoro è terminato, elimina anche l’avanzamento dal diagramma. Questo metodo elimina i dati che non sono più utilizzati solo dal motore del flusso di lavoro e non influisce sul comportamento del flusso di lavoro.

## Funzioni

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Statico:**

Sì
