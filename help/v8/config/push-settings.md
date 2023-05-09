---
title: Integrare l’SDK di AEP e Campaign
description: Scopri come integrare l’SDK di Adobe Experience Platform Mobile con la tua app.
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e3ea361cc486096fe6c19ac469e8a71b636371ac
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 2%

---


# SDK AEP + Campaign: configurare il canale di notifica push {#push-notification-configuration}

Prima di iniziare a inviare notifiche push con Adobe Campaign, devi accertarti che le configurazioni e le integrazioni siano presenti nell’app mobile e per i tag in Adobe Experience Platform.... .... ....


## Prima di iniziare {#before-starting}

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

### Integrare la tua app mobile con l’SDK di Adobe Experience Platform {#integrate-mobile-app}

L’SDK di Adobe Experience Platform Mobile fornisce API di integrazione lato client per i dispositivi mobili tramite SDK compatibili con Android e iOS. Segui [Documentazione di Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} per effettuare la configurazione con gli SDK di Adobe Experience Platform Mobile nella tua app.

Alla fine di questo, avresti dovuto anche creare e configurare una proprietà mobile in [!DNL Adobe Experience Platform Data Collection]. In genere creerai una proprietà mobile per ogni app mobile che desideri gestire. Scopri come creare e configurare una proprietà mobile in [Documentazione di Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.


## Passaggio 1: Aggiungere le credenziali push dell&#39;app nella raccolta dati di Adobe Experience Platform {#push-credentials}

Dopo aver concesso le autorizzazioni utente corrette, ora devi aggiungere le credenziali push dell’app mobile nella raccolta dati di Adobe Experience Platform.

La registrazione delle credenziali push dell’app mobile è necessaria per autorizzare l’Adobe a inviare notifiche push per tuo conto. Fai riferimento ai passaggi descritti di seguito:

1. Da [!DNL Adobe Experience Platform Data Collection], sfoglia fino a **[!UICONTROL App Surfaces]** nella barra a sinistra.

1. Fai clic su **[!UICONTROL Create App Surface]** per creare una nuova configurazione.

1. Inserisci un **[!UICONTROL Name]** per la configurazione.

1. Da **[!UICONTROL Mobile Application Configuration]**, selezionare il sistema operativo:

   * **Per iOS**

      1. Immetti l’app mobile **Id Bundle** in **[!UICONTROL App ID (iOS Bundle ID)]** campo . L’ID bundle dell’app si trova nella sezione **Generale** scheda del target principale in **XCode**.

      1. Acceso il **[!UICONTROL Push Credentials]** per aggiungere le credenziali.

      1. Trascina e rilascia il file .p8 Apple Push Notification Authentication Key . Questa chiave può essere acquisita dalla **Certificati**, **Identificatori** e **Profili** pagina.

      1. Fornisci **ID chiave**. Si tratta di una stringa di 10 caratteri assegnata durante la creazione della chiave di autenticazione p8. Si trova in **Chiavi** scheda in **Certificati**, **Identificatori** e **Profili** pagina.

      1. Fornisci **ID team**. Questo è un valore di stringa che si trova nella scheda Appartenenza.
   * **Per Android**

      1. Fornisci **[!UICONTROL App ID (Android package name)]**: in genere il nome del pacchetto è l&#39;ID app nel tuo `build.gradle` file.

      1. Acceso il **[!UICONTROL Push Credentials]** per aggiungere le credenziali.

      1. Trascina e rilascia le credenziali push FCM. Per ulteriori dettagli su come ottenere le credenziali push, consulta [Documentazione di Google](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.



1. Fai clic su **[!UICONTROL Save]** per creare la configurazione dell’app.


## Passaggio 2: Impostare una proprietà tag mobile in Adobe Experience Platform Data Collection {#launch-property}

La configurazione di una proprietà mobile consente allo sviluppatore o all’addetto al marketing dell’app mobile di configurare gli attributi degli SDK per dispositivi mobili, ad esempio Timeout sessione, e [!DNL Adobe Experience Platform] sandbox di destinazione e **[!UICONTROL Adobe Experience Platform Datasets]** da utilizzare per l’SDK mobile per l’invio di dati a .

Per ulteriori dettagli e procedure su come impostare un **proprietà mobile** , fai riferimento ai passaggi descritti in [Documentazione di Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.

Per far funzionare gli SDK necessari per la notifica push, avrai bisogno delle seguenti estensioni SDK, sia per Android che per iOS:

* **[!UICONTROL Mobile Core]** (installato automaticamente)
* **[!UICONTROL Profile]** (installato automaticamente)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, facoltativo ma consigliato per eseguire il debug dell’implementazione mobile.

Ulteriori informazioni [!DNL Adobe Experience Platform Data Collection] tag in [Documentazione di Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

Una volta creata, apri la nuova proprietà tag e crea una libreria. Per eseguire questa operazione:

1. Sfoglia per **Flusso di pubblicazione** nella navigazione a sinistra e seleziona **Aggiungi libreria**.
1. Immetti il nome della libreria e seleziona l’ambiente .
1. Seleziona **Aggiungi tutte le risorse modificate** e **Salva e genera in sviluppo**.
1. Infine, imposta questa libreria come libreria di lavoro dal **Selezionare una libreria di lavoro** pulsante .


## Passaggio 3: Configura l’estensione Adobe Campaign nella tua proprietà mobile {#configure-extension}

La **Estensione Adobe Campaign Classic** per gli SDK di Adobe Experience Platform Mobile puoi abilitare le notifiche push per le tue app mobili e aiutarti a raccogliere i token push degli utenti e a gestire la misurazione delle interazioni con Adobe Experience Platform Services.

Questa estensione è preinstallata nel tuo ambiente e deve essere configurata. Per configurare l’estensione per la proprietà del tag mobile, segui questi passaggi:

1. Apri la proprietà tag creata in precedenza.
1. Dalla navigazione a sinistra, cerca **Estensioni**, e apri la **Catalogo** scheda . Utilizza il campo di ricerca per trovare il **Adobe Campaign Classic** estensione.
1. Dalla scheda Campaign Classic, fai clic su **Installa** pulsante .
1. Immetti le impostazioni come descritto in [Documentazione di Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

Ora puoi aggiungere Campaign alla tua app, come descritto in  [Documentazione di Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Passaggio 4: Configurare i servizi mobili in Campaign{#push-service}

Una volta che l’app mobile è stata configurata in [!DNL Adobe Experience Platform Data Collection], devi creare due servizi (uno per i dispositivi iOS, uno per i dispositivi Android) per poter inviare notifiche push da **[!DNL Adobe Campaign]**.

Scopri come creare e configurare un servizio per le notifiche push iOS e Android in [questa sezione](../send/push.md#push-config).
