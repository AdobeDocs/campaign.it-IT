---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 12%
---
# getNewIds

Restituisce un elenco di ID delle chiavi del database interno.

```text
getNewIds (count [, sequence ])
```

## Parametri

**count** numero di ID che il metodo deve restituire.

**sequenza** Nome della sequenza da utilizzare.

## Valore restituito

Una tabella contenente l’elenco degli ID:

## Osservazioni

Questo metodo equivale ai metodi SOAP NLWS.xtkSession.GetNewIds() e NLWS.xtkSession.GetNewIdsEx(), pur essendo più efficienti.

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
