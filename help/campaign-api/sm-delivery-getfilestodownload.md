---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 29%
---
# GetFilesToDownload

Restituisce l’elenco dei file trovati sul server associato alla consegna.

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number deliveryId )
```

## Parametri

**deliveryId** Identificatore di consegna

## Valore/i restituito/i

**filesToDownload** Restituisce l&#39;elenco dei file che possono essere scaricati come elemento \[properties/filesToDownload\]

**filesNotToDownload** Restituisce l&#39;elenco dei file che non possono essere scaricati come elemento \[properties/filesNotToDownload\]

## Funzioni

**Schema:** [nms:delivery](s-nms-delivery.md)

**Statico:**

Sì
