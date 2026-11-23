---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 6%
---
# onLog

Aggiunge o elimina una funzione di intercettazione per i messaggi scritti nel giornale di registrazione

```text
onLog ( [function ])
```

## Parametri

**funzione** Funzione di intercettazione da aggiungere. Se questo parametro viene omesso, la funzione aggiunta più di recente viene eliminata.

## Valore restituito

Nessuno.

## Osservazioni

La funzione aggiunta più di recente viene richiamata per prima. La funzione accetta un oggetto e con le seguenti proprietà come argomento:

* type (Number) - Il tipo di messaggio (0=error, 1=warning, 2=information, 3=status, 4=verbose)
* code (Number) - Il codice di errore (0 se non si tratta di un errore)
* object (String) - Oggetto collegato al messaggio (non utilizzato)
* message (String) - The message

La funzione deve restituire un valore booleano. Il valore true impedirà a qualsiasi funzione di intercettazione seguente di ricevere il messaggio. La funzione è protetta contro il rientro: non intercetta i messaggi che ha scritto al diario stesso. Esempio:

```javascript
var file = new File("c:/temp/log.txt")
file.open("w")

// Add a new log handler
application.onLog(function(log) {
  file.writeln(log.type.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the log handler
application.onLog()

// This message won't be caught
logInfo("Finished.")

file.close()
```

## Funzioni

**Metodo di classe:** [Applicazione](c-application.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
