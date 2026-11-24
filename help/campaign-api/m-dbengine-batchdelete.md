---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 15%
---
# batchDelete

Elimina i record di una tabella in base ai pacchetti.

```text
batchDelete (table, pk [, where ])
```

## Parametri

**tabella** Nome SQL della tabella.

**pk** Nome campo utilizzato come chiave primaria.

**where** condizione filtro record SQL.

## Valore restituito

Nessuno.

## Osservazioni

Esempio:

```javascript
      engine.batchDelete("NmsRecipient", "iRecipientId", "sName IS NULL")
```

L&#39;operatore necessita di diritti &#39;sql&#39; per utilizzare questa funzione, altrimenti viene generata un&#39;eccezione.

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
