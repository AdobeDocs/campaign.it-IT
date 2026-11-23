---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 15%
---
# GetTrackingLogs

Consente di raccogliere i registri di tracciamento generati dal servizio di reindirizzamento e monitoraggio web.

```text
[ String pointer, Number logCount, String logs, Date srvDate ] = GetTrackingLogs ( String instance, String dbId, Number version, String pointer, Number logCount )
```

## Parametri

**istanza** Identificatore breve

**dbId** Identificatore di database per il cliente che esegue una consegna

**versione** versione del registro di tracciamento

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
