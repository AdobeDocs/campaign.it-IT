---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 6%
---
# MemoryBuffer (classe)

Rappresenta un contenuto binario memorizzato.

Un oggetto è un oggetto intermedio per la manipolazione di dati da e verso un file.

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [elimina](m-memorybuffer-dispose.md) | Libera le risorse utilizzate dall&#39;oggetto. |
| [carica](m-memorybuffer-load.md) | Carica il contenuto di un file nel buffer. |
| [salva](m-memorybuffer-save.md) | Salva il contenuto del buffer in un file. |
| [toXML](m-memorybuffer-toxml.md) | Restituisce un oggetto JavaScript XML ottenuto dal contenuto di [MemoryBuffer](c-memorybuffer.md). Funzione obsoleta. Utilizzare [toDocument()](m-memorybuffer-todocument.md) |
| [toDocument](m-memorybuffer-todocument.md) | Restituisce un documento XML dal contenuto di testo di questo buffer. |
| [toString](m-memorybuffer-tostring.md) | Restituisce il contenuto di [MemoryBuffer](c-memorybuffer.md) sotto forma di stringa di caratteri. |
| [daStringa](m-memorybuffer-fromstring.md) | Carica il contenuto di una stringa di caratteri nel buffer. |
| [aBase64](m-memorybuffer-tobase64.md) | Converte il buffer o parte della stringa di caratteri codificata in base 64. |
| [appendBase64](m-memorybuffer-appendbase64.md) | Aggiunge i dati di una stringa di caratteri codificata in base 64 alla fine del buffer. |
| [removeAll](m-memorybuffer-removeall.md) | Svuota il buffer. |
| [sha1](m-memorybuffer-sha1.md) | Calcola la firma SHA-1 del contenuto MemoryBuffer. |
| [sha224](m-memorybuffer-sha224.md) | Calcola la firma SHA-2 a 224 bit del contenuto MemoryBuffer. |
| [sha256](m-memorybuffer-sha256.md) | Calcola la firma SHA-2 a 256 bit del contenuto MemoryBuffer. |
| [sha384](m-memorybuffer-sha384.md) | Calcola la firma SHA-2 a 384 bit del contenuto MemoryBuffer. |
| [sha512](m-memorybuffer-sha512.md) | Calcola la firma SHA-2 a 512 bit del contenuto MemoryBuffer. |
| [fromHexString](m-memorybuffer-fromhexstring.md) | Carica il contenuto di una stringa esadecimale nel buffer. |
| [toHexString](m-memorybuffer-tohexstring.md) | Converte il buffer in una stringa di caratteri esadecimali. |
| [hmac](m-memorybuffer-hmac.md) | Calcola l’hash MD5, SHA-1 o SHA-256 del buffer. |

## Proprietà

| Proprietà | Descrizione |
| --- | --- |
| [dimensioni](p-memorybuffer-size.md) | Restituisce la dimensione del buffer in byte. |
| [isEmpty](p-memorybuffer-isempty.md) | Restituisce true se il buffer è vuoto. |

## Funzioni

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
