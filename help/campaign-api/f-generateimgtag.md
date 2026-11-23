---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 20%
---
# generateImgTag

Abilita la generazione di un tag &lt;img> HTML basato su una risorsa pubblica.

```text
generateImgTag (ID)
```

## Parametri

**ID** ID risorsa pubblica

## Valore restituito

Restituisce il tag &lt;img> HTML con le proprietà dell&#39;immagine contenute nella definizione della risorsa pubblica.

## Osservazioni

Le risorse devono essere pubblicate sui server frontali. Esempio:

```xml
              <%= generateImgTag(content.@["banner-id"]) %>Code HTML généré :<img src="http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg" width="800" height="200" alt="My image"/>
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
