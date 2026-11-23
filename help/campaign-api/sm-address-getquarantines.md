---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 10%
---
# GetQuarantines

Recupera le ultime quarantene e le uscite dalla quarantena.

```text
[ XML result, Date nextDate, Boolean hasMore ] = GetQuarantines ( Date startDate, String pointerName, Number quarantineCount, Date callerDate )
```

## Parametri

**startDate** Recupera le quarantene modificate da questa data. Se vuoto, viene utilizzato il valore del puntatore.

**pointerName** Recupera le quarantene modificate dopo questo puntatore (facoltativo).

**quarantineCount** Numero massimo di quarantene da recuperare, a condizione che non siano state aggiornate durante lo stesso secondo.

**callerDate** Data di riferimento del chiamante. Consente di modificare la data di quarantena referenziale (facoltativo).

## Valore/i restituito/i

**risultato** Documento di output, elenco di quarantene.

**nextDate** Data della prima quarantena non recuperata (notevolmente superiore a startDate).

**hasMore** In tal caso, sono ancora presenti quarantene da recuperare.

## Funzioni

**Schema:** [nms:address](s-nms-address.md)

**Statico:**

Sì
