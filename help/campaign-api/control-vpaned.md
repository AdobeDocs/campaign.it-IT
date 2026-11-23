---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 1%
---
# VPaned

Dispone diversi contenitori in orizzontale.

## Proprietà

**coloreIndietro - stringa** Colore di sfondo (btnshadow, bianco).

**nome - stringa** ID contenitore.

**padding-left - integer** Spazio in pixel a sinistra del contenitore.

**spaziatura a destra - numero intero** Spazio in pixel a destra del contenitore.

**padding-top - integer** Spazio in pixel sopra il contenitore.

**padding-bottom - integer** Spazio in pixel sotto il contenitore.

**spaziatura interna - numero intero** Spazio in pixel attorno al contenitore.

**readOnly - boolean** Forza il controllo e tutti i relativi discendenti a sola lettura.

## Osservazioni

Ogni sottoelemento deve essere un contenitore. Ciascun contenitore secondario può specificare la percentuale della larghezza totale che desidera utilizzare grazie alla proprietà width-percent. Esempio:

```xml
<container type="vpaned">
  <container label="Group 1" width-percent="25"/>
    <input .../>
  </container>
  <container label="Group 2" width-percent="75"/>
    <input .../>
  </container>
</container>
```
