---
title: Note preliminari sulla versione di Campaign v8
description: Versione preliminare di Campaign v8
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: dfc86ebaa2acc0b7777843b2d1d370939b6bfcc2
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 49%

---

# Note preliminari sulla versione {#e-new-release}

Questa pagina descrive i miglioramenti e le correzioni inclusi nella prossima versione di Campaign v8. **Le note preliminari sulla versione riportate di seguito sono soggette a modifiche senza preavviso fino alla data di disponibilità del rilascio**. I collegamenti, le schermate e la documentazione aggiornata sono pubblicati nella [note sulla versione](release-notes.md), alla data di rilascio.

## Versione 8.7.2 {#release-8-7-2}

_mercoledì 30 luglio 2024_


>[!AVAILABILITY]
>
>Questa versione è in **Disponibilità limitata** (LA). È limitata ai clienti che eseguono la migrazione **da Adobe Campaign Standard ad Adobe Campaign v8** e non possono essere distribuiti in nessun altro ambiente.
>
>In qualità di utente Campaign Standard che passa a Campaign v8, scopri di più su questa transizione nella [Documentazione sull’interfaccia web di Campaign v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### Nuove funzioni {#new-8-7-2}

* **Nuovo connettore di invio SMS** - Il connettore di invio SMS è stato modernizzato e migliorato per abilitare le connessioni SMPP in modalità ricetrasmettitore, abilitare le connessioni SMPP permanenti e garantire una migliore compatibilità per gli ambienti in transizione da Adobe Campaign Standard. È ora disponibile un nuovo account SMS esterno per tutte le nuove implementazioni SMS. L’implementazione esistente è ancora supportata, tuttavia si consiglia di passare a questo nuovo connettore moderno ed esteso.

* **Notifica push potenziata (GA)** - È ora possibile inviare notifiche push potenziate. La notifica push avanzate è una forma avanzata di notifica mobile che va oltre i semplici messaggi di testo incorporando elementi multimediali come immagini, pulsanti interattivi o altri contenuti rich media. Con questa versione, è ora disponibile un set di modelli per notifiche push potenziate per le app iOS e Android. [Ulteriori informazioni](../send/rich-push.md).

* **Branding** - Le opzioni di branding sono ora disponibili per tutti i canali, inclusi SMS e Direct mail. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=it){target="_blank"}


### Correzioni {#fixes-8-7-2}

In questa versione sono stati risolti i seguenti problemi:

NEO-76592, NEO-75400, NEO-77406, NEO-77674, NEO-77899, NEO-73989, NEO-76064, NEO-76039, NEO-76040, NEO-76845, NEO-76664, NEO-76682, NEO-76663, NEO-73602, NEO-72915, NEO-78134, NEO-77000, NEO-77002, NEO-76955, NEO-76864, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, NEO, NEO-, NEO-, NEO-, NEO-, NEO-NEO-76926 76495 77168 41058 75581 74647 74585 74586 74831 77319 78607.

## Versione 8.6.3 {#release-8-6-3}

_mercoledì 30 luglio 2024_


### Nuove funzioni {#new-8-6-3}

* **Notifica push potenziata** - È ora possibile inviare notifiche push potenziate. La notifica push avanzate è una forma avanzata di notifica mobile che va oltre i semplici messaggi di testo incorporando elementi multimediali come immagini, pulsanti interattivi o altri contenuti rich media. Con questa versione, è ora disponibile un set di modelli per notifiche push potenziate per le app iOS e Android. [Ulteriori informazioni](../send/rich-push.md).

* A partire da questa versione, poiché le credenziali dell’account di servizio (JWT) sono state dichiarate obsolete da Adobe, le integrazioni in uscita di Campaign con le soluzioni e le app Adobe ora si basano sulle credenziali OAuth server-to-server. [Ulteriori informazioni](release-notes.md#change-8-7-1)


### Miglioramenti generali {#improvements-8-6-3}

* Per aumentare la sicurezza su tutte le comunicazioni tra applicazioni, mTLS è ora supportato per le chiamate API esterne.

### Correzioni {#fixes-8-6-3}

In questa versione sono stati risolti i seguenti problemi:

NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-72504, NEO-70263, NEO-67620, NEO-63197, NEO-58596, NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->