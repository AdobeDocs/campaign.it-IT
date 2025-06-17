---
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 9187ac7fd0d17a6dc28c3b6564913bcd93e45943
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Versioni più recenti {#latest-release}

In questa pagina sono elencate le nuove funzionalità, i miglioramenti e le correzioni introdotte con le **versioni più recenti** di Campaign v8 (console). Ulteriori informazioni sulle versioni e gli aggiornamenti di Campaign sono disponibili in [questa pagina](upgrades.md). Altre versioni sono elencate nella sezione Versioni precedenti di questa documentazione.

>[!BEGINSHADEBOX]

**In questa pagina**

* [Versione 8.6.5](#release-8-6-5)
* [Versione 8.7.4](#release-8-7-4)
* [Versione 8.6.4](#release-8-6-4)

>[!ENDSHADEBOX]

## Versione 8.6.5 {#release-8-6-5}

_25 aprile 2025_

>[!AVAILABILITY]
>
>Questa versione è in **disponibilità limitata** (LA).

### Nuove funzioni {#features-8-6-5}

**Nuovo connettore di invio SMS** - Il connettore di invio SMS è stato modernizzato e migliorato per abilitare le connessioni SMPP in modalità ricetrasmettitore, abilitare le connessioni SMPP permanenti e garantire una migliore compatibilità per gli ambienti in transizione da Adobe Campaign Standard. È ora disponibile un nuovo account esterno SMS per tutte le nuove implementazioni SMS. L’implementazione esistente è ancora supportata, tuttavia si consiglia di passare a questo nuovo connettore moderno ed esteso. [Ulteriori informazioni](../send/sms/sms.md).

### Miglioramenti generali {#improvements-8-6-5}

* Le prestazioni globali dell’applicazione sono state migliorate, nel contesto di una distribuzione Enterprise (FFDA), inclusi l’invio di bozze di consegna e la pulizia del database.

* Per aumentare la sicurezza su tutte le comunicazioni tra applicazioni, mTLS è ora supportato per le chiamate API esterne.

* Mail Transfer Agent (MTA): è stato risolto un elemento secondario MTA orfano bloccato nello stato **[!UICONTROL Start pending]**.

### Correzioni {#fixes-8-6-5}

In questa versione sono stati risolti anche i seguenti problemi:

NEO-67620, NEO-71534, NEO-80245, NEO-81105, NEO-81758, NEO-81908, NEO-82351, NEO-82742, NEO-83044, NEO-83138, NEO-83350, NEO-83729, NEO-83793, NEO-83809, NEO-84038, NEO-84108, NEO-85269, NEO-86121, NEO-86556, NEO-86739

## Versione 8.7.4 {#release-8-7-4}

_10 aprile 2025_

>[!AVAILABILITY]
>
>Questa versione è in **Disponibilità limitata** (LA). È limitata ai clienti che eseguono la migrazione **da Adobe Campaign Standard ad Adobe Campaign v8** e non possono essere distribuiti in nessun altro ambiente.
>
>In qualità di utente Campaign Standard che passa a Campaign v8, scopri di più su questa transizione nella [documentazione sull’interfaccia utente web di Campaign v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuove funzioni {#features-8-7-4}

* **Supporto API REST SMS**: l’API REST per la messaggistica transazionale è ora disponibile per il canale SMS. Quando nel payload sono presenti sia e-mail che telefono cellulare, puoi utilizzare il campo “wishedChannel” per specificare il canale. Se non viene fornito, per impostazione predefinita verrà utilizzata l’e-mail, a meno che wishedChannel non richieda esplicitamente l’SMS.

* **Consegne multilingue**: a partire dalla versione di aprile dell’interfaccia utente di Campaign Web, sarà possibile inviare più consegne e-mail in lingue diverse e accedere ai rapporti dinamici correlati. Questa funzionalità sarà disponibile nell’interfaccia utente di Adobe Campaign Web solo alla fine di aprile e richiederà un aggiornamento del server a Campaign v8.7.4.

### Correzioni {#fixes-8-7-4}

In questa versione sono stati risolti i seguenti problemi:

NEO-80245, NEO-83559

## Versione 8.6.4 {#release-8-6-4}

_15 gennaio 2025_

### Miglioramenti generali {#improvements-8-6-4}

* La stabilità dell’applicazione Campaign è stata migliorata durante l’analisi della consegna nel contesto di una [distribuzione Enterprise (FFDA)](../../v8/architecture/enterprise-deployment.md).
* Questa versione include meccanismi dell’architettura FFDA migliorati e rafforzati, tra cui gestione delle chiavi, staging e replica dei dati.
* Sono stati introdotti nuovi flussi di lavoro tecnici per la [distribuzione Enterprise (FFDA)](../../v8/architecture/enterprise-deployment.md). Questi flussi di lavoro replicano la consegna e i dati correlati centralizzando le richieste di replica parallela sulle tabelle corrispondenti. Il flusso di lavoro inizia con `Replicate nms`. [Ulteriori informazioni](../architecture/replication.md)
* Nelle proprietà del flusso di lavoro è ora disponibile una nuova opzione **Abilita il supervisore watchdog per mantenere il flusso di lavoro in esecuzione permanente**. Quando questa opzione è abilitata, i flussi di lavoro si riavviano automaticamente dopo che si è verificato un errore. Per impostazione predefinita, il riavvio si verifica ogni 30 secondi se il flusso di lavoro presenta ancora un errore. Per modificare questo intervallo, puoi creare una nuova opzione `XtkWorkflow_WatchdogRestartTimerTimeout` e impostare un tipo di dati interi per specificare il nuovo ritardo. Questa opzione deve essere abilitata solo nei flussi di lavoro tecnici. [Ulteriori informazioni](../../automation/workflow/workflow-properties.md#execution)

### Miglioramenti di sicurezza {#security-8-6-4}

La connessione con le soluzioni e le app Adobe tramite l’account esterno di **[!UICONTROL Adobe Experience Cloud]** è stata aggiornata per rafforzare la sicurezza.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Aggiornamenti della compatibilità {#comp-8-6-4}

Sono stati aggiunti i seguenti connettori FDA. Consulta [questa pagina](compatibility-matrix.md#FederatedDataAccessFDA).

* Databricks è ora supportato come database esterno con il Federated Data Access (FDA) di Adobe Campaign.

* È ora disponibile un nuovo connettore Amazon Redshift FDA ODBC. Offre connettività migliorata, manutenzione semplificata e compatibilità avanzata. Questa nuova versione include i seguenti miglioramenti:

   * Il nuovo connettore si basa sull’interfaccia ODBC che si allinea ai connettori FDA più recenti. Questo garantisce un supporto a lungo termine.
   * Inoltre, introduce un nuovo meccanismo di caricamento dei dati utilizzando bucket S3, che migliora in modo significativo le prestazioni.

  È comunque possibile utilizzare il connettore legacy. Se desideri provare quello nuovo, contatta il tuo rappresentante Adobe.

### Correzioni {#fixes-8-6-4}

In questa versione sono stati risolti i seguenti problemi:

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-81127, NEO-81209, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592, NEO-82640, NEO-82665, NEO-82781, NEO-82920, NEO-83081, NEO-83096, NEO-83137, NEO-83143.

