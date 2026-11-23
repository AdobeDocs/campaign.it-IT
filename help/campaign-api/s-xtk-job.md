---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 57%
---
# processo

Processi batch eseguiti sul server dell’applicazione

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [Annulla](sm-job-cancel.md) | Annullare un processo |
| [CheckIfJobInProcess](sm-job-checkifjobinprocess.md) | Verificare se il processo è ancora in esecuzione |
| [Esegui](sm-job-execute.md) | Esegue un processo in modo sincrono (in questa modalità, le informazioni sull’avanzamento e l’annullamento non sono disponibili). |
| [FileEsistenti](sm-job-filesexist.md) | Verifica se i file esistono già sul server (come file o nella tabella delle risorse). |
| [GetJobsInProcess](sm-job-getjobsinprocess.md) | Restituisce i processi non esterni in esecuzione |
| [GetStatus](sm-job-getstatus.md) | Ottieni informazioni sull’avanzamento dell’elaborazione del processo. Avviso: questa API non garantisce la restituzione di un elenco di voci di registro univoche (il chiamante deve deduplicarle utilizzando il proprio ID ). |
| [HaAvvertenza](sm-job-haswarning.md) | Esegue query sulla generazione di avvertenze o errori per questo processo |
| [Pausa](sm-job-pause.md) | Metti in pausa un processo |
| [Invia](sm-job-submit.md) | Invia un processo per un‘elaborazione asincrona |
| [InviaDaModello](sm-job-submitfrommodel.md) | Invia un processo da un modello |
| [InviaChiamataSoap](sm-job-submitsoapcall.md) | Invia un processo per un‘elaborazione asincrona |
| [WaitJobCanceled](sm-job-waitjobcancelled.md) | In attesa dell’annullamento del processo |

## Metodi generici

| Elemento “method” | Descrizione |
| --- | --- |
| [crea](f-create.md) | Crea una nuova entità corrispondente a uno schema specificato. |
| [carica](f-load.md) | Carica e restituisce un&#39;entità corrispondente a uno schema e a una chiave specifici. |
| [salva](m-entity-save.md) | Salva un&#39;entità nel database. |
