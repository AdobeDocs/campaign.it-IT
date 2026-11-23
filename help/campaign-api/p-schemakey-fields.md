---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 27%
---
# campi

Restituisce una tabella che contiene il campo dei campi ([SchemaNode](c-schemanode.md)) della chiave.

```text
fields
```

## Osservazioni

Esempio:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var key in schema.root.keys)
{
  logInfo("Key: " + key.name)
  for each(var field in key.fields)
    logInfo("\t" + field.name + "\t" + field.type)
}
    
```

## Funzioni

**Proprietà della classe:** [SchemaKey](c-schemakey.md)

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
