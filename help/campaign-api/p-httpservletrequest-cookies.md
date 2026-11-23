---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 13%
---
# cookie

Restituisce i cookie della query.

```text
cookies
```

## Osservazioni

La proprietà cookies restituisce un oggetto, con un cookie corrispondente per ciascuna delle relative proprietà. Esempio:

```javascript
var cookies = request.cookies
for(var name in cookies)
{
var value = cookies[name].value
document.write(name + " : " + value + "<br>")
}
```

## Funzioni

**Proprietà della classe:** [HttpServletRequest](c-httpservletrequest.md)

**Sola lettura:**

Sì

**Disponibile in:**

* JSSP
* WebApp
