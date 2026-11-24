---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 15%
---
# setEntry

Aggiunge o aggiorna un file nell&#39;archivio.

```text
setEntry (filename, buffer)
```

## Parametri

**nomefile** Nome del file di origine.

**buffer** MemoryBuffer contenente il file.

## Valore restituito

Nessuno.

## Osservazioni

L&#39;archivio non verrà effettivamente modificato sul disco finché non verrà chiamato il metodo [save()](m-zipfile-save.md).

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
