---
title: Problemi noti di Campaign v8
description: Problemi noti nell’ultima versione di Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 099d14ace04df1b98e03be283a6436f49f535958
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 1%

---

# Problemi noti{#known-issues}

In questa pagina sono elencati i problemi noti identificati nel **ultima versione di Campaign v8**. Sono inoltre elencate le limitazioni in arrivo con Campaign v8 [in questa pagina](known-limitations.md).


>[!NOTE]
>
>L’Adobe pubblica a propria discrezione questo elenco di questioni note. Si basa sul numero di rapporti sui clienti, sulla gravità e sulla disponibilità della soluzione alternativa. Se un problema che stai riscontrando non è presente nell’elenco, potrebbe non corrispondere ai criteri di pubblicazione in questa pagina.

## Modifica problema dell’attività Origine dati {#issue-1}

### Descrizione

La **Cambia origine dati** Errore durante il trasferimento dei dati dal database locale di Campaign al database cloud di Snowflake. Quando si cambia direzione, l’attività può generare problemi.

### Passaggi di riproduzione

1. Collegati alla console client e crea un flusso di lavoro.
1. Aggiungi un **Query** attività e **Cambia origine dati** attività.
1. Definire una query sul **email**, che è una stringa.
1. Esegui il flusso di lavoro e fai clic con il pulsante destro del mouse sulla transizione per visualizzare il gruppo: i record e-mail vengono visualizzati sostituiti da `****`.
1. Controlla i registri del flusso di lavoro: la **Cambia origine dati** l’attività interpreta questi record come valori numerici.

### Soluzione alternativa

Per trasferire i dati dal database cloud di Snowflake al database locale di Campaign e tornare al Snowflake, devi utilizzare due diversi **Cambia origine dati** attività.

### Riferimento interno

Riferimento: NEO-45549


## Impossibile caricare il file sul server durante l&#39;attività di caricamento dei dati (file) {#issue-2}

### Descrizione

Il caricamento dei file sul server Campaign si interrompe al 100% dell’avanzamento ma non termina mai.

### Passaggi di riproduzione

1. Collegati alla console client e crea un flusso di lavoro.
1. Aggiungi un **Caricamento dati (file)** e configuralo.
1. Seleziona la **Carica sul server** opzione .
1. Selezionare il file nel computer locale,
1. Fai clic su **Carica**

### Soluzione alternativa

Nessuno

### Riferimento interno

Riferimento: NEO-47269