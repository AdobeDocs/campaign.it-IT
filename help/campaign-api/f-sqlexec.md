---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 6%
---
# sqlExec

Esegue uno script SQL.

```text
sqlExec (query [, value1, ... ])
```

## Parametri

**query** La query SQL.

**valore1, ...** Variabili della query SQL.

## Valore restituito

Il numero di record aggiornati o inseriti in caso di comando UPDATE o INSERT SQL.

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
* $(dur) intervallo di tempo in millisecondi (ms)

I seguenti parametri di sostituzione (validi solo per un &quot;aggiornamento&quot;) vengono sostituiti automaticamente con un valore e non è necessaria una variabile collegata.

* $(id) genera un identificatore
* $(id:NmsTrackingLogId) genera un identificatore utilizzando una sequenza specifica
* $(curdate) data e ora correnti

L&#39;operatore deve disporre del diritto &#39;sql&#39; per utilizzare questa funzione, altrimenti viene generata un&#39;eccezione. Esempio:

```javascript
      var sql4 = "INSERT INTO Reporting (sClientdesc,sClient) values ('" + client.@description.toString() + "','" + client.@clientCode.toString() +"')";
sqlExec(sql4);
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
