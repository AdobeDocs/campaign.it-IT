---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 33%
---
# GetTrackingInfo

Consente a un server di reindirizzamento remoto di scaricare le informazioni relative a un’azione di consegna.

```text
XML document = GetTrackingInfo ( String instance, String dbId, String deliveryId )
```

## Parametri

Nome istanza **istanza**

**dbId** Identificatore di database per il cliente che esegue una consegna

**deliveryId** ID consegna.

## Valore/i restituito/i

**documento** Documento contenente le informazioni di tracciamento per questa consegna

## Funzioni

**Schema:** [nms:remoteTracking](s-nms-remotetracking.md)

**Statico:**

Sì
