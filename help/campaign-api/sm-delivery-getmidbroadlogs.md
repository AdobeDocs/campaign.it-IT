---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 15%
---
# GetMidBroadLogs

Recupera i registri di consegna modificati per ultimi in modalità mid-sourcing.

```text
[ XML result, Date nextDate ] = GetMidBroadLogs ( Date startDate, Number logCount, Date emitterDate )
```

## Parametri

**startDate** Recupera i registri modificati a partire da questa data (sul server di mid-sourcing).

**logCount** Numero massimo di registri da recuperare, purché non siano stati aggiornati nello stesso secondo.

**emitterDate** Data di riferimento dal server di emissione. Utilizzato per regolare le date del registro di consegna.

## Valore/i restituito/i

**risultato** Documento di output, elenco dei registri di consegna.

**nextDate** Data del primo registro recuperato (successiva a startDate).

## Funzioni

**Schema:** [nms:delivery](s-nms-delivery.md)

**Statico:**

Sì
