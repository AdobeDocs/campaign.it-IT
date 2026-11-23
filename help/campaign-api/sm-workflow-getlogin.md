---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 2%
---
# GetLogin

Restituisce informazioni dall&#39;account di esecuzione.

```text
[ Number id, String login, String cs ] = GetLogin ( String workflowId )
```

## Parametri

**workflowId** Identificatore o nome interno del workflow.

## Valore/i restituito/i

**id** Identificatore dell&#39;operatore o 0 se a questo flusso di lavoro non è associato alcun operatore.

**accesso** Accesso dell&#39;operatore o stringa vuota se a questo flusso di lavoro non è associato alcun operatore.

**cs** Stringa di descrizione dell&#39;operatore o stringa vuota se a questo flusso di lavoro non è associato alcun operatore.

## Osservazioni

L’account di esecuzione associato a un flusso di lavoro consente di forzare i diritti di esecuzione a un operatore specifico anziché all’operatore che ha avviato il flusso di lavoro. L’account di esecuzione non viene propagato quando viene duplicato un flusso di lavoro.

## Funzioni

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Statico:**

Sì
