---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 23%
---
# hasRight

Verifica se l’operatore dispone di un diritto denominato specifico.

```text
hasRight (name)
```

## Parametri

**nome** Nome corretto.

## Valore restituito

True se l&#39;operatore dispone di questo diritto.

## Osservazioni

Esempio:

```javascript
      var hasAdminRight = application.operator.hasRight("admin")
```

## Funzioni

**Metodo di classe:** [CurrentOperator](c-currentoperator.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
