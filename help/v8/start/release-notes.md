---
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: e119c415ce363a635f9f0318e3fd70f90f4bde06
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 97%

---

# Versioni più recenti {#latest-release}

Adobe Campaign viene aggiornato regolarmente. La frequenza regolare degli aggiornamenti è volta a far ottenere agli utenti il prodotto migliore e più recente, mantenendo l’ambiente sicuro e migliorando l’esperienza di utilizzo. Adobe consiglia vivamente a tutta la clientela di effettuare l’aggiornamento alla versione più recente. In questa pagina sono elencate le nuove funzionalità, i miglioramenti e le correzioni introdotte con le versioni più recenti di Campaign v8 (console). Per ulteriori informazioni su versioni e aggiornamenti di Campaign, visita [questa pagina](upgrades.md).

In qualità di utente di Managed Cloud Services, la tua istanza viene aggiornata da Adobe con ogni nuova versione. Adobe ti contatterà per aggiornare i tuoi ambienti. La console client di Campaign **deve essere aggiornata alla stessa versione** come i server di Campaign. Scopri come aggiornare la console client in questa [pagina](../start/connect.md#upgrade-ac-console).

Inoltre, in qualità di cliente, assicurati di utilizzare la versione supportata più recente dei sistemi elencati nella [Matrice di compatibilità](compatibility-matrix.md).

## Versione 8.5.3 {#release-8-5-3}

_28 maggio 2024_

### Migrazione alle credenziali OAuth server-to-server {#change-8-5-3}

A partire da questa versione, poiché le credenziali dell’account di servizio (JWT) sono state dichiarate obsolete da Adobe, le integrazioni in uscita di Campaign con le soluzioni e le app Adobe ora si basano sulle credenziali OAuth server-to-server. [Ulteriori informazioni](#change-8-7-1)

### Correzioni {#fixes-8-5-3}

In questa versione sono stati risolti i seguenti problemi:

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-59544, NEO-52542


## Aggiornamenti di maggio {#may-updates}

La seguente modifica è stata rilasciata a maggio ed è ora disponibile per gli utenti di Campaign v8:

* **Nuovo componente aggiuntivo di sicurezza avanzato**: per rendere più sicura la connessione di rete e migliorare la sicurezza delle risorse, Adobe Campaign offre un nuovo componente aggiuntivo di sicurezza avanzato, che include due funzionalità: integrazione CMK sicura e tunneling VPN sicuro. [Ulteriori informazioni](../config/enhanced-security.md)


## Versione 8.7.1 {#release-8-7-1}

_2 maggio 2024_

>[!AVAILABILITY]
>
>Questa versione è in **Disponibilità limitata** (LA). È limitata ai clienti che eseguono la migrazione **da Adobe Campaign Standard ad Adobe Campaign v8** e non possono essere distribuiti in nessun altro ambiente.
>
>In qualità di utente Campaign Standard che passa a Campaign v8, scopri di più su questa transizione nella [Documentazione sull’interfaccia web di Campaign v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### Nuove funzioni {#new-8-7-1}

* **Modelli di notifiche push avanzate**: è ora possibile inviare notifiche push avanzate tramite Android. La notifica push avanzate è una forma avanzata di notifica mobile che va oltre i semplici messaggi di testo incorporando elementi multimediali come immagini, pulsanti interattivi o altri contenuti rich media. [Ulteriori informazioni](../send/rich-push.md).

* **Branding**: in qualità di utente Campaign Standard migrato, gli amministratori tecnici possono ora definire uno o più brand per centralizzare i parametri che ne influiscono l’identità. Ciò include il logo del brand, il dominio dell’URL di accesso delle pagine di destinazione o le impostazioni di tracciamento dei messaggi. Puoi creare questi brand e collegarli a messaggi o pagine di destinazione. Questa configurazione viene gestita tramite modelli. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=it){target="_blank"}

* **API REST**: in qualità di utente migrato a Campaign Standard, puoi utilizzare le API REST per creare integrazioni per Adobe Campaign e un proprio ecosistema interfacciando Adobe Campaign con il pannello di tecnologie che utilizzi. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=it){target="_blank"}

* **Reporting dinamico**: in qualità di utente Campaign Standard migrato, puoi accedere al Reporting dinamico che fornisce rapporti completamente personalizzabili e in tempo reale per misurare l’impatto delle attività di marketing. Permette di accedere ai dati del profilo, abilitando l’analisi demografica per dimensioni di profilo, come genere, città ed età, oltre ai dati funzionali delle campagne e-mail come aperture e clic. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=it){target="_blank"}




### Aggiornamenti della compatibilità {#comp-8-7-1}

* Databricks è ora supportato come database esterno con Federated Data Access (FDA) di Adobe Campaign. Per ulteriori informazioni, consulta [questa pagina](compatibility-matrix.md#FederatedDataAccessFDA).

### Migrazione alle credenziali OAuth server-to-server {#change-8-7-1}

A partire da questa versione, poiché le credenziali dell’account di servizio (JWT) sono state dichiarate obsolete da Adobe, le integrazioni in uscita di Campaign con le soluzioni e le app Adobe ora si basano sulle credenziali OAuth server-to-server. Adobe eseguirà la migrazione da JWT a OAuth per le integrazioni in uscita, ad esempio l’integrazione Campaign-Analytics o l’integrazione dei trigger di Experience Cloud.

Se hai implementato le integrazioni in entrata con Campaign, devi migrare l’account tecnico come descritto in [questa documentazione](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Le credenziali dell’account di servizio (JWT) esistenti continueranno a funzionare fino al **27 gennaio 2025**. Inoltre, Developer Console continuerà a supportare la creazione di nuove credenziali dell’account di servizio (JWT) fino al **3 giugno 2024**. Dopo tale data, non sarà possibile creare o aggiungere nuove credenziali dell’account di servizio (JWT) a un progetto.


### Miglioramenti generali {#improvements-8-7-1}

* Diversi schemi sono stati modificati da 32 a 64 bit. Questo vale solo per i clienti che eseguono la migrazione da Campaign Standard. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=it){target="_blank"}

* Nelle tabelle di Campaign, i seguenti attributi ora vengono compilati per impostazione predefinita dalla data e dall’ora del server: `lastModified` e `created`. Il valore dell’attributo `createdBy-id` ora viene compilato con l’ID di accesso corrente per impostazione predefinita. I valori forniti dagli utenti nelle chiamate API vengono ignorati. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

### Correzioni {#fixes-8-7-1}

In questa versione sono stati risolti i seguenti problemi:
NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054
