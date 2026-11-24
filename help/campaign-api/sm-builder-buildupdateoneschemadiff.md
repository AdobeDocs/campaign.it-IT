---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 48%
---
# BuildUpdateOneSchemaDiff

Genera un documento che descrive le differenze tra una tabella nel database fisico e la descrizione logica di questa tabella.

```text
XML sqlSchemaDiff = BuildUpdateOneSchemaDiff ( String schemaId, Boolean useNamingConventions )
```

## Parametri

**schemaId** Identificatore schema

**useNamingConventions** Utilizza le convenzioni di denominazione SQL per calcolare i percorsi dei nuovi campi.

## Valore/i restituito/i

**sqlSchemaDiff** schema generato

## Funzioni

**Schema:** [xtk:builder](s-xtk-builder.md)

**Statico:**

Sì
