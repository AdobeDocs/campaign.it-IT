---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 1%
---
# TreeEdit

Controllo per visualizzare e modificare vari valori raggruppati in varie categorie.

![Controllo TreeEdit](assets/treeedit.253f1374.png)

## Proprietà

**coloreIndietro - stringa** Colore di sfondo (btnshadow, bianco).

**bordo - stringa** Modifica lo stile della struttura del controllo (solido, doppio, interno, esterno, nessuno).

**editable - string** Autorizza la modifica (true per impostazione predefinita).

**font-size - integer** Modifica la dimensione del font.

**etichetta - stringa** etichetta associata.

**noImage - string** Nasconde le immagini degli elementi dell&#39;elenco.

**nolabel - booleano** Nasconde l&#39;etichetta associata.

**readOnly - boolean** Impone al controllo di sola lettura.

## Osservazioni

Proprietà dei sottoelementi

* visibleIf: una condizione XTK per visualizzare o nascondere l&#39;elemento.
* label: label dell’elemento.
* exprLabel: etichetta dell&#39;elemento sotto forma di espressione.
* xpath: XPath dell’elemento.
* img: Immagine dell’elemento.

Proprietà dei sottoelementi di input

* modificabile: valore modificabile. Il valore predefinito viene ereditato dall&#39;elemento principale.

Proprietà dei sottoelementi contenitore

* compressa: true\|false Visualizza o nasconde gli elementi secondari.

Esempio:

```xml
<input nolabel="true" type="treeEdit">
  <container label="Text fields">
    <input xpath="@text1"/>
    <input xpath="@text2"/>
    <input xpath="@text3"/>
    <input xpath="@text4"/>
    <input xpath="@text5"/>
  </container>
  <container label="Boolean fields">
    <input xpath="@boolean1"/>
    <input xpath="@boolean2"/>
    <input xpath="@boolean3"/>
  </container>
</input>
    
```
