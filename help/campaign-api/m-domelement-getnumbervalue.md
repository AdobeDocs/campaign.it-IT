---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 16%
---
# getNumberValue

Restituisce il valore del nodo digitale a cui fa riferimento l&#39;XPath specificato.

```text
getNumberValue (xpath)
```

## Parametri

Percorso **xpath**.

## Valore restituito

Il valore digitale corrisponde al nodo a cui si fa riferimento.

## Osservazioni

La sintassi per XPath accetta solo un sottoinsieme di linguaggio XPath. Viene generata un&#39;eccezione se il formato del percorso non è corretto o se il valore non è un numero valido.

## Funzioni

**Metodo di classe:** [DOMElement](c-domelement.md)

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
