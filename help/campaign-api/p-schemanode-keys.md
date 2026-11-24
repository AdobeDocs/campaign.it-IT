---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '35'
ht-degree: 28%
---
# tasti

Restituisce una tabella con le definizioni delle chiavi [SchemaKey](c-schemakey.md) del nodo corrente.

```text
keys
```

## Osservazioni

Esempio:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var key in schema.root.keys)
  logInfo("Key: " + key.name + "\t is-internal: " + key.isInternal)
    
```

## Funzioni

**Proprietà della classe:** [SchemaNode](c-schemanode.md)

**Sola lettura:**

Sì

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
