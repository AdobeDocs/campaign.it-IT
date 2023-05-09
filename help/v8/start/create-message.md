---
title: Introduzione ai messaggi
description: Introduzione ai messaggi
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: ht
source-wordcount: '429'
ht-degree: 100%

---

# Introduzione ai messaggi{#gs-ac-audiences}

Con Adobe Campaign, puoi inviare campagne cross-channel tra cui e-mail, SMS, notifiche push e direct mail; inoltre, puoi misurarne l’efficacia utilizzando diversi rapporti dedicati. Questi messaggi sono progettati e inviati tramite consegna e possono essere personalizzati per ogni destinatario.

Le funzionalità di base includono il targeting, la definizione e la personalizzazione dei messaggi, l’esecuzione delle comunicazioni e i relativi rapporti operativi. Il punto di accesso funzionale principale è l’assistente alla consegna. Permette di sfruttare diverse funzionalità incluse in Adobe Campaign.

Adobe Campaign v8 è dotato dei canali di consegna seguenti:

* **Canale e-mail**: le consegne e-mail ti consentono di inviare e-mail personalizzate alla popolazione target. Per ulteriori informazioni, consulta [questa pagina](../send/email.md).

* **Canale direct mailing**: le consegne tramite direct mailing ti consentono di generare un file di estrazione che contiene dati sulla popolazione target.  Per ulteriori informazioni, consulta [questa pagina](../send/direct-mail.md)

* **Canale mobile**: le consegne sui canali mobili ti consentono di inviare SMS personalizzati alla popolazione target.  Per ulteriori informazioni, consulta [questa pagina](../send/sms.md)

* **Canale dell’app mobile**: le consegne tramite app mobile ti consentono di inviare notifiche ai sistemi iOS e Android.  Per ulteriori informazioni, consulta [questa pagina](../send/push.md)

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## Scegli come inviare i messaggi{#gs-send-msg}

Dopo aver creato il messaggio e averne progettato e testato il relativo contenuto, puoi scegliere come inviarlo. Campaign offre una serie di funzionalità per:

* Inviare messaggi manualmente al target principale

   ![](assets/send-email.png)

   Scopri come inviare messaggi in [questa sezione](../send/send.md)

* Inviare messaggi associati a una [campagna di marketing](campaigns.md)

   ![](assets/deliveries-in-a-campaign.png)

   Per scoprire come inviare messaggi nel contesto di una campagna, consulta [questa sezione](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=it).

* Inviare messaggi tramite un [flusso di lavoro](../config/workflows.md)

   ![](assets/send-in-a-wf.png)

   Per scoprire come automatizzare le consegne di e-mail, consulta [questa pagina](../../automation/workflow/delivery.md).

* [Attivare i messaggi](../send/transactional.md) da un evento

* Pianificare i messaggi

   ![](assets/schedule-send.png)

[Caso d’uso: scopri come pianificare e inviare un’e-mail di compleanno](../../automation/workflow/send-a-birthday-email.md)


## Aggiungere personalizzazione{#personalization}

I messaggi consegnati da Adobe Campaign possono essere personalizzati in vari modi. [Ulteriori informazioni sulle funzionalità di personalizzazione](../send/personalize.md)

È possibile eseguire le seguenti operazioni:

* Inserire campi di personalizzazione dinamici. [Ulteriori informazioni](../send/personalization-fields.md)
* Inserire blocchi di personalizzazione predefiniti. [Ulteriori informazioni](../send/personalization-blocks.md)
* Creare contenuto condizionale. [Ulteriori informazioni](../send/conditions.md)

## Inviare messaggi transazionali{#gs-transac-messages}

La messaggistica transazionale (Message Center) è il modulo di Campaign progettato per la gestione dei messaggi di attivazione.

Ulteriori informazioni sulle funzionalità per messaggi transazionali in [questa sezione](../architecture/architecture.md#transac-msg-archi)

Scopri come configurare e inviare messaggi transazionali in [questa pagina](../send/transactional.md)


## Registri di consegna e di tracciamento{#gs-tracking-logs}

Il monitoraggio delle consegne dopo l’invio è un passaggio fondamentale per garantire l’efficienza delle campagne di marketing e l’effettivo raggiungimento dei clienti. Puoi monitorare una consegna, oltre a capire come vengono gestiti errori e quarantene.

![](../assets/do-not-localize/book.png) Scopri come monitorare le consegne nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=it#sending-messages){target="_blank"}

