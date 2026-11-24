---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%
---
# corpo

Corpo della query HTTP.

```text
body
```

## Osservazioni

L’oggetto assegnato al corpo della query viene elaborato come segue:

* undefined, null, function: non sono considerati elementi inviabili, il corpo della query HTTP è vuoto.
* number, boolean, string, XML, Object: è stato modificato in una stringa di caratteri basata sul metodo toString e codificata in base al tipo di contenuto dell&#39;intestazione HTTP.
* [MemoryBuffer](c-memorybuffer.md): il contenuto viene copiato nel corpo della query senza modifiche.

Esempio:

```javascript
var query = "Select \"urn:schemas:calendar:uid\" " // etc...
var apptRequest =
  "<g:searchrequest xmlns:g="DAV:">\n" +
  "  <g:sql>\n" +
        query +
  "  </g:sql>\n" +
  "</g:searchrequest>"
http.body = apptRequest
    
```

## Funzioni

**Proprietà della classe:** [HttpClientRequest](c-httpclientrequest.md)

**Sola lettura:**

No

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
