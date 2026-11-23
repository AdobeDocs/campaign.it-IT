---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 3%
---
# generateTrackingTag

Genera automaticamente un tag JavaScript per il tracciamento web.

```text
generateTrackingTag (request [, tagid ] [, folder ])
```

## Parametri

**richiesta** L&#39;oggetto HttpServletRequest

**tagid** Stringa di caratteri che rappresentano il nome del tagid personalizzato. Se è vuota, la funzione genera il tag in base al nome del percorso.

**cartella** Stringa di caratteri che rappresentano il nome interno di una cartella. Se è vuoto, il tag viene creato nella directory predefinita, ovvero &quot;Tag di tracciamento web&quot;.

## Valore restituito

Stringa di caratteri contenente il codice JavaScript da includere.

## Osservazioni

Il tag generato si basa sul nome dell’app web, della pagina html, del controllore o, in generale, sul nome del percorso, se non viene immesso il tag. L’ultimo parametro specifica la cartella di destinazione del tag. Per richiamare la funzione, passa l’oggetto della richiesta come argomento. Si noti l&#39;utilizzo di &lt;%== poiché la funzione genera codice html. Esempio:

```xml
              <%== generateTrackingTag(request, request.getParameter('art'), request.getParameter('cat')) %>
```

## Funzioni

**Disponibile in:**

* JSSP
* WebApp
