---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 14%
---
# toBase64

Converte il buffer o parte della stringa di caratteri codificata in base 64.

```text
toBase64 ( [start ] [, length ])
```

## Parametri

**start** Numero di byte da ignorare all&#39;inizio del buffer. Il primo byte corrisponde al valore 0 (valore predefinito).

**lunghezza** Numero di byte da convertire. Per impostazione predefinita, vengono presi in considerazione tutti i byte rimanenti.

## Valore restituito

Il contenuto del buffer codificato in base 64.

## Funzioni

**Metodo di classe:** [MemoryBuffer](c-memorybuffer.md)

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
