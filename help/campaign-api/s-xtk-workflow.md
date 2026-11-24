---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 2%
---
# workflow

Definizioni dei flussi di lavoro

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [Pulizia](sm-workflow-cleanup.md) | Cancella la cronologia del flusso di lavoro. |
| [EliminaRisultato](sm-workflow-deleteresult.md) | Cancella i risultati di una o più attività. |
| [Esegui](sm-workflow-execute.md) | Esegue immediatamente un flusso di lavoro e attende il suo completamento. |
| [ExecuteInstance](sm-workflow-executeinstance.md) | Esegue immediatamente un flusso di lavoro e attende il suo completamento. |
| [GetLogin](sm-workflow-getlogin.md) | Restituisce informazioni dall&#39;account di esecuzione. |
| [GetValidationParameters](sm-workflow-getvalidationparameters.md) | Restituisce i parametri di un&#39;attività del flusso di lavoro in corso. |
| [Termina](sm-workflow-kill.md) | Interrompe incondizionatamente un flusso di lavoro. |
| [Pausa](sm-workflow-pause.md) | Sospende l&#39;esecuzione di un flusso di lavoro in corso. |
| [PostEvent](sm-workflow-postevent.md) | Genera un evento da qualsiasi tipo di attività. |
| [Risposta](sm-workflow-reply.md) | Risponde a un&#39;attività di tipo convalida in corso. |
| [Riavvia](sm-workflow-restart.md) | Collega tra loro un&#39;interruzione e un inizio del flusso di lavoro. |
| [RiavviaAttività](sm-workflow-restarttask.md) | Forza il riavvio di una o più attività completate. |
| [ImpostaAccesso](sm-workflow-setlogin.md) | Modifica l’account di esecuzione. |
| [Simula](sm-workflow-simulate.md) | Avvia un flusso di lavoro in modalità simulazione. |
| [SimulateWithParameters](sm-workflow-simulatewithparameters.md) | Avvia un flusso di lavoro in modalità simulazione e gli fornisce i parametri. |
| [Spawn](sm-workflow-spawn.md) | Crea un’istanza di flusso di lavoro da un modello, applica una patch e avvia il flusso di lavoro. |
| [SpawnWithParameters](sm-workflow-spawnwithparameters.md) | Crea un&#39;istanza del flusso di lavoro da un modello, quindi richiama il metodo [StartWithParameters](sm-workflow-startwithparameters.md) su questa istanza. |
| [SpawnWithParametersEx](sm-workflow-spawnwithparametersex.md) | Crea un&#39;istanza del flusso di lavoro da un modello e richiama il metodo [StartWithParameters](sm-workflow-startwithparameters.md) o [SimulateWithParameters](sm-workflow-simulatewithparameters.md) in questa istanza. |
| [Inizio](sm-workflow-start.md) | Avvia o riprende l&#39;esecuzione di un flusso di lavoro. |
| [IniziaConParametri](sm-workflow-startwithparameters.md) | Avvia un flusso di lavoro e gli fornisce i parametri. |
| [Interrompi](sm-workflow-stop.md) | Interrompe un flusso di lavoro in corso. |
| [Riattivazione](sm-workflow-wakeup.md) | Forza l&#39;elaborazione anticipata di tutte le attività in sospeso. |
| [Attività di riattivazione](sm-workflow-wakeuptask.md) | Forza l&#39;elaborazione anticipata di una o più attività in sospeso. |

## Metodi generici

| Elemento “method” | Descrizione |
| --- | --- |
| [crea](f-create.md) | Crea una nuova entità corrispondente a uno schema specificato. |
| [carica](f-load.md) | Carica e restituisce un&#39;entità corrispondente a uno schema e a una chiave specifici. |
| [salva](m-entity-save.md) | Salva un&#39;entità nel database. |
