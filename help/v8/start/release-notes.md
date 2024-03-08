---
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 3a63539bc6bb20fa79bdac76dd60efe7b232458b
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 16%

---

# Ultima versione{#latest-release}

Adobe Campaign viene aggiornato regolarmente. La frequenza regolare degli aggiornamenti è volta a far ottenere agli utenti il meglio e più recente, mantenendo l’ambiente sicuro e migliorando l’esperienza di utilizzo del prodotto. Adobe consiglia vivamente a tutti i clienti di effettuare l’aggiornamento alla versione più recente. Ulteriori informazioni sulle versioni e sui consigli di Campaign [in questa pagina](upgrades.md).

In qualità di utente di Managed Cloud Service, l’istanza viene aggiornata da Adobe con ogni nuova versione. Adobe ti contatterà per aggiornare i tuoi ambienti. Console client di Campaign **deve essere aggiornato alla stessa versione** come server di Campaign. Scopri come aggiornare la console client [in questa pagina](../start/connect.md#upgrade-ac-console).

Inoltre, in qualità di cliente, assicurati di utilizzare la versione supportata più recente dei sistemi elencati in [Matrice di compatibilità](compatibility-matrix.md).


## Versione 8.6.2 {#release-8-6-2}

_23 febbraio 2024_

### Correzioni {#fixes-8-6-2}

Questa versione risolve il seguente problema:

* È stato risolto un problema di prestazioni che poteva verificarsi sull’istanza di mid-sourcing (NEO-72595).

## Versione 8.6.1 {#release-8-6-1}

_14 febbraio 2024_

### Nuove funzioni {#new-8-6-1}

* A partire da questa versione, potrai accedere alla nuova **Interfaccia utente di Campaign Web**, disponibile nell’ambiente Adobe Experience Cloud centrale. Experience Cloud è un insieme integrato di applicazioni, prodotti e servizi per il marketing digitale di Adobe. Grazie alla sua interfaccia intuitiva, puoi accedere rapidamente alle applicazioni cloud, alle funzionalità dei prodotti e ai servizi. Scopri come connettersi a Adobe Experience Cloud e accedere all’interfaccia web di Adobe Campaign [in questa pagina](campaign-ui.md#ac-web-ui).


* Adobe Campaign v8 ora si integra con **Adobe Experience Manager as a Cloud Service**, con possibilità di creare contenuti esclusivamente tramite l’interfaccia utente web di Adobe Campaign. [Ulteriori informazioni](../connect/ac-aem.md)

* Ora puoi utilizzare il tuo **Libreria Adobe Experience Manager Assets** insieme alle risorse di Experience Cloud anche se il pacchetto Integrazione con Adobe Experience Cloud è installato nell’istanza di Adobe Campaign. [Ulteriori informazioni](../connect/ac-aem.md#assets-library)

### Miglioramenti generali {#improvements-8-6-1}

* Campaign v8.6 offre una velocità effettiva migliorata per **indicatori di tracciamento delle consegne e-mail**. Con i nostri processi ottimizzati, il tracciamento dell’acquisizione e del tempo di elaborazione si riduce e puoi controllare gli indicatori chiave di consegna molto più rapidamente.


### Aggiornamenti del recapito messaggi {#deliverability-8-6-1}

* Entro febbraio 2024, qualsiasi azienda che invii più di 5.000 messaggi e-mail tramite Google o Yahoo! dovrà iniziare a utilizzare una tecnologia di autenticazione nota come Domain-based Message Authentication Reporting and Conformance (DMARC). Assicurati di aver impostato il record DMARC per tutti i sottodomini che utilizzi con Adobe Campaign. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=it){target="_blank"}

* A partire dal 1° giugno 2024, Google e Yahoo! richiederà ai mittenti di conformarsi all’opzione One-Click List-Unsubscribe. Adobe Campaign ora supporta questa opzione. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#one-click-list-unsubscribe){target="_blank"}


### Correzioni {#fixes-8-6-1}

In questa versione sono stati risolti i seguenti problemi: NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455 62406 61580 61199 60786 59544 59198 59059 58637 55197 52542 50488 47789, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, O-, NEO-, NEO-, NEO-