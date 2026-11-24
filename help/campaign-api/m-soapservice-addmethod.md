---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 6%
---
# addMethod

Dichiara una funzione sul servizio.

```text
addMethod (name, action, arguments, responses, requestNodeName, responseNodeName)
```

## Parametri

**name** Nome del metodo. Questo è il nome esposto in JavaScript e il nome del metodo SOAP.

Parametro **action** SOAP-Action.

**argomenti** Dichiarazione di argomenti sotto forma di tabella contenente un elenco di stringhe raggruppate per coppie. La prima stringa è il nome dell&#39;argomento e la seconda corrisponde al tipo: \[&quot;name1&quot;, &quot;type1&quot;, &quot;name2&quot;, &quot;type2&quot;, ...\]

**risposte** Dichiarazione dei valori restituiti sotto forma di tabella contenente un elenco di stringhe raggruppate per coppie: La prima stringa è il nome dell&#39;argomento e la seconda corrisponde al tipo: \[&quot;name1&quot;, &quot;type1&quot;, &quot;name2&quot;, &quot;type2&quot;, ...\]

**requestNodeName** Stringa di caratteri che specifica il nome del nodo XML della query SOAP anziché il nome del metodo.

**responseNodeName** Stringa di caratteri che specifica il nome del nodo XML della risposta di SOAP anziché il nome del metodo seguito da Response.

## Valore restituito

Nessuno.

## Osservazioni

Sono supportati i seguenti tipi:

* stringa
* booleano
* lungo
* breve
* byte
* mobile
* doppio
* data
* ora
* Data e ora
* NLDocument
* NLElement
* NLRawXML
* NLCollection

Quando un metodo viene dichiarato nel servizio, diventa un metodo del servizio e può essere richiamato direttamente chiamando il metodo con il relativo nome. Il tipo NLRawXML utilizzato su un parametro in ingresso copia l&#39;intero nodo XML per sostituire l&#39;argomento. Utilizzato come tipo restituito, contiene l’intero primo elemento figlio della risposta SOAP. Il suo utilizzo implica che la risposta SOAP ha un solo elemento figlio. Il tipo NLCollection utilizzato in un parametro in ingresso copia tutti gli elementi figlio per sostituire l&#39;argomento. Questa opzione è utile quando l&#39;argomento in ingresso è un parametro variabile. Utilizzato come tipo restituito, contiene l’intera risposta SOAP, poiché questa è la radice del valore restituito. In caso di errori, viene generata un’eccezione. Se si tratta di un errore SOAP con formato corretto, l&#39;eccezione generata ha una proprietà soapFault e contiene il nodo XML dell&#39;errore SOAP. Esempio:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
session.addMethod("GetOption", "xtk:session#GetOption",
  ["token", "string", "name", "string"],
  ["value", "string", "type", "byte"])
try
{
var result  = session.GetOption("admin/", "NmsBroadcast_DefaultProvider")
var value   = result[0]
var type    = result[1]
logInfo("Value = " + value)
logInfo("Type = " + type)
}
catch( e )
{
  if( e.soapFault )
    logInfo("A SOAP Fault occured : " + e.soapFault.toXMLString());
  else
    logInfo("An error occured : " + e);
}
```

## Funzioni

**Metodo di classe:** [SoapService](c-soapservice.md)

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
