---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 11%
---
# queryString

Restituisce la parte dell’URL della query che corrisponde ai parametri.

```text
queryString
```

## Osservazioni

Esempio: QueryString del seguente URL:

```javascript
      http://adobe.com/nms/test.jst?id=1234&param=dummy#aFragment
```

restituisce la stringa seguente:

```javascript
id=1234&param=dummy
```

## Funzioni

**Proprietà della classe:** [HttpServletRequest](c-httpservletrequest.md)

**Sola lettura:**

Sì

**Disponibile in:**

* JSSP
* WebApp
