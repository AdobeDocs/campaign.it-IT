---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 17%
---
# toXML

Restituisce un oggetto JavaScript XML ottenuto dal contenuto di [MemoryBuffer](c-memorybuffer.md). Funzione obsoleta. Utilizzare [toDocument()](m-memorybuffer-todocument.md)

```text
toXML ( [codePage ])
```

## Parametri

**codePage** Numero intero che codifica la pagina di caratteri utilizzata. Per impostazione predefinita, MemoryBuffer.CODEPAGE\_UTF8.

## Valore restituito

Contenuto di un timbro sotto forma di oggetto XML.

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
