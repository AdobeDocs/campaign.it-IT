---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 6%
---
# CreateRequestByName

Crea una nuova richiesta di accesso a dati personali utilizzando il nome interno dello spazio dei nomi

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending Number regulation )
```

## Parametri

Nome interno dello spazio dei nomi **namespaceName**

**riconciliazioneValue** Valore di riconciliazione

**type** ReconciliationValue

**confirmDeletePending** Richiesta di conferma prima di eliminare i dati

Tipo di regolamento **regulation** con i seguenti valori:

```xml
           
               <value label="GDPR" name="gdpr" value="1"/>
            <value label="CCPA" name="ccpa" value="2"/>
            <value label="PDPA" name="pdpa" value="3"/>
            <value label="LGPD" name="lgpd" value="4"/>
           
           
```

## Valore/i restituito/i

ID **id** della richiesta appena creata

## Funzioni

**Schema:** [nms:privacyRequest](s-nms-privacyrequest.md)

**Statico:**

Sì
