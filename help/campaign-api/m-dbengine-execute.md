---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 5%
---
# esegui

Esegue un comando SQL.

```text
execute (command [, value1, ... ])
```

## Parametri

Comando SQL **comando**.

**valore1, ...** Variabili del comando.

## Valore restituito

Numero di record aggiornati o inseriti, se applicabile al comando eseguito, altrimenti zero.

## Osservazioni

Le variabili vengono utilizzate per sostituire i parametri del comando. Il tipo di variabile deve corrispondere al tipo dichiarato nel comando. I tipi sono i seguenti:

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

I seguenti parametri sostitutivi vengono sostituiti automaticamente da un valore e non richiedono una variabile associata.

* $(id) Genera un identificatore
* $(id:NmsTrackingLogId) Genera un identificatore grazie a una sequenza specifica
* $(curdate) Data e ora correnti

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
