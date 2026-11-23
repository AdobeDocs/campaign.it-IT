---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 5%
---
# inoltra

Reindirizza la query a un&#39;altra pagina senza passare dal client.

```text
forward (location)
```

## Parametri

**posizione** URL di reindirizzamento.

## Valore restituito

Nessuno.

## Osservazioni

inoltra consente di eseguire un processo preliminare prima di trasferire la query a un’altra risorsa che produrrà il contenuto della risposta. Prima di una chiamata di inoltro, non deve essere stato restituito alcun dato al client come risposta; in caso contrario verrà generato un errore.

## Funzioni

**Metodo di classe:** [HttpServletRequest](c-httpservletrequest.md)

**Disponibile in:**

* JSSP
* WebApp
