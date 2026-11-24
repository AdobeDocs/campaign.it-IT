---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 18%
---
# GetTrackingLogs4

Consente di recuperare i registri di tracciamento generati dal server di reindirizzamento remoto e di tracciamento web, utilizzando un formato post 4.0.

```text
[ String pointer, Number logCount, String logs, Date srvDate ] = GetTrackingLogs4 ( String instance, String dbId, String pointer, Number logCount )
```

## Parametri

**istanza** Identificatore breve

**dbId** Identificatore di database per il cliente che esegue una consegna

**puntatore** Identificatore (int64 serializzato) del registro da cui recuperare i registri.

**logCount** Numero di registri da recuperare per la richiesta (0 significa valore predefinito), numero di registri restituiti dalla risposta.

## Valore/i restituito/i

**puntatore** Identificatore (int64 serializzato) del registro da cui recuperare i registri.

**logCount** Numero di registri da recuperare per la richiesta (0 significa valore predefinito), numero di registri restituiti dalla risposta.

**registri** registri recuperati

**srvDate** ora GMT del server al momento della richiesta di recupero del registro

## Funzioni

**Schema:** [nms:remoteTracking](s-nms-remotetracking.md)

**Statico:**

Sì
