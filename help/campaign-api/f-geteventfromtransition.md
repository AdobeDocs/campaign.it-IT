---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 6%
---
# getEventFromTransition

Restituisce l’ultimo evento a cui è stata applicata una determinata transizione.

```text
getEventFromTransition (transitionName)
```

## Parametri

**transitionName** Il nome interno della transizione.

## Valore restituito

L’ultimo evento a cui è stata applicata la transizione specificata o null. L&#39;oggetto corrisponde a un&#39;entità nello schema &#39;xtk:workflowEvent&#39;.

## Funzioni

**Disponibile in:**

* Flusso di lavoro
