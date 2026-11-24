---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 14%
---
# getElementsByTagNameNS

Restituisce l&#39;elenco di tutti gli elementi figlio con il nome specificato.

```text
getElementsByTagNameNS (namespaceURI, localName)
```

## Parametri

**namespaceURI** URI dello spazio dei nomi degli elementi cercati.

**localName** Nome degli elementi cercati.

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
