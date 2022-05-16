---
title: Inviare notifiche push con Adobe Campaign
description: Guida introduttiva alla notifica push in Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 3%

---

# Creare e inviare notifiche push

Le consegne di app mobili ti consentono di inviare notifiche ai sistemi iOS e Android.

Per inviare notifiche push in Adobe Campaign, devi:

1. Configurare l’ambiente Campaign
1. Crea un servizio di informazioni di tipo app mobile per la tua app mobile.
1. Aggiungi al servizio le versioni iOS e Android dell&#39;applicazione.
1. Crea una consegna per iOS e Android.

![](../assets/do-not-localize/book.png) Scopri come iniziare a utilizzare l’app mobile in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html){target=&quot;_blank&quot;}

## Integrare Campaign SDK

L’SDK di Campaign facilita l’integrazione dell’app mobile nella piattaforma Adobe Campaign.

Le versioni SDK compatibili sono elencate in [Matrice di compatibilità di Campaign](../start/compatibility-matrix.md#MobileSDK).

![](../assets/do-not-localize/glass.png) Scopri come integrare gli SDK di Campaign Android e iOS con la tua app in [questa sezione](../config/push-config.md)

<!--
### Configure Campaign Extension in Launch

You can integrate Adobe Experience Platorm Launch SDK with Campaign, by leveraging Campaign Classic extension.

![](../assets/do-not-localize/book.png) Learn more in [Adobe Mobile SDK documentation](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic){target="_blank"}

-->

## Configurare le impostazioni dell’app in Campaign

Devi definire le impostazioni delle app iOS e Android in Adobe Campaign.

![](../assets/do-not-localize/book.png) Le linee guida per la configurazione di iOS sono descritte in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages){target=&quot;_blank&quot;}

![](../assets/do-not-localize/book.png) Le linee guida di configurazione per Android sono descritte in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages){target=&quot;_blank&quot;}

## Creare la prima notifica push

Questa sezione descrive gli elementi specifici per la consegna delle notifiche iOS e Android.

>[!CAUTION]
>
>Con Campaign v8, la registrazione mobile è ora **asincrono**. [Ulteriori informazioni](../dev/staging.md)

Per creare una nuova consegna, seleziona **[!UICONTROL Campaigns]** scheda , fai clic su **[!UICONTROL Deliveries]** e fai clic su **[!UICONTROL Create]** , sopra l’elenco delle consegne esistenti.

![](assets/delivery_step_1.png)

![](../assets/do-not-localize/book.png) Per informazioni globali su come creare una consegna, consulta [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}

### Invio di notifiche su iOS {#send-notifications-on-ios}

1. Seleziona la **[!UICONTROL Deliver on iOS]** modello di consegna e fai clic su **[!UICONTROL Continue]**.

   ![](assets/push-template-ios.png)

1. Per definire il target della notifica, fai clic sul pulsante **[!UICONTROL To]** collegamento, quindi fai clic su **[!UICONTROL Add]**.

   ![](assets/push-ios-select-target.png)

1. Seleziona **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**, seleziona il servizio pertinente alla tua app mobile, quindi seleziona la versione iOS dell’applicazione.

   ![](assets/push-ios-subscribers.png)

1. Seleziona il tipo di notifica: **[!UICONTROL Alert]**, **[!UICONTROL Badge]**, **[!UICONTROL Alert and badge]** o **[!UICONTROL Silent Push]**.

   ![](assets/push-ios-alert.png)

1. In **[!UICONTROL Title]** , immetti l’etichetta del titolo che desideri visualizzare nella notifica.

1. Inserisci il **[!UICONTROL Message]** e **[!UICONTROL Value of the badge]** in base al tipo di notifica scelto.

1. Puoi anche definire i seguenti elementi:

   * La **[!UICONTROL Action button]** consente di definire un’etichetta per il pulsante di azione visualizzato nelle notifiche di avviso (**action_loc_key** campo del payload).

   * In **[!UICONTROL Play a sound]** selezionare il suono che deve essere riprodotto dal terminale mobile quando viene ricevuta la notifica.

   * In **[!UICONTROL Application variables]** immettere il valore di ciascuna variabile. Ad esempio, puoi configurare una schermata specifica dell’applicazione da visualizzare quando l’utente attiva la notifica.

1. Una volta configurata la notifica, fai clic sul pulsante **[!UICONTROL Preview]** per visualizzare in anteprima la notifica.

   ![](assets/push-ios-preview.png)


### Invio di notifiche su Android {#send-notifications-on-android}

1. Seleziona la **[!UICONTROL Deliver on Android (android)]** modello di consegna.

   ![](assets/push-template-android.png)

1. Per definire il target della notifica, fai clic sul pulsante **[!UICONTROL To]** collegamento, quindi fai clic su **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. Seleziona **[!UICONTROL Subscribers of an Android mobile application]**, scegli il servizio pertinente alla tua app mobile (in questo caso Neotrips), quindi seleziona la versione Android dell&#39;applicazione.

   ![](assets/push-ios-subscribers.png)

1. Quindi inserisci il contenuto della notifica.

   ![](assets/push-android-content.png)

1. Fai clic sul pulsante **[!UICONTROL Insert emoticon]** per inserire gli emoticon nella notifica push.

1. In **[!UICONTROL Application variables]** immettere il valore di ciascuna variabile. Ad esempio, puoi configurare una schermata specifica dell’applicazione da visualizzare quando l’utente attiva la notifica.

1. Una volta configurata la notifica, fai clic sul pulsante **[!UICONTROL Preview]** per visualizzare in anteprima la notifica.

   <!--![](assets/push-android-preview.png)-->

## Test, invio e monitoraggio delle notifiche push

Per inviare una bozza e la consegna finale, utilizza lo stesso processo delle consegne e-mail. Ulteriori informazioni sono disponibili nella documentazione di Campaign Classic v7:

* Convalidare una consegna e inviare bozze
   ![](../assets/do-not-localize/book.png) [Scopri i passaggi chiave per convalidare una consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=it){target=&quot;_blank&quot;}

* Conferma e invia la consegna
   ![](../assets/do-not-localize/book.png) [Scopri i passaggi chiave per inviare una consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=en){target=&quot;_blank&quot;}

Dopo aver inviato i messaggi, puoi monitorare e tenere traccia delle consegne. Ulteriori informazioni sono disponibili nella documentazione di Campaign Classic v7:

* quarantene di notifiche push
   ![](../assets/do-not-localize/book.png) [Ulteriori informazioni sulla quarantena delle notifiche push](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html?lang=en#push-notification-quarantines){target=&quot;_blank&quot;}

* Risoluzione dei problemi
   ![](../assets/do-not-localize/book.png) [Scopri come risolvere i problemi delle notifiche push](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/troubleshooting.html?lang=en){target=&quot;_blank&quot;}
