---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 6%
---
# Applicazione (classe)

Questa classe dispone di una singola istanza che consente di accedere a determinate proprietà del server applicativo. Questo singleton è accessibile tramite la variabile globale `application`.

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [hasPackage](m-application-haspackage.md) | Verifica se un pacchetto è installato. |
| [getSchema](m-application-getschema.md) | Restituisce un mapping a uno schema di Adobe Campaign o null se lo schema non esiste. |
| [getDBMSType](m-application-getdbmstype.md) | Restituisce il tipo di server del database. |
| [getNewIds](m-application-getnewids.md) | Restituisce un elenco di ID delle chiavi del database interno. |
| [getConnection](m-application-getconnection.md) | Restituisce una nuova connessione al server di database. |
| [getTimezoneJson](m-application-gettimezonejson.md) | Restituisce una stringa di caratteri che è la rappresentazione JSON dell’elenco delle differenze temporali con ora UTC e la relativa data di inizio rispetto al periodo UNIX per un fuso orario. |
| [onLog](m-application-onlog.md) | Aggiunge o elimina una funzione di intercettazione per i messaggi scritti nel giornale di registrazione |
| [onTrace](m-application-ontrace.md) | Aggiunge o elimina una funzione di intercettazione dei messaggi di traccia. |

## Proprietà

| Proprietà | Descrizione |
| --- | --- |
| [buildNumber](p-application-buildnumber.md) | Restituisce il numero di build del server applicativo. |
| [nomeIstanza](p-application-instancename.md) | Nome dell’istanza in cui viene eseguito lo script. |
| [instanceVarDir](p-application-instancevardir.md) | Percorso completo della directory &#39;var&#39; per l&#39;istanza in cui viene eseguito lo script. |
| [instanceUploadDir](p-application-instanceuploaddir.md) | Percorso completo della directory &quot;upload&quot; per l’istanza in cui viene eseguito lo script. |
| [operatore](p-application-operator.md) | Restituisce un oggetto contenente informazioni sull’operatore corrente (nome, identificatori, diritti, ecc.). |
| [impostazioni locali](p-application-locale.md) | Restituisce una stringa di caratteri corrispondente all&#39;istanza Local. |

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
