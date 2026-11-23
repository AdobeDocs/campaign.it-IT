---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 3%
---
# Spawn

Crea un’istanza di flusso di lavoro da un modello, applica una patch e avvia il flusso di lavoro.

```text
Number instanceId = Spawn ( String workflowId, XML patch )
```

## Parametri

**workflowId** Identificatore o nome interno del modello di workflow.

**patch** L&#39;elemento XML che deve essere unito al modello per ottenere l&#39;istanza prima di eseguirla. Esempio:

```xml
    <workflow>
      <activities>
        <extern name="notepad">
          <additionnalArgs><![CDATA[c:\xxx.txt]]>
          </additionnalArgs>
        </extern>
      </activities>
    </workflow>
    
```

Questo esempio sostituisce gli argomenti dell&#39;attività &#39;notepad&#39;. Se non desideri applicare questa patch, utilizza un elemento &lt;workflow/> vuoto o una stringa vuota.

## Valore/i restituito/i

**instanceId** Identificatore dell&#39;istanza creata dal modello.

## Osservazioni

Il comando viene eseguito in modalità asincrona e non ha un effetto immediato dopo il ritorno del metodo. Il flusso di lavoro viene avviato con l’account dell’operatore chiamante.

## Funzioni

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Statico:**

Sì
