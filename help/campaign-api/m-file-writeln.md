---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 25%
---
# write

Scrive una riga di testo nel file.

```text
writeln (line)
```

## Parametri

**riga** La riga di testo da scrivere.

## Valore restituito

Nessuno.

## Osservazioni

Esempio:

```javascript
var f = new File("c:/file.txt")
f.open("a")
f.writeln("line 1")
f.writeln("line 2")
f.close()
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
