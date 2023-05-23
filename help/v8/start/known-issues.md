---
title: Problemi noti di Campaign v8
description: Problemi noti nell’ultima versione di Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
source-git-commit: 9ae93ce4e2b0424bb3b3862b2c7d016309bd630e
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 4%

---

# Problemi noti{#known-issues}

In questa pagina sono elencati i problemi noti identificati in **ultime versioni di Campaign v8**. Inoltre, sono elencate le limitazioni di Campaign v8 [in questa pagina](ac-guardrails.md).


>[!NOTE]
>
>L’Adobe pubblica questo elenco di problemi noti a propria discrezione. Si basa sul numero di rapporti dei clienti, sulla gravità e sulla disponibilità della soluzione alternativa. Se un problema che stai riscontrando non è elencato, potrebbe non essere conforme ai criteri di pubblicazione in questa pagina.

## Campaign v8.3.8{#8.3-issues}

### Cambia problema di attività dell’origine dati {#issue-2}

#### Descrizione{#issue-2-desc}

Quando si inseriscono dati in un database cloud di Snowflake con una campagna **Query** e un **Cambia origine dati** se nei dati è presente un carattere barra rovesciata, il processo non riesce. La stringa di origine non ha escape e i dati non vengono elaborati correttamente nel Snowflake.

Questo problema si verifica solo se il carattere barra rovesciata si trova alla fine della stringa, ad esempio: `Barker\`.


#### Passaggi di riproduzione{#issue-2-repro}

1. Connettiti alla console client e crea un flusso di lavoro.
1. Aggiungi un **Query** e configurarlo.
1. Seleziona i dati con le caratteristiche descritte in precedenza.
1. Aggiungi un **Cambia origine dati** e configurarlo per selezionare Snowflake cloud database.
1. Esegui il flusso di lavoro e controlla i registri del flusso di lavoro per visualizzare l’errore.


#### Messaggio di errore{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

#### Soluzione alternativa{#issue-2-workaround}

La soluzione consiste nell&#39;escludere i dati contenenti il carattere barra rovesciata alla fine della stringa o rimuoverli dal file di origine.


#### Riferimento interno{#issue-2-ref}

Riferimento: NEO-45549


### L’attività di caricamento dati (file) non è riuscita a caricare il file sul server {#issue-3}

#### Descrizione{#issue-3-desc}

Quando si carica un file sul server Campaign con un **Caricamento dati (file)** il processo si arresta al 100% ma non termina mai.

#### Passaggi di riproduzione{#issue-3-repro}

1. Connettiti alla console client e crea un flusso di lavoro.
1. Aggiungi un **Caricamento dati (file)** e configurarlo.
1. Seleziona la **Carica sul server** opzione.
1. Selezionare il file sul computer locale,
1. Clic **Carica**


#### Messaggio di errore{#issue-3-error}

Il processo non termina mai.

#### Soluzione alternativa{#issue-3-workaround}

La soluzione consiste nell’utilizzare una console client precedente. Potrai quindi caricare il file sul server.

In qualità di amministratore di Campaign, puoi scaricare la console client di Campaign v8.3.1 in [Distribuzione di software di Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Aversion&amp;1_group.propertyvalues.operation=equals&amp;1_group.propertyvalues.0_values=versione-destinazione%3Acampaign%2F8&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&amp;orderby.sort=desc&amp;layout=list&amp;p.offset=0&amp;p.limit=4){target="_blank"}.

Scopri come accedere a Adobe Software Distribution [in questa pagina](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=it){target="_blank"}.

Scopri come aggiornare la console client [in questa pagina](connect.md)

#### Riferimento interno{#issue-3-ref}

Riferimento: NEO-47269

