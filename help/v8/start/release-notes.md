---
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 82622a4517356eaba1f7eba23d4b3050d8ca37c9
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 25%

---

# Versioni più recenti {#latest-release}

In questa pagina sono elencate nuove funzionalità, miglioramenti e correzioni introdotti con Campaign v8 (console) **ultime versioni**. Ulteriori informazioni sulle versioni, gli aggiornamenti e le versioni di Campaign in [questa pagina](upgrades.md). Altre versioni sono elencate nella sezione Versioni precedenti di questa documentazione.

>[!BEGINSHADEBOX]

**In questa pagina**

* Campaign v8.6 - [Versione 8.6.4](#release-8-6-4)
* Campaign v8.7 - [Versione 8.7.3](#release-8-7-3)

>[!ENDSHADEBOX]


## Versione 8.7.3 {#release-8-7-3}

_5 febbraio 2025_

>[!AVAILABILITY]
>
>Questa versione è in **Disponibilità limitata** (LA). È limitata ai clienti che eseguono la migrazione **da Adobe Campaign Standard ad Adobe Campaign v8** e non possono essere distribuiti in nessun altro ambiente.
>
>In qualità di utente Campaign Standard che passa a Campaign v8, scopri di più su questa transizione nella [Documentazione sull’interfaccia web di Campaign v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuove funzioni {#features-8-7-3}

* **Reporting dinamico per messaggi transazionali** - È ora possibile monitorare i messaggi transazionali nell&#39;interfaccia utente di Reporting dinamico. Questi rapporti forniscono all’addetto marketing la possibilità di visualizzare in tempo reale tutte le metriche e le dimensioni di reporting dei messaggi transazionali, con l’analisi delle consegne inviate tramite un modello. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}

* **API REST per la messaggistica transazionale** - Le API transazionali basate su eventi sono ora disponibili per le e-mail. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}

### Correzioni {#fixes-8-7-3}

In questa versione sono stati risolti i seguenti problemi:

NEO-79373, NEO-81908, NEO-83081.


## Versione 8.6.4 {#release-8-6-4}

_15 gennaio 2025_

### Miglioramenti generali {#improvements-8-6-4}

* La stabilità dell&#39;applicazione Campaign è stata migliorata durante l&#39;analisi della consegna nel contesto di una distribuzione [Enterprise (FFDA)](../../v8/architecture/enterprise-deployment.md).
* Questa versione include meccanismi dell’architettura FFDA migliorati e rafforzati, tra cui gestione delle chiavi, staging e replica dei dati.
* Sono stati introdotti nuovi flussi di lavoro tecnici per la distribuzione [Enterprise (FFDA)](../../v8/architecture/enterprise-deployment.md). Questi flussi di lavoro replicano la consegna e i dati correlati centralizzando le richieste di replica parallela sulle tabelle corrispondenti. Il flusso di lavoro inizia con `Replicate nms`. [Ulteriori informazioni](../architecture/replication.md)
* Nelle proprietà del flusso di lavoro è ora disponibile una nuova opzione **Abilita il supervisore watchdog per mantenere il flusso di lavoro in esecuzione in modo permanente**. Quando questa opzione è abilitata, i flussi di lavoro si riavviano automaticamente dopo un errore. Per impostazione predefinita, il riavvio si verifica ogni 30 secondi se il flusso di lavoro presenta ancora un errore. Per modificare questo intervallo, è possibile creare una nuova opzione `XtkWorkflow_WatchdogTimerTimeout` e impostare un tipo di dati Integer per specificare il nuovo ritardo. Questa opzione deve essere abilitata solo nei flussi di lavoro tecnici. [Ulteriori informazioni](../../automation/workflow/workflow-properties.md#execution)

### Miglioramenti di sicurezza {#security-8-6-4}

La connessione con le soluzioni e le app Adobe tramite l&#39;account esterno **[!UICONTROL Adobe Experience Cloud]** è stata aggiornata per rafforzare la sicurezza.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Aggiornamenti della compatibilità {#comp-8-6-4}

Databricks è ora supportato come database esterno con Federated Data Access (FDA) di Adobe Campaign. Per ulteriori informazioni, consulta [questa pagina](compatibility-matrix.md#FederatedDataAccessFDA).

### Correzioni {#fixes-8-6-4}

In questa versione sono stati risolti i seguenti problemi:

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-81127, NEO-81209, NEO-81223, NEO-81287, NEO-81290 81312 81512 81520 81566 81704 81908 82195 82591 82592 82640 82665 82781 82920 83081 83096 83137 83143, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, NEO, NEO-, NEO-, NEO-, NEO-, NEO-NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-.

