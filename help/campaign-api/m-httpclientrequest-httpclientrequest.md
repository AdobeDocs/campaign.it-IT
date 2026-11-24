---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 20%
---
# HttpClientRequest

Crea un nuovo oggetto per eseguire una query client HTTP.

```text
HttpClientRequest ( [URL ])
```

## Parametri

**URL** URL del destinatario della query.

## Valore restituito

Nessuno.

## Osservazioni

Se il comando FTP ha esito negativo, viene generata un&#39;eccezione. Esempio:

```javascript
var http = new HttpClientRequest("http://www.somewhere.com/login")

var buffer = new MemoryBuffer()
buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"

http.method = "SEARCH"
http.body = "<xml>any content</xml>"

http.execute()
       
```

## Funzioni

**Metodo di classe:** [HttpClientRequest](c-httpclientrequest.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
