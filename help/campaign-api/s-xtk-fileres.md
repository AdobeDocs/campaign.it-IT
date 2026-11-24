---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 56%
---
# fileRes

Risorsa di file memorizzata sul server o nel database

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [PubblicazioneFile](sm-fileres-filepublishing.md) | Pubblica le risorse pubbliche sui server frontali. |
| [GetPublicFileResURL](sm-fileres-getpublicfileresurl.md) | Ottiene l’URL della cartella |
| [GetServerFileName](sm-fileres-getserverfilename.md) | Restituisce il nome del file sul server dopo averlo copiato, se necessario, nella cartella di caricamento. |
| [GetURL](sm-fileres-geturl.md) | Ottiene l’URL del file |
| [PostUpload](sm-fileres-postupload.md) | Elaborazione post-caricamento a seconda del tipo di archiviazione definito. |
| [PreDownload](sm-fileres-predownload.md) | Prepara il download della risorsa in base al tipo di archiviazione definito. |
| [PublishIfNeeded](sm-fileres-publishifneeded.md) | Copia il file sui server multimediali, se necessario |
| [PublishIfNeededFromId](sm-fileres-publishifneededfromid.md) | Copia il file sui server multimediali, se necessario, utilizzando l’ID della risorsa |
| [WebPostUpload](sm-fileres-webpostupload.md) | Completa l’archiviazione della risorsa dopo il caricamento (da una pagina web) sul server, a seconda del tipo di archiviazione utilizzata. Recupera la tabella codici e il tipo di contenuto. |

## Metodi generici

| Elemento “method” | Descrizione |
| --- | --- |
| [crea](f-create.md) | Crea una nuova entità corrispondente a uno schema specificato. |
| [carica](f-load.md) | Carica e restituisce un&#39;entità corrispondente a uno schema e a una chiave specifici. |
| [salva](m-entity-save.md) | Salva un&#39;entità nel database. |
