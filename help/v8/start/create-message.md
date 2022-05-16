---
title: Introduzione ai messaggi
description: Introduzione ai messaggi
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 100%

---

# Introduzione ai messaggi{#gs-ac-audiences}

Con Adobe Campaign, puoi inviare campagne cross-channel tra cui e-mail, SMS, notifiche push e direct mail; inoltre, puoi misurarne l’efficacia utilizzando diversi rapporti dedicati. Questi messaggi sono progettati e inviati tramite consegna e possono essere personalizzati per ogni destinatario.

Le funzionalità di base includono il targeting, la definizione e la personalizzazione dei messaggi, l’esecuzione delle comunicazioni e i relativi rapporti operativi. Il punto di accesso funzionale principale è l’assistente alla consegna. Permette di sfruttare diverse funzionalità incluse in Adobe Campaign.

Per informazioni sui passaggi principali per creare una consegna, consulta la [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=it).

Adobe Campaign v8 è dotato dei canali di consegna seguenti:

* **Canale e-mail**: le consegne e-mail ti consentono di inviare e-mail personalizzate alla popolazione target. Per ulteriori informazioni, consulta [questa pagina](../send/email.md).

* **Canale direct mailing**: le consegne tramite direct mailing ti consentono di generare un file di estrazione che contiene dati sulla popolazione target.  Per ulteriori informazioni, consulta [questa pagina](../send/direct-mail.md)

* **Canale mobile**: le consegne sui canali mobili ti consentono di inviare SMS personalizzati alla popolazione target.  Per ulteriori informazioni, consulta [questa pagina](../send/sms.md)

* **Canale dell’app mobile**: le consegne tramite app mobile ti consentono di inviare notifiche ai sistemi iOS e Android.  Per ulteriori informazioni, consulta [questa pagina](../send/push.md)

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## Scegli come inviare i messaggi

Dopo aver creato il messaggio e averne progettato e testato il relativo contenuto, puoi scegliere come inviarlo. Campaign offre una serie di funzionalità per:

* Inviare messaggi manualmente al target principale

   ![](assets/send-email.png)

   ![](../assets/do-not-localize/book.png) Scopri come inviare messaggi nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html?lang=it){target=&quot;_blank&quot;}.

* Inviare messaggi associati a una [campagna di marketing](campaigns.md)

   ![](assets/deliveries-in-a-campaign.png)

   ![](../assets/do-not-localize/book.png) Scopri come inviare messaggi nel contesto di una campagna nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=it){target=&quot;_blank&quot;}.

* Inviare messaggi tramite un [flusso di lavoro](../config/workflows.md)

   ![](assets/send-in-a-wf.png)

   ![](../assets/do-not-localize/book.png) Scopri come automatizzare le consegne e-mail nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html?lang=it){target=&quot;_blank&quot;}.

* [Attivare i messaggi](../send/transactional.md) da un evento
   ![](../assets/do-not-localize/book.png) [Caso d’uso: scopri come inviare un’e-mail transazionale con un allegato](https://experienceleague.adobe.com/docs/campaign-classic/using//transactional-messaging/transactional-email-with-attachments.html?lang=it){target=&quot;_blank&quot;}

* Pianificare i messaggi

   ![](assets/schedule-send.png)

   ![](../assets/do-not-localize/book.png) [Caso d’uso: scopri come pianificare e inviare un’e-mail di compleanno](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=it){target=&quot;_blank&quot;}


## Aggiungi personalizzazione

I messaggi consegnati da Adobe Campaign possono essere personalizzati in vari modi.

Puoi:

* Inserire campi di personalizzazione dinamici
   ![](../assets/do-not-localize/book.png) Scopri come utilizzare i campi di personalizzazione nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html?lang=it){target=&quot;_blank&quot;}
* Inserire blocchi di personalizzazione predefiniti.
   ![](../assets/do-not-localize/book.png) Scopri cos’è un blocco di personalizzazione e come utilizzarlo, nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html?lang=it){target=&quot;_blank&quot;}
* Creare contenuti condizionali
   ![](../assets/do-not-localize/book.png) Scopri come inserire contenuti condizionali nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html?lang=it){target=&quot;_blank&quot;}

## Inviare messaggi transazionali

La messaggistica transazionale (Message Center) è il modulo di Campaign progettato per la gestione dei messaggi di attivazione.

![](../assets/do-not-localize/glass.png) Scopri le funzionalità per messaggi transazionali in [questa sezione](../dev/architecture.md#transac-msg-archi)

![](../assets/do-not-localize/glass.png) Scopri come configurare e inviare messaggi transazionali in [questa pagina](../send/transactional.md)

![](../assets/do-not-localize/book.png) Scopri questa funzionalità con un caso d’uso end-to-end descritto nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=it){target=&quot;_blank&quot;}

## Registri di consegna e di tracciamento

Il monitoraggio delle consegne dopo l’invio è un passaggio fondamentale per garantire l’efficienza delle campagne di marketing e l’effettivo raggiungimento dei clienti. Puoi monitorare una consegna, oltre a capire come vengono gestiti errori e quarantene.

![](../assets/do-not-localize/book.png) Scopri come monitorare le consegne nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=it#sending-messages){target=&quot;_blank&quot;}.


**Argomenti correlati** nella documentazione di Campaign Classic v7:

* [Best practice per la consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=it){target=&quot;_blank&quot;}

* [Verificare e inviare un’e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html){target=&quot;_blank&quot;}

* [Inviare bozze](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=it){target=&quot;_blank&quot;}
