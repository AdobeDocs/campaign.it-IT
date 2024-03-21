---
title: Utilizzare gli schemi di Campaign
description: Introduzione agli schemi
feature: Schema Extension, Configuration, Data Model
role: Developer
level: Intermediate, Experienced
exl-id: 87af72fe-6c84-4d9a-afed-015900890cce
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 5%

---

# Utilizzare gli schemi{#gs-ac-schemas}

La struttura fisica e logica dei dati trasferiti nell’applicazione è descritta in XML. Obbedisce a una grammatica specifica di Adobe Campaign, denominata **schema**.

Uno schema è un documento XML associato a una tabella di database. Definisce la struttura dati e descrive la definizione SQL della tabella:

* Nome della tabella
* Campi
* Collegamenti con altre tabelle

Descrive inoltre la struttura XML utilizzata per memorizzare i dati:

* Elementi e attributi
* Gerarchia di elementi
* Tipi di elementi e attributi
* Valori predefiniti
* Etichette, descrizioni e altre proprietà

Gli schemi consentono di definire un’entità nel database. Esiste uno schema per ogni entità.

Adobe Campaign utilizza gli schemi di dati per:

* Definire il modo in cui l&#39;oggetto dati all&#39;interno dell&#39;applicazione viene associato alle tabelle di database sottostanti.
* Definire i collegamenti tra i diversi oggetti dati all’interno dell’applicazione Campaign.
* Definire e descrivere i singoli campi inclusi in ciascun oggetto.

Per informazioni sulle tabelle integrate di Campaign e sulla loro interazione, consulta [questa sezione](datamodel.md).

>[!CAUTION]
>
>Ad alcuni schemi integrati di Campaign è associato uno schema nel database Cloud. Questi schemi sono identificati da **Xxl** e non devono essere modificati o estesi.

## Sintassi degli schemi {#syntax-of-schemas}

L’elemento principale dello schema è **`<srcschema>`**. Contiene il **`<element>`** e **`<attribute>`** sottoelementi.

Il primo **`<element>`** sottoelemento coincide con la radice dell’entità.

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
>L’elemento principale dell’entità ha lo stesso nome dello schema.

![](assets/schema_and_entity.png)

Il **`<element>`** I tag definiscono i nomi degli elementi di entità. **`<attribute>`** I tag dello schema definiscono i nomi degli attributi nel **`<element>`** i tag a cui sono stati collegati.

## Identificazione di uno schema {#identification-of-a-schema}

Uno schema di dati è identificato dal nome e dallo spazio dei nomi.

Uno spazio dei nomi consente di raggruppare un set di schemi per area di interesse. Ad esempio, il **cus** lo spazio dei nomi viene utilizzato per la configurazione specifica del cliente (**clienti**).

>[!CAUTION]
>
>Come standard, il nome dello spazio dei nomi deve essere conciso e deve contenere solo caratteri autorizzati in conformità alle regole di denominazione XML.
>
>Gli identificatori non devono iniziare con caratteri numerici.

## Spazi dei nomi riservati {#reserved-namespaces}

Alcuni spazi dei nomi sono riservati alle descrizioni delle entità di sistema necessarie per il funzionamento dell’applicazione Adobe Campaign. Il seguente spazio dei nomi **non deve essere utilizzato** per identificare un nuovo schema, in qualsiasi combinazione maiuscola/minuscola:

* **xxl**: riservato agli schemi di database Cloud
* **xtk**: riservato ai dati del sistema della piattaforma
* **nl**: riservato all’uso generale dell’applicazione
* **nms**: riservato alle consegne (destinatario, consegna, tracciamento, ecc.)
* **ncm**: riservato alla gestione dei contenuti
* **temp**: riservato a schemi temporanei
* **crm**: riservato all’integrazione dei connettori CRM

La chiave di identificazione di uno schema è una stringa creata utilizzando lo spazio dei nomi e il nome separato da due punti, ad esempio: **nms:destinatario**.

## Creare o estendere gli schemi di Campaign {#create-or-extend-schemas}

Per aggiungere un campo o un altro elemento a uno degli schemi di dati di base in Campaign, ad esempio la tabella dei destinatari (nms:recipient), devi estendere tale schema.

Per ulteriori informazioni, consulta [Estendere uno schema](extend-schema.md).

Per aggiungere un tipo di dati completamente nuovo che non esiste in Adobe Campaign (ad esempio, una tabella di contratti) puoi creare direttamente uno schema personalizzato.

Per ulteriori informazioni, consulta [Crea un nuovo schema](create-schema.md).

![](assets/schemaextension_1.png)


Dopo aver creato o esteso uno schema in cui lavorare, la best practice consiste nel definire gli elementi di contenuto XML nello stesso ordine in cui vengono visualizzati di seguito.

## Enumerazioni {#enumerations}

Le enumerazioni vengono definite prima, prima dell’elemento principale dello schema. Consentono di visualizzare i valori in un elenco per limitare le scelte dell’utente per un determinato campo.

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
>È inoltre possibile utilizzare enumerazioni gestite dall&#39;utente (in genere **[!UICONTROL Administration]** > **[!UICONTROL Platform]** ) per specificare i valori per un determinato campo. Si tratta di enumerazioni globali efficaci e rappresentano una scelta migliore se l’enumerazione può essere utilizzata al di fuori dello schema specifico in cui stai lavorando.

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

Ogni tabella deve avere almeno una chiave e spesso viene stabilita automaticamente nell’elemento principale dello schema utilizzando **autopk** attributo impostato su **true**.

Inoltre, nell&#39;ambito di una [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), utilizza **@autouuid** e impostarlo su **true**.

La chiave primaria può essere definita anche utilizzando **interno** attributo.

Esempio:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

In questo esempio, invece di consentire a **@autopk** o **@autouuid** crea una chiave primaria predefinita denominata &quot;id&quot; stiamo specificando la nostra chiave primaria &quot;familyId&quot;.

>[!CAUTION]
>
>Quando crei un nuovo schema o durante un’estensione dello schema, devi mantenere lo stesso valore di sequenza di chiave primaria (@pkSequence) per l’intero schema.

Ulteriori informazioni sulle chiavi in [questa sezione](database-mapping.md#management-of-keys).

## Attributi (Campi) {#attributes--fields-}

Gli attributi consentono di definire i campi che compongono l’oggetto dati. È possibile utilizzare **[!UICONTROL Insert]** nella barra degli strumenti dell&#39;edizione dello schema per rilasciare modelli di attributi vuoti nel codice XML in cui si trova il cursore. Per ulteriori informazioni, consulta [questa sezione](create-schema.md).

![](assets/schemaextension_2.png)

L’elenco completo degli attributi è disponibile nella sezione `<attribute>` sezione elemento in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html#content-model). Di seguito sono riportati alcuni degli attributi più comunemente utilizzati: **@advanced**, **@dataPolicy**, **@default**, **@desc**, **@enum**, **@expr**, **@label**, **@length**, **@name**, **@notNull**, **@required**, **@ref**, **@xml**, **@type**.

Per ulteriori informazioni su ciascun attributo, fare riferimento alla descrizione dell&#39;attributo in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html#configuring-campaign-classic).

### Esempi {#examples}

Esempio di definizione di un valore predefinito:

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

Esempio di utilizzo di un attributo comune come modello per un campo contrassegnato come obbligatorio:

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

Esempio di un campo calcolato nascosto utilizzando **@advanced** attributo:

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

Esempio di un campo XML memorizzato anche in un campo SQL e che dispone di un **@dataPolicy** attributo.

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>Sebbene la maggior parte degli attributi sia collegata in base a una cardinalità 1-1 a un campo fisico del database, questo non avviene per i campi XML o i campi calcolati.\
>Un campo XML viene memorizzato in un campo Memo (&quot;mData&quot;) della tabella.\
>Un campo calcolato, tuttavia, viene creato in modo dinamico ogni volta che viene avviata una query, pertanto esiste solo nel livello applicativo.

## Collegamenti {#links}

I collegamenti sono alcuni degli ultimi elementi nell’elemento principale dello schema. Definiscono il modo in cui tutti i diversi schemi nella tua istanza si relazionano tra loro.

I collegamenti sono dichiarati nello schema che contiene **chiave esterna** della tabella a cui è collegato.

Esistono tre tipi di cardinalità: 1-1, 1-N e N-N. È il tipo 1-N utilizzato per impostazione predefinita.

### Esempi {#examples-1}

Un esempio di collegamento 1-N tra la tabella dei destinatari (schema predefinito) e una tabella di transazioni personalizzate:

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

Un esempio di collegamento 1-1 tra uno schema personalizzato &quot;Car&quot; (nello spazio dei nomi &quot;cus&quot;) e la tabella dei destinatari:

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

Esempio di join esterno tra la tabella dei destinatari e una tabella di indirizzi basata sull&#39;indirizzo e-mail e non su una chiave primaria:

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

Qui &quot;xpath-dst&quot; corrisponde alla chiave primaria nello schema di destinazione e &quot;xpath-src&quot; corrisponde alla chiave esterna nello schema di origine.

## Audit trail {#audit-trail}

Un elemento utile che puoi includere nella parte inferiore dello schema è un elemento di tracciamento (Audit trail).

Utilizza l’esempio seguente per includere nella tabella campi relativi alla data di creazione, all’utente che ha creato i dati, alla data e all’autore dell’ultima modifica per tutti i dati:

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## Aggiornamento della struttura del database {#updating-the-database-structure}

Una volta completate e salvate le modifiche, è necessario applicare al database tutte le modifiche che possono influire sulla struttura SQL. A tale scopo, utilizzare l&#39;Assistente all&#39;aggiornamento del database.

![](assets/schemaextension_3.png)

Per ulteriori informazioni al riguardo, consulta [questa sezione](update-database-structure.md).

>[!NOTE]
>
>Quando le modifiche non influiscono sulla struttura del database, è sufficiente rigenerare gli schemi. A questo scopo, seleziona gli schemi da aggiornare, fai clic con il pulsante destro del mouse e scegli **[!UICONTROL Actions > Regenerate selected schemas...]**.
