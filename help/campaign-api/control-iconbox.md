---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 3%
---
# Iconbox

Elenco di icone che consentono la selezione di più pagine.

![Controllo Iconbox](assets/iconbox.05daa4bf.png)

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

Ogni sottoelemento contenitore rappresenta una pagina. Esempio:

```xml
<container name="iconbox" type="iconbox">
   <container colcount="3" label="Header">
     ...
   </container>
   <container img="ncm:ctprop.bmp" label="Intro">
     ...
   </container>
   <container img="ncm:subsection.bmp" label="Event">
     ...
   </container>
   <container img="ncm:book.bmp" label="Selection">
     ...
   </container>
   <container img="nms:contacts.bmp" label="Services">
     ...
   </container>
   <container img="nms:contacts.bmp" label="Mail footer ">
     ...
   </container>
 </container>
```
