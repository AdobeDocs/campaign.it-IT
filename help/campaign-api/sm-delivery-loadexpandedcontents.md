---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 38%
---
# LoadExpandedContents

Carica un elenco di componenti per la preelaborazione con dipendenze (blocchi di personalizzazione, opzioni, oggetti script aggiuntivi, ecc.).

```text
XML material = delivery.LoadExpandedContents ( String ids ) const
```

## Parametri

**ids** Elenco di identificatori di componenti separati da virgole (ad esempio, &#39;option\|NmsServer\_URL\|text,includeView\|UnsubscriptionLink\|html&#39;).

## Valore/i restituito/i

**materiale** Restituisce il contenuto come elemento &quot;materiale&quot;.

## Funzioni

**Schema:** [nms:delivery](s-nms-delivery.md)

**Statico:**

No

**Costante:**

Sì

**Solo chiave:**

No
