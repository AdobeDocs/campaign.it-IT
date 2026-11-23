---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '34'
ht-degree: 44%
---
# GenCreateOrUpdateSchemaSequenceDDL

Genera lo script SQL utilizzato per creare o aggiornare la sequenza dello schema autoPk

```text
String sqlDDL = GenCreateOrUpdateSchemaSequenceDDL ( String schemaId, String newSequence, String oldSequence )
```

## Parametri

**schemaId** Identificatore schema

**newSequence** Nuova sequenza

**oldSequence** Sequenza precedente

## Valore/i restituito/i

Script SQL **sqlDDL**

## Funzioni

**Schema:** [xtk:builder](s-xtk-builder.md)

**Statico:**

Sì
