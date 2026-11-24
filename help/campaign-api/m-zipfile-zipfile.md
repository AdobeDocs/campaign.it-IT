---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 17%
---
# FileZip

> Avvertenza:
>
> L&#39;accesso tramite API di file è limitato alle cartelle **var**, **sftp** e temporanee di Adobe Campaign.

Crea un nuovo oggetto ZIP associato a un file.

```text
ZipFile (filename)
```

## Parametri

**nomefile** Nome dell&#39;archivio da caricare o creare.

## Valore restituito

Nessuno.

## Osservazioni

Esempio:

```javascript
var zip = new ZipFile("/tmp/archive.zip")
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
