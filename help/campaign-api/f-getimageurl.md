---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 22%
---
# getImageUrl

Abilita la generazione dell&#39;URL di accesso alle risorse pubbliche

```text
getImageUrl (ID|internal name)
```

## Parametri

**ID\|nome interno** ID della risorsa pubblica o nome interno della risorsa.

## Valore restituito

Restituisce l&#39;URL di accesso alla risorsa pubblica.

## Osservazioni

Le risorse devono essere pubblicate sui server frontali. Esempio:

```xml
              <%= getImageUrl(content.@["banner-id"]) %>Code HTML généré :http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg
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
