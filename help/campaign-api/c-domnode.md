---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 5%
---
# DOMNode (Class)

DOMNode è la classe padre di diversi componenti che compongono un documento.

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [inserisciPrima](m-domnode-insertbefore.md) | Inserire un nodo prima di una posizione specifica. |
| [replaceChild](m-domnode-replacechild.md) | Sostituire un nodo. |
| [removeChild](m-domnode-removechild.md) | Eliminare un nodo. |
| [appendChild](m-domnode-appendchild.md) | Inserisci un nodo alla fine dell’elenco delle sottocartelle. |
| [hasChildNodes](m-domnode-haschildnodes.md) | Verifica se il nodo dispone di almeno una sottocartella. |
| [normalizza](m-domnode-normalize.md) | Normalizza il nodo: i nodi di testo adiacenti vengono uniti e i nodi di testo vuoti vengono eliminati. |
| [hasAttributes](m-domnode-hasattributes.md) | Verifica se il nodo dispone di almeno un attributo. |
| [isSameNode](m-domnode-issamenode.md) | Verifica se il riferimento specificato rappresenta lo stesso nodo. |
| [isDefaultNamespace](m-domnode-isdefaultnamespace.md) | Verifica se lo spazio dei nomi specificato è quello predefinito. |
| [lookupNamespaceURI](m-domnode-lookupnamespaceuri.md) | È stata eseguita una ricerca nell’URI dello spazio dei nomi collegato al prefisso specificato. |
| [isEqualNode](m-domnode-isequalnode.md) | Confronta due nodi. |

## Proprietà

| Proprietà | Descrizione |
| --- | --- |
| [nomeNodo](p-domnode-nodename.md) | Nome nodo qualificato. Il nome dipende dal tipo di nodo. |
| [nodeValue](p-domnode-nodevalue.md) | Valore del nodo. Il valore dipende dal tipo di nodo. |
| [nodeType](p-domnode-nodetype.md) | Tipo di nodo. |
| [parentNode](p-domnode-parentnode.md) | Nodo padre o null. |
| [childNodes](p-domnode-childnodes.md) | Restituisce l&#39;elenco dei nodi figlio sotto forma di tabella. |
| [firstChild](p-domnode-firstchild.md) | Primo nodo figlio di questo nodo o null se non ha nodi figlio. |
| [lastChild](p-domnode-lastchild.md) | Ultimo nodo figlio di questo nodo o null se non ha nodi figlio. |
| [nextSibling](p-domnode-nextsibling.md) | Nodo che segue questo nodo o null. |
| [previousSibling](p-domnode-previoussibling.md) | Il nodo che determina immediatamente la precisione di questo nodo o null. |
| [attributi](p-domnode-attributes.md) | Restituisce una tabella contenente l’elenco degli attributi se il nodo è un elemento, altrimenti null. |
| [namespaceURI](p-domnode-namespaceuri.md) | URI dello spazio dei nomi del nodo. |
| [prefisso](p-domnode-prefix.md) | Prefisso dello spazio dei nomi di questo nodo o vuoto se non specificato. |
| [localName](p-domnode-localname.md) | Parte locale del nome completo del nodo. |
| [URIbase](p-domnode-baseuri.md) | URI di base del nodo. |
| [textContent](p-domnode-textcontent.md) | Contenuto testo del nodo. Il valore dipende dal tipo di nodo. |
| [ownerDocument](p-domnode-ownerdocument.md) | Documento a cui appartiene questo nodo. |

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Messaggio di consegna
* Regola di tipologia
* Importazione
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
