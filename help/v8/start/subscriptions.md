---
title: Gestione di abbonamenti e annullamenti di abbonamenti in Campaign
description: Scopri come gestire gli abbonamenti e il loro annullamento in Campaign v8
feature: Subscriptions
role: User
level: Beginner
exl-id: d5933b12-8664-49b8-953c-ea98eb428cc2
source-git-commit: b323dbf9504e39cca78f7082089b864544ee1633
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 13%

---

# Gestione di abbonamenti e annullamenti di abbonamenti{#optin-optout}

Utilizza Adobe Campaign per creare e monitorare i tuoi servizi informativi, come le newsletter, e per gestire gli abbonamenti/i loro annullamenti. È possibile definire in parallelo diversi servizi, ad esempio: newsletter specializzate per determinate categorie di prodotti, temi o aree di un sito web, abbonamenti a vari tipi di messaggi di avviso e notifiche in tempo reale. Consulta Gestione abbonamenti .

![](../assets/do-not-localize/book.png) Scopri come creare un servizio informazioni, inviare una newsletter e gestire l’opt-in e l’opt-out in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html){target=&quot;_blank&quot;}

Per abbonarti (opt-in) a un profilo di un servizio, le opzioni disponibili sono:

* Aggiungi manualmente il servizio al profilo destinatario: a tal fine, dal **[!UICONTROL Subscriptions]** scheda del profilo, fai clic su **[!UICONTROL Add]** e selezionare il servizio di informazione interessato.

   ![](assets/subscribe-to-a-service.png)

   ![](../assets/do-not-localize/book.png)Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab){target=&quot;_blank&quot;}.

* Iscriviti automaticamente al servizio un set di destinatari. L’elenco dei destinatari può provenire da un’operazione di filtro, da un gruppo, da una cartella, da un’importazione o da una selezione diretta manuale. Per sottoscrivere questi destinatari, seleziona i profili e fai clic con il pulsante destro del mouse su di essi. Seleziona **[!UICONTROL Actions > Subscribe selection to a service...]**.

   ![](assets/subscribe-selection.png)

   Selezionare il servizio interessato e avviare l&#39;operazione.

   ![](assets/subscribe-confirm.png)

   ![](../assets/do-not-localize/book.png)Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab){target=&quot;_blank&quot;}.


* Importa i destinatari e abbonali automaticamente a un servizio di informazioni. A questo scopo, seleziona il servizio interessato nell’ultimo passaggio della procedura guidata di importazione.

   ![](../assets/do-not-localize/book.png)Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=en#step-5---additional-step-when-importing-recipients){target=&quot;_blank&quot;}.

* Utilizza un modulo web per consentire ai destinatari di iscriversi a un servizio.

   ![](assets/opt-in-webapp.png)

   Campaign viene fornito con un modulo web predefinito per gestire l’opt-in. Puoi personalizzarlo e mappare i dati del profilo.

   ![](assets/web-app.png)

   ![](../assets/do-not-localize/book.png)Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=en#create-a-subscription--form-with-double-opt-in){target=&quot;_blank&quot;}.


* Creare un flusso di lavoro di targeting e utilizzare un **[!UICONTROL Subscription service]** attività.

   ![](assets/wf-subscription.png)

   Per ulteriori informazioni, consulta [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/subscription-services.html).

Per annullare l’abbonamento (opt-out) a un profilo da un servizio, le opzioni disponibili sono:

**Annullamento manuale della sottoscrizione**

* Collegamento o modulo web personalizzato per l’annullamento dell’abbonamento
* Cancellazione manuale di un servizio di informazione
* Cancellazione manuale dei destinatari da un particolare servizio di abbonamento

**Annullamento automatico della sottoscrizione**

* Specifica un limite di durata del servizio informazioni: i destinatari verranno automaticamente annullati alla scadenza del periodo di validità. Questo periodo è specificato nella scheda Modifica delle proprietà del servizio. Viene espresso in giorni.
* Imposta un flusso di lavoro di annullamento dell’abbonamento per una popolazione.

![](../assets/do-not-localize/book.png)Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=en#unsubscribing-a-recipient-from-a-service){target=&quot;_blank&quot;}.


>[!CAUTION]
>
>Nel contesto di un [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), gli abbonamenti e i loro annullamenti sono **asincrono** processi. Le richieste di consenso e rinuncia vengono elaborate ogni ora. [Ulteriori informazioni](../architecture/new-apis.md#sub-apis)

<!--
You can also enable your delivery recipients to forward messages to a friend. To do this, insert the relevant links into your delivery. You may then track this sharing process as well as the number of visits to the concerned pages. 

![](../assets/do-not-localize/book.png) For more on this capability, refer to [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html?lang=en#viral-marketing--forward-to-a-friend){target="_blank"}
-->
