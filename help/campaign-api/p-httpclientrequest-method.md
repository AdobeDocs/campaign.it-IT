---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 21%
---
# metodo

Il metodo HTTP, sotto forma di stringa di caratteri

```text
method
```

## Osservazioni

Il valore di questa proprietà viene modificato sistematicamente in maiuscolo. Esempio:

```javascript
var http = new HttpClientRequest(url)
http.method = "SEARCH"
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
