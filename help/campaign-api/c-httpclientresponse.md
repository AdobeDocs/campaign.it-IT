---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 9%
---
# HttpClientResponse (classe)

Oggetto che rappresenta la risposta a una query HTTP.

Può essere ottenuto solo dopo l&#39;esecuzione di una query HTTP da parte della proprietà `response`.

## Proprietà

| Proprietà | Descrizione |
| --- | --- |
| [corpo](p-httpclientresponse-body.md) | Corpo della risposta HTTP sotto forma di oggetto MemoryBuffer. |
| [codice](p-httpclientresponse-code.md) | Il codice restituito della risposta HTTP sotto forma di un numero intero JavaScript. |
| [tabella codici](p-httpclientresponse-codepage.md) | Valore di codePage della risposta. Utilizzato per decodificare il corpo della risposta HTTP. |
| [intestazione](p-httpclientresponse-header.md) | Oggetto contenente tutte le intestazioni HTTP. |
| [intestazioni](p-httpclientresponse-headers.md) | L’elenco delle intestazioni per la risposta HTTP raggruppate per nome. |
| [messaggio](p-httpclientresponse-message.md) | Messaggio trasmesso dalla risposta HTTP. |

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
