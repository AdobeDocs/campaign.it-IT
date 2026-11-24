---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 14%
---
# loadString

Comando obsoleto. Utilizzare ⌐[loadFile()](f-loadfile.md). Restituisce il contenuto di un file di testo

```text
loadString (filename [, codePage ])
```

## Parametri

**nomefile** Nome completo del file da caricare.

**codePage** Questo parametro facoltativo consente di specificare la codifica dei caratteri. Esempio:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## Valore restituito

Una stringa di caratteri corrispondente al contenuto del file di testo.

## Osservazioni

Se la codifica dei caratteri non è specificata, viene utilizzato il server predefinito.

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
