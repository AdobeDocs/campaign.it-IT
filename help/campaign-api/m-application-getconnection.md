---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 16%
---
# getConnection

Restituisce una nuova connessione al server di database.

```text
getConnection ()
```

## Parametri

Nessuno.

## Valore restituito

Una [connessione](c-dbengine.md) al server di database.

## Osservazioni

È possibile liberare la connessione prima della fine dell&#39;esecuzione dello script utilizzando il metodo [dispose](m-dbengine-dispose.md).

## Funzioni

**Metodo di classe:** [Applicazione](c-application.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
