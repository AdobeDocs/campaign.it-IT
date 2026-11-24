---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 34%
---
# ExecuteQuery

Recuperare dati da una query

```text
XML output = queryDef.ExecuteQuery () const
```

## Parametri

Nessuno.

## Valore/i restituito/i

**output** documento XML di output

## Osservazioni

La query supporta quattro tipi di operazioni:

* seleziona
* ottenere
* getIfExists
* count

## Esempio

```javascript
var query = NLWS.xtkQueryDef.create(
  {queryDef: {schema: "xtk:workflow", operation: "select", 
    select: {
        node: [{expr: "@id"},
               {expr: "@label"},
               {expr: "@internalName"}] 
    }, 
    where: {
      condition: [{expr: "[folder/@name]='nmsTechnicalWorkflow'"},
                  {expr: "@production = 1"}]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }})

var res = query.ExecuteQuery()

var workflows = res.getElementsByTagName("workflow")
for each (var w in workflows)
  logInfo(w.getAttribute("internalName"))
        
```

## Funzioni

**Schema:** [xtk:queryDef](s-xtk-querydef.md)

**Statico:**

No

**Costante:**

Sì

**Solo chiave:**

No
