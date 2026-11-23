---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 8%
---
# carica

> Avvertenza:
>
> L&#39;accesso tramite API di file è limitato alle cartelle **var**, **sftp** e temporanee di Adobe Campaign.

Carica e restituisce un&#39;entità corrispondente a uno schema e a una chiave specifici.

```text
load (key)
```

## Parametri

**chiave** Stringa di caratteri corrispondente alla chiave dell&#39;entità.

## Valore restituito

Restituisce l&#39;entità sotto forma di oggetto JavaScript.

## Osservazioni

load non è una funzione globale, ma un metodo di schema. Per richiamarlo, devi usare il prefisso dello schema desiderato. Ad esempio:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
```

Le proprietà e le sottoproprietà di questo oggetto possono essere modificate a piacimento. A differenza del metodo [get()](f-get.md), il documento non viene salvato automaticamente nel database, è necessario richiamare il metodo [save()](m-entity-save.md) sull&#39;oggetto. Se l’entità non viene trovata nel database, si verifica un errore e lo script viene interrotto.

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
