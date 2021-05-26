---
solution: Campaign v8
product: Adobe Campaign
title: Gestione di abbonamenti e annullamenti di abbonamenti in Campaign
description: Scopri come gestire gli abbonamenti e i loro annullamenti in Campaign v8
feature: Panoramica
role: Data Engineer
level: Beginner
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# Gestione di abbonamenti e annullamenti di abbonamenti{#optin-optout}

Utilizza Adobe Campaign per creare e monitorare i tuoi servizi informativi, come le newsletter, e per gestire gli abbonamenti/i loro annullamenti. È possibile definire in parallelo diversi servizi, ad esempio: newsletter specializzate per determinate categorie di prodotti, temi o aree di un sito web, abbonamenti a vari tipi di messaggi di avviso e notifiche in tempo reale. Consulta Gestione abbonamenti .

[!DNL :arrow_upper_right:] Scopri come creare un servizio informazioni, inviare una newsletter e gestire l’opt-in e l’opt-out nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html)

Per abbonarti (opt-in) a un profilo di un servizio, le opzioni disponibili sono:

* Aggiungi manualmente il servizio al profilo destinatario: a questo scopo, dalla scheda **[!UICONTROL Subscriptions]** del profilo, fai clic su **[!UICONTROL Add]** e seleziona il servizio informazioni interessato.

   [!DNL :arrow_upper_right:] Ulteriori informazioni nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab)

* Iscriviti automaticamente al servizio un set di destinatari. L’elenco dei destinatari può provenire da un’operazione di filtro, da un gruppo, da una cartella, da un’importazione o da una selezione diretta manuale. Per sottoscrivere questi destinatari, seleziona i profili e fai clic con il pulsante destro del mouse su di essi. Selezionare **[!UICONTROL Actions > Subscribe selection to a service...]**, selezionare il servizio interessato e avviare l&#39;operazione.

   [!DNL :arrow_upper_right:] Ulteriori informazioni nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab)


* Importa i destinatari e abbonali automaticamente a un servizio di informazioni. A questo scopo, seleziona il servizio interessato nell’ultimo passaggio della procedura guidata di importazione.

   [!DNL :arrow_upper_right:] Ulteriori informazioni nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=en#step-5---additional-step-when-importing-recipients)

* Utilizza un modulo web per consentire ai destinatari di iscriversi a un servizio.

   [!DNL :arrow_upper_right:] Ulteriori informazioni nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=en#create-a-subscription--form-with-double-opt-in)


* Crea un flusso di lavoro di targeting e utilizza un’attività **[!UICONTROL Subscription service]** .

   [!DNL :arrow_upper_right:] Ulteriori informazioni nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/subscription-services.html?lang=en#example--subscribe-a-list-of-recipients-to-a-newsletter)


Per annullare l’abbonamento (opt-out) a un profilo da un servizio, le opzioni disponibili sono:

**Annullamento manuale della sottoscrizione**

* Collegamento o modulo web personalizzato per l’annullamento dell’abbonamento
* Cancellazione manuale di un servizio di informazione
* Cancellazione manuale dei destinatari da un particolare servizio di abbonamento

**Annullamento automatico della sottoscrizione**

* Specifica un limite di durata del servizio informazioni: i destinatari verranno automaticamente annullati alla scadenza del periodo di validità. Questo periodo è specificato nella scheda Modifica delle proprietà del servizio. Viene espresso in giorni.
* Imposta un flusso di lavoro di annullamento dell’abbonamento per una popolazione

[!DNL :arrow_upper_right:] Ulteriori informazioni nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=en#unsubscribing-a-recipient-from-a-service)


>[!CAUTION]
>
>Gli abbonamenti e i loro annullamenti sono **processi asincroni**. Le richieste di consenso e rinuncia vengono elaborate ogni ora. [Ulteriori informazioni](../dev/new-apis.md#sub-apis)

Puoi anche abilitare i destinatari della consegna a inoltrare i messaggi a un amico. A questo scopo, inserisci i collegamenti rilevanti nella consegna. Puoi quindi tenere traccia di questo processo di condivisione e del numero di visite alle pagine interessate.

[!DNL :arrow_upper_right:] Per ulteriori informazioni su questa funzionalità, consulta la documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html?lang=en#viral-marketing--forward-to-a-friend).