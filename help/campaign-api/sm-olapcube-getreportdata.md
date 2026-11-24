---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 6%
---
# GetReportData

```text
XML result = GetReportData ( Number cubeId, String queryDef, Boolean selectAll, Boolean useAggregates, XML cube )
```

## Parametri

Identificatore del cubo **cubeId**. Può essere impostato su 0 se il cubo viene passato come parametro.

**queryDef** QueryDef definito nel report

**selectAll** Seleziona tutto

**useAggregates** Abilita l&#39;uso dell&#39;aggregazione

**cubo** XML che descrive il cubo.

## Valore/i restituito/i

**risultato** risultato

## Funzioni

**Schema:** [xtk:olapCube](s-xtk-olapcube.md)

**Statico:**

Sì
