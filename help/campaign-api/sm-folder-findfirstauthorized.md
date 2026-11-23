---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 28%
---
# FindFirstAuthorized

Trova la prima cartella idonea per l’utente corrente, che soddisfa la condizione folderFilter.

```text
XML folderEntity = FindFirstAuthorized ( String folderFilter, Boolean writeAccess, Number orgUnit )
```

## Parametri

**folderFilter** filtra le cartelle

**writeAccess** La cartella restituita deve essere scrivibile

**orgUnit** La cartella restituita deve essere compatibile con l&#39;entità organizzativa specificata

## Valore/i restituito/i

**folderEntity** Restituisce l&#39;entità della cartella associata (null corrisponde a nessuna cartella trovata)

## Funzioni

**Schema:** [xtk:folder](s-xtk-folder.md)

**Statico:**

Sì
