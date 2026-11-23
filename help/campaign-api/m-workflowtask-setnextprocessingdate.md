---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 5%
---
# setNextProcessingDate

Forza la successiva data di elaborazione da parte dell’attività.

```text
setNextProcessingDate (timestamp)
```

## Parametri

**timestamp** Data di elaborazione successiva. Se vuoto, l’elaborazione successiva sarà immediata.

## Valore restituito

Nessuno.

## Osservazioni

* L’utilizzo di questo metodo sostituisce la data di elaborazione successiva se fornita dal modulo di pianificazione.
* L&#39;elaborazione successiva viene sempre eseguita dalla funzione \*\_recall().

## Funzioni

**Metodo di classe:** [WorkflowTask](c-workflowtask.md)

**Disponibile in:**

* Flusso di lavoro
