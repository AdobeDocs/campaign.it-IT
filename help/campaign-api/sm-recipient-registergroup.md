---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '27'
ht-degree: 37%
---
# RegisterGroup

Aggiungi i destinatari selezionati a un elenco

```text
RegisterGroup ( XML groupList, XML recipientList, Boolean register )
```

## Parametri

**elenchi di gruppi**

**elenco destinatari** elenco destinatari

**registra** Destinatari Abbonati/Annulla Abbonamento

## Valore/i restituito/i

Nessuno.

## Esempio

```javascript
//List
var entity = <entityList><key value="24447964"/>
              <where>
                <condition enabledIf="" expr="@id = 24447964"/>
              </where>
            </entityList>
 
//Recipient
var choice = <choiceList><key value="18995462"/>
              <where>
                <condition enabledIf="" expr="@id = 18995462"/>
              </where>
            </choiceList>
nms.recipient.RegisterGroup(entity,choice,true)
        
```

## Funzioni

**Schema:** [nms:recipient](s-nms-recipient.md)

**Statico:**

Sì
