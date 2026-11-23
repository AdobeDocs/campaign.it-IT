---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 31%
---
# salva

Salva un&#39;entità nel database.

```text
save ()
```

## Parametri

Nessuno.

## Valore restituito

Nessuno.

## Osservazioni

Esempio:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.label = "Diffusion 12345"
delivery.save()
```

## Funzioni

**Metodo di classe:** [Entità](c-entity.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
