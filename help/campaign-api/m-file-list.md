---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 11%
---
# list

Elenca il contenuto di una directory.

```text
list ( [mask ] [, sort ] [, noCase ])
```

## Parametri

**mask** La maschera di ricerca (\* per impostazione predefinita).

**sort** true per ordinare il risultato (false per impostazione predefinita).

**noCase** true per ignorare la classe durante l&#39;ordinamento (false per impostazione predefinita).

## Valore restituito

Tabella contenente l&#39;elenco dei file ( [File](c-file.md) ) che corrispondono al percorso e alla maschera specificati.

## Osservazioni

Il nome della directory deve terminare con / in Linux e \\ in Windows. Esempio:

```javascript
var dir = new File("c:\\temp\\")
var files = dir.list("*.*")
for each (var file in files)
  logInfo(file.name)
```

## Funzioni

**Metodo di classe:** [File](c-file.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
