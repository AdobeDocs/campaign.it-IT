---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 2%
---
# GetValidationParameters

Restituisce i parametri di un&#39;attività del flusso di lavoro in corso.

```text
XML content = GetValidationParameters ( String workflowId, String taskIdentifier )
```

## Parametri

**workflowId** Identificatore o nome interno del workflow.

**taskIdentifier** Identificatore dell&#39;attività di tipo approvazione (campo @taskIdentifier).

## Valore/i restituito/i

**content** Il documento XML contenente i parametri.

## Osservazioni

Il documento restituito contiene tutte le informazioni relative alla convalida, chi ha risposto e chi può ancora rispondere.

* Gli attributi title, creationDate, processingDate, timeout, status, abortReason e completionDate corrispondono agli attributi del task di convalida.
* isAssignee: l&#39;operatore corrente si trova nel gruppo assegnato a questa attività.
* hasResponded: l’operatore corrente ha già risposto.
* canReply: l’operatore corrente è in grado di rispondere (nessuno ha ancora risposto oppure sono autorizzate più risposte).

## Funzioni

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Statico:**

Sì
