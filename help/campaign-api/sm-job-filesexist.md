---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 33%
---
# FileEsistente

Verifica se i file esistono già sul server (come file o nella tabella delle risorse).

```text
XML exist = FilesExist ( XML files )
```

## Parametri

**file** Elenco di file (@name) e relative chiavi MD5 (@md5) e booleano che indica se può essere una risorsa (@checkResource).

## Valore/i restituito/i

**esiste** Elenco dei risultati (@md5 e @exists)

## Funzioni

**Schema:** [xtk:job](s-xtk-job.md)

**Statico:**

Sì
