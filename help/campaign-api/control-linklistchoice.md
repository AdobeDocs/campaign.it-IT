---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 1%
---
# LinkListChoice

Scelta di una o più entità.

## Proprietà

**coloreIndietro - stringa** Colore di sfondo (btnshadow, bianco).

**bordo - stringa** Modifica lo stile della struttura del controllo (solido, doppio, interno, esterno, nessuno).

**dblClickAction - stringa** Nome del modulo da aprire al doppio clic.

**font-size - integer** Modifica la dimensione del font.

**etichetta - stringa** etichetta associata.

**multiSelection - booleano** Autorizza la selezione multipla

**nolabel - booleano** Nasconde l&#39;etichetta associata.

**readOnly - boolean** Impone al controllo di sola lettura.

**serialize - booleano** Salva l&#39;ultima selezione nella configurazione utente.wu

**xpath-link - string** Link dell&#39;elenco.

## Osservazioni

Esempi:

```xml
      <input xpath="." type="linkListChoice" xpath-link="operator">
  <input xpath="[/]"  label="Operator or named right "/>
  <input xpath="@type"/>
  <input xpath="comment"/>
  <sysFilter>
    <condition expr="@type <> 1"/>
  </sysFilter>
  <orderBy>
    <node expr="@type"/>
  </orderBy>
</input>
```
