---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 12%
---
# corpo

Corpo della risposta HTTP sotto forma di oggetto MemoryBuffer.

```text
body
```

## Osservazioni

La codifica del corpo della risposta è accessibile tramite la proprietà [codePage](p-httpclientresponse-codepage.md). Il corpo della risposta HTTP è fornito sotto forma di un oggetto [MemoryBuffer](c-memorybuffer.md). Tutti i metodi applicabili a un [MemoryBuffer](c-memorybuffer.md) sono quindi applicabili al corpo della risposta HTTP. Esempio:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
if( response.code != 200 )
  throw "HTTP request failed with " + response.message
var content = response.body.toString(response.codePage)
```

## Funzioni

**Proprietà della classe:** [HttpClientResponse](c-httpclientresponse.md)

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
