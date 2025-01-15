---
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: d4b172bc6b874d542dc9f2725e3bc35679fc7635
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 28%

---

# Versioni più recenti {#latest-release}

In questa pagina sono elencate le nuove funzionalità, i miglioramenti e le correzioni introdotte con le versioni più recenti di Campaign v8 (console). Per ulteriori informazioni sulle versioni e gli aggiornamenti di Campaign, visita [questa pagina](upgrades.md).

## Versione 8.6.4 {#release-8-6-4}

_15 gennaio 2025_


### Miglioramenti generali {#improvements-8-6-4}

* La stabilità dell&#39;applicazione Campaign è stata migliorata durante l&#39;analisi della consegna nel contesto di una distribuzione [Enterprise (FFDA)](../../v8/architecture/enterprise-deployment.md).
* Questa versione include meccanismi dell’architettura FFDA migliorati e rafforzati, tra cui gestione delle chiavi, staging e replica dei dati.
* Sono stati introdotti nuovi flussi di lavoro tecnici per la distribuzione [Enterprise (FFDA)](../../v8/architecture/enterprise-deployment.md). Questi flussi di lavoro replicano la consegna e i dati correlati centralizzando le richieste di replica parallela sulle tabelle corrispondenti. Il flusso di lavoro inizia con `Replicate nms`.
* Nelle proprietà del flusso di lavoro è ora disponibile una nuova opzione **Abilita il supervisore watchdog per mantenere il flusso di lavoro in esecuzione in modo permanente**. Quando questa opzione è abilitata, i flussi di lavoro si riavviano automaticamente dopo un errore. Per impostazione predefinita, il riavvio avviene ogni 30 secondi. Per modificare questo intervallo, è possibile creare una nuova opzione `XtkWorkflow_WatchdogTimerTimeout` e impostare un tipo di dati Integer per specificare il nuovo ritardo. Questa opzione deve essere abilitata solo nei flussi di lavoro tecnici.

### Miglioramenti di sicurezza {#security-8-6-4}

La connessione con le soluzioni e le app Adobe tramite l&#39;account esterno **[!UICONTROL Adobe Experience Cloud]** è stata aggiornata per rafforzare la sicurezza.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Aggiornamenti della compatibilità {#comp-8-6-4}

Databricks è ora supportato come database esterno con Federated Data Access (FDA) di Adobe Campaign. Per ulteriori informazioni, consulta [questa pagina](compatibility-matrix.md#FederatedDataAccessFDA).

### Correzioni {#fixes-8-6-4}

In questa versione sono stati risolti i seguenti problemi:

NEO-77452, NEO-81127, NEO-81209, NEO-80243, NEO-80314, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-83096, NEO-83081.