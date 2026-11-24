---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 8%
---
# intestazioni

L’elenco delle intestazioni per la risposta HTTP raggruppate per nome.

```text
headers
```

## Osservazioni

Ogni proprietà header riportava il nome dell’intestazione e il valore della tabella che corrisponde a ogni intestazione con questo nome. Questa funzione è diversa da [header](p-httpclientresponse-header.md) perché restituisce una tabella di valori invece di un valore univoco per un nome specificato. Questa funzione è utile per le intestazioni che possono essere visualizzate più volte, ad esempio Accept-Language o Set-Cookie. La funzione restituisce una tabella vuota se la risposta HTTP non ha un’intestazione con questo nome. Esempio:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = response
var cookies = response.headers["set-cookie"]
for each(var c in cookies)
{
  logInfo("Set-Cookie: " + c)
}
```

le proprietà delle intestazioni non possono essere suddivise in singole voci. I nomi delle proprietà non fanno distinzione tra maiuscole e minuscole.

## Funzioni

**Proprietà della classe:** [HttpClientResponse](c-httpclientresponse.md)

**Sola lettura:**

Sì

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
