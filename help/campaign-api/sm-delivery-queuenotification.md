---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 21%
---
# NotificaCoda

Richiesta di mettere in coda una notifica con riferimento a un modello di consegna.

```text
QueueNotification ( String scenarioName, XML target )
```

## Parametri

**scenarioName** Nome interno del modello

**target** popolazione target della consegna

## Valore/i restituito/i

Nessuno.

## Osservazioni

Questa API può essere utilizzata solo nel contesto di applicazioni web/sondaggi online. A differenza di SubmitNotification, QueueNotification utilizza un thread dedicato per le notifiche in coda.

## Funzioni

**Schema:** [nms:delivery](s-nms-delivery.md)

**Statico:**

Sì
