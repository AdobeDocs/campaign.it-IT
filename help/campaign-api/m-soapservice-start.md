---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 11%
---
# inizio

Avvia una query in modalità asincrona.

```text
start (context, name, ...)
```

## Parametri

**context** Qualsiasi parametro utente che verrà inoltrato alla funzione [complete](p-soapservice-complete.md).

**nome** Nome del metodo da chiamare.

**...** Parametri di funzione.

## Valore restituito

La query creata. Questo oggetto non ha proprietà o funzioni, è utile per la funzione [wait](m-soapservice-wait.md) che consente di attendere fino alla fine di un&#39;operazione.

## Osservazioni

La connessione al servizio deve essere asincrona. Se la connessione è bloccata, viene generata un&#39;eccezione. Impossibile eseguire query se è in esecuzione un&#39;altra query sulla connessione. In questo caso viene generata un&#39;eccezione.

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
