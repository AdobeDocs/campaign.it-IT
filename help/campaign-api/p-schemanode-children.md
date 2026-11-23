---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 25%
---
# elementi figlio

Restituisce un oggetto per il quale ogni proprietà è un nodo figlio indicizzato dal relativo nome.

```text
children
```

## Osservazioni

Esempio:

```javascript
var schema = application.getSchema("nms:recipient")
var root = schema.root

logInfo(root.children["@firstName"].label)
logInfo(root.children.country.label)

// root.children is a map which :
//   each key is the name of the child
//   each value the corresponding SchemaNode instance
for each(var node in root.children)
{
  logInfo(node.label + " (" + node.type + ")")
}
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
