---
title: Utilizzare gli schemi di Campaign
description: Guida introduttiva agli schemi
exl-id: 87af72fe-6c84-4d9a-afed-015900890cce
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '1247'
ht-degree: 5%

---

# Utilizzare gli schemi{#gs-ac-schemas}

La struttura fisica e logica dei dati trasferiti nell’applicazione è descritta in XML. Obbedisce a una grammatica specifica di Adobe Campaign, denominata **schema**.

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
>Alcuni schemi di Campaign incorporati hanno uno schema associato nel database Cloud. Questi schemi sono identificati dallo spazio dei nomi **Xxl** e non devono essere modificati o estesi.

## Sintassi degli schemi {#syntax-of-schemas}

L&#39;elemento principale dello schema è **`<srcschema>`**. Contiene i sottoelementi **`<element>`** e **`<attribute>`** .

Il primo sottoelemento **`<element>`** coincide con il livello principale dell’entità.

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

I tag **`<element>`** definiscono i nomi degli elementi di entità. **`<attribute>`** i tag dello schema definiscono i nomi degli attributi nei  **`<element>`** tag a cui sono stati collegati.

## Identificazione di uno schema {#identification-of-a-schema}

Uno schema di dati è identificato dal nome e dallo spazio dei nomi corrispondente.

Uno spazio dei nomi consente di raggruppare un set di schemi per area di interesse. Ad esempio, lo spazio dei nomi **cus** viene utilizzato per la configurazione specifica del cliente (**clienti**).

>[!CAUTION]
>
>Come standard, il nome dello spazio dei nomi deve essere conciso e deve contenere solo caratteri autorizzati in conformità alle regole di denominazione XML.
>
>Gli identificatori non devono iniziare con caratteri numerici.

## Spazi dei nomi riservati {#reserved-namespaces}

Alcuni namespace sono riservati per le descrizioni delle entità di sistema necessarie per il funzionamento dell’applicazione Adobe Campaign. Non è necessario utilizzare il seguente namespace **per identificare un nuovo schema in una combinazione maiuscola/minuscola:**

* **xxl**: riservato agli schemi di database cloud
* **xtk**: riservato ai dati di sistema della piattaforma
* **nl**: riservato all&#39;uso generale della domanda
* **nms**: riservato alle consegne (destinatario, consegna, tracciamento, ecc.)
* **ncm**: riservato alla gestione dei contenuti
* **temperatura**: riservato agli schemi temporanei
* **crm**: riservato all’integrazione dei connettori di gestione delle relazioni con i clienti

La chiave di identificazione di uno schema è una stringa creata utilizzando lo spazio dei nomi e il nome separati da due punti; ad esempio: **nms:recipient**.

## Creare o estendere gli schemi di Campaign {#create-or-extend-schemas}

Per aggiungere un campo o un altro elemento a uno degli schemi di dati principali in Campaign, ad esempio la tabella dei destinatari (nms:recipient), devi estendere tale schema.

? Per ulteriori informazioni, consulta [Estendere uno schema](extend-schema.md).

Per aggiungere un tipo completamente nuovo di dati che non esiste in Adobe Campaign (ad esempio una tabella di contratti), puoi creare direttamente uno schema personalizzato.

? Per ulteriori informazioni, consulta [Creare un nuovo schema](create-schema.md).

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
>È inoltre possibile utilizzare enumerazioni gestite dall’utente (in genere in **[!UICONTROL Administration]** > **[!UICONTROL Platform]** ) per specificare i valori di un dato campo. Si tratta di enumerazioni globali efficaci e di una scelta migliore se l’enumerazione può essere utilizzata al di fuori dello schema specifico in cui si sta lavorando.

## Chiavi {#keys}

Ogni tabella deve avere almeno una chiave e spesso viene automaticamente stabilita nell&#39;elemento principale dello schema utilizzando gli attributi **@autouuid** e **autopk** impostati su **true**.

La chiave primaria può essere definita anche utilizzando l&#39;attributo **internal** .

Esempio:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

In questo esempio, invece di lasciare che l&#39;attributo **@autouuid** crei una chiave primaria predefinita denominata &quot;id&quot;, stiamo specificando la nostra chiave primaria &quot;familyId&quot;.

>[!CAUTION]
>
>Durante la creazione di un nuovo schema o durante un&#39;estensione dello schema, è necessario mantenere lo stesso valore di sequenza della chiave primaria (@pkSequence) per l&#39;intero schema.

? Ulteriori informazioni sulle chiavi in [questa sezione](database-mapping.md#management-of-keys).

## Attributi (campi) {#attributes--fields-}

Gli attributi ti consentono di definire i campi che compongono l’oggetto dati. Puoi usare il pulsante **[!UICONTROL Insert]** nella barra degli strumenti dell’edizione dello schema per rilasciare modelli di attributi vuoti nel file XML in cui si trova il cursore. Ulteriori informazioni in [questa sezione](create-schema.md).

![](assets/schemaextension_2.png)

L’elenco completo degli attributi è disponibile nella sezione `<attribute>` elemento nella documentazione [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=en#content-model). Di seguito sono riportati alcuni degli attributi più comunemente utilizzati: **@advanced**, **@dataPolicy**, **@default**, **@desc**, **@enum**, **@expr**, **@label&lt;a 13/>,**@length **,**@name **,**@notNull **,**@required **,**@ref&lt;a22 3/>, **@xml**, **@type**.****

↗️ Per ulteriori informazioni su ciascun attributo, consulta la descrizione dell’attributo nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic).

### Esempi {#examples}

Esempio di definizione di un valore predefinito:

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

Esempio di utilizzo di un attributo comune come modello per un campo contrassegnato come obbligatorio:

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

Esempio di campo calcolato nascosto utilizzando l&#39;attributo **@advanced** :

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

Esempio di campo XML memorizzato anche in un campo SQL e con un attributo **@dataPolicy**.

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

I collegamenti sono dichiarati nello schema che contiene la **chiave esterna** della tabella a cui è collegata.

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
