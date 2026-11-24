---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 13%
---
# AppendDeliveryPart

Aggiunge una parte a una consegna in fase di preparazione.

```text
[ Number deliveryPartId, Number fatalError, String fatalErrorMsg ] = AppendDeliveryPart ( XML deliveryPart, Boolean retry )
```

## Parametri

**deliveryPart** Documento che rappresenta la parte di consegna (o una raccolta di parti di consegna).

**riprova** Specifica se si tratta di un nuovo tentativo di inviare questa parte di consegna.

## Valore/i restituito/i

**deliveryPartId** Identificatore della parte di consegna nel database (quando non è una raccolta).

**fatalError** Restituisce un codice di errore che impedisce al chiamante di eseguire nuovi tentativi. In caso contrario, l’errore può essere temporaneo.

**fatalErrorMsg** Messaggio di errore associato al codice di errore &#39;fatalError&#39;.

## Funzioni

**Schema:** [nms:delivery](s-nms-delivery.md)

**Statico:**

Sì
