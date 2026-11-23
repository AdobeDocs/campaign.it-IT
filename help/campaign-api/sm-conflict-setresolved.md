---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 5%
---
# SetResolved

Dichiara che un&#39;entità non presenta più conflitti.

```text
SetResolved ( String conflictId )
```

## Parametri

**conflittoId** Identificatore di conflitto.

## Valore/i restituito/i

Nessuno.

## Osservazioni

Quando tutti i conflitti vengono risolti, questo metodo consente di riportare l&#39;entità nella posizione normale. Prima di richiamare questo metodo, è necessario risolvere tutti gli attributi e gli elementi in conflitto.

## Funzioni

**Schema:** [xtk:conflict](s-xtk-conflict.md)

**Statico:**

Sì
