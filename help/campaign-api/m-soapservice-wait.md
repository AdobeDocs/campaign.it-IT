---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 11%
---
# attendi

Attende la fine di un elenco di query SOAP asincrone.

```text
wait (requests)
```

## Parametri

**richieste** Tabella di query.

## Valore restituito

Nessuno.

## Osservazioni

La funzione non si applica a un servizio, ma è una funzione del contenitore SoapService. Esempio:

```javascript
...
var req = service.start(1234, "GetOption", sessionToken, "XtkDatabaseId")

// Do some stuff here

// Wait until the end of the request
SoapService.wait( [req] )
```

Al termine della query, questa viene eliminata automaticamente dall’elenco. Ciò significa che quando la funzione restituisce il controllo, la tabella passata come parametro sarà vuota. L&#39;elenco può essere modificato dalla funzione [complete](p-soapservice-complete.md): ad esempio, è possibile avviare una nuova query e aggiungerla all&#39;elenco.

## Funzioni

**Metodo di classe:** [SoapService](c-soapservice.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Messaggio di consegna
* Regola di tipologia
* Importazione
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
