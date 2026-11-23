---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 12%
---
# serverName

Restituisce il nome del server di query.

```text
serverName
```

## Osservazioni

Esempio: ServerName del seguente URL:

```javascript
      http://adobe.com:8080/nms/test.jst?id=1234&param=dummy#aFragment
```

restituisce la stringa seguente:

```javascript
adobe.com
```

## Funzioni

**Proprietà della classe:** [HttpServletRequest](c-httpservletrequest.md)

**Sola lettura:**

Sì

**Disponibile in:**

* JSSP
* WebApp
