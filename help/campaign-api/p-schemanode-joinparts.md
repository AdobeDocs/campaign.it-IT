---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 14%
---
# joinParts

Restituisce una tabella di istanze SchemaNode per le quali ogni elemento rappresenta una condizione del join.

```text
joinParts
```

## Osservazioni

Ogni elemento della tabella ha due proprietà:

* source: l’elemento che rappresenta il campo della tabella sorgente.
* destination: l’elemento che rappresenta il campo della tabella di destinazione.

Esempio:

```javascript
var schema = application.getSchema("nms:recipient")
var root = schema.root

var link = root.children.country
for each(var join in link.joinParts)
{
  logInfo("src = " + join.source.name)
  logInfo("dst = " + join.destination.name)
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
