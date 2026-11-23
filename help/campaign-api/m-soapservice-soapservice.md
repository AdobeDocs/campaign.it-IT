---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 26%
---
# SoapService

Crea un servizio per richiamare le funzioni di un servizio Web.

```text
SoapService (cnx, namespace)
```

## Parametri

**cnx** La connessione HTTP ([HttpSoapConnection](c-httpsoapconnection.md)).

**namespace** Namespace del servizio.

## Valore restituito

Nessuno.

## Osservazioni

Esempio:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
```

## Funzioni

**Metodo di classe:** [SoapService](c-soapservice.md)

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
