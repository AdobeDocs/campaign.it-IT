---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 6%
---
# aggiungi

Aggiunge una nuova entità alla raccolta.

```text
add ( [index ], xml)
```

## Parametri

**index** L&#39;entità verrà aggiunta in questo punto dell&#39;indice. Se questo argomento non viene specificato, l&#39;entità verrà aggiunta alla fine dell&#39;elenco.

**xml** l&#39;entità da inserire nel modulo XML.

## Valore restituito

L’elemento creato.

## Osservazioni

Nell&#39;esempio seguente vengono illustrati due modi diversi per aggiungere un nuovo elemento a una raccolta. La prima soluzione passa la definizione completa dell’elemento al metodo add(), mentre la seconda passa e l’elemento &lt;attachment/> vuoto assegna quindi gli attributi nel modo normale.

```javascript
var delivery = NLWS.nmsDelivery.load("12435")

delivery.attachment.add(
  {attachment: {
    compressMode: "print", filterActive: "false", label: "First File", 
    nameScriptActive: "false", type: "normal", upload: "false", 
    name: { $: "file1.txt" }
  }})

var attach = delivery.attachment.add()
attach.label            = "Second File"
attach.name             = "file2.txt"
attach.compressMode     = "print"
attach.type             = "normal"
attach.filterActive     = false
attach.nameScriptActive = false
attach.upload           = false

delivery.save()
```

Le due soluzioni sono equivalenti, ma la seconda consente di utilizzare i tipi JavaScript corrispondenti ai tipi di attributo, mentre la prima supporta solo le stringhe.

## Funzioni

**Metodo di classe:** [EntityCollection](c-entitycollection.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
