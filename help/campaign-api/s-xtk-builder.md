---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 73%
---
# generatore

Processi batch eseguiti sul server dell’applicazione

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [StrutturaOutputNavTree](sm-builder-buildoutputnavtree.md) | Unisci le definizioni della struttura di navigazione presenti nel database con quelle specificate nel parametro. |
| [BuildOutputSchema](sm-builder-buildoutputschema.md) | Genera uno schema da uno schema di origine. |
| [BuildSchema](sm-builder-buildschema.md) | Genera uno schema da uno schema di origine. |
| [BuildSchemaFromId](sm-builder-buildschemafromid.md) | Genera uno schema da un identificatore dello schema di origine. |
| [BuildSqlSchemaDiff](sm-builder-buildsqlschemadiff.md) | Genera un documento che descrive le differenze tra la struttura di database effettiva e la relativa descrizione logica. |
| [BuildUpdateOneSchemaDiff](sm-builder-buildupdateoneschemadiff.md) | Genera un documento che descrive le differenze tra una tabella nel database fisico e la descrizione logica di questa tabella. |
| [BuildUpdateSchemaDiff](sm-builder-buildupdateschemadiff.md) | Genera un documento che descrive le differenze tra la struttura di database effettiva e la relativa descrizione logica. |
| [CheckTableExists](sm-builder-checktableexists.md) | Verifica se nel database esiste una tabella |
| [CreaDB](sm-builder-createdb.md) | Crea un database |
| [Valuta JavaScript](sm-builder-evaluatejavascript.md) | Valutazione del codice JavaScript. |
| [ValutaJavaScriptTemplate](sm-builder-evaluatejavascripttemplate.md) | Valutazione del modello JavaScript (JST). |
| [ExecSql](sm-builder-execsql.md) | Esecuzione di un’istruzione SQL |
| [ExecSqlScript](sm-builder-execsqlscript.md) | Esegui uno script SQL |
| [GenCreateDbDDL](sm-builder-gencreatedbddl.md) | Genera lo script SQL utilizzato per creare la struttura del database. |
| [GenCreateOrUpdateSchemaSequenceDDL](sm-builder-gencreateorupdateschemasequenceddl.md) | Genera lo script SQL utilizzato per creare o aggiornare la sequenza dello schema autoPk |
| [GenerateNavTree](sm-builder-generatenavtree.md) | Unisci tutte le definizioni della struttura di navigazione e salva il risultato come &#39;xtk:merged&#39;. |
| [GeneraSchema](sm-builder-generateschema.md) | Genera il codice dello schema utilizzando parametri di alto livello. |
| [GetDbParams](sm-builder-getdbparams.md) | Recupera i parametri correnti dell’origine dati. |
| [GetDefaultNamespace](sm-builder-getdefaultnamespace.md) | Recupera lo spazio dei nomi predefinito. |
| [InstallPackage](sm-builder-installpackage.md) | Installa un pacchetto. |
| [InstallPackageImpl](sm-builder-installpackageimpl.md) | Installazione di un pacchetto (metodo interno, non utilizzare). |
| [InstallVendorPackages](sm-builder-installvendorpackages.md) | Installa uno o più pacchetti standard. |
| [RimuoviSchemaLinkRef](sm-builder-removeschemalinkref.md) | Rimuove lo schema e i collegamenti inversi che vi fanno riferimento. |
| [ResolvePackageReferences](sm-builder-resolvepackagereferences.md) | Risolve le dipendenze nel pacchetto |
| [UpdateDb](sm-builder-updatedb.md) | Aggiornamento della struttura del database. |
| [AggiornaSchemaDaDatabase](sm-builder-updateschemafromdatabase.md) | Aggiorna lo schema in base alla sua rappresentazione fisica nel database. |
| [AggiornaSchemiTempDaDatabase](sm-builder-updatetempschemasfromdatabase.md) | Aggiorna una raccolta di schemi in base alla loro rappresentazione fisica nel database. |

## Metodi generici

| Elemento “method” | Descrizione |
| --- | --- |
| [crea](f-create.md) | Crea una nuova entità corrispondente a uno schema specificato. |
| [carica](f-load.md) | Carica e restituisce un&#39;entità corrispondente a uno schema e a una chiave specifici. |
| [salva](m-entity-save.md) | Salva un&#39;entità nel database. |
