---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%
---
# HttpServletRequest (classe)

Rappresenta la query di un client inoltrata a un servlet.

Esiste una sola istanza di questo indirizzo accessibile tramite `request`. variabile.

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [getHeader](m-httpservletrequest-getheader.md) | Restituisce un attributo definito nell&#39;intestazione della query. |
| [getParameter](m-httpservletrequest-getparameter.md) | Restituisce il valore di un parametro di query. |
| [getRemoteAddr](m-httpservletrequest-getremoteaddr.md) | Restituisce l’indirizzo IP del client o l’ultimo proxy ad aver inviato una richiesta. |
| [getUTF8Parameter](m-httpservletrequest-getutf8parameter.md) | Restituisce il valore (codificato in UTF-8) di un parametro della query. |
| [getBodyAsString](m-httpservletrequest-getbodyasstring.md) | Restituisce il corpo della query sotto forma di stringa di caratteri utilizzando la codifica della query. |
| [avanti](m-httpservletrequest-forward.md) | Reindirizza la query a un&#39;altra pagina senza passare dal client. |

## Proprietà

| Proprietà | Descrizione |
| --- | --- |
| [parametri](p-httpservletrequest-parameters.md) | Restituisce i parametri della query. |
| [cookie](p-httpservletrequest-cookies.md) | Restituisce i cookie della query. |
| [requestURI](p-httpservletrequest-requesturi.md) | Restituisce l’URL della query. |
| [stringaQuery](p-httpservletrequest-querystring.md) | Restituisce la parte dell’URL della query che corrisponde ai parametri. |
| [schema](p-httpservletrequest-scheme.md) | Restituisce il nome del protocollo utilizzato (HTTP, HTTPS, ecc.) per accedere a questa pagina. |
| [nomeServer](p-httpservletrequest-servername.md) | Restituisce il nome del server di query. |
| [portaServer](p-httpservletrequest-serverport.md) | Restituisce il numero di porta utilizzato per contattare il server. |
| [serverURL](p-httpservletrequest-serverurl.md) | Restituisce l&#39;URL per l&#39;accesso al server. |
| [servletPath](p-httpservletrequest-servletpath.md) | Restituisce la sezione dell’URL della query che corrisponde al servlet. |
| [contextPath](p-httpservletrequest-contextpath.md) | Restituisce la sezione dell’URL della query che corrisponde al contesto. |
| [informazioniPercorso](p-httpservletrequest-pathinfo.md) | Restituisce le informazioni aggiuntive dell’URL della query. |
| [metodo](p-httpservletrequest-method.md) | Restituisce una stringa di caratteri contenente il metodo HTTP utilizzato per richiamare la query (GET, HEAD, POST, ecc.). |

## Funzioni

**Disponibile in:**

* JSSP
* WebApp
