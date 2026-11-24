---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 15%
---
# nodeValue

Valore del nodo. Il valore dipende dal tipo di nodo.

```text
nodeValue
```

## Osservazioni

È possibile accedere a questa proprietà con autorizzazioni di lettura e scrittura. Esempio per recuperare una riga dell’oggetto e aggiungerla ai dati aggiuntivi da un’attività Query in un flusso di lavoro:

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',data), 1, 255)
```

Esempio per recuperare una riga oggetto da un’attività di arricchimento in un flusso di lavoro:

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',[target/data]), 1, 255)
```

## Funzioni

**Proprietà della classe:** [DOMNode](c-domnode.md)

**Sola lettura:**

Sì

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
