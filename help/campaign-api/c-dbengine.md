---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 4%
---
# Motore DBE (classe)

Rappresenta una connessione al database.

Questo oggetto consente di eseguire query sul database ed eseguire operazioni correlate.

La maggior parte dei metodi di questa classe richiede i diritti &#39;sql&#39;. Se l&#39;operatore richiama un metodo e non dispone dei diritti appropriati, viene generata un&#39;eccezione. In generale, tutti i metodi che modificano il database richiedono i diritti &#39;sql&#39;, mentre i metodi che visualizzano semplicemente le informazioni non lo richiedono. Per informazioni sull’eventuale necessità dei diritti, consulta la documentazione relativa a ciascun metodo.

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [batchDelete](m-dbengine-batchdelete.md) | Elimina i record di una tabella in base ai pacchetti. |
| [elimina](m-dbengine-dispose.md) | Libera la connessione da tutte le risorse ad essa collegate. |
| [esegui](m-dbengine-execute.md) | Esegue un comando SQL. |
| [esegui](m-dbengine-exec.md) | Alias del comando execute. Questa funzione è obsoleta. Utilizzare [execute()](m-dbengine-execute.md) |
| [query](m-dbengine-query.md) | Esegue una query SQL SELECT. |
| [queryWithTypes](m-dbengine-querywithtypes.md) | Esegue una query SQL di tipo SELECT con specifica del tipo di colonna. |
| [inizio](m-dbengine-begin.md) | Avvia una nuova transazione sulla connessione. |
| [commit](m-dbengine-commit.md) | Approva la transazione in corso sulla connessione. |
| [rollback](m-dbengine-rollback.md) | Annulla la transazione in corso sulla connessione. |

## Proprietà

| Proprietà | Descrizione |
| --- | --- |
| [isOracle](p-dbengine-isoracle.md) | Restituisce true se il database è Oracle. |
| [isDB2](p-dbengine-isdb2.md) | Restituisce true se il database è di tipo DB2. |
| [isMySQL](p-dbengine-ismysql.md) | Restituisce true se il database è di tipo MySQL. |
| [isMSSQL](p-dbengine-ismssql.md) | Restituisce true se il database è SQL Server. |
| [isPostgreSQL](p-dbengine-ispostgresql.md) | Restituisce true se il database è PostgreSQL. |
| [isSybase](p-dbengine-issybase.md) | Restituisce true se il database è Sybase. |
| [isSybaseIQ](p-dbengine-issybaseiq.md) | Restituisce true se il database è Sybase IQ. |
| [isFDA](p-dbengine-isfda.md) | Restituisce true se il database è accessibile tramite FDA. |
| [isBroken](p-dbengine-isbroken.md) | Restituisce true se la connessione non è più utilizzabile. |
| [useUnicodeData](p-dbengine-useunicodedata.md) | Restituisce true se il database contiene dati Unicode. |
| [useNChar](p-dbengine-usenchar.md) | Restituisce true se Adobe Campaign utilizza campi di tipo NCHAR, NVARCHAR, NCLOB e NTEXT. |

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
