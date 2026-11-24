---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 13%
---
# getElements

Restituisce l&#39;elenco degli elementi figlio con il nome specificato, appartenenti a questo elemento.

```text
getElements ( [tagName ])
```

## Parametri

**tagName** Nome degli elementi cercati. Se questo parametro viene omesso, la funzione restituisce tutti gli elementi figlio.

## Valore restituito

Tabella contenente l’elenco degli elementi.

## Osservazioni

Questo metodo crea una nuova tabella per ogni chiamata. È quindi meglio mantenere la tabella in una variabile locale anziché effettuare diverse chiamate.

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
