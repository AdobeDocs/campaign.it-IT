---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 7%
---
# SubmitNotification

Crea e invia una notifica da uno scenario.

```text
Number notificationId = SubmitNotification ( String scenarioName, XML target )
```

## Parametri

**scenarioName** Nome interno del modello

**target** Popolazione target di consegna che sostituisce quella dello scenario

## Valore/i restituito/i

**notificationId** Identificatore di notifica

## Osservazioni

Avviso: questa API non è creata per gestire grandi volumi di dati o lavorare in tempo reale. È sviluppato per elaborare un massimo di diverse chiamate al minuto. SubmitNotification blocca il thread durante l’analisi della consegna. L&#39;operazione potrebbe richiedere alcuni secondi. Il parametro &quot;target&quot; specifica il target della consegna. Sostituirà una destinazione specificata nel modello. Per consegnare a una destinazione nel database, l’elemento target utilizza la seguente sintassi:

```xml
<delivery>
  <targets>
    <deliveryTarget>
      <targetPart type='query' exclusion='false' ignoreDeleteStatus='false'>
        <where>
          <condition expr='[@folder-id] = 1050'/>
        </where>
      </targetPart>
    </deliveryTarget>
  </targets>
</delivery>
```

Per consegnare a una destinazione in un file:

```xml
<delivery>
  <targets>
    <deliveryFile upload='false'>
      <name>c:/tmp/myFile.csv</name>
    </deliveryFile>
  </targets>
</delivery>
```

È possibile definire esplicitamente il target (in realtà il contenuto del file utilizzato come target):

```xml
<delivery>
  <targets fromExternalSource='true'>
    <externalSource>MsgId|ClientId|Title|Name|FirstName|Mobile|Email|Market_segment|Product_propensity1|Product_propensity2|Product_propensity3|Product_propensity4|Support_Number|Amount|Threshold1|
                    000001234|M.|Martin|Peter|0650201020|pmartin@neolane.com|1|A1|A2|A3|A4|E12|120000|100000
    </externalSource>
  </targets>
</delivery>
```

È anche possibile mantenere il target definito nel modello con l&#39;attributo &quot;\_keepTemplateTarget&quot;

```xml
<delivery>
  <targets _keepScenarioTarget='true'/>
</delivery>
```

## Funzioni

**Schema:** [nms:delivery](s-nms-delivery.md)

**Statico:**

Sì
