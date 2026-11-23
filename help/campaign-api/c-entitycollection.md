---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 14%
---
# EntityCollection (classe)

Rappresenta un insieme di un&#39;entità.

Non è possibile creare un&#39;istanza diretta di un oggetto di questo tipo. È necessario utilizzare i metodi create(), get() o load().

È possibile enumerare gli elementi di una raccolta con `for` o `for each`. Questo esempio mostra un’enumerazione di file collegati a un’azione di consegna.

```text
var delivery = NLWS.nmsDelivery.load("12345") for each(var attach in delivery.attachment) logInfo(attach.label)
```

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [aggiungi](m-entitycollection-add.md) | Aggiunge una nuova entità alla raccolta. |
| [rimuovi](m-entitycollection-remove.md) | Elimina un&#39;entità dalla raccolta. |
| [removeAll](m-entitycollection-removeall.md) | Elimina tutte le entità dalla raccolta. |

## Proprietà

| Proprietà | Descrizione |
| --- | --- |
| [lunghezza](p-entitycollection-length.md) | Restituisce il numero di entità dell&#39;insieme. |

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
