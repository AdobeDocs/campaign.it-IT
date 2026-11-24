---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 6%
---
# completo

Funzione da richiamare al termine di una query asincrona.

```text
complete
```

## Osservazioni

La funzione deve accettare quattro argomenti:

* Il servizio
* Il risultato
* Contesto: parametro passato alla funzione [start](m-soapservice-start.md)
* Stato

Lo stato può avere i seguenti valori:

* &quot;success&quot; significa che è stato ricevuto un risultato.
* &quot;error&quot; (errore) può indicare che la comunicazione è stata interrotta, che la risposta non è stata strutturata correttamente o che si è verificato un errore HTTP.
* &quot;fault&quot; (errore) se viene restituito un errore SOAP. In questo caso, il risultato contiene un oggetto che descrive l’errore.
* &quot;timeout&quot; significa che non è stato possibile stabilire la connessione o che non è stata ricevuta alcuna risposta entro la scadenza configurata.

Quando il risultato è &quot;success&quot; (successo), dipende dal numero di parametri restituiti:

* void se la query non restituisce alcun valore
* Valore se la query restituisce un singolo parametro
* una tabella se la query restituisce diversi parametri

Quando lo stato è &quot;fault&quot; (errore), il risultato è un oggetto che contiene le seguenti proprietà:

* message (messaggio): messaggio di descrizione dell’errore.
* object: oggetto XML contenente i dettagli dell&#39;errore.

Esempio:

```javascript
http.complete = function(result, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + result[0])
}
```

## Funzioni

**Proprietà della classe:** [SoapService](c-soapservice.md)

**Sola lettura:**

No

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
