---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 27%
---
# TestCalcField

Testa il campo calcolato utilizzando le righe di esempio memorizzate nello script.

```text
XML calcFieldValues = TestCalcField ( XML dataTransferStep, String calcFieldName )
```

## Parametri

**trasferimentoDati** Passaggio di trasferimento dati in cui è definito il campo calcolato

**calcFieldName** Campo calcolato da testare

## Valore/i restituito/i

**calcFieldValues** Restituisce l&#39;elenco di valori per ogni riga di esempio (calcFieldValues/line) e il nome del campo (calcFieldValues/@name)

## Funzioni

**Schema:** [xtk:dataTransfer](s-xtk-datatransfer.md)

**Statico:**

Sì
