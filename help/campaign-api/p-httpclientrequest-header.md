---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 14%
---
# intestazione

Oggetto JavaScript contenente le intestazioni HTTP dell&#39;intestazione.

```text
header
```

## Osservazioni

Tutte le proprietà dell&#39;oggetto intestazione sono accessibili in modalità di lettura/scrittura e sono enumerabili. Ogni proprietario dell’oggetto intestazione è una voce nell’intestazione HTTP della query. I nomi delle proprietà non fanno distinzione tra maiuscole e minuscole (come per le intestazioni HTTP). Esempio:

```javascript
var http = new HttpClientRequest(url)

var buffer = new MemoryBuffer()
buffer.fromString(userName + ':' + password, "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"
http.header["Date"] = (new Date()).toGMTString()
//Note: http.header.Date == http.header.date

for( var i in http.header )
logInfo("header[" + i + "] => " + http.header[i])
```

## Funzioni

**Proprietà della classe:** [HttpClientRequest](c-httpclientrequest.md)

**Sola lettura:**

Sì

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
