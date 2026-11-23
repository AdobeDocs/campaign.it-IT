---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '33'
ht-degree: 9%
---
# WorkflowTransition (classe)

Rappresenta una transizione di flusso di lavoro.

Una transizione è un oggetto opaco che viene recuperato utilizzando metodi come o e che viene utilizzato per attivare la transizione di un&#39;attività.

Esempio:

```text
var done = task.doneTransition() task.postEvent(done) task.setCompleted() return 0
```

## Funzioni

**Disponibile in:**

* Flusso di lavoro
