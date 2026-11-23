---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 14%
---
# fromJXON

Crea un nuovo documento da un oggetto JXON.

```text
fromJXON (obj)
```

## Parametri

**obj** Oggetto JXON che rappresenta il documento XML da creare.

## Valore restituito

Nessuno.

## Osservazioni

Anche le funzioni che passano un DOMDocument o un DOMElement come parametro accettano direttamente un oggetto JXON. Non è necessario creare un oggetto intermedio utilizzando questa funzione. Viene generata un&#39;eccezione se l&#39;oggetto non è un oggetto JXON valido. Questa funzione si applica alla classe DOMDocument. Esempio:

```javascript
var doc = DOMDocument.fromJXON(
    {form : {name: "address", "namespace": "nms", colcount: 2}})
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
