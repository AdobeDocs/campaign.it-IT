---
title: Utilizzare gli schemi di Campaign
description: Guida introduttiva agli schemi
exl-id: 87af72fe-6c84-4d9a-afed-015900890cce
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '1266'
ht-degree: 5%

---

# Utilizzare gli schemi{#gs-ac-schemas}

La struttura fisica e logica dei dati trasferiti nell’applicazione è descritta in XML. Obbedisce a una grammatica specifica di Adobe Campaign, chiamata **schema**.

Uno schema è un documento XML associato a una tabella di database. Definisce la struttura dati e descrive la definizione SQL della tabella:

* Nome della tabella
* Campi
* Collegamenti ad altre tabelle

Descrive inoltre la struttura XML utilizzata per memorizzare i dati:

* Elementi e attributi
* Gerarchia degli elementi
* Tipi di elementi e attributi
* Valori predefiniti
* Etichette, descrizioni e altre proprietà.

Gli schemi consentono di definire un’entità nel database. Esiste uno schema per ogni entità.

Adobe Campaign utilizza gli schemi di dati per:

* Definire il modo in cui l’oggetto dati all’interno dell’applicazione è associato alle tabelle di database sottostanti.
* Definire i collegamenti tra i diversi oggetti dati all’interno dell’applicazione Campaign.
* Definire e descrivere i singoli campi inclusi in ciascun oggetto.

Per una migliore comprensione delle tabelle integrate di Campaign e della loro interazione, consulta [questa sezione](datamodel.md).

>[!CAUTION]
>
>Alcuni schemi di Campaign incorporati hanno uno schema associato nel database Cloud. Tali schemi sono identificati dal **Xxl** spazio dei nomi e non deve essere modificato o esteso.

## Sintassi degli schemi {#syntax-of-schemas}

L&#39;elemento principale dello schema è **`<srcschema>`**. Contiene il **`<element>`** e **`<attribute>`** sottoelementi.

Il primo **`<element>`** il sottoelemento coincide con il livello principale dell’entità.

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">  
    <attribute name="lastName"/>
    <attribute name="email"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

>[!NOTE]
>
>L&#39;elemento principale dell&#39;entità ha lo stesso nome dello schema.

![](assets/schema_and_entity.png)

La **`<element>`** I tag definiscono i nomi degli elementi di entità. **`<attribute>`** i tag dello schema definiscono i nomi degli attributi nel **`<element>`** a cui sono stati collegati.

## Identificazione di uno schema {#identification-of-a-schema}

Uno schema di dati è identificato dal nome e dallo spazio dei nomi corrispondente.

Uno spazio dei nomi consente di raggruppare un set di schemi per area di interesse. Ad esempio, il **muco** Lo spazio dei nomi viene utilizzato per la configurazione specifica del cliente (**clienti**).

>[!CAUTION]
>
>Come standard, il nome dello spazio dei nomi deve essere conciso e deve contenere solo caratteri autorizzati in conformità alle regole di denominazione XML.
>
>Gli identificatori non devono iniziare con caratteri numerici.

## Spazi dei nomi riservati {#reserved-namespaces}

Alcuni namespace sono riservati per le descrizioni delle entità di sistema necessarie per il funzionamento dell’applicazione Adobe Campaign. Spazio dei nomi seguente **non devono essere utilizzati** per identificare un nuovo schema, in qualsiasi combinazione maiuscolo/minuscolo:

* **xxl**: riservato agli schemi di database cloud
* **xtk**: riservato ai dati di sistema della piattaforma
* **nl**: riservato all&#39;uso generale della domanda
* **nms**: riservato alle consegne (destinatario, consegna, tracciamento, ecc.)
* **ncm**: riservato alla gestione dei contenuti
* **temp**: riservato agli schemi temporanei
* **crm**: riservato all’integrazione dei connettori di gestione delle relazioni con i clienti

La chiave di identificazione di uno schema è una stringa creata utilizzando lo spazio dei nomi e il nome separati da due punti; ad esempio: **nms:recipient**.

## Creare o estendere gli schemi di Campaign {#create-or-extend-schemas}

Per aggiungere un campo o un altro elemento a uno degli schemi di dati principali in Campaign, ad esempio la tabella dei destinatari (nms:recipient), devi estendere tale schema.

![](../assets/do-not-localize/glass.png) Per ulteriori informazioni, consulta [Estendere uno schema](extend-schema.md).

Per aggiungere un tipo completamente nuovo di dati che non esiste in Adobe Campaign (ad esempio una tabella di contratti), puoi creare direttamente uno schema personalizzato.

![](../assets/do-not-localize/glass.png) Per ulteriori informazioni, consulta [Creare un nuovo schema](create-schema.md).

![](assets/schemaextension_1.png)


Dopo aver creato o esteso uno schema in cui lavorare, la procedura consigliata consiste nel definire i relativi elementi di contenuto XML nello stesso ordine in cui compaiono di seguito.

## Enumerazioni {#enumerations}

Le enumerazioni sono definite per prime, prima dell&#39;elemento principale dello schema. Consentono di visualizzare i valori in un elenco al fine di limitare le scelte disponibili per un dato campo.

Esempio:

```
<enumeration basetype="byte" name="exTransactionTypeEnum" default="store">
<value label="Website" name="web" value="0"/>
<value label="Call Center" name="phone" value="1"/>
<value label="In Store" name="store" value="2"/>
</enumeration>
```

Quando definisci i campi, puoi quindi utilizzare questa enumerazione nel modo seguente:

```
<attribute desc="Type of Transaction" label="Transaction Type" name="transactionType" 
type="string" enum="exTransactionTypeEnum"/>
```

>[!NOTE]
>
>È inoltre possibile utilizzare enumerazioni gestite dagli utenti (in genere in **[!UICONTROL Administration]** > **[!UICONTROL Platform]** ) per specificare i valori di un dato campo. Si tratta di enumerazioni globali efficaci e di una scelta migliore se l’enumerazione può essere utilizzata al di fuori dello schema specifico in cui si sta lavorando.

<!--
## Index {#index} 

In the context of a [FDA Snowflake deployment](../architecture/fda-deployment.md), you need to declare indexes. Indexes are the first elements declared in the main element of the schema. 

They can be unique or not, and reference one or more fields.

Examples:

```
<dbindex name="email" unique="true">
  <keyfield xpath="@email"/>
</dbindex>
```

```
<dbindex name="lastNameAndZip">
  <keyfield xpath="@lastName"/>
  <keyfield xpath="location/@zipCode"/>
</dbindex>
```

The **xpath** attribute points to the field in your schema that you wish to index.

>[!IMPORTANT]
>
>It is important to remember that the SQL query read performance gains provided by indexes also come with a performance hit on writing records. The indexes should therefore be used with precaution.

For more on indexes, refer to the [Indexed fields](database-mapping.md#indexed-fields) section.

-->

## Chiavi {#keys}

Ogni tabella deve avere almeno una chiave e spesso viene automaticamente stabilita nell’elemento principale dello schema utilizzando il **autopk** attributo impostato su **true**.

Inoltre, nel contesto di un [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), utilizza **@autouuid** e impostarlo su **true**.

La chiave primaria può essere definita anche utilizzando **interno** attributo.

Esempio:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

In questo esempio, invece di lasciare che **@autopk** o **@autouuid** creazione di una chiave primaria predefinita denominata &quot;id&quot; stiamo specificando la chiave primaria &quot;familyId&quot;.

>[!CAUTION]
>
>Durante la creazione di un nuovo schema o durante un&#39;estensione dello schema, è necessario mantenere lo stesso valore di sequenza della chiave primaria (@pkSequence) per l&#39;intero schema.

![](../assets/do-not-localize/glass.png) Ulteriori informazioni sulle chiavi in [questa sezione](database-mapping.md#management-of-keys).

## Attributi (campi) {#attributes--fields-}

Gli attributi ti consentono di definire i campi che compongono l’oggetto dati. È possibile utilizzare **[!UICONTROL Insert]** nella barra degli strumenti di modifica dello schema per rilasciare modelli di attributi vuoti nel codice XML in cui si trova il cursore. Ulteriori informazioni in [questa sezione](create-schema.md).

![](assets/schemaextension_2.png)

L’elenco completo degli attributi è disponibile nella sezione `<attribute>` sezione elemento in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=en#content-model). Di seguito sono riportati alcuni degli attributi più comunemente utilizzati: **@advanced**, **@dataPolicy**, **@default**, **@desc**, **@enum**, **@expr**, **@label**, **@length**, **@name**, **@notNull**, **@required**, **@ref**, **@xml**, **@type**.

![](../assets/do-not-localize/book.png) Per ulteriori informazioni su ciascun attributo, consulta la descrizione dell’attributo in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic).

### Esempi {#examples}

Esempio di definizione di un valore predefinito:

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

Esempio di utilizzo di un attributo comune come modello per un campo contrassegnato come obbligatorio:

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

Esempio di campo calcolato nascosto utilizzando la variabile **@advanced** attributo:

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

Esempio di campo XML memorizzato anche in un campo SQL e con un **@dataPolicy** attributo.

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>Sebbene la maggior parte degli attributi siano collegati in base a una cardinalità 1-1 a un campo fisico del database, ciò non avviene per i campi XML o i campi calcolati.\
>Un campo XML viene memorizzato in un campo Memo (&quot;mData&quot;) della tabella.\
>Un campo calcolato viene tuttavia creato dinamicamente ogni volta che viene avviata una query, quindi esiste solo nel livello applicativo.

## Collegamenti {#links}

I collegamenti sono alcuni degli ultimi elementi nell’elemento principale dello schema. Definiscono il modo in cui tutti i diversi schemi nella tua istanza si relazionano tra loro.

I collegamenti sono dichiarati nello schema che contiene **chiave estera** della tabella a cui è collegata.

Ci sono tre tipi di cardinalità: 1-1, 1-N e N-N. È il tipo 1-N utilizzato per impostazione predefinita.

### Esempi {#examples-1}

Esempio di collegamento 1-N tra la tabella dei destinatari (schema predefinito) e una tabella delle transazioni personalizzate:

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

Esempio di collegamento 1-1 tra uno schema personalizzato &quot;Car&quot; (nello spazio dei nomi &quot;cus&quot;) e la tabella dei destinatari:

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

Esempio di join esterno tra la tabella dei destinatari e una tabella di indirizzi basata sull’indirizzo e-mail e non su una chiave primaria:

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

Qui &quot;xpath-dst&quot; corrisponde alla chiave primaria nello schema di destinazione e &quot;xpath-src&quot; corrisponde alla chiave esterna nello schema di origine.

## Audit trail {#audit-trail}

Un elemento utile da includere nella parte inferiore dello schema è un elemento di tracciamento (Audit trail).

Utilizza l’esempio seguente per includere i campi relativi alla data di creazione, all’utente che ha creato i dati, alla data e all’autore dell’ultima modifica per tutti i dati nella tabella:

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## Aggiornamento della struttura del database {#updating-the-database-structure}

Una volta completate e salvate le modifiche, tutte le modifiche che possono influire sulla struttura SQL devono essere applicate al database. A questo scopo, utilizza l’assistente all’aggiornamento del database.

![](assets/schemaextension_3.png)

Per ulteriori informazioni al riguardo, consulta [questa sezione](update-database-structure.md).

>[!NOTE]
>
>Quando le modifiche non influiscono sulla struttura del database, è sufficiente rigenerare gli schemi. A questo scopo, seleziona gli schemi da aggiornare, fai clic con il pulsante destro del mouse e scegli **[!UICONTROL Actions > Regenerate selected schemas...]** .
