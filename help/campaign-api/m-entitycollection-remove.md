---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 20%
---
# rimuovere

Elimina un&#39;entità dalla raccolta.

```text
remove (index|object)
```

## Parametri

**index\|object** Indice dell&#39;entità da eliminare o dell&#39;entità stessa.

## Valore restituito

Nessuno.

## Osservazioni

Esempi:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.remove(1)
delivery.save()
```

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
var attach = delivery.attachment[1]
delivery.attachment.remove(attach)
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
