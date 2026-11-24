---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 25%
---
# importNode

Crea una copia del nodo da un altro documento.

```text
importNode (importedNode, deep)
```

## Parametri

**importedNode** nodo Source.

**deep** true se è necessario copiare il nodo completo, altrimenti false.

## Valore restituito

Copia del nodo.

## Osservazioni

Esempio:

```javascript
var result = doc.importNode(rcpResult, true);
doc.root.appendChild(result);
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
