---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 17%
---
# SubmitFromModel

Invia un processo da un modello

```text
Number jobId = SubmitFromModel ( String schema, String where, String methodName, XML diff, Boolean async )
```

## Parametri

**schema** Schema del modello di processo

**where** espressione di selezione modello

**methodName** Nome del metodo da chiamare

**diff** contenuto XML da aggiungere al modello

**asincrono** Esegui invio processo asincrono

## Valore/i restituito/i

**jobId** Identificatore del processo appena creato

## Funzioni

**Schema:** [xtk:job](s-xtk-job.md)

**Statico:**

Sì
