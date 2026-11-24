---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 5%
---
# sqlGetMemo

Restituisce il campo Memo risultante da una query SQL.

```text
sqlGetMemo (query [, value1, ... ])
```

## Parametri

**query** La query SQL.

**valore1, ...** Variabili della query SQL.

## Valore restituito

Il campo Memo che corrisponde alla query.

## Osservazioni

Le variabili sostituiscono i parametri nel comando. Il tipo di variabile deve coincidere con il parametro dichiarato nel comando. Queste variabili sono disponibili in una dichiarazione di tipo &quot;select&quot; o &quot;update&quot;. Abbiamo i seguenti tipi:

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
* Intervallo di tempo $(dur) in millisecondi (ms)

I seguenti parametri di sostituzione (validi solo per un &quot;aggiornamento&quot;) vengono sostituiti automaticamente con un valore e non è necessaria una variabile collegata.

* $(id) Genera un identificatore
* $(id:NmsTrackingLogId) Genera un identificatore utilizzando una sequenza specifica
* $(curdate) Data e ora correnti

L’utilizzo delle variabili non influisce sulle prestazioni di Adobe Campaign. La query SQL deve selezionare un campo a riga singola e un campo a testo singolo. L&#39;operatore deve disporre del diritto &#39;sql&#39; per utilizzare questa funzione, altrimenti viene generata un&#39;eccezione. Esempio:

```javascript
      var logData = sqlGetMemo('select log from IncomingLog where sEmail =$(sz) order by tsCreated DESC LIMIT 1', email)
```

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
