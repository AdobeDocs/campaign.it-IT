---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 1%
---
# HPaned

Dispone verticalmente diversi contenitori.

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

Ogni sottoelemento deve essere un contenitore. Ciascuno dei relativi contenitori secondari può specificare la percentuale dell’altezza totale che desidera utilizzare grazie alla proprietà altezza-percentuale. Esempio:

```xml
<container type="hpaned">
  <container label="Group 1" height-percent="25"/>
    <input .../>
  </container>
  <container label="Group 2" height-percent="75"/>
    <input .../>
  </container>
</container>
```
