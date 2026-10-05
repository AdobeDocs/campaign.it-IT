---
title: Connettori SMS
description: Scopri i connettori SMS in Adobe Campaign
feature: SMS
role: User, Admin
level: Intermediate
exl-id: 5ec3f172-22dc-458b-8688-9974009c985e
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 1%
---
# Informazioni sui tipi di connettore SMS {#sms-connectors}

Adobe Campaign supporta due connettori SMS utilizzati per inviare messaggi SMS ai clienti:

* **Connettore SMS legacy**: prima versione del connettore utilizzato in Campaign v7 e versioni precedenti di Campaign v8. [Ulteriori informazioni](#legacy-sms-connector)
* **Connettore SMS v2**: disponibile in GA a partire da Campaign v8.9.1, questo connettore SMS dedicato v2 è stato modernizzato per offrire prestazioni e affidabilità migliorate. [Ulteriori informazioni](#sms-connector-v2)

## Connettore SMS legacy {#legacy-sms-connector}

Il connettore SMS legacy è il connettore SMS basato su MTA utilizzato nelle versioni precedenti di Adobe Campaign. Questo connettore è ancora supportato per le implementazioni esistenti, ma Adobe consiglia vivamente di eseguire l’aggiornamento alla versione v8.9.1 o successiva per beneficiare delle prestazioni e dell’affidabilità migliorate del connettore v2.

Per informazioni su come trarre vantaggio dal connettore v2, consulta la sezione [Activation](#activation).

Per informazioni dettagliate sulla configurazione e sull&#39;utilizzo del connettore SMS legacy, consulta la [documentazione di Campaign Classic](https://experienceleague.adobe.com/it/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

## Connettore SMS v2 {#sms-connector-v2}

Disponibile in GA a partire dalla versione 8.9.1, il connettore v2 abilita le connessioni SMPP in modalità ricetrasmettitore, le connessioni SMPP persistenti e garantisce una migliore compatibilità. È disponibile un account esterno SMS dedicato per tutte le implementazioni SMS che utilizzano il connettore v2.

Il connettore v2 è abilitato per impostazione predefinita per le nuove installazioni. Se hai effettuato l’aggiornamento da una versione precedente utilizzando il connettore legacy, devi contattare il rappresentante Adobe per passare al connettore v2. Consulta la sezione [Activation](#activation).

Per informazioni su come utilizzare il connettore SMS v2 in Campaign v8, consulta la [documentazione SMS](sms.md).

>[!NOTE]
>
>Il connettore v2 è disponibile anche nelle seguenti build con alcune limitazioni:
>* 8.8.1: versione per tutti gli ambienti FDA di Campaign. Non disponibile per le distribuzioni FFDA di Campaign.
>* 8.8.2: versione per tutti i tipi di distribuzione, incluso FFDA. Rilasciato a disponibilità limitata (LA).

## Attivazione {#activation}

### Perché passare al connettore v2 {#why-switch-v2}

Il processo SMS dedicato introduce il supporto per la modalità ricetrasmettitore SMPP, riducendo il conteggio delle connessioni e migliorando l’efficienza delle risorse, supportando al tempo stesso le configurazioni del trasmettitore/ricevitore se necessario. Offre una maggiore stabilità, con un ripristino più rapido dagli errori, connessioni persistenti e nessuna dipendenza dai file locali o dalla comunicazione tra processi. Anche le prestazioni sono migliorate, con latenza inferiore, throughput più elevato e microbatch intelligente per bilanciare velocità e affidabilità. Inoltre, l’isolamento del processo SMS semplifica la risoluzione dei problemi e riduce al minimo l’impatto su più canali. Questi miglioramenti rendono il connettore dedicato una soluzione più solida e scalabile per la consegna di SMS.

### Configurazione {#configuration}

Con Adobe Campaign Managed Cloud Services, la configurazione del server e la migrazione del connettore SMS sono gestite da Adobe. Questa procedura tecnica richiede l&#39;accesso diretto ai file di configurazione del server e alle operazioni del database.

Per attivare e avviare l’utilizzo del connettore SMS v2, devi prima eseguire l’aggiornamento alla versione v8.9.1 o successiva. Contatta il tuo rappresentante Adobe o l’Assistenza clienti Adobe. Pianificheranno ed eseguiranno gli aggiornamenti necessari per l’istanza.
