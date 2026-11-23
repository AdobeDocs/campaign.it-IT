---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 27%
---
# escapeXmlStr

Converte una stringa di caratteri in formato XML.

```text
escapeXmlStr (value)
```

## Parametri

**valore** Stringa di caratteri da convertire.

## Valore restituito

La stringa di caratteri dopo la conversione.

## Osservazioni

La funzione trasforma i caratteri &amp;, &lt;, > e \\&quot; nelle sequenze di escape corrispondenti:

* &amp;
* &lt; &lt;
* > >
* &quot; &amp;quot;

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
