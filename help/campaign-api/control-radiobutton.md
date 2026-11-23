---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 2%
---
# RadioButton

Un pulsante di scelta consente di scegliere tra diverse opzioni. I tag &lt;input> vengono utilizzati per enumerare le opzioni possibili.

![Controllo RadioButton](assets/radio.11bc90a8.png)

## Proprietà

**coloreIndietro - stringa** Colore di sfondo (btnshadow, bianco).

**border - string** Modifica lo stile del bordo del controllo (solid, double, inset, outset, none).

**valore selezionato - stringa** Valore collegato alla scelta.

**font-size - integer** Modifica la dimensione del font.

**etichetta - stringa** etichetta associata.

**nolabel - booleano** Nasconde l&#39;etichetta associata.

**readOnly - boolean** Impone al controllo di sola lettura.

## Osservazioni

Esempio:

```xml
      <input type="RadioButton" xpath="@gender" checkedValue="0" label="Choice 1"/>
<input type="RadioButton" xpath="@gender" checkedValue="1" label="Choice 2"/>
<input type="RadioButton" xpath="@gender" checkedValue="2" label="Choice 3"/>
```
