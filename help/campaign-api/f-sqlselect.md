---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 13%
---
# sqlSelect

Esegue una query SQL e restituisce il risultato come documento XML.

```text
sqlSelect (format, query [, dataSource ])
```

## Parametri

**format** Stringa separata da virgole che descrive il formato dei dati previsti come nome:type\[:length\] type list docName, \[fieldXPath:type,\]\*

**query** La query SQL.

**dataSource** L&#39;origine dati.

## Valore restituito

Oggetto XML contenente un elenco di elementi per ogni riga del risultato della query.

## Osservazioni

Esempio:

```javascript
var res = sqlSelect("publicUrl,@sstringValue:string",
        "select sstringValue from XtkOption where sname='XtkFileRes_PublicUrl'")
logInfo(res.publicUrl.@sstringValue.toString())
```

```javascript
var xmlRes = sqlSelect("name:string,file:string:64","select relname, relfilenode from  pg_class WHERE relkind='r' AND pg_get_userbyid(relowner)<>'postgres';");
```

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
