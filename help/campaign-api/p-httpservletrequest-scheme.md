---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 10%
---
# schema

Restituisce il nome del protocollo utilizzato (HTTP, HTTPS, ecc.) per accedere a questa pagina.

```text
scheme
```

## Osservazioni

Esempio: lo schema del seguente URL:

```javascript
      http://adobe.com:8080/nms/test.jst?id=1234&param=dummy#aFragment
```

restituisce la stringa seguente:

```javascript
http
```

## Funzioni

**Proprietà della classe:** [HttpServletRequest](c-httpservletrequest.md)

**Sola lettura:**

Sì

**Disponibile in:**

* JSSP
* WebApp
