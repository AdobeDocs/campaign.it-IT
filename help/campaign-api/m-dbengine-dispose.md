---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 14%
---
# eliminare

Libera la connessione da tutte le risorse ad essa collegate.

```text
dispose ()
```

## Parametri

Nessuno.

## Valore restituito

Nessuno.

## Osservazioni

Una connessione creata con il metodo [application.getConnection()](m-application-getconnection.md) viene liberata automaticamente alla fine dello script. La chiamata di questo metodo è utile per gli script che possono avere una lunga durata.

## Funzioni

**Metodo di classe:** [DBEngine](c-dbengine.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
