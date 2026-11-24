---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 11%
---
# saveString

Comando obsoleto. Utilizzare [saveFile()](f-savefile.md). Salva una stringa di caratteri in un file.

```text
saveString (text, filename [, codePage ])
```

## Parametri

**testo** Stringa di testo da salvare.

**nomefile** Nome completo del file da salvare.

**codePage** Questo parametro facoltativo consente di specificare la codifica dei caratteri. Esempio:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## Valore restituito

Nessuno.

## Osservazioni

Se la codifica dei caratteri non è specificata, viene utilizzato il server predefinito.

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
