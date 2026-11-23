---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 6%
---
# DeployTriggerMessageSingle

Pubblica il messaggio transazionale sulle istanze di esecuzione. Restituisce true se la pubblicazione ha esito positivo e false in caso contrario.

```text
Boolean isSuccess = DeployTriggerMessageSingle ( Number deliveryId, Boolean localPublish )
```

## Parametri

**deliveryId** ID della consegna da distribuire

**localPublish** Pubblicare solo sull&#39;istanza di controllo?

## Valore/i restituito/i

**isSuccess** Pubblicazione completata

## Funzioni

**Schema:** [nms:delivery](s-nms-delivery.md)

**Statico:**

Sì
