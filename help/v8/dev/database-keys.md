---
title: Gestione delle chiavi nel database di Campaign
description: Gestione delle chiavi negli schemi di Adobe Campaign
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
source-git-commit: 673298a60927902bba71fd9167c5408e538f4929
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---


# Gestione delle chiavi {#management-of-keys}

Ogni tabella associata a uno schema di dati deve avere almeno una chiave per identificare un record in una tabella.

Una chiave viene dichiarata dall’elemento principale dello schema di dati.

```sql
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

Una chiave è nota come &quot;chiave primaria&quot; quando è la prima dello schema a essere compilata, o se contiene `internal` attributo impostato su &quot;true&quot;.

Una chiave può fare riferimento a uno o più campi della tabella.

**Esempio**:

* Aggiunta di una chiave all&#39;indirizzo di posta elettronica e alla città:

  ```sql
  <srcSchema name="recipient" namespace="cus">
    <element name="recipient">
      <key name="email">
        <keyfield xpath="@email"/> 
        <keyfield xpath="location/@city"/> 
      </key>
  
      <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
      <element name="location" label="Location">
        <attribute name="city" type="string" length="50" label="City" userEnum="city"/>
      </element>
    </element>
  </srcSchema>
  ```

  Lo schema generato:

  ```sql
  <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
    <element name="recipient" sqltable="CusRecipient">    
     <key name="email">      
      <keyfield xpath="@email"/>      
      <keyfield xpath="location/@city"/>    
     </key>    
  
     <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
     <element label="Location" name="location">      
       <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
     </element>  
    </element>
  </schema>
  ```

* Aggiunta di una chiave primaria o interna nel campo del nome &quot;id&quot;:

  ```sql
  <srcSchema name="recipient" namespace="cus">
    <element name="recipient">
      <key name="id" internal="true">
        <keyfield xpath="@id"/> 
      </key>
  
      <key name="email">
        <keyfield xpath="@email"/> 
      </key>
  
      <attribute name="id" type="long" label="Identifier"/>
      <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
    </element>
  </srcSchema>
  ```

  Lo schema generato:

  ```sql
  <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
    <element name="recipient" sqltable="CusRecipient">    
      <key name="email">      
        <keyfield xpath="@email"/>    
      </key>  
  
      <key internal="true" name="id">      
       <keyfield xpath="@id"/>    
      </key>    
  
      <attribute label="Identifier" name="id" sqlname="iRecipientId" type="long"/>    
      <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>  
    </element>
  </schema>
  ```

## Chiave primaria - Identificatore{#primary-key}

Nell&#39;ambito di una [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), la chiave primaria delle tabelle di Adobe Campaign è un **ID universalmente univoco (UUID)** generato automaticamente dal motore di database. Il valore chiave è univoco nell&#39;intero database. Il contenuto della chiave viene generato automaticamente all’inserimento del record.

**Esempio**

Nell’esempio seguente viene dichiarata una chiave incrementale nello schema di origine:

```sql
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"  autopk="true" autouuid="true">
  ...
  </element>
</srcSchema>
```

Lo schema generato:

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient"  autopk="true" autouuid="true" sqltable="CusRecipient"> 

    <key internal="true" name="id">
      <keyfield xpath="@id"/>
    </key>

    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iRecipientId" type="long"/>
  </element>
</schema>
```

Oltre alla definizione della chiave, allo schema esteso è stato aggiunto un campo numerico denominato &quot;id&quot; per contenere la chiave primaria generata automaticamente.

>[!CAUTION]
>
>Un record con una chiave primaria impostata su 0 viene inserito automaticamente al momento della creazione della tabella. Questo record viene utilizzato per evitare outer join che non sono validi per le tabelle dei volumi. Per impostazione predefinita, tutte le chiavi esterne sono inizializzate con il valore 0, in modo che un risultato possa sempre essere restituito sul join quando l&#39;elemento dati non viene popolato.

