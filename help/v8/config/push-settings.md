---
title: Integrare l’SDK di AEP e Campaign
description: Scopri come integrare l’SDK di Adobe Experience Platform Mobile con la tua app.
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: ff6990f3db1122670bff4919f417b9f9f04d3183
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 2%

---


# SDK AEP + Campaign: configurare il canale di notifica push {#push-notification-configuration}

Prima di iniziare a inviare notifiche push con Adobe Campaign, devi accertarti che le configurazioni e le integrazioni siano presenti nell’app mobile e per i tag in Adobe Experience Platform.

L’SDK di Adobe Experience Platform Mobile fornisce API di integrazione lato client per i dispositivi mobili tramite SDK compatibili con Android e iOS.

Per configurare la tua app con gli SDK di Adobe Experience Platform Mobile, segui questi passaggi:

1. Controlla [prerequisiti](#before-starting).
1. Imposta un [proprietà tag mobile](#launch-property) nella raccolta dati di Adobe Experience Platform.
1. Scarica l&#39;SDK di Adobe Experience Platform Mobile come descritto [in questa pagina](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}.
1. (facoltativo) Abilita la registrazione e le metriche del ciclo di vita, come descritto [in questa pagina](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}.
1. (facoltativo) Aggiungi [Adobe Experience Platform Assurance nella tua app](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"} to validate your implementation. Learn how to implement Adobe Experience Platform Assurance extension [in this page](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}.
1. Segui [Documentazione di Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} per effettuare la configurazione con gli SDK di Adobe Experience Platform Mobile nella tua app.
1. Installare e configurare [Estensione Adobe Campaign](#configure-extension) nella proprietà mobile.
1. Configura iOS e i servizi mobili Android in Adobe Campaign come dettagliato [in questa pagina](../send/push.md#push-config).


## Prerequisiti {#before-starting}

### Impostare le autorizzazioni {#setup-permissions}

Prima di creare un’app mobile, è necessario assicurarsi di disporre o assegnare le autorizzazioni utente corrette per i tag in Adobe Experience Platform. Le autorizzazioni utente per i tag in Adobe Experience Platform vengono assegnate agli utenti tramite Adobe Admin Console. Ulteriori informazioni in [Documentazione sui tag](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}.

>[!CAUTION]
>
>La configurazione push deve essere eseguita da un utente esperto. A seconda del modello di implementazione e degli utenti tipo coinvolti in questa implementazione, potrebbe essere necessario assegnare l’intero set di autorizzazioni a un singolo profilo di prodotto o condividere le autorizzazioni tra lo sviluppatore dell’app e l’ **Adobe Campaign** amministratore.

Per assegnare **Proprietà** e **Azienda** diritti, segui i passaggi seguenti:

1. Accedere al **[!DNL Admin Console]**.
1. Da **[!UICONTROL Products]** seleziona la scheda **[!UICONTROL Adobe Experience Platform Data Collection]** il Card.
1. Seleziona un **[!UICONTROL Product Profile]** o creane uno nuovo con il **[!UICONTROL New profile]** pulsante . Scopri come creare un nuovo **[!UICONTROL New profile]** in [Documentazione di Admin Console](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"}.
1. Dalla sezione **[!UICONTROL Permissions]**, seleziona **[!UICONTROL Property Rights]**.
1. Fai clic su **[!UICONTROL Add all]**. Questo aggiungerà il seguente diritto al tuo profilo di prodotto:
   * **[!UICONTROL Approve]**
   * **[!UICONTROL Develop]**
   * **[!UICONTROL Edit Property]**
   * **[!UICONTROL Manage Environments]**
   * **[!UICONTROL Manage Extensions]**
   * **[!UICONTROL Publish]**

   Queste autorizzazioni sono necessarie per installare e pubblicare l&#39;estensione Adobe Campaign e la proprietà dell&#39;app in **Adobe Experience Platform Mobile SDK**.

1. Quindi, seleziona **[!UICONTROL Company rights]** nel menu a sinistra.
1. Aggiungi i seguenti diritti:

   * **[!UICONTROL Manage App Configurations]**
   * **[!UICONTROL Manage Properties]**

   Queste autorizzazioni sono necessarie affinché lo sviluppatore di app mobili possa impostare le credenziali push in **Raccolta dati Adobe Experience Platform**.

1. Fai clic su **[!UICONTROL Save]**.

Per assegnare questo **[!UICONTROL Product profile]** per gli utenti, segui i passaggi seguenti:

1. Accedere al **[!DNL Admin Console]**.
1. Da **[!UICONTROL Products]** seleziona la scheda **[!UICONTROL Adobe Experience Platform Data Collection]** il Card.
1. Seleziona la **[!UICONTROL Product profile]** configurata in precedenza.
1. Dalla scheda **[!UICONTROL Users]**, fai clic su **[!UICONTROL Add user]**.
1. Digita il nome o l’indirizzo e-mail dell’utente e seleziona l’utente. Quindi, fai clic su **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Se l’utente non è stato creato in precedenza in Admin Console, consulta la [Aggiungere la documentazione degli utenti](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"}.

### Configurare l’app {#configure-app}

La configurazione tecnica prevede una stretta collaborazione tra lo sviluppatore dell’app e l’amministratore aziendale. Prima di iniziare a inviare notifiche push con [!DNL Adobe Campaign], è necessario definire le impostazioni in [!DNL Adobe Experience Platform Data Collection] e integra la tua app mobile con gli SDK di Adobe Experience Platform Mobile.

Segui i passaggi di implementazione descritti nei collegamenti seguenti:

* Per **Apple iOS**: Scopri come registrare l’app con APN in [Documentazione di Apple](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}
* Per **Google Android**: Scopri come configurare un’app client Firebase Cloud Messaging su Android in [Documentazione di Google](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}

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

## Impostare una proprietà tag mobile in Adobe Experience Platform Data Collection {#launch-property}

L’impostazione di una proprietà mobile consente allo sviluppatore o all’addetto al marketing dell’app mobile di configurare gli SDK per dispositivi mobili. In genere creerai una proprietà mobile per ogni app mobile che desideri gestire. Scopri come creare e configurare una proprietà mobile in [Documentazione di Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.
<!--
To get the SDKs needed for push notification to work you will need the following SDK extensions, for both Android and iOS:

* **[!UICONTROL Mobile Core]** (installed automatically)
* **[!UICONTROL Profile]** (installed automatically)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optional but recommended to debug the mobile implementation.
-->

Ulteriori informazioni [!DNL Adobe Experience Platform Data Collection] tag in [Documentazione di Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

Una volta creata, apri la nuova proprietà tag e crea una libreria. Per eseguire questa operazione:

1. Sfoglia per **Flusso di pubblicazione** nella navigazione a sinistra e seleziona **Aggiungi libreria**.
1. Immetti il nome della libreria e seleziona l’ambiente .
1. Seleziona **Aggiungi tutte le risorse modificate** e **Salva e genera in sviluppo**.
1. Infine, imposta questa libreria come libreria di lavoro dal **Selezionare una libreria di lavoro** pulsante .


## Configura l’estensione Adobe Campaign nella tua proprietà mobile {#configure-extension}

La **Estensione Adobe Campaign Classic** per gli SDK di Adobe Experience Platform Mobile puoi abilitare le notifiche push per le tue app mobili e aiutarti a raccogliere i token push degli utenti e a gestire la misurazione delle interazioni con Adobe Experience Platform Services.

Questa estensione, valida sia per Campaign Classic v7 che per Campaign v8, è preinstallata nel tuo ambiente e deve essere configurata. Per configurare l’estensione per la proprietà del tag mobile, segui questi passaggi:

1. Apri la proprietà tag creata in precedenza.
1. Dalla navigazione a sinistra, cerca **Estensioni**, e apri la **Catalogo** scheda . Utilizza il campo di ricerca per trovare il **Adobe Campaign Classic** estensione.
1. Dalla scheda Campaign Classic, fai clic su **Installa** pulsante .
1. Immetti le impostazioni come descritto in [Documentazione di Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

Ora puoi aggiungere Campaign alla tua app, come descritto in  [Documentazione di Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Configurare i servizi mobili in Campaign{#push-service}

Una volta che l’app mobile è stata configurata in [!DNL Adobe Experience Platform Data Collection], devi creare due servizi (uno per i dispositivi iOS, uno per i dispositivi Android) per poter inviare notifiche push da **[!DNL Adobe Campaign]**.

Scopri come creare e configurare un servizio per le notifiche push iOS e Android in [questa sezione](../send/push.md#push-config).
