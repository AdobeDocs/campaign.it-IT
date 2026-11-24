---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 15%
---
# offuscare

Offusca un numero intero in una stringa di caratteri. Il valore originale può essere recuperato chiamando [unobfuscate](f-unobfuscate.md).

```text
obfuscate (value [, size ] [, version ])
```

## Parametri

**value** Numero intero da oscurare.

**size** la dimensione della stringa risultante dall&#39;offuscamento. Un numero intero compreso tra 6 e 10. 6 per impostazione predefinita.

**versione** la versione di offuscamento da applicare. 0 per impostazione predefinita.

## Valore restituito

Stringa di caratteri che rappresenta il numero intero offuscato.

## Funzioni

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
