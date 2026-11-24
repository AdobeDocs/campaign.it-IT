---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 19%
---
# intestazione

Oggetto contenente tutte le intestazioni HTTP.

```text
header
```

## Osservazioni

Il nome delle proprietà non fa distinzione tra maiuscole e minuscole. Esempio:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
for(var i in response.header)
  logInfo("header[" + i + "] => " + response.header[i])
    
```

Per ripristinare più intestazioni con lo stesso nome, utilizza la proprietà [headers](p-httpclientresponse-headers.md) anziché la proprietà header.

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
