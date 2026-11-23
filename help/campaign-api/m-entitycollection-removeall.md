---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 31%
---
# removeAll

Elimina tutte le entità dalla raccolta.

```text
removeAll ()
```

## Parametri

Nessuno.

## Valore restituito

Nessuno.

## Osservazioni

Esempio:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.removeAll()
delivery.save()
```

## Funzioni

**Metodo di classe:** [EntityCollection](c-entitycollection.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
