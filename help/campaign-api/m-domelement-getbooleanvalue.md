---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 12%
---
# getBooleanValue

Restituisce il valore del nodo boleano a cui fa riferimento l&#39;XPath specificato.

```text
getBooleanValue (xpath)
```

## Parametri

Percorso **xpath**.

## Valore restituito

true se il valore di testo del nodo di riferimento è &#39;true&#39; o &#39;1&#39;, false è il valore &#39;false&#39; o &#39;0&#39;.

## Osservazioni

La sintassi per XPath accetta solo un sottoinsieme di linguaggio XPath. Il test del valore non fa distinzione tra maiuscole e minuscole. Viene generata un&#39;eccezione se il percorso non è formattato correttamente o se il valore non è un valore booleano valido.

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
