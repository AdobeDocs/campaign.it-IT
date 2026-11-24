---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 7%
---
# SoapService (classe)

Consente di eseguire chiamate SOAP a un servizio Web.

## Blocco delle chiamate

Di seguito è riportato un esempio tipico di utilizzo: è necessario innanzitutto creare una connessione, quindi un servizio che utilizza questa connessione e infine dichiarare i metodi di SOAP per questo servizio. Il metodo SOAP viene esposto sotto forma di un metodo JavaScript dell&#39;oggetto servizio.

```text
var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0) var session = new SoapService(cnx, "xtk:session") session.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) var result = session.GetOption("admin/", "NmsBroadcast_DefaultProvider") var value = result[0] var type = result[1] logInfo("Value = " + value) logInfo("Type = " + type)
```

## Chiamate non bloccanti

È possibile eseguire chiamate non di blocco (asincrone), ovvero eseguire una query SOAP su un server e continuare l’esecuzione dello script senza attendere il risultato. Le differenze principali rispetto alla modalità di blocco sono:

* La connessione deve essere creata in modalità asincrona

* Utilizza i

  [inizio](m-soapservice-start.md)

  funzione.

* Definisci un

  [completo](p-soapservice-complete.md)

  sul servizio, da chiamare al momento della ricezione della risposta.

* Il

  [SoapService.wait](m-soapservice-wait.md)

  viene utilizzata per attendere la fine dell’elaborazione di un set di query.

Lo script di esempio seguente effettua una serie di chiamate SOAP &quot;GetOption&quot; a un server Adobe Campaign aprendo 3 connessioni contemporaneamente.

```text
var list = [ "XtkDatabaseId", "XtkKey", "WdbcTimeZone", "NmsServer_URL", "NmsBroadcast_DefaultProvider"] var requests = [] function complete(service, result, context, status) { if( status == "success" ) logInfo("option " + context + ": value = " + result[0]) else if( status == "fault" ) logInfo("option " + context + ": fault = " + result.message) else logInfo("option " + context + ": " + status) sendNext(service) } function createService() { // Create the connection var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0, true) // Create the service var service = new SoapService(cnx, "xtk:session") service.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) // Change the timeout to 5 seconds service.timeout = 5000 // Setup the callback function service.complete = complete return service } function sendNext(service) { if( list.length == 0) return // Pick an item from the list var name = list.shift() // Use the name as context var context = name // Send the request var req = service.start(context, "GetOption", "admin/", name) // Add the request to the wait queue requests.push(req) } // Open 3 connections and start a request on each one sendNext(createService()) sendNext(createService()) sendNext(createService()) SoapService.wait(requests) logInfo("Done.")
```

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [ServizioSoap](m-soapservice-soapservice.md) | Crea un servizio per richiamare le funzioni di un servizio Web. |
| [addMethod](m-soapservice-addmethod.md) | Dichiara una funzione sul servizio. |
| [elimina](m-soapservice-dispose.md) | Libera le risorse utilizzate dall&#39;oggetto. |
| [inizio](m-soapservice-start.md) | Avvia una query in modalità asincrona. |
| [attendi](m-soapservice-wait.md) | Attende la fine di un elenco di query SOAP asincrone. |

## Proprietà

| Proprietà | Descrizione |
| --- | --- |
| [completato](p-soapservice-complete.md) | Funzione da richiamare al termine di una query asincrona. |
| [intestazione](p-soapservice-header.md) | Stringa di caratteri copiata letteralmente nell’intestazione SOAP. |
| [timeout](p-soapservice-timeout.md) | Tempo di attesa massimo in millisecondi in caso di query asincrona. Se questo parametro non è definito, il tempo di attesa è di 5 minuti. |

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Messaggio di consegna
* Regola di tipologia
* Importazione
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
