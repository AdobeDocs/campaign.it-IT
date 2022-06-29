---
title: Inviare notifiche push con Adobe Campaign
description: Guida introduttiva alla notifica push in Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 110cf2ff705ecbc0b3a1690e9dfc2791f5744b97
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 6%

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
>Nel contesto di un [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), la registrazione mobile è ora **asincrono**. [Ulteriori informazioni](../architecture/staging.md)

Per creare una nuova consegna, seleziona **[!UICONTROL Campaigns]** scheda , fai clic su **[!UICONTROL Deliveries]** e fai clic su **[!UICONTROL Create]** , sopra l’elenco delle consegne esistenti.

![](assets/delivery_step_1.png)

![](../assets/do-not-localize/book.png) Per informazioni globali su come creare una consegna, consulta [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}

### Invio di notifiche su iOS {#send-notifications-on-ios}

>[!NOTE]
>
>Questa funzionalità è disponibile a partire da Campaign v8.3. Per verificare la versione, consulta [questa sezione](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

1. Seleziona la **[!UICONTROL Deliver on iOS]** modello di consegna.

   ![](assets/push_ios_1.png)

1. Per definire il target della notifica, fai clic sul pulsante **[!UICONTROL To]** collegamento, quindi fai clic su **[!UICONTROL Add]**.

   ![](assets/push_ios_2.png)

1. Seleziona **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**, seleziona il servizio pertinente alla tua app mobile, quindi seleziona la versione iOS dell’applicazione.

   ![](assets/push_ios_3.png)

1. Scegli la tua **[!UICONTROL Notification type]** tra **[!UICONTROL General notification (Alert, Sound, Badge)]** o **[!UICONTROL Silent notification]**.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >La **Push silenzioso** consente di inviare una notifica &quot;silenziosa&quot; a un’app mobile. L&#39;utente non viene informato dell&#39;arrivo della notifica. Viene trasferito direttamente all&#39;applicazione.

1. In **[!UICONTROL Title]** immettere l&#39;etichetta del titolo che si desidera visualizzare nell&#39;elenco delle notifiche disponibili dal centro notifiche.

   Questo campo ti consente di definire il valore del **title** del payload di notifica iOS.

1. Puoi aggiungere una **[!UICONTROL Subtitle]**, il valore **sottotitolo** del payload di notifica iOS.

1. Immetti il contenuto del messaggio nel **[!UICONTROL Message content]** della procedura guidata.

1. Da **[!UICONTROL Sound and Badge]** è possibile modificare le seguenti opzioni:

   * **[!UICONTROL Clean Badge]**: abilita queste opzioni per aggiornare il valore del badge.

   * **[!UICONTROL Value]**: imposta un numero che verrà utilizzato per visualizzare direttamente sull&#39;icona dell&#39;applicazione il numero di nuove informazioni non lette.

   * **[!UICONTROL Critical alert mode]**: abilitare questa opzione per aggiungere l&#39;audio alla notifica anche se il telefono dell&#39;utente è impostato in modalità di attivazione o se l&#39;iPhone è disattivato.

   * **[!UICONTROL Name]**: selezionare l&#39;audio che deve essere riprodotto dal terminale mobile quando viene ricevuta la notifica.

   * **[!UICONTROL Volume]**: volume del suono da 0 a 100.

      >[!NOTE]
      > 
      >I suoni devono essere inclusi nell&#39;applicazione e definiti al momento della creazione del servizio.
      >
      >Le linee guida per la configurazione di iOS sono descritte in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html){target=&quot;_blank&quot;}.
   ![](assets/push_ios_5.png)

1. Da **[!UICONTROL Application variables]** scheda **[!UICONTROL Application variables]** vengono aggiunti automaticamente. Consentono di definire il comportamento di notifica, ad esempio, di configurare una schermata specifica dell’applicazione da visualizzare quando l’utente attiva la notifica.

   Per ulteriori informazioni, consulta la [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html){target=&quot;_blank&quot;}.

1. Da **[!UICONTROL Advanced]** è possibile modificare le seguenti opzioni generali:

   * **[!UICONTROL Mutable content]**: abilita questa opzione per consentire all’app mobile di scaricare contenuti multimediali.

   * **[!UICONTROL Thread-id]**: identificatore utilizzato per raggruppare le notifiche correlate.

   * **[!UICONTROL Category]**: nome dell’ID categoria che mostrerà i pulsanti di azione. Queste notifiche forniscono all’utente un modo più rapido per eseguire diverse attività in risposta a una notifica senza aprire o esplorare l’applicazione.

   ![](assets/push_ios_6.png)

1. Per le notifiche sensibili al tempo, puoi specificare le seguenti opzioni:

   * **[!UICONTROL Target content ID]**: identificatore utilizzato per individuare la finestra dell&#39;applicazione da inoltrare all&#39;apertura della notifica.

   * **[!UICONTROL Launch image]**: nome del file immagine di lancio da visualizzare. Se l&#39;utente sceglie di avviare l&#39;applicazione, l&#39;immagine selezionata verrà visualizzata al posto della schermata di avvio dell&#39;applicazione.

   * **[!UICONTROL Interruption level]**:

      * **[!UICONTROL Active]**: Impostato per impostazione predefinita, il sistema presenta immediatamente la notifica, accende lo schermo e può riprodurre un suono. Le notifiche non si interrompono tra le modalità di messa a fuoco.

      * **[!UICONTROL Passive]**: Il sistema aggiunge la notifica all&#39;elenco delle notifiche senza accendere lo schermo o riprodurre un suono. Le notifiche non si interrompono tra le modalità di messa a fuoco.

      * **[!UICONTROL Time sensitive]** Il sistema presenta immediatamente la notifica, si accende lo schermo, può riprodurre un suono e rompere le modalità di messa a fuoco. Questo livello non richiede un&#39;autorizzazione speciale da parte di Apple.

      * **[!UICONTROL Critical]** Il sistema presenta immediatamente la notifica, accende lo schermo e bypassa l&#39;interruttore muto o le modalità di messa a fuoco. Tieni presente che questo livello richiede un’autorizzazione speciale da parte di Apple.
   * **[!UICONTROL Relevance score]**: imposta un punteggio di rilevanza da 0 a 100. Il sistema utilizza questo per ordinare le notifiche nel riepilogo delle notifiche.

   ![](assets/push_ios_7.png)

1. Una volta configurata la notifica, fai clic sul pulsante **[!UICONTROL Preview]** per visualizzare in anteprima la notifica.

   ![](assets/push-ios-preview.png)

### Invio di notifiche su Android {#send-notifications-on-android}

1. Seleziona la **[!UICONTROL Deliver on Android (android)]** modello di consegna.

   ![](assets/push-template-android.png)

1. Per definire il target della notifica, fai clic sul pulsante **[!UICONTROL To]** collegamento, quindi fai clic su **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. Seleziona **[!UICONTROL Subscribers of an Android mobile application]**, scegli il servizio pertinente alla tua app mobile (in questo caso Neotrips), quindi seleziona la versione Android dell&#39;applicazione.

   ![](assets/push-android-subscribers.png)

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
   ![](../assets/do-not-localize/book.png) [Scopri i passaggi chiave per inviare una consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html){target=&quot;_blank&quot;}

Dopo aver inviato i messaggi, puoi monitorare e tenere traccia delle consegne. Ulteriori informazioni sono disponibili nella documentazione di Campaign Classic v7:

* quarantene di notifiche push
   ![](../assets/do-not-localize/book.png) [Ulteriori informazioni sulla quarantena delle notifiche push](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html#push-notification-quarantines){target=&quot;_blank&quot;}

* Risoluzione dei problemi
   ![](../assets/do-not-localize/book.png) [Scopri come risolvere i problemi delle notifiche push](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/troubleshooting.html){target=&quot;_blank&quot;}
