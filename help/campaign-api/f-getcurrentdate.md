---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 21%
---
# getCurrentDate

Restituisce la data corrente del server di database.

```text
getCurrentDate ()
```

## Parametri

Nessuno.

## Valore restituito

Data corrente del server di database.

## Osservazioni

Esempio:

```javascript
      date = formatDate(getCurrentDate(),"%4Y/%2M/%2D %02H:%02N:%02S")
```

Per ulteriori informazioni sulla funzione formatDate(), fare riferimento a [formatDate(date, format)](f-formatdate.md)

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
