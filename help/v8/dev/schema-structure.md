---
title: Struttura dello schema della campagna
description: Struttura dello schema della campagna
feature: Schema Extension, Configuration, Data Model
role: Developer
level: Intermediate, Experienced
exl-id: 9c4a9e71-3fc8-4b4e-8782-0742bbeaf426
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '1395'
ht-degree: 1%

---

# Struttura dello schema{#schema-structure}

La struttura di base di un `<srcschema>` è il seguente:

```
<srcSchema>
    <enumeration>
        ...          //definition of enumerations
    </enumeration>
   
    <element>         //definition of the root <element>    (mandatory)

        <compute-string/>  //definition of a compute-string
        <key>
            ...        //definition of keys
        </key>
        <sysFilter>
            ...           //definition of filters
        </sysFilter>
        <attribute>
            ...             //definition of fields
        </attribute>
    
            <element>           //definition of sub-<element> 
                  <attribute>           //(collection, links or XML)
                  ...                         //and additional fields
                  </attribute>
                ...
            </element>
      
    </element> 

        <methods>                 //definition of SOAP methods
            <method>
                ...
            </method>
            ...
    </methods>  
          
</srcSchema>
```

Il documento XML di uno schema dati deve contenere **`<srcschema>`** elemento principale con **nome** e **namespace** attributi per popolare il nome dello schema e il relativo spazio dei nomi.

```
<srcSchema name="schema_name" namespace="namespace">
...
</srcSchema>
```

Per illustrare la struttura di uno schema di dati, utilizziamo i seguenti contenuti XML:

```
<recipient email="John.doe@aol.com" created="AAAA/DD/MM" gender="1"> 
  <location city="London"/>
</recipient>
```

Con lo schema di dati corrispondente:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <attribute name="email"/>
    <attribute name="created"/>
    <attribute name="gender"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

## Descrizione {#description}

Il punto di ingresso dello schema è il suo elemento principale. È facile da identificare perché ha lo stesso nome dello schema e dovrebbe essere l’elemento secondario dell’elemento principale. La descrizione del contenuto inizia con questo elemento.

Nel nostro esempio, l’elemento principale è rappresentato dalla seguente riga:

```
<element name="recipient">
```

Gli elementi **`<attribute>`** e **`<element>`** che seguono l&#39;elemento principale consentono di definire le posizioni e i nomi degli elementi dati nella struttura XML.

Nello schema di esempio, questi sono:

```
<attribute name="email"/>
<attribute name="created"/>
<attribute name="gender"/>
<element name="location">
  <attribute name="city"/>
</element>
```

Devono essere rispettate le seguenti regole:

* Ogni **`<element>`** e **`<attribute>`** devono essere identificati per nome tramite **nome** attributo.

  >[!CAUTION]
  >
  >Il nome dell&#39;elemento deve essere conciso, preferibilmente in inglese, e includere solo caratteri autorizzati in conformità alle regole di denominazione XML.

* Solo **`<element>`** Gli elementi possono contenere **`<attribute>`** elementi e **`<element>`** elementi nella struttura XML.
* Un **`<attribute>`** deve avere un nome univoco all&#39;interno di un **`<element>`**.
* L&#39;uso di **`<elements>`** nelle stringhe di dati su più righe è consigliato.

## Tipi di dati {#data-types}

Il tipo di dati viene immesso tramite **tipo** attributo in **`<attribute>`** e **`<element>`** elementi.

Un elenco dettagliato è disponibile in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html#configuring-campaign-classic).

Quando questo attributo non viene popolato, **stringa** è il tipo di dati predefinito a meno che l&#39;elemento non contenga elementi figlio. In caso affermativo, viene utilizzato solo per strutturare gli elementi in modo gerarchico (**`<location>`** nel nostro esempio).

Negli schemi sono supportati i seguenti tipi di dati:

* **stringa**: stringa di caratteri. Esempi: un nome, una città, ecc.

  La dimensione può essere specificata tramite il **length** (facoltativo, valore predefinito &quot;255&quot;).

* **booleano**: campo booleano Esempio di valori possibili: true/false, 0/1, sì/no, ecc.
* **byte**, **corto**, **long**: numeri interi (1 byte, 2 byte, 4 byte). Esempi: un’età, un numero di conto, un numero di punti, ecc.
* **doppio**: numero a virgola mobile a doppia precisione. Esempi: un prezzo, un tasso, ecc.
* **data**, **datetime**: date e date + ore. Esempi: una data di nascita, una data di acquisto, ecc.
* **datetimenotz**: data + ora senza dati relativi al fuso orario.
* **intervallo di tempo**: durate. Esempio: anzianità.
* **promemoria**: campi di testo lunghi (più righe). Esempi: una descrizione, un commento, ecc.
* **uuid**: campi &quot;uniqueidentifier&quot;

  >[!NOTE]
  >
  >Per contenere un **uuid** , la funzione &quot;newuuid()&quot; deve essere aggiunta e completata con il relativo valore predefinito.

Di seguito è riportato uno schema di esempio con i tipi immessi:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <attribute name="email" type="string" length="80"/>
    <attribute name="created" type="datetime"/>
    <attribute name="gender" type="byte"/>
    <element name="location">
      <attribute name="city" type="string" length="50"/>
   </element>
  </element>
</srcSchema>
```

## Properties {#properties}

Il **`<elements>`** e **`<attributes>`** Gli elementi dello schema dati possono essere arricchiti con varie proprietà. Puoi popolare un’etichetta per descrivere l’elemento corrente.

### Etichette e descrizioni {#labels-and-descriptions}

* Il **etichetta** consente di immettere una breve descrizione.

  >[!NOTE]
  >
  >L’etichetta è associata alla lingua corrente dell’istanza.

  **Esempio**:

  ```
  <attribute name="email" type="string" length="80" label="Email"/>
  ```

  L’etichetta può essere vista dal modulo di input della console client di Adobe Campaign:

  ![](assets/schema_label.png)

* Il **desc** consente di immettere una descrizione lunga.

  La descrizione può essere visualizzata dal modulo di input nella barra di stato della finestra principale di Adobe Campaign Client Console.

  >[!NOTE]
  >
  >La descrizione è associata alla lingua corrente dell’istanza.

  **Esempio**:

  ```
  <attribute name="email" type="string" length="80" label="Email" desc="Email of recipient"/>
  ```

### Valori predefiniti {#default-values}

Il **predefinito** consente di definire un’espressione che restituisce un valore predefinito al momento della creazione del contenuto.

Il valore deve essere un&#39;espressione compatibile con il linguaggio XPath. Per ulteriori informazioni al riguardo, consulta [questa sezione](#reference-with-xpath).

**Esempio**:

* Data corrente: **default=&quot;GetDate()&quot;**
* Contatore: **default=&quot;&#39;FRM&#39;+CounterValue(&#39;myCounter&#39;)&quot;**

  In questo esempio, il valore predefinito viene costruito utilizzando la concatenazione di una stringa e chiamando il **CounterValue** funzione con un nome di contatore libero. Il numero restituito viene incrementato di uno a ogni inserimento.

  >[!NOTE]
  >
  >Nella console client di Adobe Campaign, il **[!UICONTROL Administration>Counters]** nodo utilizzato per gestire i contatori.

Per collegare un valore predefinito a un campo, è possibile utilizzare `<default>  or  <sqldefault>   field.  </sqldefault> </default>`

`<default>` : consente di precompilare il campo con un valore predefinito durante la creazione di entità. Il valore non sarà un valore SQL predefinito.

`<sqldefault>` : ti consente di avere un valore aggiunto durante la creazione di un campo. Questo valore viene visualizzato come risultato SQL. Durante un aggiornamento dello schema, questo valore influisce solo sui nuovi record.

### Enumerazioni {#enumerations}

#### Enumerazione gratuita {#free-enumeration}

Il **userEnum** consente di definire un’enumerazione gratuita per memorizzare e visualizzare i valori immessi tramite questo campo. La sintassi è la seguente:

**userEnum=&quot;nome dell’enumerazione&quot;**

Il nome assegnato all’enumerazione può essere scelto liberamente e condiviso con altri campi.

Questi valori vengono visualizzati in un elenco a discesa dal modulo di input:

![](assets/schema_user_enum.png)

>[!NOTE]
>
>Nella console client di Adobe Campaign, il **[!UICONTROL Administration > Enumerations]** nodo utilizzato per gestire le enumerazioni.

#### Imposta enumerazione {#set-enumeration}

Il **enum** proprietà consente di definire un’enumerazione fissa utilizzata quando l’elenco dei possibili valori è noto in anticipo.

Il **enum** attribute fa riferimento alla definizione di una classe di enumerazione popolata nello schema al di fuori dell’elemento principale.

Le enumerazioni consentono di selezionare un valore da un elenco a discesa anziché immetterlo in un campo di input regolare:

![](assets/schema_enum.png)

Esempio di dichiarazione di enumerazione nello schema dati:

```
<enumeration name="gender" basetype="byte" default="0">    
  <value name="unknown" label="Not specified" value="0"/>    
  <value name="male" label="male" value="1"/>   
  <value name="female" label="female" value="2"/>   
</enumeration>
```

Un’enumerazione viene dichiarata all’esterno dell’elemento principale tramite **`<enumeration>`** elemento.

Le proprietà di enumerazione sono le seguenti:

* **baseType**: tipo di dati associati ai valori,
* **etichetta**: descrizione dell’enumerazione,
* **nome**: nome dell’enumerazione,
* **predefinito**: valore predefinito dell’enumerazione.

I valori di enumerazione sono dichiarati nel **`<value>`** con i seguenti attributi:

* **nome**: nome del valore memorizzato internamente,
* **etichetta**: etichetta visualizzata tramite l’interfaccia grafica.

#### enumerazione del dbenum {#dbenum-enumeration}

* Il **dbenum** proprietà consente di definire un’enumerazione le cui proprietà sono simili a quelle della proprietà **enum** proprietà.

  Tuttavia, il **nome** L’attributo non memorizza il valore internamente, ma memorizza un codice che consente di estendere le tabelle interessate senza modificarne lo schema.

  I valori sono definiti tramite **[!UICONTROL Administration>Enumerations]** nodo.

  Questa enumerazione viene utilizzata per specificare la natura delle campagne, ad esempio.

  ![](assets/schema_dbenum.png)

### Esempio {#example}

Di seguito è riportato uno schema di esempio con le proprietà compilate:

```
<srcSchema name="recipient" namespace="cus">
  <enumeration name="gender" basetype="byte">    
    <value name="unknown" label="Not specified" value="0"/>    
    <value name="male" label="male" value="1"/>   
    <value name="female" label="female" value="2"/>   
  </enumeration>

  <element name="recipient">
    <attribute name="email" type="string" length="80" label="Email" desc="Email of recipient"/>
    <attribute name="created" type="datetime" label="Date of creation" default="GetDate()"/>
    <attribute name="gender" type="byte" label="gender" enum="gender"/>
    <element name="location" label="Location">
      <attribute name="city" type="string" length="50" label="City" userEnum="city"/>
   </element>
  </element>
</srcSchema>
```

## Raccolte {#collections}

Una raccolta è un elenco di elementi con lo stesso nome e lo stesso livello gerarchico.

Il **non associato** con il valore &quot;true&quot; consente di popolare un elemento di raccolta.

**Esempio**: definizione del **`<group>`** elemento di raccolta nello schema.

```
<element name="group" unbound="true" label="List of groups">
  <attribute name="label" type="string" label="Label"/>
</element>
```

Con la proiezione del contenuto XML:

```
<group label="Group1"/>
<group label="Group2"/>
```

## Riferimento con XPath {#reference-with-xpath}

Il linguaggio XPath viene utilizzato in Adobe Campaign per fare riferimento a un elemento o attributo appartenente a uno schema di dati.

XPath è una sintassi che consente di individuare un nodo nella struttura di un documento XML.

Gli elementi sono designati dal loro nome e gli attributi sono designati dal nome preceduto dal carattere &quot;@&quot;.

**Esempio**:

* **@email**: seleziona l’e-mail,
* **posizione/@city**: seleziona l’attributo &quot;city&quot; sotto il **`<location>`** elemento
* **.../@email**: seleziona l’indirizzo e-mail dall’elemento padre dell’elemento corrente
* **gruppo`[1]/@label`**: seleziona l’attributo &quot;label&quot; che è l’elemento secondario del primo **`<group>`** elemento di raccolta
* **gruppo`[@label='test1']`**: seleziona l’attributo &quot;label&quot; che è l’elemento figlio del **`<group>`** e contiene il valore &quot;test1&quot;

>[!NOTE]
>
>Quando il percorso attraversa un sottoelemento, viene aggiunto un vincolo aggiuntivo. In questo caso, tra le parentesi deve essere inserita la seguente espressione:
>
>* **posizione/@city** non è valido; utilizzare **`[location/@city]`**
>* **`[@email]`** e **@email** sono equivalenti
>

È inoltre possibile definire espressioni complesse, ad esempio le seguenti operazioni aritmetiche:

* **@gender+1**: aggiunge 1 al contenuto della **genere** attributo,
* **@email + &#39;(&#39;+@created+&#39;)&#39;**: crea una stringa prendendo il valore dell’indirizzo e-mail aggiunto alla data di creazione tra parentesi (per il tipo di stringa, inserisci la costante tra virgolette).

Sono state aggiunte funzioni di alto livello alle espressioni per arricchire il potenziale di questo linguaggio.

Puoi accedere all’elenco delle funzioni disponibili tramite qualsiasi editor di espressioni nella console client di Adobe Campaign:

![](assets/schema_function.png)

**Esempio**:

* **GetDate()**: restituisce la data corrente
* **Year(@created)**: restituisce l’anno della data contenuta nell’attributo &quot;created&quot;.
* **GetEmailDomain(@email)**: restituisce il dominio dell’indirizzo e-mail.

## Creazione di una stringa tramite la stringa di calcolo {#building-a-string-via-the-compute-string}

A **Stringa di calcolo** è un&#39;espressione XPath utilizzata per creare una stringa che rappresenta un record in una tabella associata allo schema. **Stringa di calcolo** viene utilizzato principalmente nell’interfaccia grafica per visualizzare l’etichetta di un record selezionato.

Il **Stringa di calcolo** è definito tramite **`<compute-string>`** nell&#39;elemento principale dello schema dati. Un **espr** contiene un&#39;espressione XPath per calcolare la visualizzazione.

**Esempio**: stringa di calcolo della tabella dei destinatari.

```
<srcSchema name="recipient" namespace="nms">  
  <element name="recipient">
    <compute-string expr="@lastName + ' ' + @firstName +' (' + @email + ')' "/>
    ...
  </element>
</srcSchema>
```

Risultato della stringa calcolata per un destinatario: **Doe John (john.doe@aol.com)**

>[!NOTE]
>
>Se lo schema non contiene una stringa di calcolo, per impostazione predefinita viene compilata una stringa di calcolo con i valori della chiave primaria dello schema.
