---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 5%
---
# Risposta

Risponde a un&#39;attività di tipo convalida in corso.

```text
Reply ( String workflowId, String taskIdentifier, String response, String choice )
```

## Parametri

**workflowId** Identificatore o nome interno del workflow.

**taskIdentifier** Identificatore dell&#39;attività di tipo approvazione (campo @taskIdentifier).

**risposta** Il commento associato alla risposta.

**scelta** La scelta della risposta. Questa scelta deve corrispondere al nome della transizione da attivare.

## Valore/i restituito/i

Nessuno.

## Osservazioni

L&#39;operatore corrente deve trovarsi nel gruppo assegnato all&#39;attività.

## Funzioni

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Statico:**

Sì
