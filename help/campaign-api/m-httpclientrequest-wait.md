---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 6%
---
# attendi

Attende la fine di un elenco di query asincrone.

```text
wait (requests,waitAll)
```

## Parametri

**richieste** Tabella di query.

**waitAll** Boolean (per impostazione predefinita è true), attendi il completamento di tutte le richieste dall&#39;elenco delle query. Se è impostata su false, se viene completata almeno una richiesta, la funzione esce dal loop di ascolto.

## Valore restituito

Nessuno.

## Osservazioni

La funzione non si applica a una query, ma è una funzione del contenitore HttpClientRequest. Esempio:

```javascript
var req = new HttpClientRequest("http://www.adobe.com/it/")
req.complete = function(req, context, status) { logInfo(status) }
req.execute(false, true)

HttpClientRequest.wait( [req] )
```

Una query può essere aggiunta all&#39;elenco solo se è asincrona e se la chiamata [execute](m-httpclientrequest-execute.md) non ha generato un&#39;eccezione. Al termine della query, questa viene eliminata automaticamente dall’elenco. Ciò significa che quando la funzione restituisce il controllo, la tabella passata come parametro sarà vuota. L&#39;elenco può essere modificato dalla funzione [complete](p-httpclientrequest-complete.md): ad esempio, è possibile avviare una nuova query e aggiungerla all&#39;elenco.

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
