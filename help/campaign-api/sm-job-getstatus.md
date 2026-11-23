---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 4%
---
# GetStatus

Ottieni informazioni sull’avanzamento dell’elaborazione del processo. Avviso: questa API non garantisce la restituzione di un elenco di voci di registro univoche (il chiamante deve deduplicarle utilizzando il proprio ID ).

```text
[ Number status, XML returnLogs, XML properties ] = GetStatus ( String id, Number lastLogId, Number maxLogCount )
```

## Parametri

Identificatore processo **id**

**lastLogId** Identificatore dell&#39;ultima voce di registro restituita nella chiamata precedente

**maxLogCount** Numero massimo di voci di registro da inviare

## Valore/i restituito/i

**stato** stato processo

**returnLogs** Messaggi di registro

**proprietà** Proprietà (avanzamento...)

## Funzioni

**Schema:** [xtk:job](s-xtk-job.md)

**Statico:**

Sì
