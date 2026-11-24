---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 14%
---
# getDateValue

Restituisce il valore di tipo data+ora del riferimento al nodo in base all&#39;XPath specificato.

```text
getDateValue (xpath)
```

## Parametri

Percorso **xpath**.

## Valore restituito

Oggetto di tipo Data corrispondente al valore del nodo a cui si fa riferimento.

## Osservazioni

La sintassi per XPath accetta solo un sottoinsieme di linguaggio XPath. Viene generata un&#39;eccezione se il percorso non è formattato correttamente o se il valore non è una data valida.

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
