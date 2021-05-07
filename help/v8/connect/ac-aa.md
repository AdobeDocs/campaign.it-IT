---
solution: Campaign
product: Adobe Campaign
title: Utilizzare Campaign e Adobe Analytics
description: Scopri come utilizzare Campaign e Adobe Analytics
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 3%

---

# Utilizzare Campaign e Adobe Analytics

## Trigger di Experience Cloud

Puoi utilizzare i trigger di Experience Cloud per collegare i dati tra Adobe Campaign e Adobe Analytics utilizzando la pipeline. La pipeline recupera le azioni o gli attivatori degli utenti dal sito web. Un abbandono del carrello è un esempio di trigger. Gli attivatori vengono elaborati in Adobe Campaign per inviare e-mail in tempo quasi reale.

:speech_balloon: In qualità di utente di Cloud Services gestiti, [contatta Adobe](../start/support.md#support) per implementare i trigger di Experience Cloud con Campaign.

## Connettore dati Adobe Analytics

AGGIORNAMENTO CON LA NUOVA INTEGRAZIONE

Puoi anche configurare i Data Connectors Adobe Analytics per integrare Campaign e Analytics.

Il connettore dati (precedentemente noto come Adobe Genesis) consente ad Adobe Campaign e Adobe Analytics di interagire attraverso il pacchetto **Connettori di Web Analytics** . Questa integrazione condivide i dati da Analytics a Campaign come segmenti correlati al comportamento degli utenti dopo un’e-mail. Al contrario, invia indicatori e attributi delle campagne e-mail consegnate da Adobe Campaign ad Adobe Analytics - Data Connector.

Grazie a queste integrazioni, Adobe Campaign può recuperare i dati sul comportamento dei visitatori per uno o più siti dopo una campagna di marketing e (dopo l’analisi) può eseguire campagne di remarketing per convertirli in acquirenti. Al contrario, gli strumenti di analisi web consentono ad Adobe Campaign di inoltrare indicatori e attributi della campagna alle proprie piattaforme.

I campi di azione per ogni strumento sono i seguenti:

* Adobe Analytics:

   * contrassegna le campagne e-mail avviate con Adobe Campaign
   * salva il comportamento del destinatario, sotto forma di segmenti, sul sito visualizzato dopo aver fatto clic sull’e-mail della campagna. I segmenti sono collegati a prodotti abbandonati (visualizzati ma non aggiunti al carrello o acquistati), acquisti o abbandonamenti del carrello.

* Adobe Campaign:

   * invia gli indicatori e gli attributi della campagna al connettore, che a sua volta li inoltra allo strumento di analisi web
   * recupera e analizza i segmenti
   * attiva una campagna di ricommercializzazione

CONSULTARE https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html?lang=en#technical-workflows-of-web-analytics-processes

:speech_balloon: In qualità di utente di Cloud Services gestiti, [contatta Adobe](../start/support.md#support) per integrare Adobe Analytics Data Connector con Campaign.

