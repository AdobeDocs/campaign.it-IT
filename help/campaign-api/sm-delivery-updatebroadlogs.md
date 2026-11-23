---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 31%
---
# UpdateBroadLogs

Aggiorna lo stato dei registri di consegna, effettua la gestione degli errori e aggiorna i contatori di consegna.

```text
UpdateBroadLogs ( Number deliveryId, XML logs, Boolean deliveryMustExist )
```

## Parametri

**deliveryId** Identificatore di consegna

**logs** Raccolta contenente i record nms:broadLog da aggiornare (è necessario specificare @id, @status, @eventDate e @lastModified)

**deliveryMustExist** Specifica se generare un errore per un identificatore di consegna non valido.

## Valore/i restituito/i

Nessuno.

## Funzioni

**Schema:** [nms:delivery](s-nms-delivery.md)

**Statico:**

Sì
