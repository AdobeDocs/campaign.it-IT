---
product: Adobe Campaign
title: Inviare notifiche push con Adobe Campaign
description: Guida introduttiva alla notifica push in Campaign
feature: Panoramica
role: Data Engineer
level: Beginner
source-git-commit: aa3f2f17981ad10221771b3a22c76f7a445b94c9
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 2%

---

# Creare e inviare notifiche push

Le consegne di app mobili ti consentono di inviare notifiche ai sistemi iOS e Android.

Per inviare notifiche push in Adobe Campaign, devi:

1. Configurare l’ambiente Campaign
1. Crea un servizio di informazioni di tipo app mobile per la tua app mobile.
1. Aggiungi al servizio le versioni iOS e Android dell&#39;applicazione.
1. Crea una consegna per iOS e Android.

[!DNL :arrow_upper_right:] Scopri come iniziare a utilizzare l’app mobile nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html)

## Integrare con Adobe SDK

### Integrare Campaign SDK

L’SDK di Campaign facilita l’integrazione dell’app mobile nella piattaforma Adobe Campaign.

Le versioni SDK compatibili sono elencate in [Matrice di compatibilità di Campaign](../start/compatibility-matrix.md#MobileSDK).

<!--
[!DNL :arrow_upper_right:] Learn how to integrate Campaign Android and iOS SDKs with your app in [this section](../config/push-config.md)
-->


### Configurare l’estensione Campaign in Launch

Puoi integrare l’SDK di Adobe Experience Platform Launch con Campaign, sfruttando l’estensione Campaign Classic.

[!DNL :arrow_upper_right:] Ulteriori informazioni nella documentazione SDK di  [Adobe Mobile](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)

## Configurare le impostazioni dell’app in Campaign

Devi definire le impostazioni delle app iOS e Android in Adobe Campaign.

[!DNL :arrow_upper_right:] Le linee guida per la configurazione di iOS sono descritte in dettaglio nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages)

[!DNL :arrow_upper_right:] Le linee guida per la configurazione di Android sono descritte in dettaglio nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages)

## Creare la prima notifica push

Questa sezione descrive gli elementi specifici per la consegna delle notifiche iOS e Android.

[!DNL :arrow_upper_right:] Tutti i passaggi per creare le notifiche push sono descritti in dettaglio nella documentazione di  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en)

>[!CAUTION]
>
>Con Campaign v8, la registrazione mobile è ora **asincrona**. [Ulteriori informazioni](../dev/staging.md)

Per creare una nuova consegna, passa alla scheda **[!UICONTROL Campaigns]** , fai clic su **[!UICONTROL Deliveries]** e fai clic sul pulsante **[!UICONTROL Create]** sopra l’elenco delle consegne esistenti.

![](assets/delivery_step_1.png)

[!DNL :arrow_upper_right:] Per informazioni globali su come creare una consegna, consulta la documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages).

### Inviare notifiche su iOS {#send-notifications-on-ios}

1. Seleziona il modello di consegna **[!UICONTROL Deliver on iOS]** e fai clic su **[!UICONTROL Continue]**.

   ![](assets/push-template-ios.png)

1. Per definire la destinazione della notifica, fai clic sul collegamento **[!UICONTROL To]** , quindi fai clic su **[!UICONTROL Add]**.

   ![](assets/push-ios-select-target.png)

1. Seleziona **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**, seleziona il servizio pertinente alla tua app mobile, quindi seleziona la versione iOS dell&#39;applicazione.

   ![](assets/push-ios-subscribers.png)

1. Seleziona il tipo di notifica: **[!UICONTROL Alert]**, **[!UICONTROL Badge]**, **[!UICONTROL Alert and badge]** o **[!UICONTROL Silent Push]**.

   ![](assets/push-ios-alert.png)

1. Nel campo **[!UICONTROL Title]** , immetti l’etichetta del titolo che desideri visualizzare nella notifica.

1. Immetti i valori **[!UICONTROL Message]** e **[!UICONTROL Value of the badge]** in base al tipo di notifica scelto.

1. Puoi anche definire i seguenti elementi:

   * Il **[!UICONTROL Action button]** ti consente di definire un’etichetta per il pulsante di azione visualizzato nel campo notifiche di avviso (**action_loc_key** del payload).

   * Nel campo **[!UICONTROL Play a sound]** , seleziona il suono che deve essere riprodotto dal terminale mobile quando viene ricevuta la notifica.

   * Nel campo **[!UICONTROL Application variables]** , immetti il valore di ciascuna variabile. Ad esempio, puoi configurare una schermata specifica dell’applicazione da visualizzare quando l’utente attiva la notifica.

1. Una volta configurata la notifica, fai clic sulla scheda **[!UICONTROL Preview]** per visualizzare l’anteprima della notifica.

   ![](assets/push-ios-preview.png)

[!DNL :arrow_upper_right:] Tutti i passaggi dettagliati per la creazione e l’invio di notifiche push su iOS sono descritti in dettaglio nella documentazione di  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)

### Invia notifiche su Android {#send-notifications-on-android}

1. Seleziona il modello di consegna **[!UICONTROL Deliver on Android (android)]**.

   ![](assets/push-template-android.png)

1. Per definire la destinazione della notifica, fai clic sul collegamento **[!UICONTROL To]** , quindi fai clic su **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. Seleziona **[!UICONTROL Subscribers of an Android mobile application]**, scegli il servizio pertinente alla tua app mobile (in questo caso Neotrips), quindi seleziona la versione Android dell&#39;applicazione.

   ![](assets/push-ios-subscribers.png)

1. Quindi inserisci il contenuto della notifica.

   ![](assets/push-android-content.png)

1. Fai clic sull’icona **[!UICONTROL Insert emoticon]** per inserire gli emoticon nella notifica push.

1. Nel campo **[!UICONTROL Application variables]** , immetti il valore di ciascuna variabile. Ad esempio, puoi configurare una schermata specifica dell’applicazione da visualizzare quando l’utente attiva la notifica.

1. Una volta configurata la notifica, fai clic sulla scheda **[!UICONTROL Preview]** per visualizzare l’anteprima della notifica.

   <!--![](assets/push-android-preview.png)-->

[!DNL :arrow_upper_right:] Tutti i passaggi dettagliati per la creazione e l’invio di notifiche push su Android sono descritti in dettaglio nella documentazione di  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-android)

## Test, invio e monitoraggio delle notifiche push

Per inviare una bozza e la consegna finale, utilizza lo stesso processo delle consegne e-mail. Ulteriori informazioni nella documentazione di Campaign Classic v7:

* Convalidare una consegna e inviare bozze
   [!DNL :arrow_upper_right:] [Scopri i passaggi chiave per convalidare una consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)

* Conferma e invia la consegna
   [!DNL :arrow_upper_right:] [Scopri i passaggi chiave per inviare una consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=en)

Dopo aver inviato i messaggi, puoi monitorare e tenere traccia delle consegne. Ulteriori informazioni nella documentazione di Campaign Classic v7:

* quarantene di notifiche push
   [!DNL :arrow_upper_right:] [Ulteriori informazioni sulla quarantena delle notifiche push](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html?lang=en#push-notification-quarantines)

* Risoluzione dei problemi
   [!DNL :arrow_upper_right:] [Scopri come risolvere i problemi delle notifiche push](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/troubleshooting.html?lang=en)