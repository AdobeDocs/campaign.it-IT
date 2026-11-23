---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 23%
---
# hasPackage

Verifica se un pacchetto è installato.

```text
hasPackage (name)
```

## Parametri

**name** Nome completo del pacchetto.

## Valore restituito

True se il pacchetto è installato.

## Osservazioni

Esempio:

```javascript
var hasMRM = application.hasPackage("nms:mrm")
```

## Funzioni

**Metodo di classe:** [Applicazione](c-application.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
