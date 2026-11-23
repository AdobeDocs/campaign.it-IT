---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 19%
---
# GetMidDeliveries

Recupera lo stato delle consegne modificate per ultime in modalità mid-sourcing.

```text
[ XML result, Date nextDate ] = GetMidDeliveries ( Date startDate, Number maxCount, Date emitterDate )
```

## Parametri

**startDate** Recupera le modifiche da questa data (sul server di mid-sourcing).

**maxCount** Numero massimo di consegne da recuperare, a condizione che non siano state aggiornate durante lo stesso secondo.

**emitterDate** Data di riferimento del server emittente. Utilizzato per adeguare le date delle consegne.

## Valore/i restituito/i

**risultato** Documento di output, elenco delle consegne aggiornato.

**nextDate** Data di inizio della chiamata successiva.

## Funzioni

**Schema:** [nms:delivery](s-nms-delivery.md)

**Statico:**

Sì
