---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 3%
---
# Attività di riattivazione

Forza l&#39;elaborazione anticipata di una o più attività in sospeso.

```text
WakeupTask ( String workflowId, String taskIdentifier, String activityName )
```

## Parametri

**workflowId** Identificatore o nome interno del workflow.

**taskIdentifier** Identificatore dell&#39;attività (campo @taskIdentifier) o stringa vuota per forzare l&#39;elaborazione anticipata di tutte le attività in sospeso associate a una determinata attività.

**activityName** Il nome dell&#39;attività per forzare l&#39;elaborazione anticipata di tutte le attività associate o di una stringa vuota.

## Valore/i restituito/i

Nessuno.

## Osservazioni

Se non vengono specificati né taskIdentifier né activityName, vengono prese in considerazione tutte le attività in sospeso.

## Funzioni

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Statico:**

Sì
