---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 13%
---
# Esporta

Generazione ed esportazione di un rapporto

```text
Export ( String reportName, XML context, String exportFormat, String fileName, Boolean isAdHoc )
```

## Parametri

**reportName** Nome interno del report

**contesto** Contesto di esecuzione.

**exportFormat** I valori possibili sono: XLS, OOXML\_SS, ODF\_SS, PDF

XLS genera un documento di Excel 94-2003\
 OOXML\_SS genera un documento di Excel 2007\
 ODF\_SS genera un documento aperto

**nomeFile** Nome file di output

**isAdHoc** Specifica se l&#39;esportazione riguarda un report ad hoc

## Valore/i restituito/i

Nessuno.

## Funzioni

**Schema:** [xtk:report](s-xtk-report.md)

**Statico:**

Sì
