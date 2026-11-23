---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 12%
---
# accesso

Cambia il contesto di esecuzione dello script con l&#39;accesso corrente.

```text
logon (sessionToken)
```

```text
logon (login, password)
```

```text
logon (context)
```

## Parametri

**sessionToken** Token di sessione da utilizzare.

**login** L&#39;account di accesso dell&#39;operatore da utilizzare.

**password** La password dell&#39;operatore. La password può essere una stringa vuota se l&#39;accesso corrente dispone dei diritti di &quot;amministratore&quot;.

**contesto** Oggetto che rappresenta un account di accesso, restituito da una precedente chiamata all&#39;accesso.

## Valore restituito

Restituisce un oggetto che corrisponde all&#39;accesso precedente. In questo modo è possibile ripristinare l’accesso precedente passando questo parametro alla funzione di accesso.

## Osservazioni

Esempio:

```javascript
var oldContext = logon("jdoe", "")

// ...

logon(oldContext)
```

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
