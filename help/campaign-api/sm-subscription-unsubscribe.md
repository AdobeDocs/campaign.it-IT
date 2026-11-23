---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '29'
ht-degree: 41%
---
# Annullamento iscrizione

Annulla l’iscrizione di un destinatario dai servizi informazioni.

```text
Unsubscribe ( String serviceName, XML recipient )
```

## Parametri

**serviceName** Elenco di nomi di servizi di informazioni (separati da virgola)

Destinatario **recipient**

## Valore/i restituito/i

Nessuno.

## Esempio

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Unsubscribe("SVC1", recipient)
        
```

## Funzioni

**Schema:** [nms:subscription](s-nms-subscription.md)

**Statico:**

Sì
