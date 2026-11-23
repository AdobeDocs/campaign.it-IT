---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 6%
---
# CheckPlanningTask

Funzione interna utilizzata per controllare i sovraccarichi all’interno delle pianificazioni degli operatori di attività (restituisce &quot;true&quot; in caso di sovraccarico). Questa funzione controlla inoltre la coerenza delle pianificazioni delle attività correlate e, se necessario, le aggiorna.

```text
Boolean workloadAlert = CheckPlanningTask ( Number taskId )
```

## Parametri

**taskId** Identificatore attività.

## Valore/i restituito/i

**workloadAlert** Avviso di sovraccarico risorse

## Funzioni

**Schema:** [nms:task](s-nms-task.md)

**Statico:**

Sì
