---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%
---
# LinkEdit

Controllo per la modifica di collegamenti.

![Controllo LinkEdit](assets/linkedit.7cb7bf14.png)

## Proprietà

**coloreIndietro - stringa** Colore di sfondo (btnshadow, bianco).

**bordo - stringa** Modifica lo stile della struttura del controllo (solido, doppio, interno, esterno, nessuno).

**choiceButton - booleano** Nasconde o mostra il pulsante di scelta (nascosto per impostazione predefinita).

**computeStringExpr - stringa** Espressione campo calcolato.

**computestringKey - string** Aggiorna la stringa calcolata anziché la chiave esterna.

**computeStringAlias - stringa** Alias stringa calcolato.

**createMode - string** Crea il collegamento se non esiste (none, inline), con la modalità di modifica predefinita.

**externalKey - boolean** Utilizza la chiave esterna.

**font-size - integer** Modifica la dimensione del font.

**modulo - stringa** Forza il modulo di modifica del collegamento.

**etichetta - stringa** etichetta associata.

**loadEntityOnChange - booleano** Ricarica l&#39;entità quando il collegamento cambia.

**obbligatorio - booleano** Nega valori vuoti.

**noAutoComplete - booleano** Disattiva la modalità di completamento automatico.

**noEdition - booleano** Impossibile modificare il collegamento.

**nolabel - booleano** Nasconde l&#39;etichetta associata.

**notificationPathList - string** Elenco di XPaths separati dagli elementi collegati da virgole, da caricare nel contesto.

**noTransaction - boolean** Disattiva la modalità transazionale.

**noZoom - booleano** Nessun modulo di modifica dei collegamenti.

**orderBy - element** Pianificazione delle scelte.

**readOnly - boolean** Impone al controllo di sola lettura.

**obbligatorio - booleano** Il campo è obbligatorio.

**schema - stringa** Schema del collegamento.

**serialize - boolean** Salva l&#39;ultima selezione nella configurazione utente.

**sysFilter - element** Limitazione di scelte.

**xpathMandatory - string** Percorso di una proprietà booleana che indica se il collegamento può essere vuoto o meno.

## Osservazioni

Esempi:

```xml
<input xpath="operator">
  <sysFilter>
    <condition expr="@type= 1/>
  </sysFilter>
  <orderBy>
    <node expr="@name"/>
  </orderBy>
</input>

<input xpath="/tmp/recipient" type="linkEdit" label="Recipient"
       schema="nms:recipient">
```
