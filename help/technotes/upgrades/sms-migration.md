---
title: Passaggio al nuovo connettore SMS v2
description: Scopri come passare al nuovo connettore SMS v2
feature: Technote
role: Admin
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
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
source-wordcount: '225'
ht-degree: 0%
---
# Passaggio al nuovo connettore SMS v2

Adobe Campaign v8 introduce un nuovo **connettore di elaborazione SMS dedicato** (v2), che offre prestazioni e affidabilità migliorate rispetto al connettore SMS basato su MTA legacy.

## Perché passare al connettore v2

Il processo SMS dedicato introduce il supporto per la modalità ricetrasmettitore SMPP, riducendo il conteggio delle connessioni e migliorando l’efficienza delle risorse, supportando al tempo stesso le configurazioni del trasmettitore/ricevitore se necessario. Offre una maggiore stabilità, con un ripristino più rapido dagli errori, connessioni persistenti e nessuna dipendenza dai file locali o dalla comunicazione tra processi. Anche le prestazioni sono migliorate, con latenza inferiore, throughput più elevato e microbatch intelligente per bilanciare velocità e affidabilità. Inoltre, l’isolamento del processo SMS semplifica la risoluzione dei problemi e riduce al minimo l’impatto su più canali. Questi miglioramenti rendono il connettore dedicato una soluzione più solida e scalabile per la consegna di SMS.

## Configurazione

Con Adobe Campaign Managed Cloud Services, la configurazione del server e la migrazione del connettore SMS sono gestite da Adobe. Questa procedura tecnica richiede l&#39;accesso diretto ai file di configurazione del server e alle operazioni del database.

Se devi migrare al nuovo connettore SMS v2, contatta il tuo rappresentante Adobe o l’Assistenza clienti di Adobe. Pianificheranno ed eseguiranno gli aggiornamenti necessari per l’istanza.

Per ulteriori informazioni sul canale SMS in Campaign v8, consulta la [documentazione SMS](../../v8/send/sms/sms.md).
