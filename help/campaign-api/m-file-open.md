---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 5%
---
# apri

Apre il file in modalità di lettura o scrittura.

```text
open ( [mode ] [, codepage ])
```

## Parametri

**mode** Modalità di apertura file. La modalità può essere uno dei seguenti valori:

* &quot;r&quot; - Apre il file in modalità di sola lettura. Questa è la modalità predefinita.
* &quot;w&quot; - Apre il file in modalità di scrittura.
* &quot;a&quot; - Apre il file in modalità &#39;append&#39;. I dati scritti nel file vengono aggiunti alla fine.

**codepage** Codifica del file. La codifica può essere uno dei seguenti valori:

* File.CODEPAGE\_CURRENT - Questa è la tabella codici predefinita.
* File.CODEPAGE\_OEM
* File.CODEPAGE\_MAC
* File.CODEPAGE\_THREAD
* File.CODEPAGE\_LATIN1
* File.CODEPAGE\_LATIN2
* File.CODEPAGE\_ISOLATIN1
* File.CODEPAGE\_ISOLATIN2
* File.CODEPAGE\_EMLATIN1
* File.CODEPAGE\_EMLATIN2
* File.CODEPAGE\_UTF7
* File.CODEPAGE\_UTF8
* File.CODEPAGE\_ISOLATION9
* File.CODEPAGE\_OEMUS
* File.CODEPAGE\_SHIFTJIS
* File.CODEPAGE\_BIG5
* File.CODEPAGE\_CINESE
* File.CODEPAGE\_EUCKOREAN
* File.CODEPAGE\_UTF16LE
* File.CODEPAGE\_UTF16BE

## Valore restituito

Nessuno.

## Osservazioni

Se non è possibile aprire il file, viene generata un&#39;eccezione.

## Funzioni

**Metodo di classe:** [File](c-file.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
