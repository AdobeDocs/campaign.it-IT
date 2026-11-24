---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 16%
---
# setHeader

Specifica un&#39;intestazione HTTP.

```text
setHeader (headerName, headerValue)
```

## Parametri

**headerName** Stringa di caratteri che è il nome dell&#39;intestazione HTTP.

**headerValue** Stringa di caratteri che rappresenta il contenuto dell&#39;intestazione HTTP.

## Valore restituito

Nessuno.

## Osservazioni

Les en-têtes ainsi spécifiés prévalent sur les en-têtes par défaut lors des appels SOAP. Esempio:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/test/Service1.asmx");
var memBuf = new MemoryBuffer();
memBuf.fromString("rico:pass@word1")
cnx.setHeader("Authorization","Basic " + memBuf.toBase64());
```

## Funzioni

**Metodo di classe:** [HttpSoapConnection](c-httpsoapconnection.md)

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
