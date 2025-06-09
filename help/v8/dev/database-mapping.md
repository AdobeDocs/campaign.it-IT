---
title: Mappatura del database di Campaign
description: Mappatura del database di Campaign
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: a804d164-58bf-4b15-a48e-8cf75d793668
source-git-commit: 673298a60927902bba71fd9167c5408e538f4929
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---

# Mappatura del database{#database-mapping}

La mappatura SQL dello schema di esempio fornisce il seguente documento XML:

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">
  <enumeration basetype="byte" name="gender">    
    <value label="Not specified" name="unknown" value="0"/>    
    <value label="Male" name="male" value="1"/>    
    <value label="Female" name="female" value="2"/> 
  </enumeration>  

  <element name="recipient" sqltable="CusRecipient">    
    <attribute desc="Recipient e-mail address" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
    <attribute default="GetDate()" label="Date of creation" name="created" sqlname="tsCreated" type="datetime"/>    
    <attribute enum="gender" label="Gender" name="gender" sqlname="iGender" type="byte"/>    
    <element label="Location" name="location">      
      <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
    </element>  
  </element>
</schema>
```

## Descrizione {#description}

L&#39;elemento radice dello schema non è più **`<srcschema>`**, ma **`<schema>`**.

Questo ci porta a un altro tipo di documento, che viene generato automaticamente dallo schema di origine, semplicemente denominato schema. Questo schema verrà utilizzato dall’applicazione Adobe Campaign.

I nomi SQL vengono determinati automaticamente in base al nome e al tipo dell&#39;elemento.

Le regole di denominazione SQL sono le seguenti:

* tabella: concatenazione dello spazio dei nomi e del nome dello schema

  Nel nostro esempio, il nome della tabella viene immesso tramite l&#39;elemento principale dello schema nell&#39;attributo **sqltable**:

  ```sql
  <element name="recipient" sqltable="CusRecipient">
  ```

* campo: nome dell’elemento preceduto da un prefisso definito secondo il tipo (&quot;i&quot; per numero intero, &quot;d&quot; per doppio, &quot;s&quot; per stringa, &quot;ts&quot; per date, ecc.)

  Il nome del campo viene immesso tramite l&#39;attributo **sqlname** per ogni tipo di **`<attribute>`** e **`<element>`**:

  ```sql
  <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
  ```

>[!NOTE]
>
>I nomi SQL possono essere sovraccaricati dallo schema di origine. A questo scopo, compila gli attributi &quot;sqltable&quot; o &quot;sqlname&quot; sull’elemento interessato.

Lo script SQL per creare la tabella generata dallo schema esteso è il seguente:

```sql
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

I vincoli del campo SQL sono i seguenti:

* nessun valore nullo nei campi numerici e di data
* i campi numerici sono inizializzati a 0

## Campi XML {#xml-fields}

Per impostazione predefinita, qualsiasi elemento **`<attribute>`** e **`<element>`** digitato è mappato su un campo SQL della tabella dello schema dati. È tuttavia possibile fare riferimento a questo campo in formato XML anziché in formato SQL, il che significa che i dati vengono memorizzati in un campo Memo (&quot;mData&quot;) della tabella contenente i valori di tutti i campi XML. La memorizzazione di questi dati è un documento XML che osserva la struttura dello schema.

Per compilare un campo in XML, è necessario aggiungere l&#39;attributo **xml** con il valore &quot;true&quot; all&#39;elemento interessato.

**Esempi**

* Campo commento su più righe:

  ```sql
  <element name="comment" xml="true" type="memo" label="Comment"/>
  ```

* Descrizione dei dati in formato HTML:

  ```sql
  <element name="description" xml="true" type="html" label="Description"/>
  ```

  Il tipo &quot;html&quot; consente di memorizzare il contenuto HTML in un tag CDATA e di visualizzare uno speciale HTML edit check nell’interfaccia client di Adobe Campaign.

L&#39;utilizzo di campi XML consente di aggiungere campi senza dover modificare la struttura fisica del database. Un altro vantaggio consiste nell&#39;utilizzo di meno risorse (dimensioni allocate ai campi SQL, limite al numero di campi per tabella, ecc.).
