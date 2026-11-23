---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 14%
---
# getElementsByTagNameNS

Restituisce l&#39;elenco di tutti gli elementi del documento con il nome e lo spazio dei nomi specificati.

```text
getElementsByTagNameNS (namespaceURI, localName)
```

## Parametri

**namespaceURI** URI dello spazio dei nomi.

**localName** Nome degli elementi cercati.

## Valore restituito

Tabella contenente l’elenco degli elementi.

## Osservazioni

Questo metodo crea una nuova tabella per ogni chiamata. È quindi meglio mantenere la tabella in una variabile locale anziché effettuare diverse chiamate.

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
