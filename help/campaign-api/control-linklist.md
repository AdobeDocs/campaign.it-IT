---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%
---
# LinkList

Controllo per la modifica delle raccolte.

![Controllo LinkList](assets/linklist.8b71bb0e.png)

## Proprietà

**addButton - booleano** Visualizza il pulsante di aggiunta. Questa opzione è valida solo se è attivata l&#39;opzione hideEditButtons.

**coloreIndietro - stringa** Colore di sfondo (btnshadow, bianco).

**bordo - stringa** Modifica lo stile della struttura del controllo (solido, doppio, interno, esterno, nessuno).

**dblClickAction - stringa** Nome del modulo da aprire al doppio clic.

**delButton - booleano** Visualizza il pulsante Elimina. Questa opzione è valida solo se il pulsante hideEditButtons è attivato.

**enumImage - string** Nome dell&#39;enumerazione di sistema utilizzata per visualizzare l&#39;immagine di ogni riga.

**font-size - integer** Modifica la dimensione del font.

**modulo - stringa** Modulo per modifica collegamenti.

**hideEditButtons - booleano** Nasconde i pulsanti di aggiunta, eliminazione e modifica.

**img - stringa** immagine.

**etichetta - stringa** etichetta associata.

**nolabel - booleano** Nessuna etichetta davanti al controllo.

**noToolbar - booleano** Nasconde la barra degli strumenti.

**orderBy - element** Pianificazione elenco.

**readOnly - boolean** Impone al controllo di sola lettura.

**sysFilter - elemento** Filtro elenco.

**toobarAlign - stringa** orizzontale \| verticale.

**toobarCaption - stringa** Etichetta visualizzata nella barra degli strumenti.

**xpath-link - string** Link dell&#39;elenco (vedi esempio sui gruppi).

**xpathIndex - string** L&#39;indice di selezione verrà archiviato nel percorso specificato da questo percorso.

**xpathLinkEdit - string** Link per la modifica (vedi esempio sui gruppi).

**zoom - booleano** autorizza la modifica del collegamento.

## Osservazioni

Esempi:

```xml
      <input type="linkList" xpath="operator" enumImage="@type" nolabel="true">
  <input xpath="@name" label="Name" colSize="30"/>
  <input xpath="@login"/>
  <sysFilter>
    <condition expr="@type=1"/>
  </sysFilter>
</input>

<input type="linkList" xpath="operator" enumImage="@type" nolabel="true">
  <input xpath="@name" label="Name" colSize="30"/>
  <input xpath="@login"/>
  <form label="Add operators">
  <input xpath="." type="linkListChoice" xpath-link="recipient" img="nms:group.bmp">
  <input xpath="@lastName"/>
  <input xpath="@firstName"/>
  </input>
  </form>
</input>

<input type="linklist" xpath="rcpGrpRel" zoom="true" label="Recipients" form="nms:recipient"
       xpath-link="rcpGroup"
       xpathLinkEdit="recipient">
  <input xpath="recipient/@lastName"/>
  <input xpath="recipient/@firstName"/>
  <input xpath="recipient/@email"/>
  <input xpath="recipient/@phone"/>
</input>
```
