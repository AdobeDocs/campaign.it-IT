---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 9%
---
# getDBMSType

Restituisce il tipo di server del database.

```text
getDBMSType ( [name ] [, checkIfUpdated ])
```

## Parametri

**nome** Nome dell&#39;origine dati.

**checkIfUpdated** Verificare che lo schema sia stato aggiornato nella cache. Nessun impatto, se lo schema è già stato creato come istanza nello script.

## Valore restituito

Stringa di testo contenente il tipo di server del database.

## Osservazioni

Se l&#39;origine dati non è specificata, la funzione utilizza &#39;nms:default&#39; per impostazione predefinita. L&#39;origine dati deve esistere, altrimenti viene generata un&#39;eccezione.

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
