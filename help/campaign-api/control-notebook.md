---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%
---
# Quaderno

Elenco di schede per visualizzare diverse pagine.

![Controllo blocco appunti](assets/notebook.3b531a46.png)

## Proprietà

**coloreIndietro - stringa** Colore di sfondo (btnshadow, bianco).

**nome - stringa** ID contenitore.

**padding-left - integer** Spazio in pixel a sinistra del contenitore.

**spaziatura a destra - numero intero** Spazio in pixel a destra del contenitore.

**padding-top - integer** Spazio in pixel sopra il contenitore.

**padding-bottom - integer** Spazio in pixel sotto il contenitore.

**spaziatura interna - numero intero** Spazio in pixel attorno al contenitore.

**readOnly - boolean** Forza il controllo e tutti i relativi discendenti a sola lettura.

**stile - stringa** piatta \| giù \| su (impostazione predefinita).

## Osservazioni

Ogni sottoelemento rappresenta una pagina. Esempi:

```xml
      <container colspan="2" style="down" type="notebook">
   <container label="Products">
     ...
   </container>

   <container colcount="3" xpath="link">
     ...
   </container>

   <container xpath="linkCollection">
     ...
   </container>
 </container>
```
