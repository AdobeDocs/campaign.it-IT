---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 10%
---
# getEntry

Estrae un file dall&#39;archivio.

```text
getEntry (filename)
```

## Parametri

**nomefile** Nome del file nell&#39;archivio.

## Valore restituito

⌐ [MemoryBuffer](c-memorybuffer.md) che contiene il contenuto del file.

## Osservazioni

Per poter utilizzare questo metodo, è necessario che l&#39;archivio sia stato aperto con il metodo ⌐[open()](m-zipfile-open.md). In caso contrario, viene generata un&#39;eccezione. Esempio: nell&#39;esempio seguente il file dir/content.xml viene estratto da un archivio e salvato nella cartella /tmp/.

```javascript
var zip = new ZipFile("/tmp/archive.zip")
zip.open()

var content = zip.getEntry("dir/content.xml")
content.save("/tmp/content.xml")

zip.dispose()
content.dispose()
```

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
