---
title: Note preliminari sulla versione di Campaign v8
description: Versione preliminare di Campaign v8
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 68%

---

# Note preliminari sulla versione {#e-new-release}

Questa pagina descrive i miglioramenti e le correzioni inclusi nella prossima versione di Campaign v8. Questo contenuto è soggetto a modifiche senza preavviso fino alla data di rilascio. Le note ufficiali sulla versione sono disponibili in questa [pagina](../start/release-notes.md).

## Versione 8.6.1 {#release-8-6-1}

_14 febbraio 2024_


### Nuove funzioni {#new-8-6-1}

* A partire da questa versione, potrai accedere alla nuova **Interfaccia utente di Campaign Web**, disponibile nell’ambiente Adobe Experience Cloud centrale. Experience Cloud è un insieme integrato di applicazioni, prodotti e servizi per il marketing digitale di Adobe. Grazie alla sua interfaccia intuitiva, puoi accedere rapidamente alle applicazioni cloud, alle funzionalità dei prodotti e ai servizi. Scopri come connetterti ad Adobe Experience Cloud e come accedere all’interfaccia di Adobe Campaign Web [in questa pagina](campaign-ui.md#ac-web-ui).

* La versione a 32 bit della console client è ora obsoleta. A partire dalla versione 8.6, la console client sarà disponibile solo a 64 bit. L’aggiornamento alla versione a 64 bit della console client è semplice. Per ulteriori informazioni su come aggiornare il sistema operativo, fare riferimento a [nota tecnica](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=it){target="_blank"}.


### Miglioramenti generali {#improvements-8-6-1}

* Campaign v8.6 offre una velocità effettiva migliorata per gli **indicatori di tracciamento delle consegne e-mail**. Grazie ai processi ottimizzati, il tracciamento dell’acquisizione e del tempo di elaborazione si riduce e puoi controllare gli indicatori chiave di consegna molto più rapidamente.

* Ora puoi collegare la tua istanza di Campaign v8 al database esterno della tua Azure synapse. Questa connessione viene gestita tramite un nuovo account esterno.

* Adobe Campaign v8 ora si integra con **Adobe Experience Manager as a Cloud Service**, con possibilità di creare contenuti esclusivamente tramite l’interfaccia utente web di Adobe Campaign.

* Ora puoi utilizzare il tuo **Libreria Adobe Experience Manager Assets** insieme alle risorse di Experience Cloud anche se **Integrazione con Adobe Experience Cloud** è installato nell’istanza di Adobe Campaign.

* Non è più possibile creare operatori dalla console client. Ora devi utilizzare l’Admin Console. [Ulteriori informazioni](../start/gs-permissions.md).

* Diversi strumenti di terze parti sono stati aggiornati per ottimizzare la sicurezza.

### Aggiornamenti del recapito messaggi {#deliverability-8-6-1}

* Entro febbraio 2024, qualsiasi azienda che invia più di 5.000 messaggi e-mail tramite Google o Yahoo! dovrà iniziare a utilizzare una tecnologia di autenticazione nota come Domain-based Message Authentication Reporting and Conformance (DMARC). Assicurati di aver impostato il record DMARC per tutti i sottodomini che utilizzi con Adobe Campaign. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=it){target="_blank"}

* A partire dal 1° giugno 2024, Google e Yahoo! richiederanno ai mittenti di conformarsi all’opzione Annulla iscrizione elenco con un clic. Adobe Campaign ora supporta questa opzione. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=it#one-click-list-unsubscribe){target="_blank"}


### Correzioni {#fixes-8-6-1}

In questa versione sono stati risolti i seguenti problemi:
NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789