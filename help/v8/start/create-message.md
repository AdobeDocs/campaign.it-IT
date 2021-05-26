---
solution: Campaign v8
product: Adobe Campaign
title: Introduzione ai messaggi
description: Introduzione ai messaggi
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 167730cc3e81ee47f02bcdbc2c39fe793a99c534
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 4%

---

# Guida introduttiva ai messaggi{#gs-ac-audiences}

Con Adobe Campaign, puoi inviare campagne cross-channel tra cui e-mail, SMS, notifiche push e direct mailing e misurarne l’efficacia utilizzando vari rapporti dedicati. Questi messaggi sono progettati e inviati tramite le consegne e possono essere personalizzati per ogni destinatario.

Le funzionalità di base includono il targeting, la definizione e la personalizzazione dei messaggi, l’esecuzione di comunicazioni e i relativi rapporti operativi. Il punto di accesso funzionale principale è l’assistente alla consegna. Questo punto di accesso porta a più funzionalità coperte da Adobe Campaign.

Scopri i passaggi chiave per creare una consegna nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html).

Adobe Campaign v8 viene fornito con i seguenti canali di consegna:

* **Canale** e-mail: Le consegne e-mail ti consentono di inviare e-mail personalizzate alla popolazione target. Ulteriori informazioni in [questa pagina](../send/email.md).

* **Canale** direct mailing: le consegne di direct mailing ti consentono di generare un file di estrazione che contiene dati sulla popolazione target.  Ulteriori informazioni in [questa pagina](../send/direct-mail.md)

* **Canale** mobile: le consegne sui canali mobili ti consentono di inviare SMS personalizzati alla popolazione target.  Ulteriori informazioni in [questa pagina](../send/sms.md)

* **Canale** dell&#39;applicazione mobile: le consegne di app mobili ti consentono di inviare notifiche ai sistemi iOS e Android.  Ulteriori informazioni in [questa pagina](../send/push.md)

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## Scegliere come inviare i messaggi

Una volta creato il messaggio e il relativo contenuto progettato e testato, puoi scegliere come inviarlo. Campaign offre una serie di funzionalità per:

* Invia messaggi manualmente alla destinazione principale
   [!DNL :arrow_upper_right:] [Scopri come inviare messaggi](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)
* Inviare messaggi associati a una [campagna di marketing](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html)
   [!DNL :arrow_upper_right:] [Scopri come inviare messaggi nel contesto di una campagna](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html).
* Inviare messaggi tramite un [flusso di lavoro](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
   [!DNL :arrow_upper_right:] [Scopri come automatizzare le consegne di e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html)
* [Attivare ](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html) messaggi da un evento
   [!DNL :arrow_upper_right:] [Caso di utilizzo: scopri come inviare un’e-mail transazionale con un allegato](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html)
* Pianificare i messaggi
   [!DNL :arrow_upper_right:] [Caso di utilizzo: scopri come pianificare e inviare un’e-mail di compleanno](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?)


## Aggiungi personalizzazione

I messaggi inviati da Adobe Campaign possono essere personalizzati in vari modi.

Puoi:

* Inserire campi di personalizzazione dinamici.
   [!DNL :arrow_upper_right:] Scopri come utilizzare i campi di personalizzazione nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)
* Inserire blocchi di personalizzazione predefiniti.
   [!DNL :arrow_upper_right:] Scopri cos’è un blocco di personalizzazione e come utilizzarlo nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html)
* Creare contenuto condizionale.
   [!DNL :arrow_upper_right:] Scopri come inserire contenuto condizionale nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html)

## Inviare messaggi transazionali

La messaggistica transazionale (Message Center, Centro messaggi) è il modulo Campaign progettato per la gestione dei messaggi di attivazione.

[!DNL :bulb:] Ulteriori informazioni sulla funzionalità dei messaggi transazionali in  [questa sezione](../dev/architecture.md#transac-msg-archi)

[!DNL :bulb:] I passaggi per configurare e inviare messaggi transazionali sono descritti in  [questa pagina](../send/transactional.md)

:[!DNL :arrow_upper_right:]: Scopri questa funzionalità in un caso d’uso end-to-end nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=en#transactional-messaging)

## Log di consegna e di tracciamento

Il monitoraggio delle consegne dopo l’invio è un passaggio chiave per garantire l’efficienza delle campagne di marketing e la disponibilità dei clienti. Puoi monitorare dopo l’invio di una consegna, nonché capire come vengono gestiti gli errori di consegna e le quarantena.

:[!DNL :arrow_upper_right:]: [Scopri come monitorare le consegne in questa sezione](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages)


**Argomenti correlati**

:[!DNL :arrow_upper_right:]:  [Best practice per la consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html)

:[!DNL :arrow_upper_right:]:  [Test e invio di un&#39;e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

:[!DNL :arrow_upper_right:]:  [Invia bozze](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
