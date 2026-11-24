---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 1%
---
# SchemaNode (classe)

Rappresenta l’elemento di uno schema

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [trovaNodo](m-schemanode-findnode.md) | Restituisce un&#39;istanza di [SchemaNode](c-schemanode.md) o null se il nodo non esiste e il parametro mustExist è impostato su false. |

## Proprietà

| Proprietà | Descrizione |
| --- | --- |
| [figli](p-schemanode-children.md) | Restituisce un oggetto per il quale ogni proprietà è un nodo figlio indicizzato dal relativo nome. |
| [computeString](p-schemanode-computestring.md) | Restituisce la stringa calcolata dal nodo corrente. |
| [criteriDati](p-schemanode-datapolicy.md) | Restituisce una stringa di caratteri che fornisce il criterio dati del nodo corrente. |
| [descrizione](p-schemanode-description.md) | Restituisce una stringa di caratteri che descrive il nodo corrente. |
| [valorePredefinito](p-schemanode-defaultvalue.md) | Restituisce una stringa di caratteri che fornisce il valore predefinito del nodo corrente. |
| [editType](p-schemanode-edittype.md) | Restituisce una stringa di caratteri che specifica il tipo di modifica del nodo corrente. |
| [enumerazione](p-schemanode-enumeration.md) | Restituisce un oggetto [Enumeration](c-enumeration.md) che rappresenta l&#39;enumerazione collegata al nodo corrente o null se non è presente alcuna enumerazione. |
| [enumerationImage](p-schemanode-enumerationimage.md) | Restituisce il nome dell&#39;immagine del nodo corrente sotto forma di stringa di caratteri. |
| [folderModel](p-schemanode-foldermodel.md) | Solo sul nodo principale, restituisce una stringa contenente i modelli di cartelle. Sugli altri nodi, restituisce indefinito. |
| [immagine](p-schemanode-image.md) | Restituisce il nome dell&#39;immagine sotto forma di una stringa di caratteri. |
| [integrità](p-schemanode-integrity.md) | Restituisce il tipo di integrità del collegamento. |
| [chiavi](p-schemanode-keys.md) | Restituisce una tabella con le definizioni delle chiavi [SchemaKey](c-schemakey.md) del nodo corrente. |
| [hasEnumeration](p-schemanode-hasenumeration.md) | Restituisce un valore booleano che indica se il valore del nodo corrente è collegato a un&#39;enumerazione. |
| [childCount](p-schemanode-childrencount.md) | Restituisce un numero che specifica il numero di nodi figlio. |
| [hasSQLTable](p-schemanode-hassqltable.md) | Restituisce un valore booleano che indica se il nodo corrente è collegato a una tabella SQL. |
| [hasUserEnumeration](p-schemanode-hasuserenumeration.md) | Restituisce un valore booleano che indica se il valore del nodo corrente è collegato a un&#39;enumerazione utente. |
| [guida](p-schemanode-help.md) | Restituisce la stringa di caratteri della Guida. |
| [schema](p-schemanode-schema.md) | Restituisce l&#39;istanza dell&#39;oggetto [Schema](c-schema.md) padre di questo nodo. |
| [isAdvanced](p-schemanode-isadvanced.md) | Restituisce un valore booleano che indica se il nodo corrente è avanzato o meno. |
| [isAnyType](p-schemanode-isanytype.md) | Restituisce un valore booleano che indica se il nodo corrente è ordinario. |
| [isAttribute](p-schemanode-isattribute.md) | Restituisce un valore booleano che indica se il nodo corrente è un attributo. |
| [isAutoIncrement](p-schemanode-isautoincrement.md) | Restituisce un valore booleano che indica se il valore del nodo corrente viene incrementato automaticamente. |
| [isAutoPK](p-schemanode-isautopk.md) | Restituisce un valore booleano che indica se il nodo corrente è una chiave primaria. |
| [isBlob](p-schemanode-isblob.md) | Restituisce un valore booleano che indica se il nodo corrente è un BLOB. |
| [isCalculated](p-schemanode-iscalculated.md) | Restituisce un valore booleano che indica se il valore del nodo corrente è il risultato di un calcolo. |
| [isCDATA](p-schemanode-iscdata.md) | Restituisce un valore booleano che indica se il nodo corrente è mappato da XML di tipo CDATA. |
| [isCollection](p-schemanode-iscollection.md) | Restituisce un valore booleano che indica se il nodo corrente è una raccolta di sottoelementi e/o attributi. |
| [isDefaultOnDuplicate](p-schemanode-isdefaultonduplicate.md) | Restituisce un valore booleano. Se il valore aggiunto è variabile, durante la deduplicazione dei record il valore predefinito (definito in defaultValue) viene riapplicato automaticamente durante la registrazione. |
| [isElementOnly](p-schemanode-iselementonly.md) | Restituisce un valore booleano che indica se il nodo corrente è una suddivisione logica dello schema. |
| [isExternalJoin](p-schemanode-isexternaljoin.md) | True se il nodo è un collegamento e se il join è esterno. |
| [isFeature](p-schemanode-isfeature.md) | Restituisce un valore booleano che indica se il nodo è una funzione. |
| [isLink](p-schemanode-islink.md) | Restituisce un valore booleano che indica se il nodo è un collegamento. |
| [isMappedAsXML](p-schemanode-ismappedasxml.md) | Restituisce un valore booleano che indica se il nodo è un mapping XML. |
| [isMemo](p-schemanode-ismemo.md) | Restituisce un valore booleano che indica se il nodo corrente è mappato da un oggetto Memo. |
| [isMemoData](p-schemanode-ismemodata.md) | Restituisce un valore booleano che indica se il nodo corrente è mappato da un oggetto MemoData. |
| [isNotNull](p-schemanode-isnotnull.md) | Restituisce un valore booleano che indica se il nodo corrente può prendere in considerazione o meno il valore null. |
| [isRequired](p-schemanode-isrequired.md) | Restituisce un valore booleano che indica se il valore del nodo corrente è obbligatorio o meno. |
| [isRoot](p-schemanode-isroot.md) | Restituisce un valore booleano che indica se il nodo è la radice dello schema. |
| [isSQL](p-schemanode-issql.md) | Restituisce un valore booleano che indica se il nodo corrente è mappato in SQL. |
| [isTemporaryTable](p-schemanode-istemporarytable.md) | Restituisce un valore booleano che indica se la tabella è temporanea. La tabella non verrà creata durante la creazione del database. |
| [isUnbound](p-schemanode-isunbound.md) | Restituisce un valore booleano che indica se il nodo corrente ha un numero illimitato di figli dello stesso tipo. |
| [isUser](p-schemanode-isuser.md) | Restituisce un valore booleano che indica se il nodo è di tipo utente o meno. |
| [joinParts](p-schemanode-joinparts.md) | Restituisce una tabella di istanze SchemaNode per le quali ogni elemento rappresenta una condizione del join. |
| [etichetta](p-schemanode-label.md) | Restituisce una stringa di caratteri che corrisponde alla descrizione del nodo corrente. |
| [nome](p-schemanode-name.md) | Restituisce una stringa di caratteri che rappresenta il nome del nodo corrente. |
| [percorsoNodo](p-schemanode-nodepath.md) | Restituisce una stringa di caratteri che rappresenta il percorso assoluto del nodo corrente. |
| [padre](p-schemanode-parent.md) | Restituisce un oggetto [SchemaNode](c-schemanode.md) che è l&#39;oggetto padre o null se non esiste. |
| [PKSequence](p-schemanode-pksequence.md) | Restituisce una stringa di caratteri che fornisce il nome della sequenza da utilizzare per la chiave primaria. |
| [packageStatus](p-schemanode-packagestatus.md) | Restituisce un numero che indica lo stato del pacchetto. |
| [reverseLink](p-schemanode-reverselink.md) | Se l&#39;elemento è un collegamento, restituisce un oggetto [SchemaNode](c-schemanode.md) che rappresenta un collegamento inverso tramite lo schema di destinazione. In caso contrario, la proprietà non è definita. |
| [SQLName](p-schemanode-sqlname.md) | Nome SQL del campo. La proprietà è una stringa vuota se l&#39;oggetto non è un campo di tipo SQL. |
| [SQLTable](p-schemanode-sqltable.md) | Nome SQL della tabella. La proprietà è una stringa vuota se l&#39;oggetto non è l&#39;elemento principale o se il mapping dello schema non è di tipo SQL. |
| [dimensioni](p-schemanode-size.md) | Dimensione del tipo di stringa di caratteri. |
| [tableDefinition](p-schemanode-tabledefinition.md) | Un&#39;istanza di un [SchemaNode](c-schemanode.md) che è la descrizione della tabella contenente il nodo corrente, null se non esiste. |
| [destinazione](p-schemanode-target.md) | L’elemento principale dello schema della destinazione del collegamento. Se l&#39;oggetto non è un collegamento, la proprietà non viene definita. |
| [tipo](p-schemanode-type.md) | Restituisce una stringa di caratteri che fornisce il tipo di valore del nodo corrente. |
| [enumerazioneUtente](p-schemanode-userenumeration.md) | Restituisce una stringa di caratteri che rappresenta il nome dell&#39;enumerazione utente utilizzata dal nodo corrente. |

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
