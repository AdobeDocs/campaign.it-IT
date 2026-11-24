---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 33%
---
# GetDlStatusAndLogs

Recupera gli ultimi registri dal giornale di registrazione e lo stato di consegna.

```text
[ Number deliveryState, XML returnLogs ] = GetDlStatusAndLogs ( Number deliveryId, Number lastLogId )
```

## Parametri

**deliveryId** Identificatore di consegna

**lastLogId** Identificatore dell&#39;ultima voce del diario restituita nella chiamata precedente

## Valore/i restituito/i

**deliveryState** stato consegna

**returnLogs** Messaggi di registro

## Funzioni

**Schema:** [nms:delivery](s-nms-delivery.md)

**Statico:**

Sì
