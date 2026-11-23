---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 11%
---
# getUrl

Recupera un contenuto di testo da un URL.

```text
getUrl (url [, timeout ])
```

## Parametri

**url** L&#39;indirizzo della pagina da ripristinare.

**timeout** Timeout della connessione. Se non è possibile stabilire la connessione entro il ritardo specificato, viene generato un errore e lo script viene interrotto.

## Valore restituito

Una stringa di caratteri contenente la pagina di testo.

## Osservazioni

La codifica della stringa restituita è quella specificata dalla risposta (Content-Type). Se si verifica un errore durante il download o se il codice restituito è diverso da 200 (OK), viene generato un errore e lo script in esecuzione viene interrotto. Esempio:

```javascript
      var content = getUrl("http://www.google.com/index.html")
```

## Funzioni

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
