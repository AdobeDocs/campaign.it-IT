---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 1%
---
# SubFormButton

Pulsante per aprire un sottomodulo.

![Controllo SubFormButton](assets/button.f0aea09a.png)

## Proprietà

**coloreIndietro - stringa** Colore di sfondo (btnshadow, bianco).

**bordo - stringa** Modifica lo stile della struttura del controllo (solido, doppio, interno, esterno, nessuno).

**discardReadOnly - string** Impedisce la propagazione della proprietà &quot;sola lettura&quot; al modulo secondario.

**font-size - integer** Modifica la dimensione del font.

**img - stringa** immagine associata.

**etichetta - stringa** Etichetta del pulsante.

**nolabel - stringa** Consente di allineare il controllo nella colonna dell&#39;etichetta.

**prebuildSubForm - string** Inizializza il sottomodulo durante la creazione del controllo. Questa opzione è attivata per impostazione predefinita, ma può essere disattivata per accelerare la visualizzazione iniziale.

**obbligatorio - booleano** Il campo è obbligatorio.

## Osservazioni

Esempio:

```xml
      <input type="subformbutton" label="Advanced parameters...">
  <form label=" Advanced parameters">
    <input xpath="@stopIfTooManyRejects"/>
    <input xpath="@traceMode"/>
  </form>
</input>
```
