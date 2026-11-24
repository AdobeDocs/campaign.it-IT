---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 3%
---
# Uccidi

Interrompe incondizionatamente un flusso di lavoro.

```text
Kill ( String workflowId )
```

## Parametri

**workflowId** Identificatore o nome interno del workflow.

## Valore/i restituito/i

Nessuno.

## Osservazioni

Questo metodo è utile se non è possibile arrestare normalmente un flusso di lavoro. Ciò può verificarsi se il flusso di lavoro o un&#39;attività hanno un&#39;affinità in particolare o se il modulo wfserver gestisce questa affinità se non è più in esecuzione. In questo caso, il flusso di lavoro rimane contrassegnato come &#39;Interrompi richiesta&#39; e può essere interrotto solo dal comando Kill.

## Funzioni

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Statico:**

Sì
