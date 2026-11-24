---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 32%
---
# Iscrizione

Crea o aggiorna l‘iscrizione di un destinatario a un servizio informativo

```text
Subscribe ( String serviceName, XML recipient, Boolean create )
```

## Parametri

**serviceName** Elenco di nomi di servizi di informazioni (separati da virgola)

**destinatario** Destinatario da registrare e facoltativamente da creare

**crea** Crea destinatario se non esiste

## Valore/i restituito/i

Nessuno.

## Esempio

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Subscribe("SVC1", recipient, false)
        
```

## Funzioni

**Schema:** [nms:subscription](s-nms-subscription.md)

**Statico:**

Sì
