---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 25%
---
# sha1

Calcola la firma SHA-1 del contenuto MemoryBuffer.

```text
sha1 ()
```

## Parametri

Nessuno.

## Valore restituito

Stringa di caratteri che rappresenta esadecimalmente la firma SHA-1.

## Osservazioni

Esempio:

```javascript
var memBuf = new MemoryBuffer();
memBuf.fromString("Hello world", "utf-8");
logInfo(memBuf.sha1()); // Writes down  => 7b502c3a1f48c8609ae212cdfb639dee39673f5e
```

## Funzioni

**Metodo di classe:** [MemoryBuffer](c-memorybuffer.md)

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
