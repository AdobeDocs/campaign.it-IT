---
title: Note sulla versione 2023 di Campaign v8 (console)
description: Elenco delle funzioni e dei miglioramenti introdotti con le versioni v8 di Campaign 2023
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
source-git-commit: 69ef7e81d5fc0f5cf0dc74fa16d970ef89607331
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 77%

---

# Note sulla versione 2024 {#2024-rn}

In questa pagina sono elencate nuove funzionalità, miglioramenti e correzioni introdotti con le versioni di **2024 Campaign v8**.


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

NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, NEO-, NEO, NEO-, NEO-, NEO-, NEO-, NEO-NEO-62406 61580 61199 60786 59544 59198 59059 58637 55197 52542 50488 47789, NEO-
