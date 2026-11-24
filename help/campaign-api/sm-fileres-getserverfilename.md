---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 51%
---
# GetServerFileName

Restituisce il nome del file sul server dopo averlo copiato, se necessario, nella cartella di caricamento.

```text
String serverFileName = fileRes.GetServerFileName ()
```

## Parametri

Nessuno.

## Valore/i restituito/i

**serverFileName** Nome completo del file sul server (vuoto se il file non viene trovato).

## Esempio

```javascript
var query = xtk.queryDef.create(
  {queryDef: {schema: "xtk:fileRes", operation: "get", 
    select: {
      node: [
      {expr: "@label"}, 
      {expr: "@originalName"}, 
      {expr: "@storageType"}, 
      {expr: "@fileName"}, 
      {expr: "@md5"}]
    }, 
    where: {
      condition: {expr: "@id = 4216"}
    }
  }})

var fileRes = xtk.fileRes.create(query.ExecuteQuery())
var sFileName = fileRes.GetServerFileName();
        
```

## Funzioni

**Schema:** [xtk:fileRes](s-xtk-fileres.md)

**Statico:**

No

**Costante:**

No

**Solo chiave:**

No
