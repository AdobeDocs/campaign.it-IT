---
title: Problemi noti di Campaign v8
description: Problemi noti nell’ultima versione di Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
source-git-commit: 96e9f5fe5f07ea0c476395d33efa4d6bcf10cf60
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 4%

---

# Problemi noti{#known-issues}

In questa pagina sono elencati i problemi noti identificati nel **ultime versioni di Campaign v8**. Sono inoltre elencate le limitazioni in arrivo con Campaign v8 [in questa pagina](ac-guardrails.md).


>[!NOTE]
>
>L’Adobe pubblica a propria discrezione questo elenco di questioni note. Si basa sul numero di rapporti sui clienti, sulla gravità e sulla disponibilità della soluzione alternativa. Se un problema che stai riscontrando non è presente nell’elenco, potrebbe non corrispondere ai criteri di pubblicazione in questa pagina.

## Campaign v8.3.8{#8.3-issues}

### Cambia problema dell’attività Origine dati n. 1 {#issue-1}

#### Descrizione{#issue-1-desc}

La **Cambia origine dati** Errore durante il trasferimento dei dati dal database locale di Campaign al database cloud di Snowflake. Quando si cambia direzione, l’attività può generare problemi.

#### Passaggi di riproduzione{#issue-1-repro}

1. Collegati alla console client e crea un flusso di lavoro.
1. Aggiungi un **Query** attività e **Cambia origine dati** attività.
1. Definire una query sul **email**, che è una stringa.
1. Esegui il flusso di lavoro e fai clic con il pulsante destro del mouse sulla transizione per visualizzare il gruppo: i record e-mail vengono visualizzati sostituiti da `****`.
1. Controlla i registri del flusso di lavoro: la **Cambia origine dati** l’attività interpreta questi record come valori numerici.

#### Messaggio di errore{#issue-1-error}

```sql
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

#### Soluzione alternativa{#issue-1-workaround}

Per trasferire i dati dal database cloud di Snowflake al database locale di Campaign e tornare al Snowflake, devi utilizzare due diversi **Cambia origine dati** attività.

#### Riferimento interno{#issue-1-ref}

Riferimento: NEO-45549



### Modifica problema dell’attività Origine dati {#issue-2}

#### Descrizione{#issue-2-desc}

Durante l’inserimento di dati nel database cloud di Snowflake con una campagna **Query** e **Cambia origine dati** attività , il processo non riesce quando nei dati è presente un carattere barra rovesciata. La stringa di origine non è preceduta da escape e i dati non vengono elaborati correttamente sul Snowflake.

Questo problema si verifica solo se il carattere barra rovesciata si trova alla fine della stringa, ad esempio: `Barker\`.


#### Passaggi di riproduzione{#issue-2-repro}

1. Collegati alla console client e crea un flusso di lavoro.
1. Aggiungi un **Query** e configuralo.
1. Selezionare i dati con le caratteristiche descritte sopra.
1. Aggiungi un **Cambia origine dati** e configuralo per selezionare il database cloud di Snowflake.
1. Esegui il flusso di lavoro e controlla i registri del flusso di lavoro per visualizzare l’errore.


#### Messaggio di errore{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

#### Soluzione alternativa{#issue-2-workaround}

La soluzione consiste nell’escludere i dati contenenti il carattere barra rovesciata alla fine della stringa o nel rimuoverlo dal file di origine.


#### Riferimento interno{#issue-2-ref}

Riferimento: NEO-45549


### Impossibile caricare il file sul server durante l&#39;attività di caricamento dei dati (file) {#issue-3}

#### Descrizione{#issue-3-desc}

Quando carichi un file sul server Campaign con un **Caricamento dati (file)** attività, il processo si ferma al 100% ma non termina mai.

#### Passaggi di riproduzione{#issue-3-repro}

1. Collegati alla console client e crea un flusso di lavoro.
1. Aggiungi un **Caricamento dati (file)** e configuralo.
1. Seleziona la **Carica sul server** opzione .
1. Selezionare il file nel computer locale,
1. Fai clic su **Carica**


#### Messaggio di errore{#issue-3-error}

Il processo non finisce mai.

#### Soluzione alternativa{#issue-3-workaround}

La soluzione consiste nell’utilizzare una console client precedente. Potrai quindi caricare il file sul server.

In qualità di amministratore di Campaign, puoi scaricare la console del client Campaign v8.3.1 in [Distribuzione di software di Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Aversion&amp;1_group.property.operation=equals&amp;1_group.property.values.0_values=target-version%3AcamCampaign%2F8&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&amp;orderby.sort=desc&amp;desc=list&amp;p.offset=0&amp;p.limit=4){target=&quot;_blank&quot;}.

Scopri come accedere alla Distribuzione di software di Adobe [in questa pagina](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=it){target=&quot;_blank&quot;}.

Scopri come aggiornare la console client [in questa pagina](connect.md)

#### Riferimento interno{#issue-3-ref}

Riferimento: NEO-47269