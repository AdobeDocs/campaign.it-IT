---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 29%
---
# CreateRequestByName

Crea una nuova richiesta GDPR utilizzando il nome interno dello spazio dei nomi

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending )
```

## Parametri

Nome interno dello spazio dei nomi **namespaceName**

**riconciliazioneValue** Valore di riconciliazione

**type** ReconciliationValue

**confirmDeletePending** Richiesta di conferma prima di eliminare i dati

## Valore/i restituito/i

ID **id** della richiesta appena creata

## Funzioni

**Schema:** [nms:gdprRequest](s-nms-gdprrequest.md)

**Statico:**

Sì
