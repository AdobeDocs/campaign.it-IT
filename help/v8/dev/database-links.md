---
title: Gestione dei collegamenti negli schemi di Campaign
description: Gestione dei collegamenti negli schemi di Adobe Campaign
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: f7047c6e-f045-4534-b117-311dd90dd92b
source-git-commit: 0f5efba364ef924447324bdd806e15e6db8d799d
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 0%

---

# Gestione collegamenti {#links--relation-between-tables}

Un collegamento descrive l’associazione tra una tabella e un’altra.

I tipi di associazioni, noti anche come cardinalità, sono elencati di seguito.

* Cardinalità 1-1: una occorrenza della tabella sorgente può avere al massimo una occorrenza corrispondente della tabella di destinazione.
* Cardinalità 1-N: una occorrenza della tabella sorgente può avere diverse occorrenze corrispondenti della tabella di destinazione, ma una occorrenza della tabella di destinazione può avere al massimo una occorrenza corrispondente della tabella sorgente.
* Cardinalità N-N: una occorrenza della tabella sorgente può avere diverse occorrenze corrispondenti della tabella di destinazione e viceversa.

Nell’interfaccia utente, le cardinalità sono rappresentate da un’icona specifica.

Per le relazioni di join con una tabella o un database di Campaign:

* ![](assets/do-not-localize/join_with_campaign11.png): Cardinalità 1-1. Ad esempio, tra un destinatario e un ordine corrente. Un destinatario può essere correlato a una sola occorrenza della tabella dell&#39;ordine corrente alla volta.
* ![](assets/do-not-localize/externaljoin11.png): Cardinalità 1-1, join esterno. Ad esempio, tra un destinatario e il suo paese. Un destinatario può essere correlato a una sola occorrenza del paese della tabella. Il contenuto della country table non verrà salvato.
* ![](assets/do-not-localize/join_with_campaign1n.png) : Cardinalità 1-N. Ad esempio, tra un destinatario e la tabella delle sottoscrizioni. Un destinatario può essere correlato a diverse occorrenze nella tabella delle sottoscrizioni.

Per le relazioni di join che utilizzano Federated Database Access (FDA):

* ![](assets/do-not-localize/join_fda_11.png): Cardinalità 1-1
* ![](assets/do-not-localize/join_fda_1m.png): cardinalità 1-N

Per ulteriori informazioni sulle tabelle FDA, vedere [Accesso a un database esterno](../connect/fda.md).

È necessario dichiarare un collegamento nello schema contenente la chiave esterna della tabella collegata tramite l’elemento principale:

```sql
<element name="name_of_link" type="link" target="key_of_destination_schema">
  <join xpath-dst="xpath_of_field1_destination_table" xpath-src="xpath_of_field1_source_table"/>
  <join xpath-dst="xpath_of_field2_destination_table" xpath-src="xpath_of_field2_source_table"/>
  ...
</element>
```

I collegamenti rispettano le seguenti regole:

* La definizione di un collegamento viene immessa in un **`<element>`** di tipo **link** con i seguenti attributi:

   * **nome**: nome del collegamento dalla tabella di origine
   * **target**: nome dello schema di destinazione
   * **etichetta**: etichetta del collegamento
   * **revLink** (facoltativo): nome del collegamento inverso dallo schema di destinazione (dedotto automaticamente per impostazione predefinita)
   * **integrità** (facoltativo): integrità referenziale dell&#39;occorrenza della tabella di origine rispetto all&#39;occorrenza della tabella di destinazione.
I valori possibili sono:

      * **define**: è possibile eliminare l&#39;occorrenza di origine se un&#39;occorrenza di destinazione non vi fa più riferimento
      * **normal**: l&#39;eliminazione dell&#39;occorrenza di origine inizializza le chiavi del collegamento all&#39;occorrenza di destinazione (modalità predefinita). Questo tipo di integrità inizializza tutte le chiavi esterne
      * **own**: l&#39;eliminazione dell&#39;occorrenza di origine determina l&#39;eliminazione dell&#39;occorrenza di destinazione
      * **owncopy**: uguale a **own** (in caso di eliminazione) o duplica le occorrenze (in caso di duplicazione)
      * **neutro**: nessun comportamento specifico

   * **revIntegrity** (facoltativo): integrità nello schema di destinazione (facoltativo, &quot;normal&quot; per impostazione predefinita)
   * **revCardinality** (facoltativo): con il valore &quot;single&quot; compila la cardinalità con il tipo 1-1 (1-N per impostazione predefinita)
   * **externalJoin** (facoltativo): forza l&#39;outer join
   * **revExternalJoin** (facoltativo): forza il join esterno sul collegamento inverso

* Un collegamento fa riferimento a uno o più campi dalla tabella di origine alla tabella di destinazione. Non è necessario compilare i campi che compongono il join (elemento `<join>`) perché vengono dedotti automaticamente per impostazione predefinita utilizzando la chiave interna dello schema di destinazione.
* Un indice viene aggiunto automaticamente alla chiave esterna del collegamento nello schema esteso.
* Un collegamento è costituito da due collegamenti intermedi, in cui il primo viene dichiarato dallo schema di origine e il secondo viene creato automaticamente nello schema esteso dello schema di destinazione.
* Un join può essere un outer join se viene aggiunto l&#39;attributo **externalJoin** con il valore &quot;true&quot; (supportato in PostgreSQL).

>[!NOTE]
>
>Come standard, i collegamenti sono gli elementi dichiarati alla fine dello schema.

## Esempio: collegamento inverso {#example-1}

Nell’esempio seguente, dichiariamo una relazione 1-N alla tabella dello schema &quot;cus:company&quot;:

```sql
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    ...
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

Lo schema generato:

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" sqltable="CusRecipient"> 
    <dbindex name="companyId">      
      <keyfield xpath="@company-id"/>    
    </dbindex>
    ...
    <element label="Company" name="company" revLink="recipient" target="cus:company" type="link">      
      <join xpath-dst="@id" xpath-src="@company-id"/>    
    </element>    
    <attribute advanced="true" label="Foreign key of 'Company' link (field 'id')" name="company-id" sqlname="iCompanyId" type="long"/>
  </element>
</schema>
```

La definizione del collegamento è completata dai campi che compongono il join, ovvero la chiave primaria con il relativo XPath (&quot;@id&quot;) nello schema di destinazione e la chiave esterna con il relativo XPath (&quot;@company-id&quot;) nello schema.

La chiave esterna viene aggiunta automaticamente in un elemento che utilizza le stesse caratteristiche del campo associato nella tabella di destinazione, con la seguente convenzione di denominazione: nome dello schema di destinazione seguito dal nome del campo associato (&quot;company-id&quot; nel nostro esempio).

Schema esteso del target (&quot;cus:company&quot;):

```sql
<schema mappingType="sql" name="company" namespace="cus" xtkschema="xtk:schema">  
  <element name="company" sqltable="CusCompany" autopk="true"> 
    <dbindex name="id" unique="true">     
      <keyfield xpath="@id"/>    
    </dbindex>   
    <key internal="true" name="id">      
      <keyfield xpath="@id"/>    
    </key>
    ...
    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iCompanyId" type="long"/>
    ...
    <element belongsTo="cus:recipient" integrity="define" label="Contact" name="recipient" revLink="company" target="nms:recipient" type="link" unbound="true">      
      <join xpath-dst="@company-id" xpath-src="@id"/>    
    </element>
  </element>
</schema>
```

È stato aggiunto un collegamento inverso alla tabella &quot;cus:recipient&quot; con i seguenti parametri:

* **nome**: dedotto automaticamente dal nome dello schema di origine (può essere forzato con l&#39;attributo &quot;revLink&quot; nella definizione del collegamento nello schema di origine)
* **revLink**: nome del collegamento inverso
* **target**: chiave dello schema collegato (schema &quot;cus:recipient&quot;)
* **unbound**: il collegamento è dichiarato come elemento di raccolta per una cardinalità 1-N (per impostazione predefinita)
* **integrità**: &quot;define&quot; per impostazione predefinita (può essere forzato con l&#39;attributo &quot;revIntegrity&quot; nella definizione del collegamento nello schema di origine).

## Esempio: collegamento semplice {#example-2}

In questo esempio viene dichiarato un collegamento alla tabella dello schema &quot;nms:address&quot;. Il join è un outer join e viene compilato esplicitamente con l&#39;indirizzo e-mail del destinatario e il campo &quot;@address&quot; della tabella collegata (&quot;nms:address&quot;).

```sql
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"> 
    ...
    <element integrity="neutral" label="Info about email" name="emailInfo" revIntegrity="neutral" revLink="recipient" target="nms:address" type="link" externalJoin="true">      
      <join xpath-dst="@address" xpath-src="@email"/>
    </element>
  </element>
</srcSchema>
```

## Esempio: cardinalità univoca {#example-3}

In questo esempio, creiamo una relazione 1-1 alla tabella dello schema &quot;cus:extension&quot;:

```sql
<element integrity="own" label="Extension" name="extension" revCardinality="single" revLink="recipient" target="cus:extension" type="link"/>
```

## Esempio: collegamento a una cartella {#example-4}

In questo esempio viene dichiarato un collegamento a una cartella (schema &quot;xtk:folder&quot;):

```sql
<element default="DefaultFolder('nmsFolder')" label="Folder" name="folder" revDesc="Recipients in the folder" revIntegrity="own" revLabel="Recipients" target="xtk:folder" type="link"/>
```

Il valore predefinito restituisce l&#39;identificatore del primo file del tipo di parametro idoneo immesso nella funzione &quot;DefaultFolder(&#39;nmsFolder&#39;)&quot;.

## Esempio: creare una chiave su un collegamento {#example-5}

In questo esempio, creiamo una chiave su un collegamento (schema &quot;company&quot; to &quot;cus:company&quot;) con l&#39;attributo **xlink** e un campo della tabella (&quot;email&quot;):

```sql
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <key name="companyEmail"> 
      <keyfield xpath="@email"/>
      <keyfield xlink="company"/>
    </key>
    
    <attribute name="email" type="string" length="80" label="Email" desc="Recipient email"/>
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

Lo schema generato:

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" sqltable="CusRecipient"> 
    <dbindex name="companyId">      
      <keyfield xpath="@company-id"/>    
    </dbindex>

    <dbindex name="companyEmail" unique="true">
      <keyfield xpath="@email"/>      
      <keyfield xpath="@company-id"/>    
    </dbindex>    

    <key name="companyEmail">      
      <keyfield xpath="@email"/>      
      <keyfield xpath="@company-id"/>    
    </key>

    <attribute desc="Email address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>
    <element label="Company" name="company" revLink="recipient" target="sfa:company" type="link">      
      <join xpath-dst="@id" xpath-src="@company-id"/>    
    </element>    
    <attribute advanced="true" label="Foreign key of link 'Company' (field 'id')" name="company-id" sqlname="iCompanyId" type="long"/>
  </element>
</schema>
```

La definizione della chiave del nome &quot;companyEmail&quot; è stata estesa con la chiave esterna del collegamento &quot;company&quot;. Questa chiave genera un indice univoco su entrambi i campi.
