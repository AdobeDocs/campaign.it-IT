---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 1%
---
# PostEvent

Genera un evento da qualsiasi tipo di attività.

```text
PostEvent ( String workflowId, String activity, String transition, XML parameters, Boolean complete )
```

## Parametri

**workflowId** Identificatore o nome interno del workflow.

**attività** Il nome dell&#39;attività da cui inizia l&#39;evento

**transizione** Il nome della transizione da attivare. Se questo nome è vuoto, l’evento viene emesso alla prima transizione valida (gli eventi di tipo a scadenza vengono ignorati).

**parametri** Parametri dell&#39;evento sotto forma di un elemento XML. Il nome dell’elemento deve essere una variabile. Se non desideri trasmettere una variabile, puoi utilizzare un elemento vuoto &lt;variabili/> o una stringa vuota &quot;&quot;.

**complete** Tutte le attività in sospeso dell&#39;attività specificata sono terminate.

## Valore/i restituito/i

Nessuno.

## Osservazioni

* Il comando viene eseguito in modalità asincrona e non ha un effetto immediato dopo il ritorno del metodo.
* Il flusso di lavoro di destinazione deve essere avviato quando viene chiamato questo metodo. Se non viene avviato, viene scritto un errore nel file di registro corrispondente.
* Se il flusso di lavoro di destinazione viene sospeso quando viene chiamato il metodo, il comando viene lasciato in coda fino alla ripresa del flusso di lavoro.
* L’attività non è soggetta ad alcuna restrizione: non è necessario che l’attività sia in corso né che sia stata completata.

## Funzioni

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Statico:**

Sì
