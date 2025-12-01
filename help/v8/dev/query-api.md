---
title: Eseguire una query sul database con queryDef
description: Scopri come utilizzare i metodi queryDef e NLWS per eseguire query sul database di Campaign
feature: API
role: Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: 0fd39d6c-9e87-4b0f-a960-2aef76c9c8eb
source-git-commit: 26fededf0ee83299477e45e891df30a46c6d40fe
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 1%

---

# Eseguire una query sul database con queryDef {#query-database-api}

[!DNL Adobe Campaign] fornisce potenti metodi di JavaScript per interagire con il database utilizzando `queryDef` e `NLWS`. Questi metodi consentono di caricare, creare, aggiornare ed eseguire query sui dati utilizzando JSON, XML o SQL.

>[!NOTE]
>
>Questa documentazione descrive le API orientate ai dati per l’esecuzione di query sul database a livello di programmazione. Per le API REST, fare riferimento a [Introduzione alle API REST](api/get-started-apis.md). Per la creazione di query visive, fare riferimento a [Utilizzare l&#39;editor di query](../start/query-editor.md).

## Prerequisiti {#prerequisites}

Prima di utilizzare i metodi queryDef e NLWS, è necessario conoscere:

* JavaScript
* [!DNL Adobe Campaign] modello dati e schemi
* Espressioni XPath per la navigazione tra gli elementi dello schema

Ulteriori informazioni sul modello dati di Campaign in [questa pagina](datamodel.md).

## Metodi statici dello schema di entità {#entity-schema-methods}

Ogni schema in [!DNL Adobe Campaign] (ad esempio, `nms:recipient`, `nms:delivery`) include metodi statici accessibili tramite l&#39;oggetto `NLWS`. Questi metodi forniscono un modo pratico per interagire con le entità del database.

### Caricare, salvare e creare entità {#load-save-create}

**Caricare un&#39;entità per ID e aggiornarla:**

```javascript
// Load a delivery by @id and save
var delivery = NLWS.nmsDelivery.load("12435");
delivery.label = "New label";
delivery.save();
```

**Crea un destinatario utilizzando JSON:**

```javascript
// Create via JSON, edit via JS and save
var recipient = NLWS.nmsRecipient.create({
  x: { // the key 'x' doesn't matter
    email: 'john.doe@example.com',
  }
});
recipient.folder_id = 1183;
recipient.firstName = 'John';
recipient.lastName = 'Doe';
recipient.save();
```

**Crea un destinatario tramite XML:**

```javascript
// Create via XML and save
var recipient = NLWS.nmsRecipient.create(
  <recipient
    email="support@adobe.com"
    lastName="Adobe"
    firstName="Support"
  />
);
recipient.save();
```

## Panoramica di QueryDef {#querydef-overview}

Lo schema `xtk:queryDef` fornisce metodi per generare ed eseguire query sul database. È possibile utilizzare `NLWS.xtkQueryDef.create()` per creare query con sintassi JSON o XML.

**Operazioni disponibili:**

* `select` - Recupera più record
* `get` - Recupera un singolo record (SQL `LIMIT 1`)
* `getIfExists` - Recupera un singolo record, restituisce null se non viene trovato
* `count` - Conta record corrispondenti ai criteri

Ulteriori informazioni sui metodi queryDef sono disponibili nella [documentazione JSAPI di Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html){target="_blank"}.

## Query con JSON {#query-json}

Utilizza `NLWS.xtkQueryDef.create()` per creare query con sintassi JSON. L&#39;operazione `get` recupera un singolo record (SQL `LIMIT 1`), mentre `select` recupera più record.

**Ottieni un singolo destinatario:**

```javascript
var email = "contact@example.com";
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "get", // "get" does a SQL "LIMIT 1"
    select: { 
      node: [{expr: "@id"}, {expr: "@email"}, {expr: "@firstName"}] 
    },
    where: { 
      condition: [
        {expr: "@email = '" + email + "'"}, // filter by email
      ],
    }
  }
});

var res = query.ExecuteQuery(); 
// res is an XML object such as <recipient id="1234" email="contact@example.com" firstName="John"/>
var recipient = NLWS.nmsRecipient.load(res.$id); // conversion to a JavaScript object
recipient.email = "newemail@example.com";
recipient.save();
```

**Utilizzare `getIfExists` per evitare eccezioni:**

Se il record potrebbe non esistere, utilizzare `operation: "getIfExists"` anziché `get` per evitare eccezioni:

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "getIfExists",
    select: { node: [{expr: "@id"}] },
    where: { 
      condition: [{expr: "@email = 'nonexistent@example.com'"}]
    }
  }
});

var res = query.ExecuteQuery();
if (res) {
  logInfo("Recipient found: " + res.$id);
} else {
  logInfo("Recipient not found");
}
```

## Seleziona più record {#select-multiple}

Utilizzare l&#39;operazione `select` per recuperare più record. Puoi aggiungere condizioni, ordini e limiti.

**Eseguire query sui flussi di lavoro con filtri e ordinamento:**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "xtk:workflow", 
    operation: "select", 
    select: {
      node: [
        {expr: "@id"},
        {expr: "@label"},
        {expr: "@internalName"}
      ] 
    }, 
    where: {
      condition: [
        {expr: "[folder/@name]='nmsTechnicalWorkflow'"},
        {expr: "@production = 1"}
      ]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }
});

var res = query.ExecuteQuery();

var workflows = res.getElementsByTagName("workflow");
for each (var w in workflows) {
  logInfo(w.getAttribute("internalName"));
}
```

**Eseguire query sulle consegne con sintassi XML:**

```javascript
var q = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select" lineCount="3">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
      <node expr="@created"/>
    </select>
    <where>
      <condition expr="@label NOT LIKE '%Proof%'" bool-operator="AND"/>
      <condition expr="@created &lt;= '2024-12-01'" bool-operator="AND"/>
    </where>
    <orderBy>
      <node expr="@lastModified" sortDesc="true"/>
    </orderBy>    
  </queryDef>
);

var deliveries = q.ExecuteQuery();
for each(var delivery in deliveries.delivery) {
  logInfo(delivery.@id + ": " + delivery.@label);
}
```

>[!NOTE]
>
>Il parametro `lineCount` limita il numero di risultati. Senza di esso, il limite predefinito è 10.000 record.

Ulteriori informazioni su [ExecuteQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-ExecuteQuery.html){target="_blank"}.

## Eseguire una query sui dati di transizione del flusso di lavoro {#workflow-transition-data}

Quando si utilizzano le attività JavaScript nei flussi di lavoro, è possibile eseguire query sui dati delle transizioni in ingresso utilizzando `vars.targetSchema` e `vars.tableName`.

**Eseguire query sui dati dei destinatari da una transizione del flusso di lavoro:**

```javascript
// Query data from the incoming transition
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema, // The schema from the previous activity
    operation: 'select', 
    lineCount: 999999999, // Override default 10,000 limit
    select: { 
      node: [
        {expr: '@id'},
        {expr: '@email'},
        {expr: '@firstName'},
        {expr: '@lastName'}
      ]
    },
  }
});

var records = query.ExecuteQuery(); // Returns a DOMElement

for each(var record in records.getElements()) {
  logInfo("Processing: " + record.$id + " - " + record.$email);
  
  // Clean email address
  var cleanedEmail = record.$email.replace(/\s+/g, '').toLowerCase();
  
  // Update using parameterized query to prevent SQL injection
  sqlExec(
    "UPDATE " + vars.tableName + " SET sEmail=$(sz) WHERE iId=$(l)", 
    cleanedEmail, 
    record.$id
  );
}
```

>[!CAUTION]
>
>Utilizzare sempre query con parametri con `$(sz)` per le stringhe e `$(l)` per i numeri interi per evitare vulnerabilità SQL injection. Ulteriori informazioni sono disponibili nella [documentazione JSAPI per Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/f-sqlExec.html){target="_blank"}.

## Conteggio dei record {#count-records}

Utilizzare `Count(@id)` con un alias per contare i record.

**Conteggio ipotesi in esecuzione:**

```javascript
var jobCount = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:remaHypothesis" operation="get">
    <select>
      <node expr="Count(@id)" alias="@count"/>
    </select>
    <where>
      <condition expr={"@status=" + HYPOTHESIS_STATUS_RUNNING}/>
    </where>
  </queryDef>
);

var iJobCount = parseInt(jobCount.ExecuteQuery().@count);
logInfo("Running jobs: " + iJobCount);
```

**Conteggio con più condizioni:**

```javascript
var xmlQuery = <queryDef schema="nms:trackingLogRcp" operation="select">
  <select>
    <node expr="DateOnly(@logDate)" groupBy="1"/>
    <node expr="count(@id)" alias="@count"/>
    <node expr="countDistinct([@broadLog-id])" alias="@distinctCount"/>
  </select>
  <where>
    <condition expr={"@logDate IS NOT NULL AND @logDate &lt; #" + today + "# AND [@url-id] &lt;&gt; 1"}/>
  </where>
</queryDef>;

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## Distribuzione dei valori {#distribution-values}

Ottieni la distribuzione dei valori per un campo specifico, utile per analizzare i pattern di dati.

**Distribuzione dei codici paese:**

```javascript
/**
 * @class DistributionOfValues
 * @param {string} schema - The schema name (e.g., 'nms:recipient')
 * @param {string} field - The field to analyze (e.g., '@country')
 */
function DistributionOfValues(schema, field) {
  this.queryDef = {
    operation: 'select', 
    lineCount: 200, 
    schema: schema,
    select: {
      node: [
        {alias: '@expr', expr: field, groupBy: 'true', noSqlBind: 'true'},
        {alias: '@count', expr: 'COUNT()', label: 'Count'},
      ]
    },
    orderBy: {
      node: [{expr: 'COUNT()', sortDesc: 'true'}]
    },
  };
  
  /**
   * Execute the query and return results
   * @return {Array} XML list of results
   */
  this.get = function() {
    this.results = NLWS.xtkQueryDef.create({queryDef: this.queryDef}).ExecuteQuery();
    return this.results.getElements();
  };
}

// Usage example
var d = new DistributionOfValues('nms:recipient', '@country');

// Optional: Add additional filters
d.queryDef.where = {
  condition: [{expr: 'DateOnly(@created) = #2024-12-01#'}]
};

// Execute and display results
for each(var result in d.get()) {
  logInfo(result.$expr + ': ' + result.$count);
}
```

## Costruzione di query dinamiche {#dynamic-queries}

Crea le query in modo dinamico aggiungendo le condizioni a livello di programmazione.

**Aggiungi condizioni a una query esistente:**

```javascript
var xmlQuery = <queryDef schema="nms:delivery" operation="select">
  <select>
    <node expr="@id"/>
    <node expr="@label"/>
  </select>
  <where/>
</queryDef>;

// Dynamically add conditions
if (includeProofs) {
  xmlQuery.where.appendChild(
    <condition expr="@label LIKE '%Proof%'"/>
  );
}

if (startDate) {
  xmlQuery.where.appendChild(
    <condition expr={"@created >= #" + Format.toISO8601(startDate) + "#"}/>
  );
}

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

**Generare clausole Select e Where nei cicli:**

```javascript
// Build select dynamically
var select = <select/>;
var fields = ["@id", "@label", "@created"];
for each(var field in fields) {
  select.appendChild(<node expr={field}/>);
}

// Build where dynamically
var where = <where/>;
var conditions = [
  "@status = 1",
  "@type = 'email'"
];
for each(var condition in conditions) {
  where.appendChild(<condition expr={condition}/>);
}

// Create complete query
var xmlQuery = <queryDef operation="select" schema="nms:delivery"/>;
xmlQuery.appendChild(select);
xmlQuery.appendChild(where);

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## Metodi queryDef avanzati {#advanced-methods}

Oltre a `ExecuteQuery()`, queryDef fornisce diversi metodi specializzati per casi d&#39;uso avanzati.

### BuildQuery - Genera SQL senza eseguire {#build-query}

Utilizzare `BuildQuery()` per generare l&#39;istruzione SQL senza eseguirla. È utile per il debug, la registrazione o il passaggio di query a sistemi esterni.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
    </select>
    <where>
      <condition expr="@email IS NOT NULL"/>
    </where>
  </queryDef>
);

// Get the generated SQL
var sql = query.BuildQuery();
logInfo("Generated SQL: " + sql);
// Output: "SELECT iRecipientId, sEmail FROM NmsRecipient WHERE sEmail IS NOT NULL"
```

Ulteriori informazioni su [BuildQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQuery.html){target="_blank"}.

### BuildQueryEx - Ottieni SQL con stringa di formato {#build-query-ex}

`BuildQueryEx()` restituisce sia la query SQL che una stringa di formato compatibile con la funzione `sqlSelect()`.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
      <node expr="@firstName"/>
    </select>
  </queryDef>
);

var [sql, format] = query.BuildQueryEx();
logInfo("SQL: " + sql);
logInfo("Format: " + format);

// Use with sqlSelect
var results = sqlSelect(format, sql);
```

Ulteriori informazioni su [BuildQueryEx](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQueryEx.html){target="_blank"}.

### SelectAll - Aggiungi tutti i campi da selezionare {#select-all}

Il metodo `SelectAll()` aggiunge automaticamente tutti i campi dello schema alla clausola select, evitando di elencare ogni campo manualmente.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Add all fields to the select
query.SelectAll(false);

var result = query.ExecuteQuery();
// Result contains all recipient fields
```

Ulteriori informazioni su [SelectAll](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-SelectAll.html){target="_blank"}.

### Aggiorna - Aggiorna di massa i record {#mass-update}

Il metodo `Update()` consente di eseguire aggiornamenti di massa sui record che corrispondono ai criteri di query senza caricare singolarmente ogni record.

```javascript
// Mass update example: set a field value for all matching records
var updateQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "update",
    where: {
      condition: [{expr: "@country = 'US'"}]
    },
    set: {
      node: [{expr: "@blackList", value: "0"}]
    }
  }
});

// Execute mass update
updateQuery.Update();
logInfo("Mass update completed");
```

>[!CAUTION]
>
>Gli aggiornamenti di massa influiscono su tutti i record che corrispondono alla clausola WHERE. Eseguire sempre il test delle condizioni WHERE con una query di selezione per verificare quali record saranno interessati.

Ulteriori informazioni sull&#39;[aggiornamento](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-Update.html){target="_blank"}.

### GetInstanceFromModel - Istanze modello di query {#get-instance-from-model}

Utilizza `GetInstanceFromModel()` per recuperare dati da istanze create da modelli.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
    </select>
    <where>
      <condition expr="@isModel = 1"/>
    </where>
  </queryDef>
);

// Get instance data from template
var instance = query.GetInstanceFromModel("nms:delivery");
```

Ulteriori informazioni su [GetInstanceFromModel](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-GetInstanceFromModel.html){target="_blank"}.

## Operazioni batch {#batch-operations}

Elabora più record in batch per migliorare le prestazioni.

**Etichette di consegna aggiornamento batch:**

```javascript
// Query all deliveries to update
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema,
    operation: 'select', 
    lineCount: 999999999,
    select: { 
      node: [{expr: '@id'}]
    },
    where: {
      condition: [{expr: "@label LIKE '%OLD%'"}]
    }
  }
});

var records = query.ExecuteQuery();

// Process each record
for each(var record in records.getElements()) {
  var delivery = NLWS.nmsDelivery.load(record.$id);
  var oldLabel = delivery.label.toString();
  var newLabel = oldLabel.replace(/OLD/g, 'NEW');
  
  logInfo("Updating: " + oldLabel + " => " + newLabel);
  
  delivery.label = newLabel;
  delivery.save();
}

logInfo("Updated " + records.getElements().length + " deliveries");
```

## Esecuzione SQL non elaborato {#raw-sql}

Per operazioni complesse, è possibile eseguire direttamente le istruzioni SQL non elaborate.

**Esegui SQL con parametri:**

```javascript
var dbEngine = instance.engine;

// Using parameterized query (recommended)
dbEngine.exec(
  "UPDATE NmsUserAgentStats SET iVisitorsOfTheDay=$(l) WHERE tsDate=$(dt)", 
  visitorCount,
  Format.parseDateTimeInter(dateString)
);
```

**Query con sqlSelect:**

```javascript
// Execute SELECT query and parse results
var xml = sqlSelect(
  "collection,@id,@email", 
  "SELECT iId as id, sEmail as email FROM " + vars.tableName + " WHERE iStatus = 1"
);

logInfo(xml.toXMLString()); // "<select><collection id="1" email="..."/></select>"

for each(var record in xml.collection) {
  logInfo('ID: ' + record.@id + ', Email: ' + record.@email);
  
  // Load full object if needed
  if (vars.targetSchema == "nms:recipient") {
    var recipient = NLWS.nmsRecipient.load(record.@id);
    recipient.lastName = recipient.lastName.toUpperCase();
    recipient.save();
  }
}
```

>[!CAUTION]
>
>Quando si utilizza SQL non elaborato:
>
>* Convalidare e bonificare sempre gli input utente
>* Utilizzare query con parametri con `$(sz)`, `$(l)`, `$(dt)` ecc.
>* Tieni presente le differenze tra i database locali e quelli cloud in [distribuzioni FFDA](../architecture/enterprise-deployment.md)

## Best practice {#best-practices}

Quando si utilizzano i metodi queryDef e NLWS:

* **Usa query con parametri** - Usa sempre parametri associati (`$(sz)`, `$(l)`) con `sqlExec` per impedire SQL injection
* **Imposta lineCount** - Sostituisci il limite predefinito di 10.000 record quando necessario con `lineCount: 999999999`
* **Usa getIfExists** - Usa `operation: "getIfExists"` quando i record potrebbero non esistere per evitare eccezioni
* **Ottimizza query** - Aggiungi `where` condizioni appropriate per limitare i set di risultati
* **Elaborazione batch** - Elabora set di dati di grandi dimensioni in batch per evitare timeout
* **Sicurezza delle transazioni** - Valutare la possibilità di utilizzare le transazioni per più aggiornamenti correlati
* **Riconoscimento FFDA** - Nelle [distribuzioni Enterprise (FFDA)](../architecture/enterprise-deployment.md), tieni presente che [!DNL Campaign] funziona con due database



## Casi d’uso pratici {#use-cases}

### Eseguire il debug e registrare le query {#debug-queries}

Utilizzare `BuildQuery()` per verificare l&#39;istruzione SQL generata prima dell&#39;esecuzione:

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@blackList = 0"}] }
  }
});

// Log the SQL for debugging
var sql = query.BuildQuery();
logInfo("About to execute: " + sql);

// Now execute
var results = query.ExecuteQuery();
```

### Duplicare un record con SelectAll {#duplicate-record}

Utilizza `SelectAll()` per copiare tutti i campi durante la duplicazione dei record:

```javascript
// Query the original record
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="get">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Select all fields for duplication
query.SelectAll(true); // true indicates duplication mode

var original = query.ExecuteQuery();

// Create a new delivery from the original
var newDelivery = NLWS.nmsDelivery.create(original);
newDelivery.label = original.@label + " (Copy)";
newDelivery.save();
```

### Convalida prima dell&#39;aggiornamento di massa {#validate-mass-update}

Visualizza sempre in anteprima i record interessati prima di eseguire aggiornamenti di massa:

```javascript
// Step 1: Preview what will be updated
var previewQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@country = 'US' AND @blackList = 1"}] }
  }
});

var preview = previewQuery.ExecuteQuery();
var count = preview.getElementsByTagName("recipient").length;
logInfo("About to update " + count + " recipients");

// Step 2: If count looks correct, proceed with mass update
if (count > 0 && count < 10000) {
  sqlExec("UPDATE NmsRecipient SET iBlackList = 0 WHERE sCountryCode = 'US' AND iBlackList = 1");
  logInfo("Mass update completed for " + count + " recipients");
} else {
  logWarning("Update cancelled: count is " + count);
}
```

## Riferimento della sintassi per la definizione della query {#querydef-reference}

Struttura completa dell&#39;oggetto `queryDef`:

```javascript
{
  queryDef: {
    schema: 'nms:recipient',           // Required: target schema
    operation: 'select',                // select|get|getIfExists|count
    lineCount: 100,                    // Maximum records to return
    startLine: 0,                      // Offset for pagination
    select: {
      node: [
        {
          expr: '@id',                 // XPath expression
          alias: '@myAlias',           // Optional alias
          label: 'ID',                 // Optional label
          groupBy: 'true',             // Group by this field
          noSqlBind: 'true'            // No SQL binding on constants
        }
      ]
    },
    where: {
      condition: [
        {
          expr: '@email IS NOT NULL',  // Condition expression
          boolOperator: 'AND',         // AND|OR
          setOperator: 'EXISTS',       // EXISTS|NOT EXISTS|IN|NOT IN
          enabledIf: '',               // Enabling condition
          ignore: false,               // Ignore this condition
          sql: '',                     // Native SQL expression
          'filter-name': ''            // Predefined filter name
        }
      ]
    },
    orderBy: {
      node: [
        {
          expr: '@lastModified',       // Field to sort by
          sortDesc: 'true'             // true for DESC, false for ASC
        }
      ]
    },
    groupBy: {
      node: [
        {expr: '@country'}             // Group by field
      ]
    }
  }
}
```

## Argomenti correlati {#related-topics}

* [Introduzione alle API di Campaign](api.md)
* [Riferimento API queryDef](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html){target="_blank"}
* [Documentazione JSAPI per Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html){target="_blank"}
* [Modello dati](datamodel.md)
* [Utilizzare gli schemi](schemas.md)
* [Utilizzare l’editor delle query](../start/query-editor.md)

