---
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 39a3412ab2fae2f45768598feffb7e5078c6acac
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 51%

---

# Ultima versione{#latest-release}

Adobe Campaign viene aggiornato regolarmente. La frequenza regolare degli aggiornamenti è volta a far ottenere agli utenti il prodotto migliore e più recente, mantenendo l’ambiente sicuro e migliorando l’esperienza di utilizzo. Adobe consiglia vivamente a tutti i clienti di effettuare l’aggiornamento alla versione più recente.

In qualità di utente di Managed Cloud Services, la tua istanza viene aggiornata da Adobe con ogni nuova versione. Adobe ti contatterà per aggiornare i tuoi ambienti. La console client di Campaign **deve essere aggiornata alla stessa versione** come i server di Campaign. Scopri come aggiornare la console client in questo [pagina](../start/connect.md#upgrade-ac-console).

Inoltre, in qualità di cliente, assicurati di utilizzare le versioni supportate più recenti dei sistemi elencati in [Matrice di compatibilità](compatibility-matrix.md).

## Versione 8.7.1 {#release-8-7-1}

_mercoledì 30 aprile 2024_

>[!AVAILABILITY]
>
>Questa versione è in **Disponibilità limitata** (LA). È limitato ai clienti che eseguono la migrazione **da Adobe Campaign Standard ad Adobe Campaign v8** e non possono essere distribuiti in nessun altro ambiente.
>
>Consulta le seguenti pagine della documentazione: [Transizione di Campaign Standard a Campaign v8](https://experienceleague.adobe.com/en/docs/campaign-web/v8/release-notes/acs-migration) e [Funzionalità per gli utenti di Campaign Standard](https://experienceleague.adobe.com/docs/experience-cloud/campaign/campaign-standard-migration-home.html).

### Nuove funzioni {#new-8-7-1}

* **Modelli di notifiche push potenziate** - È ora possibile inviare notifiche push potenziate tramite Android. La notifica push potenziata è una forma avanzata di notifica mobile che va oltre i semplici messaggi di testo incorporando elementi multimediali come immagini, pulsanti interattivi o altri contenuti rich media. [Ulteriori informazioni](../send/rich-push.md)

* **Marchio** - In qualità di utente Campaign Standard migrato, gli amministratori tecnici possono ora definire uno o più brand per centralizzare i parametri che influiscono sull’identità di un brand. Ciò include il logo del brand, il dominio dell’URL di accesso delle pagine di destinazione o le impostazioni di tracciamento dei messaggi. Puoi creare questi brand e collegarli a messaggi o pagine di destinazione. Questa configurazione viene gestita tramite modelli. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html)

* **API REST** - In qualità di utente Campaign Standard migrato, puoi utilizzare le API Rest per creare integrazioni per Adobe Campaign e creare il tuo ecosistema interfacciando Adobe Campaign con il pannello di tecnologie utilizzato. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html)

* **Reporting dinamico** - In qualità di utente Campaign Standard migrato, puoi accedere al Reporting dinamico che fornisce rapporti completamente personalizzabili e in tempo reale per misurare l’impatto delle attività di marketing. Aggiunge l’accesso ai dati del profilo, consentendo l’analisi demografica per dimensioni di profilo come genere, città ed età, oltre ai dati funzionali delle campagne e-mail come aperture e clic. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html)

<!--
* **New Enhanced security add-on**: To make your network connection more secure and provide improved security for your resources, Adobe Campaign offers a new Enhanced security add-on, which includes two features: Secure CMK integration and Secure VPN tunneling.
-->

### Aggiornamenti della compatibilità {#comp-8-7-1}

I database sono ora supportati come database esterno con Federated Data Access (FDA) di Adobe Campaign. Ulteriori informazioni sull’FDA sono disponibili [in questa pagina](../connect/fda.md)

### Miglioramenti generali {#improvements-8-7-1}

* Diversi schemi sono stati modificati da 32 a 64 bit. Questo vale solo per i clienti che eseguono la migrazione da Campaign Standard. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html).

* Nelle tabelle di Campaign, un nuovo flag consente di gestire le modifiche agli attributi lastModified, created e createdBy-id. Quando il flag è attivato, i valori forniti dagli utenti a questi attributi vengono ignorati. Vengono utilizzati solo l’ora del server e l’ID provenienti dal contesto dell’utente. Quando il flag è disattivato, vengono utilizzati i valori forniti dall&#39;utente per questi attributi. Il flag ignoreTimestampsID si trova in serverConf.xml sotto il nodo &quot;shared&quot;.

### Correzioni {#fixes-8-7-1}

In questa versione sono stati risolti i seguenti problemi: NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575 60250 60192 58596 58314 58004 40054, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-

## Versione 8.6.2 {#release-8-6-2}

_23 febbraio 2024_

### Correzioni {#fixes-8-6-2}

Questa versione risolve il seguente problema:

* È stato risolto un problema di prestazioni che poteva verificarsi sull’istanza mid-sourcing (NEO-72595).

## Versione 8.6.1 {#release-8-6-1}

_14 febbraio 2024_

### Nuove funzioni {#new-8-6-1}

* A partire da questa versione, potrai accedere alla nuova **Interfaccia utente di Campaign Web**, disponibile nell’ambiente Adobe Experience Cloud centrale. Experience Cloud è un insieme integrato di applicazioni, prodotti e servizi per il marketing digitale di Adobe. Grazie alla sua interfaccia intuitiva, puoi accedere rapidamente alle applicazioni cloud, alle funzionalità dei prodotti e ai servizi. Scopri come connetterti ad Adobe Experience Cloud e come accedere all’interfaccia di Adobe Campaign Web [in questa pagina](campaign-ui.md#ac-web-ui).


* Adobe Campaign v8 ora si integra con **Adobe Experience Manager as a Cloud Service** e l’authoring sarà disponibile esclusivamente tramite l’interfaccia utente di Adobe Campaign Web. [Ulteriori informazioni](../connect/ac-aem.md)

* Ora puoi utilizzare la tua **libreria Adobe Experience Manager Assets** insieme alle risorse di Experience Cloud anche se il pacchetto di integrazione con Adobe Experience Cloud è installato nell’istanza di Adobe Campaign. [Ulteriori informazioni](../connect/ac-aem.md#assets-library)

### Miglioramenti generali {#improvements-8-6-1}

* Campaign v8.6 offre una velocità effettiva migliorata per gli **indicatori di tracciamento delle consegne e-mail**. Grazie ai processi ottimizzati, il tracciamento dell’acquisizione e del tempo di elaborazione si riduce e puoi controllare gli indicatori chiave di consegna molto più rapidamente.


### Aggiornamenti del recapito messaggi {#deliverability-8-6-1}

* Entro febbraio 2024, qualsiasi azienda che invia più di 5.000 messaggi e-mail tramite Google o Yahoo! dovrà iniziare a utilizzare una tecnologia di autenticazione nota come Domain-based Message Authentication Reporting and Conformance (DMARC). Assicurati di aver impostato il record DMARC per tutti i sottodomini che utilizzi con Adobe Campaign. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=it){target="_blank"}

* A partire dal 1° giugno 2024, Google e Yahoo! richiederanno ai mittenti di conformarsi all’opzione Annulla iscrizione elenco con un clic. Adobe Campaign ora supporta questa opzione. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=it#one-click-list-unsubscribe){target="_blank"}


### Correzioni {#fixes-8-6-1}

In questa versione sono stati risolti i seguenti problemi:
NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789