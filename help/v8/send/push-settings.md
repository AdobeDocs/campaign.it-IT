---
title: Integrare AEP SDK e Campaign
description: Scopri come integrare Adobe Experience Platform mobile SDK con la tua app
feature: Push
role: Admin, Developer
level: Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 1a75f411-3f71-4114-b738-277820dc6138
source-git-commit: 110a2cac920ca3087f6fcb3cab8474729f6075be
workflow-type: tm+mt
source-wordcount: '1681'
ht-degree: 4%

---

# Configurare il canale di notifica push {#push-notification-configuration}

Per inviare notifiche push con Adobe Campaign, devi prima configurare l’ambiente e l’app come descritto in questa pagina. In Adobe Campaign, il canale per l’invio di notifiche push è il canale app mobile.

>[!CAUTION]
>
>Alcune importanti modifiche al servizio Android Firebase Cloud Messaging (FCM) verranno rilasciate nel 2024 e potranno influenzare la tua implementazione di Adobe Campaign. Per supportare questa modifica, potrebbe essere necessario aggiornare la configurazione dei servizi di abbonamento per i messaggi push Android. Puoi già verificare ed eseguire azioni. [Ulteriori informazioni](../../technotes/upgrades/push-technote.md).

Prima di iniziare a inviare notifiche push con Adobe Campaign, è necessario assicurarsi che le configurazioni e le integrazioni siano attive nell’app mobile e per i tag in Adobe Experience Platform. Adobe Experience Platform Mobile SDK fornisce API di integrazione lato client per i dispositivi mobili tramite SDK compatibili con Android e iOS.

Per configurare la tua app con gli SDK di Adobe Experience Platform Mobile, segui questi passaggi:

1. Controlla [prerequisiti](#before-starting).
1. Configura una [proprietà tag mobile](#launch-property) in Raccolta dati di Adobe Experience Platform.
1. Ottieni il SDK di Adobe Experience Platform Mobile come dettagliato [in questa pagina](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}.
1. (facoltativo) Abilita la registrazione e le metriche del ciclo di vita, come descritto [in questa pagina](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}.
1. (facoltativo) Aggiungi [Adobe Experience Platform Assurance alla tua app](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"} per convalidare la tua implementazione. Scopri come implementare l&#39;estensione Adobe Experience Platform Assurance [in questa pagina](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}.
1. Configura i tuoi iOS e Android Mobile Services in Adobe Campaign come [in questa pagina](#push-service).
1. Installa e configura [l&#39;estensione Adobe Campaign](#configure-extension) nella tua proprietà mobile.
1. Segui la [documentazione di Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} per completare la configurazione con gli SDK di Adobe Experience Platform Mobile nella tua app.

## Prerequisiti {#before-starting}

### Impostare le autorizzazioni {#setup-permissions}

Prima di creare un’app mobile, è necessario assicurarsi di disporre delle autorizzazioni utente corrette per i tag in Adobe Experience Platform o assegnarle. Le autorizzazioni utente per i tag in Adobe Experience Platform vengono assegnate agli utenti tramite Adobe Admin Console. Ulteriori informazioni nella [documentazione sui tag](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html?lang=it){target="_blank"}.

>[!CAUTION]
>
>La configurazione push deve essere eseguita da un utente esperto. A seconda del modello di implementazione e degli utenti tipo coinvolti nell&#39;implementazione, potrebbe essere necessario assegnare il set completo di autorizzazioni a un singolo profilo di prodotto o condividere le autorizzazioni tra lo sviluppatore di app e l&#39;amministratore **Adobe Campaign**.

Per assegnare i diritti di **Proprietà** e **Società**, effettua le seguenti operazioni:

1. Accedere a **[!DNL Admin Console]**.
1. Dalla scheda **[!UICONTROL Products]**, seleziona la scheda **[!UICONTROL Adobe Experience Platform Data Collection]**.
1. Selezionare un elemento **[!UICONTROL Product Profile]** esistente o crearne uno nuovo con il pulsante **[!UICONTROL New profile]**. Scopri come creare un nuovo **[!UICONTROL New profile]** nella [documentazione di Admin Console](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html?lang=it#ui){target="_blank"}.
1. Dalla sezione **[!UICONTROL Permissions]**, seleziona **[!UICONTROL Property Rights]**.
1. Fai clic su **[!UICONTROL Add all]**. Questo aggiungerà il seguente diritto al tuo profilo di prodotto:
   * **[!UICONTROL Approve]**
   * **[!UICONTROL Develop]**
   * **[!UICONTROL Edit Property]**
   * **[!UICONTROL Manage Environments]**
   * **[!UICONTROL Manage Extensions]**
   * **[!UICONTROL Publish]**

   Queste autorizzazioni sono necessarie per installare e pubblicare l&#39;estensione Adobe Campaign e pubblicare la proprietà app in **Adobe Experience Platform Mobile SDK**.

1. Selezionare **[!UICONTROL Company rights]** nel menu a sinistra.
1. Aggiungi i seguenti diritti:

   * **[!UICONTROL Manage App Configurations]**
   * **[!UICONTROL Manage Properties]**

   Queste autorizzazioni sono necessarie per consentire allo sviluppatore di app mobili di impostare le credenziali push in **Raccolta dati Adobe Experience Platform**.

1. Fai clic su **[!UICONTROL Save]**.

Per assegnare **[!UICONTROL Product profile]** agli utenti, eseguire la procedura seguente:

1. Accedere a **[!DNL Admin Console]**.
1. Dalla scheda **[!UICONTROL Products]**, seleziona la scheda **[!UICONTROL Adobe Experience Platform Data Collection]**.
1. Seleziona la **[!UICONTROL Product profile]** configurata in precedenza.
1. Dalla scheda **[!UICONTROL Users]**, fai clic su **[!UICONTROL Add user]**.
1. Digita il nome o l’indirizzo e-mail dell’utente e selezionalo. Quindi fare clic su **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Se l&#39;utente non è stato creato in precedenza in Admin Console, consulta la [documentazione sull&#39;aggiunta di utenti](https://helpx.adobe.com/it/enterprise/using/manage-users-individually.html#add-users){target="_blank"}.

### Configurare l’app {#configure-app}

La configurazione tecnica prevede una stretta collaborazione tra lo sviluppatore dell’app e l’amministratore aziendale. Prima di iniziare a inviare notifiche push con [!DNL Adobe Campaign], è necessario definire le impostazioni in [!DNL Adobe Experience Platform Data Collection] e integrare l&#39;app mobile con gli SDK di Adobe Experience Platform Mobile.

Segui i passaggi di implementazione descritti nei collegamenti seguenti:

* Per **Apple iOS**: scopri come registrare la tua app con APN nella [documentazione di Apple](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}
* Per **Google Android**: scopri come configurare un&#39;app client Firebase Cloud Messaging su Android nella [documentazione di Google](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}

<!--
## Add your app push credentials in Adobe Experience Platform Data Collection {#push-credentials}

After granting the correct user permissions, you now need to add your mobile application push credentials in Adobe Experience Platform Data Collection. 

The mobile app push credential registration is required to authorize Adobe to send push notifications on your behalf. Refer to the steps detailed below:

1. From [!DNL Adobe Experience Platform Data Collection], browse to **[!UICONTROL App Surfaces]** in the left rail.

1. Click **[!UICONTROL Create App Surface]** to create a new configuration.

1. Enter a **[!UICONTROL Name]** for the configuration.

1. From **[!UICONTROL Mobile Application Configuration]**, select the system and enter settings.

    * **For iOS**

        1. Enter the mobile app **Bundle Id** in the **[!UICONTROL App ID (iOS Bundle ID)]** field. The app Bundle ID can be found in the **General** tab of the primary target in **XCode**.
        
        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.
        
        1. Drag and drop your .p8 Apple Push Notification Authentication Key file. This key can be acquired from the **Certificates**, **Identifiers** and **Profiles** page.

        1. Provide the **Key ID**. This is a 10 character string assigned during the creation of p8 auth key. It can be found under **Keys** tab in **Certificates**, **Identifiers** and **Profiles** page.
        
        1. Provide the **Team ID**. This is a string value which can be found under the Membership tab.

    * **For Android**

        1. Provide the **[!UICONTROL App ID (Android package name)]**: usually the package name is the app id in your `build.gradle` file.

        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.

        1. Drag and drop the FCM push credentials. For more details on how to get the push credentials refer to [Google Documentation](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.
    

1. Click **[!UICONTROL Save]** to create your app configuration.
-->

## Configurare una proprietà di tag mobile in Raccolta dati di Adobe Experience Platform {#launch-property}

Configurare una proprietà mobile consente allo sviluppatore di app mobili o all’addetto al marketing di configurare gli SDK per dispositivi mobili. In genere si crea una proprietà mobile per ogni applicazione mobile che si desidera gestire. Scopri come creare e configurare una proprietà mobile nella [documentazione di Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.
<!--
To get the SDKs needed for push notification to work you will need the following SDK extensions, for both Android and iOS:

* **[!UICONTROL Mobile Core]** (installed automatically)
* **[!UICONTROL Profile]** (installed automatically)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optional but recommended to debug the mobile implementation.
-->

Ulteriori informazioni su [!DNL Adobe Experience Platform Data Collection] tag nella [documentazione di Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html?lang=it){target="_blank"}.

Una volta creata, apri la nuova proprietà tag e crea una libreria. Per eseguire questa operazione:

1. Passa a **Flusso di pubblicazione** nell&#39;area di navigazione a sinistra e seleziona **Aggiungi libreria**.
1. Immetti il nome della libreria e seleziona l’ambiente.
1. Selezionare **Aggiungi tutte le risorse modificate** e **Salva e genera nello sviluppo**.
1. Infine, impostare questa libreria come libreria di lavoro dal pulsante **Seleziona una libreria di lavoro**.

## Configurare i servizi mobili in Campaign {#push-service}

Dopo aver configurato l&#39;app mobile in [!DNL Adobe Experience Platform Data Collection], è necessario creare due servizi (uno per i dispositivi iOS e uno per i dispositivi Android) per poter inviare notifiche push da **[!DNL Adobe Campaign]**.

Le notifiche push vengono inviate agli utenti dell’app tramite un servizio dedicato. Quando gli utenti installano l’app, si abbonano a questo servizio: Adobe Campaign si basa su questo servizio per eseguire il targeting solo per gli abbonati dell’app. In questo servizio, devi aggiungere le app iOS e Android da inviare su dispositivi iOS e Android.

Per creare un servizio per l’invio di notifiche push, effettua le seguenti operazioni:

1. Passare alla scheda **[!UICONTROL Profiles and Targets > Services and Subscriptions]** e fare clic su **[!UICONTROL Create]**.

   ![](assets/new-service-push.png){width="800" align="left"}

1. Immettere **[!UICONTROL Label]** e **[!UICONTROL Internal name]** e selezionare un tipo **[!UICONTROL Mobile application]**.

   >[!NOTE]
   >
   >Il mapping di destinazione predefinito **[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]** è collegato alla tabella dei destinatari. Se si desidera utilizzare una mappatura di destinazione diversa, è necessario creare una nuova mappatura di destinazione e immetterla nel campo **[!UICONTROL Target mapping]** del servizio. Ulteriori informazioni sulle mappature di destinazione in [questa pagina](../audiences/target-mappings.md).

1. Quindi utilizza l&#39;icona **[!UICONTROL Add]** a destra per definire le applicazioni mobili che utilizzano questo servizio.

>[!BEGINTABS]

>[!TAB iOS]

Per creare un&#39;app per dispositivi iOS, effettua le seguenti operazioni:

1. Seleziona **[!UICONTROL Create an iOS application]** e fai clic su **[!UICONTROL Next]**.

   ![](assets/new-ios-app.png){width="600" align="left"}

1. Immettere il nome dell&#39;app nel campo **[!UICONTROL Label]**.
1. (facoltativo) È possibile arricchire il contenuto di un messaggio push con alcuni **[!UICONTROL Application variables]**. Questi sono completamente personalizzabili e fanno parte del payload del messaggio inviato al dispositivo mobile.

   Nell&#39;esempio seguente, le variabili **mediaURl** e **mediaExt** vengono aggiunte per creare notifiche push potenziate e quindi forniscono all&#39;applicazione l&#39;immagine da visualizzare all&#39;interno della notifica.

   ![](assets/ios-app-parameters.png){width="600" align="left"}

1. Passare alla scheda **[!UICONTROL Subscription parameters]** per definire il mapping con un&#39;estensione dello schema **[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]**.

1. Passare alla scheda **[!UICONTROL Sounds]** per definire un suono da riprodurre. Fare clic su **[!UICONTROL Add]** e compilare il campo **[!UICONTROL Internal name]** che deve contenere il nome del file incorporato nell&#39;applicazione o il nome del suono di sistema.

1. Fare clic su **[!UICONTROL Next]** per avviare la configurazione dell&#39;applicazione di sviluppo.

1. La chiave di integrazione è specifica per ogni applicazione. Collega l’app mobile ad Adobe Campaign.

   Assicurati che lo stesso **[!UICONTROL Integration key]** sia definito in Adobe Campaign e nel codice dell&#39;applicazione tramite SDK.

   Ulteriori informazioni sono disponibili nella [documentazione per sviluppatori](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > **[!UICONTROL Integration key]** è completamente personalizzabile con valore stringa, ma deve essere esattamente lo stesso specificato in SDK.
   >
   > Non è possibile utilizzare lo stesso certificato per la versione di sviluppo (sandbox) e la versione di produzione dell’applicazione.

1. Seleziona l&#39;icona dal campo **[!UICONTROL Application icon]** per personalizzare l&#39;app mobile nel servizio.

1. Seleziona **[!UICONTROL Authentication mode]**. Sono disponibili due modalità:

   * (Consigliato) **[!UICONTROL Token-based authentication]**: inserisci le impostazioni di connessione APNs **[!UICONTROL Key Id]**, **[!UICONTROL Team Id]** e **[!UICONTROL Bundle Id]**, quindi seleziona il certificato p8 facendo clic su **[!UICONTROL Enter the private key...]**. Per ulteriori informazioni su **[!UICONTROL Token-based authentication]**, consulta [Documentazione di Apple](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns){target="_blank"}.

   * **[!UICONTROL Certificate-based authentication]**: fare clic su **[!UICONTROL Enter the certificate...]**, quindi selezionare la chiave p12 e immettere la password fornita dallo sviluppatore dell&#39;app mobile. Tieni presente che questo certificato ha una data di scadenza e deve essere rinnovato su base annuale. Per evitare interruzioni del servizio per gli utenti, aggiorna i certificati prima della scadenza. I certificati sono validi per un anno e devi aggiornarli per continuare a comunicare con i numeri APN.

1. Utilizza il pulsante **[!UICONTROL Test the connection]** per convalidare la configurazione.

1. Fare clic su **[!UICONTROL Next]** per avviare la configurazione dell&#39;applicazione di produzione e seguire gli stessi passaggi descritti in precedenza.

1. Fai clic su **[!UICONTROL Finish]**.

L’applicazione iOS è ora pronta per essere utilizzata in Campaign.

>[!TAB Android]

Per creare un&#39;app per dispositivi Android, effettua le seguenti operazioni:

1. Seleziona **[!UICONTROL Create an Android application]** e fai clic su **[!UICONTROL Next]**.

   ![](assets/new-android-app.png){width="600" align="left"}

1. Immettere il nome dell&#39;app nel campo **[!UICONTROL Label]**.
1. La chiave di integrazione è specifica per ogni applicazione. Collega l’app mobile ad Adobe Campaign.

   Assicurati che lo stesso **[!UICONTROL Integration key]** sia definito in Adobe Campaign e nel codice dell&#39;applicazione tramite SDK.

   Ulteriori informazioni sono disponibili nella [documentazione per sviluppatori](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > **[!UICONTROL Integration key]** è completamente personalizzabile con valore stringa, ma deve essere esattamente lo stesso specificato in SDK.
   >

1. Seleziona l&#39;icona dal campo **[!UICONTROL Application icon]** per personalizzare l&#39;app mobile nel servizio.
1. Selezionare **HTTP v1** nell&#39;elenco a discesa **[!UICONTROL API version]**.
1. Fai clic sul collegamento **[!UICONTROL Load project json file to extract project details...]** per caricare il file di chiave JSON. Per ulteriori informazioni su come estrarre il file JSON, consulta la [documentazione di Google Firebase](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

   È inoltre possibile immettere manualmente i seguenti dettagli:
   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

1. Utilizza il pulsante **[!UICONTROL Test the connection]** per convalidare la configurazione.

   >[!CAUTION]
   >
   >Il pulsante **[!UICONTROL Test connection]** non verifica se il server MID (mid-sourcing) ha accesso al server FCM.

1. (facoltativo) Se necessario, puoi arricchire il contenuto di un messaggio push con alcuni **[!UICONTROL Application variables]**. Questi sono completamente personalizzabili e fanno parte del payload del messaggio inviato al dispositivo mobile.

1. Fare clic su **[!UICONTROL Finish]** e quindi su **[!UICONTROL Save]**. L’applicazione Android è ora pronta per essere utilizzata in Campaign.

Di seguito sono riportati i nomi del payload FCM per personalizzare ulteriormente la notifica push:

| Tipo di messaggio | Elemento del messaggio configurabile (nome del payload FCM) | Opzioni configurabili (nome payload FCM) |
|:-:|:-:|:-:|
| messaggio dati | N/D | validate_only |
| messaggio di notifica | titolo, corpo, android_channel_id, icona, suono, tag, colore, click_action, immagine, ticker, fisso, visibilità, notification_priority, notification_count <br> | validate_only |


>[!ENDTABS]

## Configurare l’estensione Adobe Campaign nella proprietà mobile {#configure-extension}

L&#39;estensione **Adobe Campaign Classic** per gli SDK Adobe Experience Platform Mobile potenzia le notifiche push per le app mobili e ti aiuta a raccogliere i token push degli utenti e a gestire la misurazione delle interazioni con i servizi Adobe Experience Platform.

Questa estensione, che si applica sia a Campaign Classic v7 che a Campaign v8, è preinstallata nell’ambiente e deve essere configurata. Per configurare l&#39;estensione per la proprietà tag per dispositivi mobili, effettua le seguenti operazioni:

1. Apri la proprietà tag creata in precedenza.
1. Dalla navigazione a sinistra, passa a **Estensioni** e apri la scheda **Catalogo**. Utilizza il campo di ricerca per trovare l&#39;estensione **Adobe Campaign Classic**.
1. Dalla scheda Campaign Classic, fai clic sul pulsante **Installa**.
1. Immetti le impostazioni come descritto nella [documentazione di Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

Ora puoi aggiungere Campaign all&#39;app, come descritto nella [documentazione di Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.
