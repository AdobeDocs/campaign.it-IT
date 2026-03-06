---
title: Connettori SMS
description: Scopri i connettori SMS in Adobe Campaign
feature: SMS
role: User, Admin
level: Intermediate
source-git-commit: e349e9f236c3eeb28ffe96bcc5ec72ab64c4c127
workflow-type: tm+mt
source-wordcount: '453'
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