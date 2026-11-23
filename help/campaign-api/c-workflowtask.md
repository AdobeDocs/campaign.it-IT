---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 4%
---
# WorkflowTask (classe)

Stato di un&#39;attività del flusso di lavoro.

⌐`WorkflowTask` è una classe che non può essere creata un&#39;istanza e per la quale esiste una sola istanza accessibile nelle attività del flusso di lavoro denominate `task`.

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [setCompleted](m-workflowtask-setcompleted.md) | Contrassegna l&#39;attività come completata. |
| [postEvent](m-workflowtask-postevent.md) | Attiva una transizione. |
| [setNextProcessingDate](m-workflowtask-setnextprocessingdate.md) | Forza la successiva data di elaborazione da parte dell’attività. |
| [fineTransizione](m-workflowtask-donetransition.md) | Restituisce la transizione &quot;completata&quot; dell’attività. |
| [errorTransition](m-workflowtask-errortransition.md) | Restituisce la transizione &quot;error&quot; dell’attività. |
| [transitionByType](m-workflowtask-transitionbytype.md) | Restituisce la transizione corrispondente al tipo specificato. |
| [transitionByName](m-workflowtask-transitionbyname.md) | Restituisce le transizioni corrispondenti al nome specificato. |
| [transizioni](m-workflowtask-transitions.md) | Restituisce l’elenco delle transizioni dell’attività. |
| [attendi](m-workflowtask-wait.md) | Aspetta un segnale. |

## Funzioni

**Disponibile in:**

* Flusso di lavoro
