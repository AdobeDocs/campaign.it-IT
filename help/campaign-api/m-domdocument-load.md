---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 13%
---
# carica

> Avvertenza:
>
> L&#39;accesso tramite API di file è limitato alle cartelle **var**, **sftp** e temporanee di Adobe Campaign.

Crea un nuovo documento da un file XML.

```text
load (filename [, allowEmpty ])
```

## Parametri

**nomefile** Nome del file da caricare.

**allowEmpty** Se true, non genera un&#39;eccezione se il file è vuoto (default=false).

## Valore restituito

Nessuno.

## Osservazioni

Viene generata un&#39;eccezione se il file non può essere caricato o se il contenuto del file non è un documento XML valido. Questa funzione si applica alla classe DOMDocument. Esempio:

```javascript
var doc = DOMDocument.load("data/test.xml")
```

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
