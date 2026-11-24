---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 16%
---
# ExportPreview

Calcola l’anteprima della colonna del file di output per le prime righe della query

```text
[ XML resultColumns, XML resultXML, String resultSQLRequest ] = ExportPreview ( XML dataTransferStep, Number lineCount, Boolean countMode, String calcFieldName )
```

## Parametri

**trasferimento dati** Passaggio di trasferimento in cui è definito il campo calcolato.

**lineCount** Numero di righe da restituire

**countMode** modalità di conteggio righe

**calcFieldName** Nome del campo calcolato osservato. Se vuota, si tratta di un’anteprima globale del file di output.

## Valore/i restituito/i

**resultColumns** Restituisce i valori delle colonne del file di esportazione (line/col/val, line/col/errors).

**resultXML** Restituisce il documento XML di output della query.

**resultSQLRequest** Restituisce la query SQL eseguita.

## Funzioni

**Schema:** [xtk:dataTransfer](s-xtk-datatransfer.md)

**Statico:**

Sì
