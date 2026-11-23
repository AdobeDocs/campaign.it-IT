---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 13%
---
# loadXmlFile

> Avvertenza:
>
> L&#39;accesso tramite API di file è limitato alle cartelle **var**, **sftp** e temporanee di Adobe Campaign.

Questa funzione è obsoleta. Utilizzare [DOMDocument.load()](m-domdocument-load.md). Carica un file sotto forma di oggetto documento XML

```text
loadXmlFile (filename [, noErr ])
```

## Parametri

**nomefile** Il nome completo del file da caricare.

**noErr** Se true, nessun errore se il file è vuoto (default=false).

## Valore restituito

Un documento XML.

## Osservazioni

Questa funzione supporta il rilevamento della tabella codici del file grazie al rilevamento della distinta base e del prologo XML.

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
