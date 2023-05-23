---
title: Moduli di input per campagne
description: Scopri come personalizzare i moduli di input
feature: Web Forms
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 62908bba-9cfa-42b6-b463-b601496d535b
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '2552'
ht-degree: 0%

---

# Introduzione ai moduli di input{#gs-ac-forms}

Quando si crea o si estende uno schema, è necessario creare o modificare i moduli di input associati per rendere tali modifiche visibili agli utenti finali.

Un modulo di input consente di modificare un’istanza associata a uno schema di dati dalla console client di Adobe Campaign. Il modulo è identificato dal nome e dallo spazio dei nomi.

La chiave di identificazione di un modulo è una stringa costituita dallo spazio dei nomi e dal nome separato da due punti, ad esempio: &quot;cus:contact&quot;.

## Modifica moduli di input

Creare e configurare moduli di input da **[!UICONTROL Administration]> [!UICONTROL Configuration] >[!UICONTROL Input forms]** cartella della console client:

![](assets/form_arbo.png)

L&#39;area di modifica consente di immettere il contenuto XML del modulo di input:

![](assets/form_edit.png)

L’anteprima genera una visualizzazione del modulo di input:

![](assets/form_preview.png)

## Struttura di un modulo

La descrizione di un modulo è un documento XML strutturato che osserva la grammatica dello schema del modulo **xtk:form**.

Il documento XML del modulo di input deve contenere `<form>` elemento principale con  **nome** e  **namespace** attributi per compilare il nome del modulo e lo spazio dei nomi.

```
<form name="form_name" namespace="name_space">
...
</form>
```

Per impostazione predefinita, un modulo è associato allo schema dati con lo stesso nome e lo stesso spazio dei nomi. Per associare un modulo a un nome diverso, impostare **entity-schema** attributo del `<form>` al nome della chiave dello schema. Per illustrare la struttura di un modulo di input, descriviamo un’interfaccia utilizzando lo schema di esempio &quot;cus:recipient&quot;:

```
<srcSchema name="recipient" namespace="cus">
  <enumeration name="gender" basetype="byte">    
    <value name="unknown" label="Not specified" value="0"/>    
    <value name="male" label="Male" value="1"/>   
    <value name="female" label="Female" value="2"/>   
  </enumeration>

  <element name="recipient">
    <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
    <attribute name="birthDate" type="datetime" label="Date"/>
    <attribute name="gender" type="byte" label="Gender" enum="gender"/>
  </element>
</srcSchema>
```

Il modulo di input basato sullo schema di esempio:

![](assets/do-not-localize/form_exemple1.png)

```
<form name="recipient" namespace="cus">
  <input xpath="@gender"/>
  <input xpath="@birthDate"/>
  <input xpath="@email"/>
</form>
```

La descrizione dei controlli di modifica inizia da `<form>` elemento principale. Un controllo di modifica viene immesso in un **`<input>`** elemento con **xpath** attributo contenente il percorso del campo nel relativo schema.

Il controllo di modifica si adatta automaticamente al tipo di dati corrispondente e utilizza l&#39;etichetta definita nello schema.

>[!NOTE]
>
>Puoi sovrascrivere l’etichetta definita nel relativo schema di dati aggiungendo la **etichetta** attribuire a `<input>` elemento:\
>`<input label="E-mail address" xpath="@name" />`

Per impostazione predefinita, ogni campo viene visualizzato su una sola riga e occupa tutto lo spazio disponibile a seconda del tipo di dati.

![](../assets/do-not-localize/book.png) Tutti gli attributi del modulo sono elencati in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/developer/campaign-api/api/control-Button.html){target="_blank"}.

## Formattazione {#formatting}

Il layout dei controlli è simile al layout utilizzato nelle tabelle HTML, con la possibilità di dividere un controllo in più colonne, di interlacciare elementi o di specificare l&#39;occupazione dello spazio disponibile. Tenete presente, tuttavia, che la formattazione consente di dividere l&#39;area solo per le proporzioni; non è possibile specificare dimensioni fisse per un oggetto.

Per visualizzare i controlli dell&#39;esempio precedente in due colonne:

![](assets/do-not-localize/form_exemple2.png)

```
<form name="recipient" namespace="cus">
  <container colcount="2">
    <input xpath="@gender"/>
    <input xpath="@birthDate"/>
    <input xpath="@email"/>
  </container>
</form>
```

Il **`<container>`** elemento con **colcount** attributo consente di forzare la visualizzazione dei controlli figlio in due colonne.

Il **colspan** in un controllo estende il controllo in base al numero di colonne immesse nel relativo valore:

![](assets/do-not-localize/form_exemple3.png)

```
<form name="recipient" namespace="cus">
  <container colcount="2">
    <input xpath="@gender"/>
    <input xpath="@birthDate"/>
    <input xpath="@email" colspan="2"/>
  </container>
</form> 
```

Compilando il **type=&quot;frame&quot;** , il contenitore aggiunge una cornice intorno ai controlli figlio con l&#39;etichetta contenuta nel **etichetta** attributo:

![](assets/do-not-localize/form_exemple4.png)

```
<form name="recipient" namespace="cus">
  <container colcount="2" type="frame" label="General">
    <input xpath="@gender"/>
    <input xpath="@birthDate"/>
    <input xpath="@email" colspan="2"/>
  </container>
</form>
```

A **`<static>`** può essere utilizzato per formattare il modulo di input:

![](assets/do-not-localize/form_exemple5.png)

```
<form name="recipient" namespace="cus">
  <static type="separator" colspan="2" label="General"/>
  <input xpath="@gender"/>
  <input xpath="@birthDate"/>
  <input xpath="@email" colspan="2"/>
  <static type="help" label="General information about recipient with date of birth, gender, and e-mail address." colspan="2"/>
</form>
```

Il **`<static>`** tag con **separatore** tipo consente di aggiungere una barra di separazione con un&#39;etichetta contenuta nel **etichetta** attributo.

È stato aggiunto un testo della guida utilizzando `<static>` tag con tipo di guida. Il contenuto del testo viene immesso nel **etichetta** attributo.

## Utilizzare i contenitori {#containers}

Utilizzare **container** per raggruppare un insieme di controlli. Essi sono rappresentati dal **`<container>`** elemento. Sono stati utilizzati in precedenza per formattare i controlli su più colonne.

Il **xpath** attributo su una `<container>` consente di semplificare il riferimento ai controlli figlio. Il riferimento dei controlli viene quindi relativo al padre `<container>` principale.

Esempio di contenitore senza &quot;xpath&quot;:

```
<container colcount="2">
  <input xpath="location/@zipCode"/>
  <input xpath="location/@city"/>
</container>
```

Esempio con l’aggiunta di &quot;xpath&quot; all’elemento denominato &quot;location&quot;:

```
<container colcount="2" xpath="location">
  <input xpath="@zipCode"/>
  <input xpath="@city"/>
</container>
```

I contenitori vengono utilizzati per creare controlli complessi utilizzando un set di campi formattati nelle pagine.

### Aggiungi schede (blocco appunti) {#tab-container}

Utilizza un **notebook** contenitore per formattare i dati nelle pagine accessibili dalle schede.

![](assets/do-not-localize/form_exemple6.png)

```
<container type="notebook">
  <container colcount="2" label="General">
    <input xpath="@gender"/>
    <input xpath="@birthDate"/>
    <input xpath="@email" colspan="2"/>
  </container>
  <container colcount="2" label="Location">
    ...
  </container>
</container>
```

Il contenitore principale è definito da **type=&quot;notebook&quot;** attributo. Le schede vengono dichiarate nei contenitori figlio e l’etichetta delle schede viene compilata dalla sezione **etichetta** attributo.

Aggiungi il **style=&quot;down&quot;** per forzare il posizionamento verticale delle etichette di tabulazione sotto il controllo. Questo attributo è facoltativo. Il valore predefinito è **&quot;su&quot;**.

![](assets/do-not-localize/form_exemple7.png)

`<container style="down" type="notebook">  ... </container>`

### Aggiungi icone (iconbox) {#icon-list}

Utilizza questo contenitore per visualizzare una barra di icone verticale che consente di selezionare le pagine da visualizzare.

![](assets/do-not-localize/form_exemple8.png)

```
<container type="iconbox">
  <container colcount="2" label="General" img="xtk:properties.png">
    <input xpath="@gender"/>
    <input xpath="@birthDate"/>
    <input xpath="@email" colspan="2"/>
  </container>
  <container colcount="2" label="Location" img="nms:msgfolder.png">
    ...
  </container>
</container>
```

Il contenitore principale è definito da **type=&quot;iconbox&quot;** attributo. Le pagine associate alle icone vengono dichiarate nei contenitori figlio. L’etichetta delle icone viene compilata dal file **etichetta** attributo.

L’icona di una pagina viene compilata dalla sezione `img="<image>"` attributo, dove `<image>` è il nome dell’immagine corrispondente alla sua chiave composta dal nome e dallo spazio dei nomi (ad esempio, &quot;xtk:properties.png&quot;).

Le immagini sono disponibili nella sezione **[!UICONTROL Administration > Configuration > Images]** nodo.

### Nascondi contenitori (visibleGroup) {#visibility-container}

È possibile nascondere un insieme di controlli tramite una condizione dinamica.

Questo esempio illustra la visibilità dei controlli sul valore del campo &quot;Gender&quot;:

```
<container type="visibleGroup" visibleIf="@gender=1">
  ...
</container>
<container type="visibleGroup" visibleIf="@gender=2">
  ...
</container>
```

Un contenitore di visibilità è definito dall&#39;attributo **type=&quot;visibleGroup&quot;**. Il **visibleIf** contiene la condizione di visibilità.

Esempi di sintassi delle condizioni:

* **visibleIf=&quot;@email=&#39;peter.martinezATneeolane.net&#39;&quot;**: verifica l’uguaglianza nei dati di tipo stringa. Il valore di confronto deve essere tra virgolette.
* **visibleIf=&quot;@gender >= 1 e @gender != 2&quot;**: condizione su un valore numerico.
* **visibleIf=&quot;@boolean1=true o @boolean2=false&quot;**: verifica sui campi booleani.

### Visualizzazione condizionale (enabledGroup) {#enabling-container}

Questo contenitore ti consente di abilitare o disabilitare un set di dati da una condizione dinamica. La disattivazione di un controllo ne impedisce la modifica. L’esempio seguente illustra l’abilitazione dei controlli dal valore del campo &quot;Genere&quot;:

```
<container type="enabledGroup" enabledIf="@gender=1">
  ...
</container>
<container type="enabledGroup" enabledIf="@gender=2">
  ...
</container>
```

Un contenitore di abilitazione è definito da **type=&quot;enabledGroup&quot;** attributo. Il **enabledIf** contiene la condizione di attivazione.

## Modificare un collegamento {#editing-a-link}

Ricorda che un collegamento viene dichiarato nello schema di dati come segue:

```
<element label="Company" name="company" target="cus:company" type="link"/>
```

Il controllo di modifica del collegamento nel relativo modulo di input è il seguente:

![](assets/do-not-localize/form_exemple9.png)

```
<input xpath="company"/>
```

La selezione del target è accessibile tramite il campo di modifica. L&#39;immissione è assistita dal completamento automatico in modo che un elemento di destinazione possa essere facilmente trovato dai primi caratteri immessi. La ricerca si basa quindi sul **Stringa di calcolo** definito nello schema di destinazione. Se lo schema non esiste dopo la convalida nel controllo, viene visualizzato un messaggio di conferma della creazione immediata del target. La conferma crea un nuovo record nella tabella di destinazione e lo associa al collegamento.

Viene utilizzato un elenco a discesa per selezionare un elemento di destinazione dall’elenco di record già creato.

Il **[!UICONTROL Modify the link]** (cartella) avvia un modulo di selezione con l’elenco degli elementi target e un’area filtro.

Il **[!UICONTROL Edit link]** (lente di ingrandimento) avvia il modulo di modifica dell’elemento collegato. Il modulo utilizzato viene dedotto per impostazione predefinita sulla chiave dello schema di destinazione. Il **modulo** attribute consente di forzare il nome del modulo di modifica (ad esempio, &quot;cus:company2&quot;).

Puoi limitare la scelta degli elementi target aggiungendo il **`<sysfilter>`** dalla definizione del collegamento nel modulo di input:

```
<input xpath="company">
  <sysFilter>
    <condition expr="[location/@city] =  'Newton"/>
  </sysFilter>
</input>
```

Puoi anche ordinare l’elenco con **`<orderby>`** elemento:

```
<input xpath="company">
  <orderBy>
    <node expr="[location/@zipCode]"/>
  </orderBy>
</input>
```

## Proprietà controllo {#control-properties}

* **noAutoComplete**: disabilita la funzione di completamento automatico (con il valore &quot;true&quot;)
* **createMode**: crea il collegamento al volo se non esiste. I valori possibili sono:

   * **nessuno**: disabilita la creazione di. Se il collegamento non esiste, viene visualizzato un messaggio di errore
   * **in linea**: crea il collegamento con il contenuto nel campo di modifica
   * **edizione**: visualizza il modulo di modifica sul collegamento. Quando il modulo viene convalidato, i dati vengono salvati (modalità predefinita)

* **noZoom**: nessun modulo di modifica sul collegamento (con il valore &quot;true&quot;)
* **modulo**: sovraccarica il modulo di modifica dell’elemento di destinazione

## Aggiungi un elenco di collegamenti (non associati) {#list-of-links}

Un collegamento immesso nello schema dati come elemento di raccolta (unbound=&quot;true&quot;) deve scorrere un elenco per visualizzare tutti gli elementi associati.

Il principio consiste nella visualizzazione dell’elenco degli elementi collegati con caricamento dei dati ottimizzato (download per batch di dati, esecuzione dell’elenco solo se è visibile).

Esempio di un collegamento di raccolta in uno schema:

```
<element label="Events" name="rcpEvent" target="cus:event" type="link" unbound="true">
...
</element>
```

L’elenco nella sua forma di input:

```
 <input xpath="rcpEvent" type="linklist">
  <input xpath="@label"/>
  <input xpath="@date"/>
</input>
```

Il controllo elenco è definito da **type=&quot;linklist&quot;** attributo. Il percorso dell’elenco deve fare riferimento al collegamento della raccolta.

Le colonne vengono dichiarate tramite **`<input>`** elementi dell&#39;elenco. Il **xpath** l&#39;attributo fa riferimento al percorso del campo nello schema di destinazione.

Una barra degli strumenti con un’etichetta (definita sul collegamento nello schema) viene automaticamente posizionata sopra l’elenco.

L’elenco può essere filtrato tramite **[!UICONTROL Filters]** e configurate per aggiungere e ordinare le colonne.

Il **[!UICONTROL Add]** e **[!UICONTROL Delete]** I pulsanti consentono di aggiungere ed eliminare elementi della raccolta sul collegamento. Per impostazione predefinita, l’aggiunta di un elemento avvia il modulo di modifica dello schema di destinazione.

Il **[!UICONTROL Detail]** viene aggiunto automaticamente quando **zoom=&quot;true&quot;** l&#39;attributo è completato il **`<input>`** tag dell’elenco: ti consente di avviare il modulo di modifica della riga selezionata.

È possibile applicare filtri e ordinamenti durante il caricamento dell’elenco:

```
 <input xpath="rcpEvent" type="linklist">
  <input xpath="@label"/>
  <input xpath="@date"/>
  <sysFilter>
    <condition expr="@type = 1"/>
  </sysFilter>
  <orderBy>
    <node expr="@date" sortDesc="true"/>
  </orderBy>
</input>
```

## Definire una tabella di relazioni {#relationship-table}

Una tabella di relazione consente di collegare due tabelle con cardinalità N-N. La tabella delle relazioni contiene solo i collegamenti alle due tabelle.

L’aggiunta di un elemento all’elenco dovrebbe pertanto consentirti di completare un elenco da uno dei due collegamenti nella tabella delle relazioni.

Esempio di tabella di relazioni in uno schema:

```
<srcSchema name="subscription" namespace="cus">
  <element name="recipient" type="link" target="cus:recipient" label="Recipient"/>
  <element name="service" type="link" target="cus:service" label="Subscription service"/>
</srcSchema>
```

Nel nostro esempio, iniziamo con il modulo di input dello schema &quot;cus:recipient&quot;. L’elenco deve visualizzare le associazioni con gli abbonamenti ai servizi e deve consentirti di aggiungere un abbonamento selezionando un servizio esistente.

![](assets/do-not-localize/form_exemple12.png)

```
<input type="linklist" xpath="subscription" xpathChoiceTarget="service" xpathEditTarget="service" zoom="true">
  <input xpath="recipient"/>
  <input xpath="service"/>
</input>
```

Il **xpathChoiceTarget** attributo consente di avviare un modulo di selezione dal collegamento inserito. La creazione del record della tabella delle relazioni aggiornerà automaticamente il collegamento al destinatario corrente e al servizio selezionato.

>[!NOTE]
>
>Il **xpathEditTarget** L&#39;attributo consente di forzare la modifica della riga selezionata sul collegamento inserito.

### Proprietà elenco {#list-properties}

* **noToolbar**: nasconde la barra degli strumenti (con il valore &quot;true&quot;)
* **toolbarCaption**: sovraccarica l’etichetta della barra degli strumenti
* **toolbarAlign**: modifica la geometria verticale o orizzontale della barra degli strumenti (valori possibili: &quot;verticale&quot;|&quot;orizzontale&quot;)
* **img**: visualizza l’immagine associata all’elenco
* **modulo**: sovraccarica il modulo di modifica dell’elemento di destinazione
* **zoom**: aggiunge **[!UICONTROL Zoom]** per modificare l’elemento di destinazione
* **xpathEditTarget**: imposta la modifica sul collegamento inserito
* **xpathChoiceTarget**: avvia inoltre il modulo di selezione sul collegamento inserito

## Aggiungere un elenco di controlli memoria {#memory-list-controls}

Gli elenchi di memoria consentono di modificare gli elementi della raccolta utilizzando il precaricamento dei dati dell’elenco. Questo elenco non può essere filtrato o configurato.

Questi elenchi vengono utilizzati su elementi di raccolta XML mappati o su collegamenti di volumi ridotti.

## Aggiungere un elenco di colonne {#column-list}

Questo controllo visualizza un elenco di colonne modificabile con una barra degli strumenti contenente i pulsanti Aggiungi ed Elimina.

```
<input xpath="rcpEvent" type="list">
  <input xpath="@label"/>
  <input xpath="@date"/>
</input>
```

Il controllo elenco deve essere compilato con **type=&quot;list&quot;** e il percorso dell&#39;elenco deve fare riferimento all&#39;elemento collection.

Le colonne vengono dichiarate nell&#39;elemento figlio **`<input>`** dell’elenco. L’etichetta e la dimensione della colonna possono essere forzate con **etichetta** e **colSize** attributi.

>[!NOTE]
>
>Le frecce di ordinamento vengono aggiunte automaticamente quando **ordered=&quot;true&quot;** L&#39;attributo viene aggiunto all&#39;elemento di raccolta nello schema dati.

I pulsanti della barra degli strumenti possono essere allineati orizzontalmente:

```
<input nolabel="true" toolbarCaption="List of events" type="list" xpath="rcpEvent" zoom="true">
  <input xpath="@label"/>
  <input xpath="@date"/>
</input>
```

Il **toolbarCaption** L&#39;attributo forza l&#39;allineamento orizzontale della barra degli strumenti e immette il titolo sopra l&#39;elenco.

### Abilitare lo zoom avanti in un elenco {#zoom-in-a-list}

L&#39;inserimento e la modifica dei dati in un elenco possono essere immessi in un modulo di modifica separato.

```
<input nolabel="true" toolbarCaption="List of events" type="list" xpath="rcpEvent" zoom="true" zoomOnAdd="true">
  <input xpath="@label"/>
  <input xpath="@date"/>

  <form colcount="2" label="Event">
    <input xpath="@label"/>
    <input xpath="@date"/>
  </form>
</input>
```

Il modulo di modifica viene completato da `<form>`  elemento nella definizione dell’elenco. La sua struttura è identica a quella di un modulo di input. Il **[!UICONTROL Detail]** viene aggiunto automaticamente quando **zoom=&quot;true&quot;** l&#39;attributo è completato il **`<input>`** dell’elenco. Questo attributo consente di avviare il modulo di modifica della riga selezionata.

>[!NOTE]
>
>Aggiunta di **zoomOnAdd=&quot;true&quot;** attribute forza la chiamata del modulo di modifica quando viene inserito un elemento elenco.

### Proprietà elenco {#list-properties-1}

* **noToolbar**: nasconde la barra degli strumenti (con il valore &quot;true&quot;)
* **toolbarCaption**: sovraccarica l’etichetta della barra degli strumenti
* **toolbarAlign**: modifica il posizionamento della barra degli strumenti (valori possibili: &quot;verticale&quot;|&quot;orizzontale&quot;)
* **img**: visualizza l’immagine associata all’elenco
* **modulo**: sovraccarica il modulo di modifica dell’elemento di destinazione
* **zoom**: aggiunge **[!UICONTROL Zoom]** per modificare l’elemento di destinazione
* **zoomOnAdd**: avvia il modulo di modifica sull’aggiunta
* **xpathChoiceTarget**: avvia inoltre il modulo di selezione sul collegamento inserito

## Aggiungi campi non modificabili {#non-editable-fields}

Per visualizzare un campo e impedirne la modifica, utilizzare **`<value>`** o completa il **readOnly=&quot;true&quot;** attributo su **`<input>`** tag.

Esempio sul campo &quot;Genere&quot;:

![](assets/do-not-localize/form_exemple16.png)

```
<value value="@gender"/>
<input xpath="@gender" readOnly="true"/>
```

## Pulsante di scelta Aggiungi {#radio-button}

Un pulsante di scelta consente di scegliere tra diverse opzioni. Il **`<input>`** i tag vengono utilizzati per elencare le opzioni possibili e le **selectedValue** attribute specifica il valore associato alla scelta.

Esempio sul campo &quot;Genere&quot;:

```
<input type="RadioButton" xpath="@gender" checkedValue="0" label="Choice 1"/>
<input type="RadioButton" xpath="@gender" checkedValue="1" label="Choice 2"/>
<input type="RadioButton" xpath="@gender" checkedValue="2" label="Choice 3"/>
```

![](assets/do-not-localize/form_exemple17.png)

## Aggiungi una casella di controllo {#checkbox}

Una casella di controllo riflette uno stato booleano (selezionato o meno). Per impostazione predefinita, questo controllo viene utilizzato dai campi &quot;booleani&quot; (true/false). A questo pulsante può essere associata una variabile che assume un valore predefinito pari a 0 o 1. Questo valore può essere sovraccaricato tramite **checkValue** attributi.

```
<input xpath="@boolean1"/>
<input xpath="@field1" type="checkbox" checkedValue="Y"/>
```

![](assets/do-not-localize/form_exemple20.png)

## Modifica gerarchia di navigazione {#navigation-hierarchy-edit}

Questo controllo crea una struttura ad albero su un insieme di campi da modificare.

I controlli da modificare sono raggruppati in un **`<container>`** immessi in **`<input>`** tag del controllo struttura:

```
<input nolabel="true" type="treeEdit">
  <container label="Text fields">
    <input xpath="@text1"/>
    <input xpath="@text2"/>
  </container>
  <container label="Boolean fields">
    <input xpath="@boolean1"/>
    <input xpath="@boolean2"/>
  </container>
</input>
```

![](assets/do-not-localize/form_exemple18.png)

## Aggiungere un campo espressione {#expression-field}

Un campo espressione aggiorna dinamicamente un campo da un’espressione; il campo **`<input>`** viene utilizzato con un tag **xpath** per immettere il percorso del campo da aggiornare e un attributo **espr** attributo contenente l&#39;espressione di aggiornamento.

```
<!-- Example: updating the boolean1 field from the value contained in the field with path /tmp/@flag -->
<input expr="Iif([/tmp/@flag]=='On', true, false)" type="expr" xpath="@boolean1"/>
<input expr="[/ignored/@action] == 'FCP'" type="expr" xpath="@launchFCP"/>
```

## Contesto dei moduli {#context-of-forms}

L&#39;esecuzione di un modulo di input inizializza un documento XML contenente i dati dell&#39;entità da modificare. Questo documento rappresenta il contesto del modulo e può essere utilizzato come area di lavoro.

### Aggiornare il contesto {#updating-the-context}

Per modificare il contesto del modulo, utilizzare `<set expr="<value>" xpath="<field>"/>` tag, dove `<field>` è il campo di destinazione, e `<value>` è l’espressione o il valore di aggiornamento.

Esempi di utilizzo del `<set>` tag:

* **`<set expr="'Test'" xpath="/tmp/@test" />`**: posiziona il valore &quot;Test&quot; nella posizione temporanea /tmp/@test1
* **`<set expr="'Test'" xpath="@lastName" />`**: aggiorna l’entità sull’attributo &quot;lastName&quot; con il valore &quot;Test&quot;
* **`<set expr="true" xpath="@boolean1" />`**: imposta il valore del campo &quot;boolean1&quot; su &quot;true&quot;
* **`<set expr="@lastName" xpath="/tmp/@test" />`**: viene aggiornato con il contenuto dell’attributo &quot;lastName&quot;

È possibile aggiornare il contesto del modulo durante l&#39;inizializzazione e la chiusura del modulo tramite **`<enter>`** e **`<leave>`** tag.

```
<form name="recipient" namespace="cus">
  <enter>
    <set...
  </enter>
  ...
  <leave>
    <set...
  </leave>
</form>
```

>[!NOTE]
>
>Il `<enter>`  e  `<leave>`   I tag possono essere utilizzati nel `<container>` di pagine (tipi &quot;notebook&quot; e &quot;iconbox&quot;).

### Linguaggio di espressione {#expression-language-}

Nella definizione del modulo è possibile utilizzare un linguaggio macro per eseguire test condizionali.

Il **`<if expr="<expression>" />`** Il tag esegue le istruzioni specificate nel tag se l’espressione viene verificata:

```
<if expr="([/tmp/@test] == 'Test' or @lastName != 'Doe') and @boolean2 == true">
  <set xpath="@boolean1" expr="true"/>
</if>
```

Il **`<check expr="<condition>" />`** combinato con **`<error>`** impedisce la convalida del modulo e visualizza un messaggio di errore se la condizione non viene soddisfatta:

```
<leave>
  <check expr="/tmp/@test != ''">
    <error>You must populate the 'Test' field!</error> 
  </check>
</leave>
```

## Assistente (procedura guidata) {#wizards}

Un assistente ti guida attraverso un set di passaggi di immissione dati sotto forma di pagine. I dati immessi vengono salvati al momento della convalida del modulo.

Per aggiungere un assistente, utilizza il seguente tipo di struttura:

```
<form type="wizard" name="example" namespace="cus" img="nms:rcpgroup32.png" label="Wizard example" entity-schema="nms:recipient">
  <container title="Title of page 1" desc="Long description of page 1">
    <input xpath="@lastName"/>
    <input xpath="comment"/>
  </container>
  <container title="Title of page 2" desc="Long description of page 2">
    ...
  </container>
  ...
</form>
```

La presenza del **type=&quot;wizard&quot;** attributo su `<form>` consente di definire la modalità procedura guidata nella costruzione del modulo. Le pagine vengono completate da `<container>` elementi, che sono figli di `<form>` elemento. Il `<container>` L&#39;elemento di una pagina viene compilato con gli attributi title per il titolo e desc per visualizzare la descrizione sotto il titolo della pagina. Il **[!UICONTROL Previous]** e **[!UICONTROL Next]** I pulsanti vengono aggiunti automaticamente per consentire la navigazione tra le pagine.

Il **[!UICONTROL Finish]** consente di salvare i dati immessi e di chiudere il modulo.

### Metodi SOAP {#soap-methods}

L&#39;esecuzione del metodo SOAP può essere avviata da un **`<leave>`** alla fine di una pagina.

Il **`<soapcall>`** Il tag contiene la chiamata per il metodo con i seguenti parametri di input:

```
<soapCall name="<name>" service="<schema>">
  <param type="<type>" exprIn="<xpath>"/>  
  ...
</soapCall>
```

Il nome del servizio e il relativo schema di implementazione vengono immessi tramite **nome** e **servizio** attributi di **`<soapcall>`** tag.

I parametri di input sono descritti nella **`<param>`** elementi sotto **`<soapcall>`** tag.

Il tipo di parametro deve essere specificato tramite **tipo** attributo. I tipi possibili sono i seguenti:

* **stringa**: stringa di caratteri
* **booleano**: booleano
* **byte**: numero intero a 8 bit
* **corto**: numero intero a 16 bit
* **long**: numero intero a 32 bit
* **corto**: numero intero a 16 bit
* **doppio**: numero a virgola mobile a doppia precisione
* **DOMElement**: nodo di tipo elemento

Il **exprIn** contiene la posizione dei dati da passare come parametro.

**Esempio**:

```
<leave>
  <soapCall name="RegisterGroup" service="nms:recipient">         
    <param type="DOMElement" exprIn="/tmp/entityList"/>         
    <param type="DOMElement" exprIn="/tmp/choiceList"/>         
    <param type="boolean"    exprIn="true"/>       
  </soapCall>
</leave>
```
