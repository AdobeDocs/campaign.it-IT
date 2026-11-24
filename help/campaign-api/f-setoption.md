---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 7%
---
# setOption

Modifica il valore di un&#39;opzione nella tabella delle opzioni.

```text
setOption (name, value, description )
```

## Parametri

**nome** Nome dell&#39;opzione.

**valore** Valore dell&#39;opzione.

**description** Valore della descrizione (facoltativo).

## Valore restituito

Nessuno.

## Osservazioni

I diversi tipi di dati sono:

* testo,
* numero intero,
* virgola mobile,
* Data e ora,
* longtext

Non è possibile creare longText e un tipo intero dall’API.

Per questi due tipi, devi innanzitutto creare l’opzione dalla console e quindi gestire i valori tramite l’API setOption.

**Esempio:**

```javascript
               //create option of type Date+Time'
               var ourDate = getCurrentDate();
               setOption("testOptionDateTime",ourDate,"option of type Date+Time");
                              
               //create option of type Floating point'
               setOption("testOptionFloat",1,"option of type Floating point");
               
               //create option of type Text'
               setOption("testOptionText","I am a text","option of type Text");               
           
```

Se desideri eliminare la descrizione, devi chiamare l’API con una descrizione vuota (setOption(name,value,&quot;&quot;).

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
