---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 29%
---
# generateRegisterHookScript

Genera lo script di estensione da chiamare durante l’evento “register” di “appSubscriptionRcp”.

```text
String JSScriptStr = generateRegisterHookScript ( XML additionalXmlNodes )
```

## Parametri

**ulterioriXmlNodes** nodi XML che contengono il collegamento tra parametri aggiuntivi e il campo di mappatura di destinazione.

## Valore/i restituito/i

**JSScriptStr** Script JS che consente di collegare parametri aggiuntivi ai campi nel mapping di destinazione.

## Funzioni

**Schema:** [nms:mobileApp](s-nms-mobileapp.md)

**Statico:**

Sì
