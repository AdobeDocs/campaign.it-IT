---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 27%
---
# enumerazioni

Restituisce la tabella che contiene l&#39;elenco di [enumerazioni](c-enumeration.md) definite in questo schema.

```text
enumerations
```

## Osservazioni

Esempio:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var e in schema.enumerations)
{
  logInfo(e.name)
}
```

## Funzioni

**Proprietà della classe:** [Schema](c-schema.md)

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
