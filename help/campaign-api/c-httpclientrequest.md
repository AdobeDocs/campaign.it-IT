---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 4%
---
# HttpClientRequest (classe)

Un oggetto HttpClientRequest consente di eseguire determinate operazioni come client HTTP.

Esempio:

```text
var req = new HttpClientRequest("http://www.somewhere.com/login") var buffer = new MemoryBuffer() buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1") req.header["Authorization"] = "Basic " + buffer.toBase64() req.header["Content-Type"] = "text/xml; charset=utf-8" req.method = "SEARCH" req.body = "<xml>any content</xml>" req.execute()
```

## &quot;Keep Alive&quot;

L&#39;oggetto può essere utilizzato in due modalità diverse: standard o keep alive. La modalità Standard ti consente di inviare una singola query, la modalità keep alive ti consente di inviare diverse query mantenendo aperta la connessione. Lo stato dell&#39;oggetto dipende dalla sequenza di utilizzo del metodo. Se viene chiamato il metodo connect(), l&#39;oggetto passa alla modalità keep alive. Esempio

```text
var req = new HttpClientRequest("http://evc-cit.info/cgi-bin/cit042/timeofday.cgi") req.connect() // Now the object is in keep-alive mode, we can sand many requests using // the same connection // Request ten times the time of the cgi var i = 0 while ( i < 10 ) { req.execute() var response = req.reponse i++ } req.disconnect()
```

## Query asincrone

Le query vengono eseguite in modalità di blocco per impostazione predefinita, il che significa che

[esegui](m-httpclientrequest-execute.md)

La funzione restituisce il controllo solo una volta inviata la query e ricevuta la risposta. È inoltre possibile eseguire query in modalità asincrona. In questo caso, il

[esegui](m-httpclientrequest-execute.md)

La funzione restituisce il controllo immediatamente e una funzione verrà chiamata una volta ricevuta la risposta. Questo consente l’esecuzione simultanea di diverse query. Il seguente programma è un esempio completo che mostra come eseguire una serie di caricamenti HTTP aprendo 3 connessioni contemporaneamente, in cui ogni caricamento inizia una volta completato l’ultimo.

```text
var list = [ "http://www.adobe.com/", "http://www.google.com/", "http://www.mozilla.org/", "http://www.linux.org/", "http://www.postgresql.org/"] var requests = [] var complete = function(req, context, status) { if( status == "success" ) logInfo("Receiving " + context + ": " + req.url + ": code = " + req.response.code) else logWarning("Error " + context + ": " + req.url + ": " + status) sendNext(context) } function sendNext(context) { // Repeat until the first execute() passes while( list.length != 0 ) { // Pick one URL from the list var url = list.shift() var req = new HttpClientRequest(url) req.complete = complete try { req.execute(false, true, context, 5000) logInfo("Sending " + url) requests.push(req) return } catch(e) { // Log a message and pick up next item from list logWarning("Failed to send " + url) } } } // Start 3 requests sendNext(1) sendNext(2) sendNext(3) // Wait until all requests are completed HttpClientRequest.wait(requests) logInfo("Finished.")
```

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [HttpClientRequest](m-httpclientrequest-httpclientrequest.md) | Crea un nuovo oggetto per eseguire una query client HTTP. |
| [connetti](m-httpclientrequest-connect.md) | Apre la connessione HTTP e passa l&#39;oggetto in modalità keep-alive |
| [disconnetti](m-httpclientrequest-disconnect.md) | Chiude la connessione HTTP di un oggetto in modalità keep-alive. |
| [esegui](m-httpclientrequest-execute.md) | Esegue la query HTTP. |
| [attendi](m-httpclientrequest-wait.md) | Osserva fino alla fine di un elenco di query asincrone. |

## Proprietà

| Proprietà | Descrizione |
| --- | --- |
| [corpo](p-httpclientrequest-body.md) | Corpo della query HTTP. |
| [completato](p-httpclientrequest-complete.md) | Funzione da richiamare al termine di una query asincrona. |
| [intestazione](p-httpclientrequest-header.md) | Oggetto JavaScript contenente le intestazioni HTTP dell&#39;intestazione. |
| [metodo](p-httpclientrequest-method.md) | Il metodo HTTP, sotto forma di stringa di caratteri |
| [risposta](p-httpclientrequest-response.md) | Risposta della query HTTP. Oggetto di tipo HttpClientResponse |
| [url](p-httpclientrequest-url.md) | Indirizzo del server remoto. |

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
