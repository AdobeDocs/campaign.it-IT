---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 22%
---
# copyTo

Copia un file.

```text
copyTo (fileName)
```

## Parametri

**fileName** Nome del file o della cartella di destinazione (deve essere il percorso completo).

## Valore restituito

Nessuno.

## Osservazioni

Esempi:

```javascript
var f = new File("c:/file.txt")
f.copyTo("c:/file2.txt")

var f2 = new File("c:/file.txt")
f2.copyTo("c:/dir/")
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
