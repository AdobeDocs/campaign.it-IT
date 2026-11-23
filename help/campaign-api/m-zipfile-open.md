---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 12%
---
# apri

Carica un archivio esistente.

```text
open ()
```

## Parametri

Nessuno.

## Valore restituito

Nessuno.

## Osservazioni

Nel caso di un archivio esistente, devi prima chiamare il metodo ⌐[fileCount](p-zipfile-filecount.md) per recuperare il numero di file oppure [getEntry()](m-zipfile-getentry.md) per estrarre un file. Il metodo genera un&#39;eccezione se il file non esiste o se non è un archivio valido.

## Funzioni

**Metodo di classe:** [ZipFile](c-zipfile.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
