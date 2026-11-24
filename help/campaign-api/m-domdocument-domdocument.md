---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 33%
---
# DOMDocument

Crea un nuovo documento.

```text
DOMDocument (name [, namespaceURI ])
```

## Parametri

**name** Nome documento.

**namespaceURI** URI spazio dei nomi documento.

## Valore restituito

Nessuno.

## Osservazioni

Esempio:

```javascript
var doc = new DOMDocument("test")
var doc2 = new DOMDocument("html", "http://www.w3.org/1999/xhtml")
```

## Funzioni

**Metodo di classe:** [DOMDocument](c-domdocument.md)

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
