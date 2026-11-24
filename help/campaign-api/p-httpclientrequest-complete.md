---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 9%
---
# completo

Funzione da richiamare al termine di una query asincrona.

```text
complete
```

## Osservazioni

La funzione deve accettare tre argomenti:

* La query
* Il contesto
* Lo stato: &quot;success&quot;, &quot;error&quot; o &quot;timeout&quot;

Lo stato &quot;success&quot; indica che è stata ricevuta una risposta, ma la risposta può avere qualsiasi codice (200, 404, 503, ecc.). Lo stato di &quot;errore&quot; può indicare un’interruzione della comunicazione di una risposta mal strutturata. Lo stato di &quot;timeout&quot; indica che non è stato possibile stabilire la connessione o che non è stata ricevuta alcuna risposta entro la scadenza configurata. Esempio:

```javascript
http.complete = function(req, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + req.response.code)
}
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
