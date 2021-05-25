---
solution: Campaign v8
product: Adobe Campaign
title: Utilizzare Campaign e Adobe Analytics
description: Scopri come utilizzare Campaign e Adobe Analytics
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: 556cd7727c7c2bf0158d59d71ae0131b4c1013ee
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# Utilizzare Campaign e Adobe Analytics


## Connettore Adobe Analytics

Puoi configurare i connettori Adobe Analytics per integrare Campaign e Analytics.

Il connettore Adobe Analytics consente ad Adobe Campaign e Adobe Analytics di interagire attraverso il componente aggiuntivo **Connettori per web Analytics**. Questa integrazione condivide i dati da Analytics a Campaign come segmenti correlati al comportamento degli utenti dopo un’e-mail. Al contrario, invia indicatori e attributi delle campagne e-mail consegnate da Adobe Campaign ad Adobe Analytics - Data Connector.

Utilizzando il connettore Adobe Analytics, Adobe Campaign ha un modo di misurare il pubblico Internet (Web Analytics). Grazie a queste integrazioni, Adobe Campaign può recuperare i dati sul comportamento dei visitatori per uno o più siti dopo una campagna di marketing e (dopo l’analisi) può eseguire campagne di remarketing per convertirli in acquirenti. Al contrario, gli strumenti di analisi web consentono ad Adobe Campaign di inoltrare indicatori e attributi della campagna alle proprie piattaforme.

I campi di azione per ogni strumento sono i seguenti:

* **Adobe Analytics**

   * contrassegna le campagne e-mail avviate con Adobe Campaign
   * salva il comportamento del destinatario, sotto forma di segmenti, sul sito visualizzato dopo aver fatto clic sull’e-mail della campagna. I segmenti sono collegati a prodotti abbandonati (visualizzati ma non aggiunti al carrello o acquistati), acquisti o abbandonamenti del carrello.

* **Adobe Campaign**

   * invia gli indicatori e gli attributi della campagna al connettore, che a sua volta li inoltra allo strumento di analisi web
   * recupera e analizza i segmenti
   * attiva una campagna di ricommercializzazione

Ulteriori informazioni su Adobe Campaign e Adobe Analytics su [questa pagina](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html)

:speech_balloon:  In qualità di utente di Cloud Services gestiti, [contatta Adobe](../start/campaign-faq.md#support) per integrare Adobe Analytics Data Connector con Campaign.


## Trigger di Experience Cloud

Puoi utilizzare i trigger di Experience Cloud per collegare i dati tra Adobe Campaign e Adobe Analytics utilizzando la pipeline. La pipeline recupera le azioni o gli attivatori dell’utente dal sito web. Un abbandono del carrello è un esempio di trigger. Gli attivatori vengono elaborati in Adobe Campaign per inviare e-mail in tempo quasi reale.

Ulteriori informazioni su Adobe Campaign e Triggers di Experience Cloud su [questa pagina](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en).

:speech_balloon:  In qualità di utente di Cloud Services gestiti, [contatta Adobe](../start/campaign-faq.md#support) per implementare i trigger di Experience Cloud con Campaign.
