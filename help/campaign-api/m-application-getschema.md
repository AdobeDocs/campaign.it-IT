---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 9%
---
# getSchema

Restituisce un mapping a uno schema di Adobe Campaign o null se lo schema non esiste.

```text
getSchema (name [, checkIfUpdated ])
```

## Parametri

**name** Nome completo dello schema.

**checkIfUpdated** Verificare se lo schema è stato aggiornato nella cache. Nessun impatto, se lo schema è già stato istanze nello script.

## Valore restituito

Un mapping di schema (fare riferimento all&#39;oggetto [Schema](c-schema.md)) o il metodo avvia un&#39;eccezione non è uno schema che coincide con il nome.

## Osservazioni

Tutti gli schemi creati in uno script rimangono allocati nella memoria fino alla fine dello script. Esempio:

```javascript
      var schema = application.getSchema("nms:recipient")
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
