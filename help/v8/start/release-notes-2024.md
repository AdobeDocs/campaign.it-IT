---
title: Note sulla versione 2024 di Campaign v8 (console)
description: Elenco delle funzioni e dei miglioramenti introdotti con le versioni v8 di Campaign 2024
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
source-git-commit: 57b18835b87be2a201ce23f5b6053266d13b9cb8
workflow-type: tm+mt
source-wordcount: '1308'
ht-degree: 77%

---

# Note sulla versione 2024 {#2024-rn}

In questa pagina sono elencate nuove funzionalità, miglioramenti e correzioni introdotti con le versioni di **2024 Campaign v8**.

>[!BEGINSHADEBOX]

**In questa pagina**

* Campaign v8.7 - [Versione 8.7.1](#release-8-7-1)
* Campaign v8.6 - [Versione 8.6.1](#release-8-6-1) | [Versione 8.6.2](#release-8-6-2) | [Versione 8.6.3](#release-8-6-3)
* Campaign v8.5 - [Versione 8.5.3](#release-8-5-3)

>[!ENDSHADEBOX]



## Versione 8.7.1 {#release-8-7-1}

_2 maggio 2024_

>[!AVAILABILITY]
>
>Questa versione è in **Disponibilità limitata** (LA). È limitata ai clienti che eseguono la migrazione **da Adobe Campaign Standard ad Adobe Campaign v8** e non possono essere distribuiti in nessun altro ambiente.
>
>In qualità di utente di Campaign Standard che passa a Campaign v8, scopri di più su questa transizione nella [documentazione dell&#39;interfaccia utente web di Campaign v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuove funzioni {#new-8-7-1}

* **Modelli di notifiche push avanzate**: è ora possibile inviare notifiche push avanzate tramite Android. La notifica push avanzata è una forma avanzata di notifica mobile che va oltre i semplici messaggi di testo incorporando elementi multimediali come immagini, pulsanti interattivi o altri contenuti rich media. [Ulteriori informazioni](../send/rich-push-ios.md).

* **Branding**: in qualità di utente Campaign Standard migrato, gli amministratori tecnici possono ora definire uno o più brand per centralizzare i parametri che ne influiscono l’identità. Ciò include il logo del brand, il dominio dell’URL di accesso delle pagine di destinazione o le impostazioni di tracciamento dei messaggi. Puoi creare questi brand e collegarli a messaggi o pagine di destinazione. Questa configurazione viene gestita tramite modelli. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=it){target="_blank"}

* **API REST**: in qualità di utente Campaign Standard migrato, puoi utilizzare le API REST per creare integrazioni per Adobe Campaign e il tuo ecosistema interfacciando Adobe Campaign con il pannello di tecnologie utilizzato. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=it){target="_blank"}

* **Reporting dinamico**: in qualità di utente Campaign Standard migrato, puoi accedere al Reporting dinamico che fornisce rapporti completamente personalizzabili e in tempo reale per misurare l’impatto delle attività di marketing. Permette di accedere ai dati del profilo, abilitando l’analisi demografica per dimensioni di profilo, come genere, città ed età, oltre ai dati funzionali delle campagne e-mail come aperture e clic. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=it){target="_blank"}

### Aggiornamenti della compatibilità {#comp-8-7-1}

Sono stati aggiunti i seguenti connettori FDA. Fai riferimento a questa [pagina](compatibility-matrix.md#FederatedDataAccessFDA).

* I database sono ora supportati come database esterno con Federated Data Access (FDA) di Adobe Campaign.

* È ora disponibile un nuovo connettore ODBC Amazon Redshift FDA. Offre connettività migliorata, manutenzione semplificata e compatibilità migliorata. Questa nuova versione include i seguenti miglioramenti:

   * Il nuovo connettore si basa sull&#39;interfaccia ODBC che si allinea ai nostri connettori FDA più recenti. Questo garantisce un supporto a lungo termine.
   * Inoltre, introduce un nuovo meccanismo di caricamento dei dati utilizzando bucket s3, che migliora in modo significativo le prestazioni.

  È comunque possibile utilizzare il connettore legacy. Se vuoi provare il nuovo, contatta il tuo rappresentante Adobe.

### Migrazione alle credenziali OAuth server-to-server {#change-8-7-1}

A partire da questa versione, poiché le credenziali dell’account di servizio (JWT) sono state dichiarate obsolete da Adobe, le integrazioni in uscita di Campaign con le soluzioni e le app Adobe ora si basano sulle credenziali OAuth server-to-server. Adobe eseguirà la migrazione da JWT a OAuth per le integrazioni in uscita, ad esempio l’integrazione Campaign-Analytics o l’integrazione dei trigger di Experience Cloud.

Se hai implementato integrazioni in entrata con Campaign, devi migrare l&#39;account tecnico come descritto in [questa documentazione](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Le credenziali dell’account di servizio (JWT) esistenti continueranno a funzionare fino al **martedì 30 giugno 2025**.

### Miglioramenti generali {#improvements-8-7-1}

* Diversi schemi sono stati modificati da 32 a 64 bit. Questo vale solo per i clienti che eseguono la migrazione da Campaign Standard. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=it){target="_blank"}

* Nelle tabelle di Campaign, i seguenti attributi ora vengono compilati per impostazione predefinita dalla data e dall’ora del server: `lastModified` e `created`. Il valore dell’attributo `createdBy-id` ora viene compilato con l’ID di accesso corrente per impostazione predefinita. I valori forniti dagli utenti nelle chiamate API vengono ignorati. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

* Per aumentare la sicurezza su tutte le comunicazioni tra applicazioni, mTLS è ora supportato per le chiamate API esterne.

### Correzioni {#fixes-8-7-1}

In questa versione sono stati risolti i seguenti problemi:

NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054



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


## Aggiornamenti di maggio 2024 {#may-updates}

La seguente modifica è stata rilasciata a maggio ed è ora disponibile per gli utenti di Campaign v8:

* **Nuovo componente aggiuntivo di sicurezza avanzato**: per rendere più sicura la connessione di rete e migliorare la sicurezza delle risorse, Adobe Campaign offre un nuovo componente aggiuntivo di sicurezza avanzato, che include due funzionalità: integrazione CMK sicura e tunneling VPN sicuro. [Ulteriori informazioni](../config/enhanced-security.md)

## Versione 8.6.2 {#release-8-6-2}

_23 febbraio 2024_

### Correzioni {#fixes-8-6-2}

Questa versione risolve il seguente problema:

* È stato risolto un problema di prestazioni che poteva verificarsi sull’istanza mid-sourcing (NEO-72595).

## Versione 8.6.1 {#release-8-6-1}

_14 febbraio 2024_

### Nuove funzioni {#new-8-6-1}

* A partire da questa versione, potrai accedere alla nuova **Interfaccia utente di Campaign Web**, disponibile nell’ambiente Adobe Experience Cloud centrale. Experience Cloud è un insieme integrato di applicazioni, prodotti e servizi per il marketing digitale di Adobe. Grazie alla sua interfaccia intuitiva, puoi accedere rapidamente alle applicazioni cloud, alle funzionalità dei prodotti e ai servizi. Scopri come connetterti ad Adobe Experience Cloud e come accedere all’interfaccia di Adobe Campaign Web [in questa pagina](campaign-ui.md#ac-web-ui).

  >[!AVAILABILITY]
  >
  >L’interfaccia utente di Campaign Web è disponibile solo per gli utenti che si connettono a Adobe Campaign con il proprio Adobe ID. Ulteriori informazioni su [Adobe Identity Management System (IMS)](https://helpx.adobe.com/it/enterprise/using/identity.html){target="_blank"}.
  >

* Adobe Campaign v8 ora si integra con **Adobe Experience Manager as a Cloud Service** e l’authoring sarà disponibile esclusivamente tramite l’interfaccia utente di Adobe Campaign Web. [Ulteriori informazioni](../connect/ac-aem.md)

* Ora puoi utilizzare la tua **libreria Adobe Experience Manager Assets** insieme alle risorse di Experience Cloud anche se il pacchetto di integrazione con Adobe Experience Cloud è installato nell’istanza di Adobe Campaign. [Ulteriori informazioni](../connect/ac-aem.md#assets-library)

### Miglioramenti generali {#improvements-8-6-1}

* Campaign v8.6 offre una velocità effettiva migliorata per gli **indicatori di tracciamento delle consegne e-mail**. Grazie ai processi ottimizzati, il tracciamento dell’acquisizione e del tempo di elaborazione si riduce e puoi controllare gli indicatori chiave di consegna molto più rapidamente.


### Aggiornamenti del recapito messaggi {#deliverability-8-6-1}

* Entro febbraio 2024, qualsiasi azienda che invia più di 5.000 messaggi e-mail tramite Google o Yahoo! dovrà iniziare a utilizzare una tecnologia di autenticazione nota come Domain-based Message Authentication Reporting and Conformance (DMARC). Assicurati di aver impostato il record DMARC per tutti i sottodomini che utilizzi con Adobe Campaign. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=it){target="_blank"}

* A partire dal 1° giugno 2024, Google e Yahoo! richiederanno ai mittenti di conformarsi all’opzione Annulla iscrizione elenco con un clic. Adobe Campaign ora supporta questa opzione. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=it#list-unsubscribe){target="_blank"}


### Correzioni {#fixes-8-6-1}

In questa versione sono stati risolti i seguenti problemi:

NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, NEO, NEO-, NEO-, NEO-, NEO-, NEO-NEO-62406 61580 61199 60786 59544 59198 59059 58637 55197 52542 50488 47789, NEO-



## Versione 8.5.3 {#release-8-5-3}

_28 maggio 2024_

### Migrazione alle credenziali OAuth server-to-server {#change-8-5-3}

A partire da questa versione, poiché le credenziali dell’account di servizio (JWT) sono state dichiarate obsolete da Adobe, le integrazioni in uscita di Campaign con le soluzioni e le app Adobe ora si basano sulle credenziali OAuth server-to-server. [Ulteriori informazioni](#change-8-7-1)

### Correzioni {#fixes-8-5-3}

In questa versione sono stati risolti i seguenti problemi:

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-59544, NEO-52542