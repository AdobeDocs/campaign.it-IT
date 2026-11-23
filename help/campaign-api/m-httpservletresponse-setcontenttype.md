---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '29'
ht-degree: 17%
---
# setContentType

Modifica il tipo di documento della risposta.

```text
setContentType (name)
```

## Parametri

Tipo MIME **name** del documento.

## Valore restituito

Nessuno.

## Osservazioni

Esempio:

```javascript
      response.setContentType("text/html;charset=ISO-8859-1")
```

## Funzioni

**Metodo di classe:** [HttpServletResponse](c-httpservletresponse.md)

**Disponibile in:**

* JSSP
* WebApp
