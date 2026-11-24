---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 9%
---
# onTrace

Aggiunge o elimina una funzione di intercettazione dei messaggi di traccia.

```text
onTrace ( [function ])
```

## Parametri

**funzione** Funzione di intercettazione da aggiungere. Se questo parametro viene omesso, la funzione aggiunta più di recente viene eliminata.

## Valore restituito

Nessuno.

## Osservazioni

La funzione accetta un oggetto e con le seguenti proprietà come argomento:

* gravità (stringa): la gravità del messaggio (&quot;error&quot;, &quot;warning&quot;, &quot;info&quot;, &quot;status&quot;, &quot;verbose&quot;)
* type (String): il tipo di messaggio (&quot;log&quot;, &quot;wdbc&quot;, ecc.)
* message (String) - The message

La funzione è protetta contro il rientro: non intercetta i messaggi di tracciamento che ha creato. Esempio:

```javascript
var file = new File("c:/temp/trace.txt")
file.open("w")

// Add a new trace handler
application.onTrace(function(log) {
  file.writeln(log.gravity.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the trace handler
application.onTrace()

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
