---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 9%
---
# CurrentOperator (classe)

Oggetto contenente informazioni sull’operatore corrente (nome, identificatori, diritti, ecc.).

Questa classe dispone di una singola istanza che consente di accedere a determinate proprietà del server applicativo. Questo singleton è accessibile tramite la proprietà della variabile globale `application`.

Esempio:

```text
var operator = application.operator logInfo("login: " + operator.login) logInfo("id: " + operator.id) logInfo("description: " + operator.computeString) logInfo("=== Groups ===") for each(var id in operator.groups) logInfo(id) logInfo("=== Rights ===") for each(var right in operator.rights) logInfo(right)
```

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [hasRight](m-currentoperator-hasright.md) | Verifica se l’operatore dispone di un diritto denominato specifico. |

## Proprietà

| Proprietà | Descrizione |
| --- | --- |
| [accesso](p-currentoperator-login.md) | Restituisce l’accesso dell’operatore corrente. |
| [id](p-currentoperator-id.md) | Restituisce l&#39;identificatore interno dell&#39;operatore corrente. |
| [computeString](p-currentoperator-computestring.md) | Restituisce la stringa di descrizione dell&#39;operatore corrente. Per impostazione predefinita, questo è il nome dell’operatore seguito dal suo accesso. |
| [gruppi](p-currentoperator-groups.md) | Restituisce l’elenco degli identificatori nei gruppi di operatori correnti. |
| [diritti](p-currentoperator-rights.md) | Restituisce l&#39;elenco dei diritti dell&#39;operatore corrente. |
| [fuso orario](p-currentoperator-timezone.md) | Restituisce il nome del fuso orario utilizzato dall&#39;operatore corrente. |
| [home](p-currentoperator-home.md) | Restituisce il nome della cartella principale dell&#39;operatore corrente. |

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
