---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 20%
---
# leggi

Legge una riga del file di testo.

```text
readln ()
```

## Parametri

Nessuno.

## Valore restituito

Stringa contenente la riga successiva del file o ⌐null se viene raggiunta la fine del file.

## Osservazioni

Esempio:

```javascript
var f = new File("c:/dummy.xml")
f.open("r", File.CODEPAGE_UTF8)
var line
while( line = f.readln() )
  logInfo(line)
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
