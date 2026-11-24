---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 1%
---
# ModificaDiagramma

Questo controllo viene utilizzato per modificare diagrammi quali flussi di lavoro o sondaggi.

![Controllo DiagramEdit](assets/diagramedit.d750db7e.png)

## Proprietà

**coloreIndietro - stringa** Colore di sfondo (btnshadow, bianco).

**bordo - stringa** Modifica lo stile della struttura del controllo (solido, doppio, interno, esterno, nessuno).

**etichetta - stringa** etichetta associata.

**nolabel - booleano** Visualizza l&#39;etichetta come una bolla di aiuto.

**readOnly - boolean** Impone al controllo di sola lettura.

## Osservazioni

La barra degli strumenti può essere personalizzata. Ogni sottoelemento di questo controllo corrisponde a pulsanti aggiuntivi nella barra degli strumenti.

```xml
<input type="diagramEdit" xpath=".">
  <input type="separator"/>
  <input img="xtk:properties.png" label="Properties" resetForm="true" prebuildSubForm="true">
    <form name="properties" label="Properties">
      <input xpath="/tmp/@test"/>
    </form>
  </input>
  <input type="separator"/>
  <input img="nms:prepare.png" label="Publish" checkModify="true">
    <form name="properties" label="Properties">
      <input xpath="/tmp/@test"/>
    </form>
  </input>
</input>
```

Per ulteriori informazioni sui pulsanti nella barra degli strumenti, vedere la documentazione relativa ai controlli SubFormButton.
