---
title: Schemi a 64 bit
description: Scopri gli schemi a 64 bit in Adobe Campaign v8 per i clienti che hanno eseguito la migrazione a Campaign Standard
feature: Technote
role: Admin
exl-id: ab5f01fd-4ad5-46e9-b132-011fe0f7bbd2
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: ab81f6c3-9317-564f-af92-6670a8784294
    internal-label: Technote
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 7%
---
# Schemi a 64 bit {#sixty-four-bit-tables}

Per facilitare la transizione da Campaign Standard a Campaign v8, diverse tabelle sono state modificate da 32 a 64 bit. In effetti, Campaign Standard supporta la PK a 64 bit in diversi schemi predefiniti, mentre Campaign v8 supporta la PK a 32 bit nella maggior parte degli schemi.

## Limitazioni

* Questa modifica tecnica si applica solo ai clienti che eseguono la migrazione da Campaign Standard.
* Lo schema e l’estensione broadlog non sono supportati in 64 bit. Rimarrà in 32 bit.
* I registri relativi alle consegne inviate agli utenti tecnici non saranno disponibili in Campaign v8.
* È supportato solo PostgreSQL.

## Schemi modificati

Elenco degli schemi modificati a 64 bit e dei relativi attributi modificati.

| Nome dello schema | Nome attributo |
|--- |--- |
| nms:broadLogRcp | ID |
| nms:trackingLogRcp | ID |
| nms:excludeLogRcp | ID |
| nms:broadLogVisitor | ID |
| nms:trackingLogVisitor | ID |
| nms:propositionRcp | interfaceId |
| nms:propositionVisitor | interfaceId |
| nms:webTrackingLog | ID |
| nms:tmpBroadcast | message-id |
| nms:tmpMarketingPressure | message-id |
| nms:tmpBroadcastExclusion | message-id |
| nms:tmpBroadcastPaper | message-id |
| nms:broadLogAppSubRcp | ID |
| nms:trackingLogAppSubRcp | ID |
| nms:excludeLogAppSubRcp | ID |
| nms:webEvent | broadLogSrc-id, broadLogRemkt-id |
| nms:broadLogMid | mktBroadLogId |
| nms:mirrorPageSearch | remoteMessageId |
