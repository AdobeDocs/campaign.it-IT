---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 5%
---
# getTimezoneJson

Restituisce una stringa di caratteri che è la rappresentazione JSON dell’elenco delle differenze temporali con ora UTC e la relativa data di inizio rispetto al periodo UNIX per un fuso orario.

```text
getTimezoneJson ( [timezone ])
```

## Parametri

**fuso orario** Il nome del fuso orario per il quale è necessario restituire l&#39;elenco delle differenze di orario rispetto a UTC. Ogni differenza di orario è collegata a una data di inizio applicabile fino alla data di inizio successiva. Se non viene restituito alcun valore, utilizza il fuso orario dell’operatore predefinito.

## Valore restituito

Restituisce una stringa di caratteri che è la rappresentazione JSON delle differenze temporali da applicare in base alle date. La stringa JSON restituita viene valutata in una tabella di {startDate, offset} coppie. La stringa di caratteri restituita ha il seguente formato:

```javascript
[
  {"startDate" : -1855958901000, "offset" : 0},
  {"startDate" : -1689814800000, "offset" : 3600000}
]
```

* startDate è l&#39;ora Posix a partire dalla quale si applica l&#39;intervallo.
* offset è il valore in millisecondi della differenza temporale con UTC. Ad esempio, UTC+02:00 è uguale a 7200000.

## Osservazioni

getTimezoneJson viene chiamato tramite l’istanza dell’applicazione.

```javascript
var tzList = eval(application.getTimezoneJson());
```

## Funzioni

**Metodo di classe:** [Applicazione](c-application.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
