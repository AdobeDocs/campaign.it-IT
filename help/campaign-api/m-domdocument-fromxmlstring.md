---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 20%
---
# fromXMLString

Crea un nuovo documento da una stringa di caratteri XML.

```text
fromXMLString (string)
```

## Parametri

**stringa** Stringa di caratteri XML.

## Valore restituito

Nessuno.

## Osservazioni

Se l&#39;argomento non è un documento XML valido, viene generata un&#39;eccezione. Questa funzione si applica alla classe DOMDocument. Esempio:

```javascript
var doc = DOMDocument.fromXMLString(
    '<?xml version="1.0" encoding="ISO-8859-1"?>' +
    '<form name="address" namespace="nms" colcount="2"/>')
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
