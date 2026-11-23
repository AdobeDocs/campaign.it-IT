---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 5%
---
# File (classe)

Classe file

> Avvertenza:
>
> L&#39;accesso tramite API di file è limitato alle cartelle **var**, **sftp** e temporanee di Adobe Campaign.

Di seguito è riportato un esempio di come utilizzare la classe per leggere ed elaborare tutte le righe di un file in sequenza.

```javascript
var file = new File("/tmp/test.txt")
file.open()
for each(var line in file)
  logInfo(line)
file.close()
 
```

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [File](m-file-file.md) | Crea un nuovo oggetto associato a un file. |
| [chiudi](m-file-close.md) | Chiude il file. |
| [copiaIn](m-file-copyto.md) | Copia un file. |
| [elimina](m-file-dispose.md) | Libera le risorse utilizzate dall&#39;oggetto. |
| [scarica](m-file-flush.md) | Forza la scrittura sul disco |
| [elenco](m-file-list.md) | Elenca il contenuto di una directory. |
| [mkdir](m-file-mkdir.md) | Crea una directory con il percorso dell&#39;oggetto [File](c-file.md) corrente. |
| [apri](m-file-open.md) | Apre il file in modalità di lettura o scrittura. |
| [rimuovi](m-file-remove.md) | Elimina il file. |
| [rinomina](m-file-renameto.md) | Rinomina un file. |
| [readln](m-file-readln.md) | Legge una riga del file di testo. |
| [rmdir](m-file-rmdir.md) | Elimina la directory (non in cascata). |
| [writeln](m-file-writeln.md) | Scrive una riga di testo nel file. |

## Proprietà

| Proprietà | Descrizione |
| --- | --- |
| [canRead](p-file-canread.md) | Restituisce true se il file può essere letto. |
| [canWrite](p-file-canwrite.md) | Restituisce true se il file può essere modificato. |
| [esiste](p-file-exists.md) | Restituisce true se è presente un file o una cartella con questo nome. |
| [fullName](p-file-fullname.md) | Restituisce il nome del file in valore assoluto. |
| [isDirectory](p-file-isdirectory.md) | Restituisce true se il file è una directory. |
| [isFile](p-file-isfile.md) | Restituisce true se il file esiste ed è un file. |
| [isOpen](p-file-isopen.md) | Restituisce true se il file è aperto. |
| [lastModified](p-file-lastmodified.md) | Restituisce l&#39;ultima data di modifica sotto forma di oggetto Date. |
| [nome](p-file-name.md) | Restituisce il nome del file con l’estensione, ma senza il percorso. |
| [percorso](p-file-path.md) | Restituisce il percorso completo del file terminato dal separatore. |
| [dimensioni](p-file-size.md) | Restituisce la dimensione del file in byte. |

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
