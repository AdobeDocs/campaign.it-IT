---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 8%
---
# sqlExecOnDataSource

Esegue uno script SQL su un&#39;origine dati.

```text
sqlExecOnDataSource (query, dataSource [, value1, ... ])
```

## Parametri

**query** La query SQL.

**dataSource** L&#39;origine dati.

**valore1, ...** Variabili della query SQL.

## Valore restituito

Numero di record aggiornati o inseriti in un comando UPDATE o INSERT SQL.

## Osservazioni

I valori autorizzati per l’origine dati possono essere:

* &quot;&quot; o &quot;default&quot; punta al database di Adobe Campaign

* &quot;nms:extAccount:InternalName&quot; fa riferimento a un&#39;origine dati definita negli account esterni di Adobe Campaign (FDA)

* &quot;name&quot; (nome dell’origine dati) fa riferimento a un’origine dati definita nel file di configurazione dell’istanza (config-instance.xml) nel formato seguente:

  ```xml
                   <dataStore hosts="*" lang="">
        <dataSource name="datasourcename">
          <dbcnx encrypted="" login="" password=""
                 provider="" server=""/>
        </dataSource>
      </dataStore>
  ```

Esempio:

```javascript
sqlExecOnDataSource("UPDATE XtkOption SET sStringValue = $(sz) WHERE sName = $(sz)", oracleExternalDB, 'WdbcOptions_TableSpaceWork_nms:extAccount:' + sExtAccount)
```

Le variabili facoltative impostate come parametri di questa funzione sono definite in [sqlGetString(query, value1, ...)](f-sqlgetstring.md)

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
