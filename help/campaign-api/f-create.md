---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 11%
---
# creare

Crea una nuova entità corrispondente a uno schema specificato.

```text
create ( [content ])
```

## Parametri

**content** Stringa di caratteri facoltativa corrispondente al codice XML dell&#39;entità da creare.

## Valore restituito

Restituisce l&#39;entità sotto forma di oggetto JavaScript.

## Osservazioni

create non è una funzione globale, ma un metodo di schema. Per richiamarlo, devi usare il prefisso dello schema desiderato. Ad esempio:

```javascript
var recipient = NLWS.nmsRecipient.create(
      {recipient: {
        email: "support@adobe.com", 
        lastName: "Adobe", 
        firstName: "Support"}})
recipient.save()
```

Il documento non viene salvato automaticamente nel database. Utilizzare il metodo ⌐⌐[save()](m-entity-save.md) sull&#39;entità.

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
