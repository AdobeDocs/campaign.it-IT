---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 28%
---
# GetFilesToDownload

Restituisce l‘elenco dei file utilizzati da questo trasferimento e presenti sul server

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number jobId )
```

## Parametri

**jobId** Identificatore di trasferimento

## Valore/i restituito/i

**filesToDownload** Restituisce l&#39;elenco dei file che possono essere scaricati come elemento \[dataTransfer/properties/filesToDownload\]

**filesNotToDownload** Restituisce l&#39;elenco dei file che non possono essere scaricati come elemento \[dataTransfer/properties/filesNotToDownload\]

## Funzioni

**Schema:** [xtk:dataTransfer](s-xtk-datatransfer.md)

**Statico:**

Sì
