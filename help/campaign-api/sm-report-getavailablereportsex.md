---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 25%
---
# GetAvailableReportsEx

Recupera l’elenco dei rapporti senza cronologia, tenendo conto delle condizioni di ordinamento dei dati e della numerazione delle pagine

```text
XML reports = GetAvailableReportsEx ( String activeContext, String schema, String selection, XML where, XML orderBy, Number editionMode, Number lineCount, Number startLine, String locationName )
```

## Parametri

**activeContext** Contesto attivo (selezione, globale)

**schema** schema interessato

**selezione** ID delle entità selezionate, separati da &#39;,&#39;

**where** Filtraggio del nodo &#39;where&#39;

**orderBy** Ordinamento del nodo &#39;orderBy&#39;

**editionMode** Durante la modifica, sono visibili anche i report non pubblicati

**lineCount** numero di report da raccogliere

**startLine** Offset da applicare per la numerazione delle pagine

**nomePosizione**

## Valore/i restituito/i

**report** Elenco dei report idonei

## Funzioni

**Schema:** [xtk:report](s-xtk-report.md)

**Statico:**

Sì
