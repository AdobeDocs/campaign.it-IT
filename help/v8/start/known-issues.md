---
title: Problemi noti di Campaign v8
description: Problemi noti nell’ultima versione di Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 2c9455a09d6b557d525b1af5da9374a1d59201d7
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 3%

---

# Problemi noti{#known-issues}

In questa pagina sono elencati i problemi noti identificati nel **ultima versione di Campaign v8**. Sono inoltre elencate le limitazioni in arrivo con Campaign v8 [in questa pagina](known-limitations.md).


>[!NOTE]
>
>L’Adobe pubblica a propria discrezione questo elenco di questioni note. Si basa sul numero di rapporti sui clienti, sulla gravità e sulla disponibilità della soluzione alternativa. Se un problema che stai riscontrando non è presente nell’elenco, potrebbe non corrispondere ai criteri di pubblicazione in questa pagina.

<!--
## Change Data Source activity issue #1 {#issue-1}

### Description{#issue-1-desc}

The **Change Data Source** activity is failing when transfering data from Campaign local database to Snowflake cloud database. When switching directions, the activity can generate issues.

### Reproduction steps{#issue-1-repro}

1. Connect to the client console and create a workflow.
1. Add a **Query** activity and a **Change Data Source** activity.
1. Define a query on the **email**, which is a string.
1. Run the workflow and right-click the transition to view the population: the email records are displayed replaced by `****`.
1. Check the workflow logs: the **Change Data Source** activity interprets these records as numeric values.

### Error message{#issue-1-error}

```sql
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

### Workaround{#issue-1-workaround}

To have the data transfered from Snowflake cloud database to Campaign local database and back to Snowflake, you must use two different **Change Data Source** activities.

### Internal reference{#issue-1-ref}

Reference: NEO-45549 
-->


## Modifica problema dell’attività Origine dati {#issue-2}

### Descrizione{#issue-2-desc}

Durante l’inserimento di dati nel database cloud di Snowflake con una campagna **Query** e **Cambia origine dati** attività , il processo non riesce quando nei dati è presente un carattere barra rovesciata. La stringa di origine non è preceduta da escape e i dati non vengono elaborati correttamente sul Snowflake.

Questo problema si verifica solo se il carattere barra rovesciata si trova alla fine della stringa, ad esempio: `Barker\`.


### Passaggi di riproduzione{#issue-2-repro}

1. Collegati alla console client e crea un flusso di lavoro.
1. Aggiungi un **Query** e configuralo.
1. Selezionare i dati con le caratteristiche descritte sopra.
1. Aggiungi un **Cambia origine dati** e configuralo per selezionare il database cloud di Snowflake.
1. Esegui il flusso di lavoro e controlla i registri del flusso di lavoro per visualizzare l’errore.


### Messaggio di errore{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

### Soluzione alternativa{#issue-2-workaround}

La soluzione consiste nell’escludere i dati contenenti il carattere barra rovesciata alla fine della stringa o nel rimuoverlo dal file di origine.

<!--
As a workaround, export the files with double quotes around the problematic values (like `Barker\`) and include a file format option `FIELD_OPTIONALLY_ENCLOSED_BY = '"'`.
-->

### Riferimento interno{#issue-2-ref}

Riferimento: NEO-45549


## Impossibile caricare il file sul server durante l&#39;attività di caricamento dei dati (file) {#issue-3}

### Descrizione{#issue-3-desc}

Quando carichi un file sul server Campaign con un **Caricamento dati (file)** attività, il processo si ferma al 100% ma non termina mai.

### Passaggi di riproduzione{#issue-3-repro}

1. Collegati alla console client e crea un flusso di lavoro.
1. Aggiungi un **Caricamento dati (file)** e configuralo.
1. Seleziona la **Carica sul server** opzione .
1. Selezionare il file nel computer locale,
1. Fai clic su **Carica**


### Messaggio di errore{#issue-3-error}

Il processo non finisce mai.

### Soluzione alternativa{#issue-3-workaround}

La soluzione consiste nell’utilizzare una console client precedente. Potrai quindi caricare il file sul server.

In qualità di amministratore, puoi scaricare la console del client Campaign v8.3.1 in [Servizio di distribuzione Adobe](https://experience.adobe.com/downloads).

Scopri come accedere al servizio di distribuzione Adobe [in questa pagina](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=it)

Scopri come aggiornare la console client [in questa pagina](connect.md)

### Riferimento interno{#issue-3-ref}

Riferimento: NEO-47269