---
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: b280be52621890c9bd840182d3ad0389912568d4
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 78%

---

# Ultima versione{#latest-release}

Adobe Campaign viene aggiornato regolarmente. La frequenza regolare degli aggiornamenti è volta a far ottenere agli utenti il prodotto migliore e più recente, mantenendo l’ambiente sicuro e migliorando l’esperienza di utilizzo. Adobe consiglia vivamente a tutta la clientela di effettuare l’aggiornamento alla versione più recente.

In qualità di utente di Managed Cloud Services, la tua istanza viene aggiornata da Adobe con ogni nuova versione. Adobe ti contatterà per aggiornare i tuoi ambienti. La console client di Campaign **deve essere aggiornata alla stessa versione** come i server di Campaign. Scopri come aggiornare la console client in questa [pagina](../start/connect.md#upgrade-ac-console).

Inoltre, in qualità di cliente, assicurati di utilizzare la versione supportata più recente dei sistemi elencati nella [Matrice di compatibilità](compatibility-matrix.md).

## Versione 8.7.1 {#release-8-7-1}

_2 maggio 2024_

>[!AVAILABILITY]
>
>Questa versione è in **Disponibilità limitata** (LA). È limitata ai clienti che eseguono la migrazione **da Adobe Campaign Standard ad Adobe Campaign v8** e non possono essere distribuiti in nessun altro ambiente.
>
>In qualità di utente Campaign Standard che passa a Campaign v8, scopri di più su questa transizione in [Documentazione sull’interfaccia web di Campaign v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### Nuove funzioni {#new-8-7-1}

* **Modelli di notifiche push avanzate**: è ora possibile inviare notifiche push avanzate tramite Android. La notifica push avanzate è una forma avanzata di notifica mobile che va oltre i semplici messaggi di testo incorporando elementi multimediali come immagini, pulsanti interattivi o altri contenuti rich media. [Ulteriori informazioni](../send/rich-push.md).

* **Branding**: in qualità di utente Campaign Standard migrato, gli amministratori tecnici possono ora definire uno o più brand per centralizzare i parametri che ne influiscono l’identità. Ciò include il logo del brand, il dominio dell’URL di accesso delle pagine di destinazione o le impostazioni di tracciamento dei messaggi. Puoi creare questi brand e collegarli a messaggi o pagine di destinazione. Questa configurazione viene gestita tramite modelli. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=it){target="_blank"}

* **API REST**: in qualità di utente Campaign Standard migrato, puoi utilizzare le API REST per creare integrazioni per Adobe Campaign e il tuo ecosistema interfacciando Adobe Campaign con il pannello di tecnologie utilizzato. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=it){target="_blank"}

* **Reporting dinamico**: in qualità di utente Campaign Standard migrato, puoi accedere al Reporting dinamico che fornisce rapporti completamente personalizzabili e in tempo reale per misurare l’impatto delle attività di marketing. Permette di accedere ai dati del profilo, abilitando l’analisi demografica per dimensioni di profilo, come genere, città ed età, oltre ai dati funzionali delle campagne e-mail come aperture e clic. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=it){target="_blank"}

* **Nuovo componente aggiuntivo Sicurezza avanzata**: per rendere più sicura la connessione di rete e migliorare la sicurezza delle risorse, Adobe Campaign offre un nuovo componente aggiuntivo Sicurezza avanzata, che include due funzionalità: integrazione CMK sicura e tunneling VPN sicuro. [Ulteriori informazioni](../config/enhanced-security.md)


### Aggiornamenti della compatibilità {#comp-8-7-1}

* Databricks è ora supportato come database esterno con Federated Data Access (FDA) di Adobe Campaign. Per ulteriori informazioni, consulta [questa pagina](compatibility-matrix.md#FederatedDataAccessFDA).

* A partire da questa versione, poiché le credenziali dell’account di servizio (JWT) sono state dichiarate obsolete da Adobe, le integrazioni in uscita di Campaign con le soluzioni e le app Adobe ora si basano sulle credenziali server-to-server OAuth. Adobe eseguirà la migrazione da JWT a OAuth per le integrazioni in uscita, ad esempio l’integrazione Campaign-Analytics o l’integrazione Experience Cloud Triggers.

  Se hai implementato le integrazioni in entrata con Campaign, devi migrare l’account tecnico come descritto in [questa documentazione](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Le credenziali dell’account di servizio (JWT) esistenti continueranno a funzionare fino al **27 gennaio 2025**. Inoltre, Developer Console continuerà a supportare la creazione di nuove credenziali dell’account di servizio (JWT) fino al **3 giugno 2024**. Non è possibile creare o aggiungere a un progetto una nuova credenziale dell’account di servizio (JWT) dopo questa data.


### Miglioramenti generali {#improvements-8-7-1}

* Diversi schemi sono stati modificati da 32 a 64 bit. Questo vale solo per i clienti che eseguono la migrazione da Campaign Standard. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=it){target="_blank"}

* Nelle tabelle Campaign, i seguenti attributi ora vengono compilati per impostazione predefinita dalla data e dall’ora del server: `lastModified` e `created`. Il `createdBy-id` Il valore dell&#39;attributo ora viene compilato con l&#39;ID di accesso corrente per impostazione predefinita. I valori forniti dagli utenti nelle chiamate API vengono ignorati. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

### Correzioni {#fixes-8-7-1}

In questa versione sono stati risolti i seguenti problemi:
NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054

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