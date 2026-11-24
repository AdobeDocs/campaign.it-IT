---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 2%
---
# attendi

Aspetta un segnale.

```text
wait (timeout)
```

## Parametri

**timeout** Tempo di attesa in millisecondi.

## Valore restituito

Da booleano a true se un segnale viene ricevuto prima della scadenza del tempo di attesa.

## Osservazioni

Il segnale è emesso dai metodi SOAP [Riattivazione](sm-workflow-wakeup.md) e [Attività di riattivazione](sm-workflow-wakeuptask.md). Il protocollo utilizzato (UDP) non garantisce la ricezione dei messaggi. Questo segnale è utile solo per eseguire un&#39;operazione più velocemente. Avviso: questo segnale non verrà mai ricevuto in un flusso di lavoro secondario. Esempio: di seguito è riportato un tipico esempio di utilizzo: un loop elabora le operazioni provenienti da una coda (poll()), quindi attende un certo periodo di tempo tra ogni operazione. Viene aggiunto un ulteriore ritardo per forzare la passivazione del flusso di lavoro.

```javascript
var lifetime = 30 * 60 * 1000 // 30 minutes
var frequency = 30 * 1000 // 30 seconds
var start = new Date().getTime()
while( new Date().getTime() - start < lifetime )
{
  poll()
  task.wait(frequency)
}
 
```

## Funzioni

**Metodo di classe:** [WorkflowTask](c-workflowtask.md)

**Disponibile in:**

* Flusso di lavoro
