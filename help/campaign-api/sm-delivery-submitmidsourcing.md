---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 21%
---
# SubmitMidSourcing

Invia una consegna in modalità mid-sourcing.

```text
[ Number remoteId, Number remoteMatchId ] = SubmitMidSourcing ( XML delivery, XML routingMatch, String folderName )
```

## Parametri

**consegna** Documento che rappresenta la consegna.

**routingMatch** non più utilizzato

**nomeCartella** Nome completo della cartella (nel database del mittente).

## Valore/i restituito/i

**remoteId** Identificatore della consegna nel database ricevente.

**remoteMatchId** non più utilizzato

## Funzioni

**Schema:** [nms:delivery](s-nms-delivery.md)

**Statico:**

Sì
