---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 6%
---
# esegui

Esegue la query HTTP.

```text
execute ( [hasProxy ] [, async ] [, reuseaddr ] [, context ] [, timeout ])
```

## Parametri

**hasProxy** Boolean impostato su true se è necessario utilizzare un proxy HTTP. Per impostazione predefinita, è impostato su false.

**async** Boolean impostato su true se la query è asincrona. Per impostazione predefinita, è impostato su false.

**reuseaddr** Boolean impostato su true se il socket sottostante deve consentire il riutilizzo degli indirizzi locali. Per impostazione predefinita, è impostato su false.

**contesto** Il contesto è qualsiasi oggetto che verrà inoltrato al secondo argomento della funzione [complete](p-httpclientrequest-complete.md) in caso di query asincrona.Per impostazione predefinita, è impostato su null.

**timeout** Tempo di attesa massimo in millisecondi in caso di query asincrona. Se questo parametro non è definito, il tempo di attesa è di 5 minuti.

## Valore restituito

Nessuno.

## Osservazioni

Se la connessione HTTP non riesce, viene generata un&#39;eccezione. La proprietà [response](p-httpclientrequest-response.md) diventa valida solo dopo una chiamata riuscita alla funzione di esecuzione. Esempio:

```javascript
          
        var http = new HttpClientRequest("http://www.google.com")
        http.method = "GET"
        // Note: Here, http.response == undefined
        http.execute()
        var response = http.response
      
```

## Funzioni

**Metodo di classe:** [HttpClientRequest](c-httpclientrequest.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
