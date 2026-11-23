---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 10%
---
# list

Restituisce l&#39;elenco dei file sul server in una directory specificata.

```text
list (URL, pattern [, max ])
```

## Parametri

**URL** Indirizzo del server FTP come URL.

**pattern** File e maschera dell&#39;elenco di file da recuperare.

**max** Numero massimo di file da restituire. Se manca questo parametro, il metodo restituirà l’elenco completo dei file.

## Valore restituito

Tabella contenente i nomi di file corrispondenti al percorso e alla maschera specificati.

## Osservazioni

Se il comando FTP ha esito negativo e viene generata un&#39;eccezione. Esempio:

```javascript
var ftp = new FTP
var files = ftp.list("ftp://ftp.funet.fi/", "pub/standards/RFC/rfc*.txt", 10)
for(var i in files)
  logInfo(files[i])
ftp.dispose()
```

## Funzioni

**Metodo di classe:** [FTP](c-ftp.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
