---
title: Problemi noti di Campaign v8
description: Problemi noti nell’ultima versione di Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 2705e9b23f9f8a61f799381434f7e94a226de1b9
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 3%

---

# Problemi noti{#known-issues}

In questa pagina sono elencati i problemi noti identificati nel **ultima versione di Campaign v8**. Sono inoltre elencate le limitazioni in arrivo con Campaign v8 [in questa pagina](known-limitations.md).


>[!NOTE]
>
>L’Adobe pubblica a propria discrezione questo elenco di questioni note. Si basa sul numero di rapporti sui clienti, sulla gravità e sulla disponibilità della soluzione alternativa. Se un problema che stai riscontrando non è presente nell’elenco, potrebbe non corrispondere ai criteri di pubblicazione in questa pagina.

## Modifica problema dell’attività Origine dati {#issue-1}

### Descrizione{#issue-1-desc}

La **Cambia origine dati** Errore durante il trasferimento dei dati dal database locale di Campaign al database cloud di Snowflake. Quando si cambia direzione, l’attività può generare problemi.

### Passaggi di riproduzione{#issue-1-repro}

1. Collegati alla console client e crea un flusso di lavoro.
1. Aggiungi un **Query** attività e **Cambia origine dati** attività.
1. Definire una query sul **email**, che è una stringa.
1. Esegui il flusso di lavoro e fai clic con il pulsante destro del mouse sulla transizione per visualizzare il gruppo: i record e-mail vengono visualizzati sostituiti da `****`.
1. Controlla i registri del flusso di lavoro: la **Cambia origine dati** l’attività interpreta questi record come valori numerici.

### Messaggio di errore{#issue-1-error}

```sql
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

### Soluzione alternativa{#issue-1-workaround}

Per trasferire i dati dal database cloud di Snowflake al database locale di Campaign e tornare al Snowflake, devi utilizzare due diversi **Cambia origine dati** attività.

### Riferimento interno{#issue-1-ref}

Riferimento: NEO-45549



## Caricamento dati (file) non riuscito a causa di una barra rovesciata {#issue-2}

### Descrizione{#issue-2-desc}

Quando si inseriscono dati nel database cloud di Snowflake con un’attività di caricamento di Campaign, il processo non riesce quando nel file di origine è presente un carattere barra rovesciata. La stringa non è preceduta da un escape e i dati non vengono elaborati correttamente sul Snowflake.

Questo problema si verifica solo se il carattere della barra rovesciata si trova alla fine della stringa, ad esempio: `Barker\`.


### Passaggi di riproduzione{#issue-2-repro}

1. Collegati alla console client e crea un flusso di lavoro.
1. Aggiungi un **Caricamento dati (file)** e configuralo.
1. Selezionare un file locale con le caratteristiche descritte sopra.
1. Esegui il flusso di lavoro e controlla i registri del flusso di lavoro per visualizzare l’errore.


### Messaggio di errore{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

### Soluzione alternativa{#issue-2-workaround}

Come soluzione alternativa, esporta i file con virgolette doppie intorno ai valori problematici (come `Barker\`) e includi un’opzione di formato file `FIELD_OPTIONALLY_ENCLOSED_BY = '"'`.

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

Nessuno

### Riferimento interno{#issue-3-ref}

Riferimento: NEO-47269