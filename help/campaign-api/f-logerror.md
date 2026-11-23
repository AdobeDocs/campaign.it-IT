---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 14%
---
# logError

Aggiunge un messaggio di errore al registro dell&#39;istanza del flusso di lavoro e sospende l&#39;esecuzione dello script.

```text
logError (message)
```

## Parametri

**message** Il messaggio da aggiungere al registro.

## Valore restituito

Nessuno.

## Osservazioni

L’attività in corso si comporta come se si fosse verificato un errore: viene segnalato un errore e il flusso di lavoro viene sospeso. Questa funzione è quindi utile per generare esplicitamente un errore in un flusso di lavoro e per sospenderlo.

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Messaggio di consegna
* Regola di tipologia
* Importazione
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
