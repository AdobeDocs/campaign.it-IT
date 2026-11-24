---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%
---
# serverPort

Restituisce il numero di porta utilizzato per contattare il server.

```text
serverPort
```

## Osservazioni

Esempio: ServerPort del seguente URL:

```javascript
http://adobe.com/it:8080/nms/test.jst
```

restituisce la stringa seguente:

```javascript
8080
```

ServerPort del seguente URL:

```javascript
http://adobe.com/nms/test.jst
```

restituisce la stringa seguente:

```javascript
80
```

## Funzioni

**Proprietà della classe:** [HttpServletRequest](c-httpservletrequest.md)

**Sola lettura:**

Sì

**Disponibile in:**

* JSSP
* WebApp
