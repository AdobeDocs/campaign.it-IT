---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 3%
---
# ModificaCodice

Controllo per la modifica del codice sorgente.

![Controllo CodeEdit](assets/codeedit.8a744c8b.png)

## Proprietà

**coloreIndietro - stringa** Colore di sfondo (btnshadow, bianco).

**bordo - stringa** Modifica lo stile della struttura del controllo (solido, doppio, interno, esterno, nessuno).

**contentType - string** Lingua del codice sorgente, utilizzata per la colorazione sintattica e altre opzioni collegate alla lingua. Sono supportate le seguenti lingue:

* predefinito
* xml
* dtd
* xsl
* html
* txt
* JavaScript
* sql

È inoltre possibile aggiungere altre lingue modificando il file editor.cfg nella stessa directory di nlclient.exe.

**font-size - integer** Modifica la dimensione del font.

**etichetta - stringa** etichetta associata.

**nolabel - booleano** Nasconde l&#39;etichetta associata.

**readOnly - boolean** Impone al controllo di sola lettura.

**barra degli strumenti - booleano** Visualizza o nasconde la barra degli strumenti.

**toolbarAlign - string** Posizione della barra degli strumenti: orizzontale o verticale.

## Osservazioni

Esempio:

```xml
<input xpath="code" nolabel="true" type="CodeEdit"
       contentType="JavaScript" toolbar="true" toolbarAlign="horizontal"/>
```
