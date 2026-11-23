---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 41%
---
# BuildUpdateSchemaDiff

Genera un documento che descrive le differenze tra la struttura di database effettiva e la relativa descrizione logica.

```text
XML sqlSchemaDiff = BuildUpdateSchemaDiff ( XML parameters, Boolean useNamingConventions )
```

## Parametri

**parametri** Aggiorna i parametri

**useNamingConventions** Utilizza le convenzioni di denominazione SQL per calcolare i percorsi dei nuovi campi.

## Valore/i restituito/i

**sqlSchemaDiff** schema generato

## Funzioni

**Schema:** [xtk:builder](s-xtk-builder.md)

**Statico:**

Sì
