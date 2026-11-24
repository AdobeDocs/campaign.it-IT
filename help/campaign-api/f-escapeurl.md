---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 15%
---
# escapeUrl

Converte una stringa di caratteri per inserirla in un URL.

```text
escapeUrl (value)
```

## Parametri

**valore** Stringa di caratteri da convertire.

## Valore restituito

La stringa di caratteri dopo la conversione.

## Osservazioni

La funzione trasforma i caratteri non alfanumerici diversi da $-\_.\!\*&#39;(),?/:@&amp;= nel valore esadecimale corrispondente. La funzione è conforme alle specifiche RFC1738 e consente di codificare solo caratteri ISO-latini. Per codificare caratteri UTF-8, utilizzare la funzione JavaScript encodeURIComponent(). Esempio:

```javascript
escapeUrl("a#value!")               // "a%23value!"
escapeUrl("Système d'exploitation") // "Syst%E8me%20d'exploitation"
```

## Funzioni

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
