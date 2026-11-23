---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 15%
---
# fileGetTempName

Genera un nome di file temporaneo.

```text
fileGetTempName ( [directory ] [, prefix ] [, extension ])
```

## Parametri

**directory** Directory del file temporaneo. Se vuoto, utilizzare la directory temporanea definita dal sistema.

**prefisso** Prefisso con massimo 4 caratteri. Se vuoto, viene utilizzato il prefisso tmp.

Estensione file **extension**.

## Valore restituito

Nome completo del file.

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
