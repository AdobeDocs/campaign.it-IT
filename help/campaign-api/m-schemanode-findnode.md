---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 7%
---
# findNode

Restituisce un&#39;istanza di [SchemaNode](c-schemanode.md) o null se il nodo non esiste e il parametro mustExist è impostato su false.

```text
findNode (name [, strict ] [, mustExist ])
```

## Parametri

**name** XPath rappresenta il nome del nodo in cui eseguire la ricerca

**strict** Valore booleano che indica se (strict to false) o meno, quando il nome dell&#39;ultimo elemento nel percorso non esiste così com&#39;è, è necessario cercarlo come attributo o elemento. Per impostazione predefinita, è true.

**mustExist** Valore booleano che indica se è necessario generare un&#39;eccezione se il nodo non esiste. true per impostazione predefinita.

## Valore restituito

Restituisce un&#39;istanza [SchemaNode](c-schemanode.md) se è possibile trovare il nodo oppure null se il parametro mustExist è impostato su false.

## Osservazioni

Esempio:

```javascript
var schema = application.getSchema("nms:recipient");

logInfo("netSales: " + schema.root.findNode("@netSales"));
logInfo("merchandise/@lastPurchaseDate: " + schema.root.findNode("merchandise/@lastPurchaseDate", true, false));
```

Risultato:

```javascript
netSales: [object NodeDef]
merchandise/@lastPurchaseDate: [object NodeDef]
```

## Funzioni

**Metodo di classe:** [SchemaNode](c-schemanode.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
