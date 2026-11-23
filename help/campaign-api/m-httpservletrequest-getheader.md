---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '30'
ht-degree: 16%
---
# getHeader

Restituisce un attributo definito nell&#39;intestazione della query.

```text
getHeader (name)
```

## Parametri

**nome** Nome dell&#39;attributo dell&#39;intestazione.

## Valore restituito

Nessuno.

## Osservazioni

Esempio:

```javascript
Host: <%= request.getHeader("host") %>
```

## Funzioni

**Metodo di classe:** [HttpServletRequest](c-httpservletrequest.md)

**Disponibile in:**

* JSSP
* WebApp
