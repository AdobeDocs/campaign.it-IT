---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 35%
---
# Esegui

Esegue un processo in modo sincrono (in questa modalità, le informazioni sull’avanzamento e l’annullamento non sono disponibili).

```text
String id = job.Execute ( String methodName ) const
```

## Parametri

**methodName** Nome del metodo da chiamare sull&#39;entità

## Valore/i restituito/i

**id** Identificatore del processo creato (restituito anche del processo non riuscito se creato nel database)

## Funzioni

**Schema:** [xtk:job](s-xtk-job.md)

**Statico:**

No

**Costante:**

Sì

**Solo chiave:**

No
