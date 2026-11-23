---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 12%
---
# isEqualNode

Confronta due nodi.

```text
isEqualNode (arg)
```

## Parametri

**arg** Il secondo nodo.

## Valore restituito

true se i due nodi sono uguali, altrimenti false.

## Osservazioni

Due nodi sono uguali se vengono verificate le seguenti condizioni:

* I due nodi sono di tipo.
* Le proprietà nodeName, localName, namespaceURI, prefix e nodeValue devono essere identiche.
* I due nodi sono di tipo.
* Gli attributi devono essere uguali.
* I nodi devono essere uguali.

Poiché la normalizzazione può influire sull’uguaglianza, ti consigliamo di normalizzare prima di confrontare.

## Funzioni

**Metodo di classe:** [DOMNode](c-domnode.md)

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
