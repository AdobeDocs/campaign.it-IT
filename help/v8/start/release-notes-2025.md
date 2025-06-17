---
title: Note sulla versione di Campaign v8 (console) 2025
description: Elenco delle funzioni e dei miglioramenti introdotti con le versioni v8 di Campaign 2025
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: 66e4b59915eae595b28076622f7bcfb5b5a0ffa4
workflow-type: ht
source-wordcount: '428'
ht-degree: 100%

---

# Note sulle versioni 2025 {#2025-rn}

In questa pagina sono elencate le nuove funzionalità, i miglioramenti e le correzioni inclusi nelle **versioni di Campaign v8 2025**. [In questa pagina](release-notes.md) sono elencate le versioni più recenti.

>[!BEGINSHADEBOX]

**In questa pagina**

* Campaign v8.7 - [Versione 8.7.2](#release-8-7-2) | [Versione 8.7.3](#release-8-7-3)


>[!ENDSHADEBOX]


## Versione 8.7.3 {#release-8-7-3}

_14 febbraio 2025_

>[!AVAILABILITY]
>
>Questa versione è in **Disponibilità limitata** (LA). È limitata ai clienti che eseguono la migrazione **da Adobe Campaign Standard ad Adobe Campaign v8** e non possono essere distribuiti in nessun altro ambiente.
>
>In qualità di utente Campaign Standard che passa a Campaign v8, scopri di più su questa transizione nella [documentazione sull’interfaccia utente web di Campaign v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuove funzioni {#features-8-7-3}

* **Reporting dinamico per messaggi transazionali**: ora puoi monitorare i messaggi transazionali nell’interfaccia utente del reporting dinamico. Questi rapporti forniscono al marketer la possibilità di visualizzare in tempo reale tutte le metriche e le dimensioni del reporting dei messaggi transazionali, con l’analisi delle consegne inviate tramite un modello. [Ulteriori informazioni](https://experienceleague.adobe.com/it/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}

* **API REST per la messaggistica transazionale**: le API transazionali basate su eventi sono ora disponibili per le e-mail. [Ulteriori informazioni](https://experienceleague.adobe.com/it/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}

### Correzioni {#fixes-8-7-3}

In questa versione sono stati risolti i seguenti problemi:

NEO-79373, NEO-81908, NEO-83081

## Versione 8.7.2 {#release-8-7-2}

_3 settembre 2024_

>[!AVAILABILITY]
>
>Questa versione è in **Disponibilità limitata** (LA). È limitata ai clienti che eseguono la migrazione **da Adobe Campaign Standard ad Adobe Campaign v8** e non possono essere distribuiti in nessun altro ambiente.
>
>In qualità di utente Campaign Standard che passa a Campaign v8, scopri di più su questa transizione nella [documentazione sull’interfaccia utente di Campaign Web v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuove funzioni {#new-8-7-2}

* **Nuovo connettore di invio SMS** - Il connettore di invio SMS è stato modernizzato e migliorato per abilitare le connessioni SMPP in modalità ricetrasmettitore, abilitare le connessioni SMPP permanenti e garantire una migliore compatibilità per gli ambienti in transizione da Adobe Campaign Standard. È ora disponibile un nuovo account esterno SMS per tutte le nuove implementazioni SMS. L’implementazione esistente è ancora supportata, tuttavia si consiglia di passare a questo nuovo connettore moderno ed esteso. [Ulteriori informazioni](../send/sms/sms.md).

* **Notifica push avanzata (GA)**: ora puoi inviare notifiche push avanzate. La notifica push avanzata è una forma avanzata di notifica mobile che va oltre i semplici messaggi di testo incorporando elementi multimediali come immagini, pulsanti interattivi o altri contenuti rich media. Con questa versione, è ora disponibile un set di modelli per notifiche push avanzate per le app iOS e Android. [Ulteriori informazioni](../send/rich-push-android.md).

* **Branding** - Le opzioni di branding sono ora disponibili per tutti i canali, inclusi SMS e Direct mail. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=it){target="_blank"}

### Correzioni {#fixes-8-7-2}

In questa versione sono stati risolti i seguenti problemi:

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328.
