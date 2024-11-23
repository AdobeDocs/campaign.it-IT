---
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: e0dbeb7402a46f76a26c28dd226bc069d52f2609
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 97%

---

# Versioni più recenti {#latest-release}

In questa pagina sono elencate le nuove funzionalità, i miglioramenti e le correzioni introdotte con le versioni più recenti di Campaign v8 (console). Ulteriori informazioni sulle versioni, gli aggiornamenti e le versioni di Campaign in [questa pagina](upgrades.md).

## Versione 8.7.2 {#release-8-7-2}

_3 settembre 2024_

>[!AVAILABILITY]
>
>Questa versione è in **Disponibilità limitata** (LA). È limitata ai clienti che eseguono la migrazione **da Adobe Campaign Standard ad Adobe Campaign v8** e non possono essere distribuiti in nessun altro ambiente.
>
>In qualità di utente Campaign Standard che passa a Campaign v8, scopri di più su questa transizione nella [Documentazione sull’interfaccia web di Campaign v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuove funzioni {#new-8-7-2}

* **Nuovo connettore di invio SMS** - Il connettore di invio SMS è stato modernizzato e migliorato per abilitare le connessioni SMPP in modalità ricetrasmettitore, abilitare le connessioni SMPP permanenti e garantire una migliore compatibilità per gli ambienti in transizione da Adobe Campaign Standard. È ora disponibile un nuovo account esterno SMS per tutte le nuove implementazioni SMS. L’implementazione esistente è ancora supportata, tuttavia si consiglia di passare a questo nuovo connettore moderno ed esteso. [Ulteriori informazioni](../send/sms/sms.md).

* **Notifica push avanzata (GA)**: ora puoi inviare notifiche push avanzate. La notifica push avanzata è una forma avanzata di notifica mobile che va oltre i semplici messaggi di testo incorporando elementi multimediali come immagini, pulsanti interattivi o altri contenuti rich media. Con questa versione, è ora disponibile un set di modelli per notifiche push avanzate per le app iOS e Android. [Ulteriori informazioni](../send/rich-push-android.md).

* **Branding** - Le opzioni di branding sono ora disponibili per tutti i canali, inclusi SMS e Direct mail. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=it){target="_blank"}


### Correzioni {#fixes-8-7-2}

In questa versione sono stati risolti i seguenti problemi:

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328.


## Versione 8.6.3 {#release-8-6-3}

_30 luglio 2024_

### Nuove funzioni {#new-8-6-3}

* **Notifica push avanzata**: ora puoi inviare notifiche push avanzate. La notifica push avanzata è una forma avanzata di notifica mobile che va oltre i semplici messaggi di testo incorporando elementi multimediali come immagini, pulsanti interattivi o altri contenuti rich media. Con questa versione, è ora disponibile un set di modelli per notifiche push avanzate per le app iOS e Android. [Ulteriori informazioni](../send/rich-push-android.md).

* A partire da questa versione, poiché le credenziali dell’account di servizio (JWT) sono state dichiarate obsolete da Adobe, le integrazioni in uscita di Campaign con le soluzioni e le app Adobe ora si basano sulle credenziali OAuth server-to-server. [Ulteriori informazioni](release-notes-2024.md#change-8-7-1)

### Miglioramenti generali {#improvements-8-6-3}

* Per aumentare la sicurezza su tutte le comunicazioni tra applicazioni, mTLS è ora supportato per le chiamate API esterne.

### Correzioni {#fixes-8-6-3}

In questa versione sono stati risolti i seguenti problemi:

NEO-79328, NEO-78843, NEO-77795, NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-72504, NEO-70263, NEO-67620, NEO-63197, NEO-58596, NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->
