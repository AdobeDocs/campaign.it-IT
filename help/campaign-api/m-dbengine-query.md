---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 4%
---
# query

Esegue una query SQL SELECT.

```text
query (command [, value1, ... ])
```

## Parametri

Comando SQL **comando**.

**valore1, ...** Variabili del comando.

## Valore restituito

Cursore che consente di eseguire iterazioni sul risultato della query.

## Osservazioni

Avvertenza: contrariamente a quanto indicato nella sezione Funzioni, la funzione di query non è disponibile in WebApp. Le variabili sostituiscono i parametri del comando. Il tipo di variabile deve corrispondere al parametro dichiarato nel comando. Sono disponibili i seguenti tipi:

* Stringa $(sz)
* Memo $(m)
* $(l) long
* $(s) corto
* byte $(b)
* $(d) doppio
* $(f) virgola mobile
* $(ts) timestamp
* Data $(dt)
* $(tm) ora
* $(dur) periodo di tempo

I seguenti parametri di sostituzione vengono sostituiti automaticamente con un valore e non è necessaria una variabile collegata.

* $(id) Genera un identificatore
* $(id:NmsTrackingLogId) Genera un identificatore grazie a una sequenza specifica
* $(curdate) Data e ora correnti

L’iterazione sul cursore si svolge tramite un &quot;per ciascuno&quot; e restituisce una tabella per ogni riga recuperata. Ogni elemento della tabella corrisponde a un campo della query e il tipo di elemento dipende dal tipo di campo. Esempio:

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)", 1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

In questo esempio, row\[0\] è un numero che coincide con iOperatorId, row\[1\] è una stringa di caratteri che coincide con sName e row\[2\] è una data che coincide con tsLastModified. L&#39;operatore necessita di diritti &#39;sql&#39; per utilizzare questa funzione, altrimenti viene generata un&#39;eccezione.

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
