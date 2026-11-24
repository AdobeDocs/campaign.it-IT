---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 8%
---
# saveXmlFile

> Avvertenza:
>
> L&#39;accesso tramite API di file è limitato alle cartelle **var**, **sftp** e temporanee di Adobe Campaign.

Salva in un file una stringa di caratteri corrispondente a un documento XML.

```text
saveXmlFile (text, filename [, codePage ])
```

## Parametri

**testo** Documento XML sotto forma di stringa di caratteri da salvare.

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

Questa funzione inserisce un prologo XML nel file, se necessario, e specifica la codifica del documento. Se la codifica dei caratteri non è specificata, viene utilizzato il server predefinito.

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
