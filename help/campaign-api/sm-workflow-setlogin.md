---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 3%
---
# SetLogin

Modifica l’account di esecuzione.

```text
SetLogin ( String workflowId, String login )
```

## Parametri

**workflowId** Identificatore o nome interno del workflow.

**accesso** Accesso dell&#39;operatore o stringa vuota se a questo flusso di lavoro non è associato alcun operatore.

## Valore/i restituito/i

Nessuno.

## Osservazioni

L’account di esecuzione associato a un flusso di lavoro consente di forzare i diritti di esecuzione a un operatore specifico anziché all’operatore che ha avviato il flusso di lavoro. L’account di esecuzione non viene propagato quando viene duplicato un flusso di lavoro.

## Funzioni

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Statico:**

Sì
