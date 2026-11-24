---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 1%
---
# Elenco

Elenco di memoria.

## Proprietà

**coloreIndietro - stringa** Colore di sfondo (btnshadow, bianco).

**bordo - stringa** Modifica lo stile della struttura del controllo (solido, doppio, interno, esterno, nessuno).

**editable - boolean** autorizza la modifica dell&#39;elenco.

**font-size - integer** Modifica la dimensione del font.

**modulo - stringa** Modulo di modifica.

**img - stringa** Immagine per ogni riga.

**etichetta - stringa** etichetta associata.

**nolabel - booleano** Nessuna etichetta.

**notitle - booleano** Non visualizza i titoli delle colonne.

**noToolbar - booleano** Nasconde la barra degli strumenti.

**ordinato - booleano** autorizza la pianificazione degli elenchi.

**readOnly - boolean** Impone al controllo di sola lettura.

**toobarAlign - stringa** orizzontale \| verticale.

**toobarCaption - stringa** Etichetta visualizzata nella barra degli strumenti.

**zoom - booleano** Visualizza il modulo di modifica.

**zoomOnAdd - booleano** Apre un modulo quando viene aggiunta una riga.

**xpathIndex - xpath** L&#39;indice della selezione verrà archiviato nel percorso specificato da questo percorso.

**xpathSelection - xpath** Il nodo in cui verrà archiviato il percorso XPATH per raggiungere l&#39;elemento selezionato.

## Osservazioni

Esempio 1:

```xml
      <input type="list" xpath="dataTransferStep" nolabel="true" editable="false"
       zoom="true" form="xtk:exportSource" zoomOnAdd="true" img="xtk:script.bmp">
  <input xpath="@name" colSize="15"/>
  <input xpath="@active" editable="true" colSize="15"/>
</input>
```

Esempio 2:

```xml
<input type="list" xpath="operator" zoom="true">
  <input xpath="@name" colSize="15"/>
  <form>
    <input xpath="@name"/>
  </form>
</input>
```
