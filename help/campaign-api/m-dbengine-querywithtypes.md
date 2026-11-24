---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 15%
---
# queryWithTypes

Esegue una query SQL di tipo SELECT con specifica del tipo di colonna.

```text
queryWithTypes (command, types [, value1, ... ])
```

## Parametri

Comando SQL **comando**.

**tipi** tabella contenente il tipo di colonna.

**value1, ...** Variabili di comando.

## Valore restituito

Cursore che consente di eseguire iterazioni sul risultato della query.

## Osservazioni

Avviso: contrariamente a quanto indicato nella sezione Funzionalità, la funzione queryWithTypes non è disponibile in WebApp. La funzione è identica a [query](m-dbengine-query.md), con il tipo di colonne aggiunto. Nella maggior parte dei casi, il tipo di colonna non viene utilizzato in quanto può essere dedotto automaticamente. Per questo motivo è preferibile [query](m-dbengine-query.md). Tuttavia, in alcuni casi, in particolare con le colonne Oracle e del tipo di data, può essere necessario esplicitare il tipo. I tipi di colonna sono stringhe di caratteri nel seguente elenco:

* stringa
* Data e ora
* data
* ora
* intervallo di tempo
* doppio
* mobile
* booleano
* byte
* breve
* lungo
* int64
* promemoria
* blob
* collegamento
* raccoglitore

Esempio:

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)",
                     ["long", "string", "datetime"],
                     1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

Per utilizzare questa funzione, l&#39;operatore deve disporre di diritti &#39;sql&#39;. In caso contrario viene generata un&#39;eccezione.

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
