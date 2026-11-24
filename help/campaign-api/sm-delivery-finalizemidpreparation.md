---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 15%
---
# FinalizeMidPreparation

Completa l’analisi di una consegna in modalità mid-sourcing.

```text
[ Number fatalError, String fatalErrorMsg ] = FinalizeMidPreparation ( Number deliveryId, Number errorCode, XML properties, Boolean retry )
```

## Parametri

**deliveryId** Identificatore di consegna

**errorCode** Codice di errore restituito dall&#39;analisi nel database di marketing (il codice di errore a livello di metodo non è utilizzato per questo)

**proprietà** Proprietà di consegna da aggiornare

**riprova** Specifica se si tratta di un nuovo tentativo per la chiamata al metodo.

## Valore/i restituito/i

**fatalError** Restituisce un codice di errore che impedisce al chiamante di eseguire nuovi tentativi. In caso contrario, l’errore può essere temporaneo.

**fatalErrorMsg** Messaggio di errore associato al codice di errore &#39;fatalError&#39;.

## Funzioni

**Schema:** [nms:delivery](s-nms-delivery.md)

**Statico:**

Sì
