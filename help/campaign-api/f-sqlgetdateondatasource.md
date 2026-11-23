---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 11%
---
# sqlGetDateOnDataSource

Restituisce la data risultante da una query SQL in un&#39;origine dati.

```text
sqlGetDateOnDataSource (query, dataSource [, value1, ... ])
```

## Parametri

**query** La query SQL.

**dataSource** L&#39;origine dati.

**valore1, ...** Variabili della query SQL.

## Valore restituito

Il valore del tipo di data che corrisponde alla query.

## Osservazioni

Il parametro &quot;origine dati&quot; è definito in [sqlExecOnDataSource(query, dataSource, value1, ...)](f-sqlexecondatasource.md) function Le variabili facoltative che sono parametri di questa funzione sono definite in [sqlGetString(query, value1, ...)](f-sqlgetstring.md)

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
