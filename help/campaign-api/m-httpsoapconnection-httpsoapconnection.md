---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 9%
---
# HttpSoapConnection

Crea una connessione HTTP a un server SOAP.

```text
HttpSoapConnection (url [, codepage ] [, protocol ] [, async ])
```

## Parametri

**url** URL del server, incluso il percorso.

**codepage** La codifica per la serializzazione della chiamata SOAP. Questo parametro facoltativo consente di specificare la codifica dei caratteri. Per impostazione predefinita, la codifica è UTF-8. Esempio:

* iso-8859-1
* utf-8
* utf-16

**protocol** Il tipo di protocollo SOAP utilizzato. Questo parametro opzionale consente di specificare il protocollo SOAP utilizzato, che è SOAP\_11 per impostazione predefinita. Valori possibili:

* SOAP\_11: Protocollo SOAP 1.1.
* SOAP\_12: Protocollo SOAP 1.2.
* 0: protocollo SOAP interno ad Adobe Campaign.

**async** Boolean impostato su true se la connessione è destinata a eseguire una query asincrona. Impostare su false per impostazione predefinita.

## Valore restituito

Nessuno.

## Osservazioni

Esempi:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp")
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-16", HttpSoapConnection.SOAP_11)
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-8", 0)
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
