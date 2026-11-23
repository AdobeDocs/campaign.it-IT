---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 7%
---
# ottenere

Carica e restituisce un&#39;entità corrispondente a uno schema e a una chiave specifici.

```text
get ( [key or content ])
```

## Parametri

**chiave o contenuto** Stringa di caratteri corrispondente alla chiave dell&#39;entità del contenuto XML per creare o avviare una nuova entità.

## Valore restituito

Restituisce l&#39;entità sotto forma di oggetto JavaScript.

## Osservazioni

get non è una funzione globale, ma un metodo di schema. Per richiamarlo, devi usare il prefisso dello schema desiderato. Ad esempio:

```javascript
var delivery = NLWS.nmsDelivery.get("12435")
```

Le proprietà e le sottoproprietà di questo oggetto possono essere modificate a piacimento. Il documento viene salvato automaticamente nel database al termine dell&#39;esecuzione dello script, se viene modificato. Se non si tratta di una creazione e l’entità non è già presente nel database, si tratta di un errore e lo script viene interrotto.

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
