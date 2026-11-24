---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 9%
---
# connetti

Apre la connessione HTTP e passa l&#39;oggetto in modalità keep-alive

```text
connect ( [hasProxy ] [, async ])
```

## Parametri

**hasProxy** Boolean su true se è necessario utilizzare un HTTP proxy. Per impostazione predefinita, è impostato su false.

**async** Boolean impostato su true se la connessione è destinata a eseguire una query asincrona. Impostare su false per impostazione predefinita.

## Valore restituito

Nessuno.

## Osservazioni

Se la connessione HTTP non riesce, viene generata un&#39;eccezione. La proprietà di risposta diventa valida solo dopo una chiamata riuscita alla funzione di esecuzione. Non dimenticare di chiamare disconnect() al termine della connessione. Esempio:

```javascript
// Mistake with the hostname gogle instead of google
var badHttp = new HttpClientRequest("www.gogle.fr");
try {
  badHttp.connect();
} catch (e) {
  // Here an exception has been raised
}

var goodHttp = new HttpClientRequest("www.google.fr");
try {
  goodHttp.connect();
} catch (e) {
  // No exeception raised
}
...
goodHttp.disconnect();
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
