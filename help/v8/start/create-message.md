---
product: Adobe Campaign
title: Introduzione ai messaggi
description: Introduzione ai messaggi
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 41ea85bc3c616ed7cdd0718ff3368aab971a5352
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 71%

---

# Introduzione ai messaggi{#gs-ac-audiences}

Con Adobe Campaign, puoi inviare campagne cross-channel tra cui e-mail, SMS, notifiche push e direct mailing e misurarne l’efficacia utilizzando vari rapporti dedicati. Questi messaggi sono progettati e inviati tramite consegna e possono essere personalizzati per ogni destinatario.

Le funzionalità di base includono il targeting, la definizione e la personalizzazione dei messaggi, l’esecuzione delle comunicazioni e i relativi rapporti operativi. Il punto di accesso funzionale principale è l’assistente alla consegna. Permette di sfruttare diverse funzionalità incluse in Adobe Campaign.

Scopri i passaggi chiave per creare una consegna nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=it).

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

* Invia messaggi manualmente alla destinazione principale
   [!DNL :arrow_upper_right:] [Scopri come inviare messaggi](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html?lang=it)
* Inviare messaggi associati a una [campagna di marketing](campaigns.md)
   [!DNL :arrow_upper_right:] [Scopri come inviare messaggi nel contesto di una campagna](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=it).
* Inviare messaggi tramite un [flusso di lavoro](../config/workflows.md)
   [!DNL :arrow_upper_right:] [Scopri come automatizzare le consegne di e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html?lang=it)
* [Attivare ](../send/transactional.md) messaggi da un evento
   [!DNL :arrow_upper_right:] [Caso di utilizzo: scopri come inviare un’e-mail transazionale con un allegato](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=it)
* Pianificare i messaggi
   [!DNL :arrow_upper_right:] [Caso di utilizzo: scopri come pianificare e inviare un’e-mail di compleanno](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=it)


## Aggiungi personalizzazione

I messaggi consegnati da Adobe Campaign possono essere personalizzati in vari modi.

Puoi:

* Inserire campi di personalizzazione dinamici.
   [!DNL :arrow_upper_right:] Scopri come utilizzare i campi di personalizzazione nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html?lang=it)
* Inserire blocchi di personalizzazione predefiniti.
   [!DNL :arrow_upper_right:] Scopri cos’è un blocco di personalizzazione e come utilizzarlo nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html?lang=it)
* Creare contenuto condizionale.
   [!DNL :arrow_upper_right:] Scopri come inserire contenuto condizionale nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html?lang=it)

## Inviare messaggi transazionali

La messaggistica transazionale (Message Center) è il modulo di Campaign progettato per la gestione dei messaggi di attivazione.

[!DNL :bulb:] Per ulteriori informazioni sulla funzionalità dei messaggi transazionali, consulta [questa sezione](../dev/architecture.md#transac-msg-archi)

[!DNL :bulb:] I passaggi per configurare e inviare messaggi transazionali sono descritti in [questa pagina](../send/transactional.md)

[!DNL :arrow_upper_right:] Scopri questa funzionalità in un caso d’uso end-to-end nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=it#transactional-messaging)

## Registri di consegna e di tracciamento

Il monitoraggio delle consegne dopo l’invio è un passaggio fondamentale per garantire l’efficienza delle campagne di marketing e l’effettivo raggiungimento dei clienti. Puoi monitorare una consegna, oltre a capire come vengono gestiti errori e quarantene.

[!DNL :arrow_upper_right:] [Scopri come monitorare le consegne in questa sezione](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=it#sending-messages)


**Argomenti correlati**

[!DNL :arrow_upper_right:]  [Best practice di consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=it)

[!DNL :arrow_upper_right:]  [Test e invio di un’e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

[!DNL :arrow_upper_right:]  [Invia bozze](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=it)
