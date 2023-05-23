---
title: Inviare notifiche push con Adobe Campaign
description: Introduzione alle notifiche push in Campaign
feature: Push
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: e7c255d30e38c4e17779ef820e8984668ac5d48b
workflow-type: tm+mt
source-wordcount: '1671'
ht-degree: 4%

---

# Creare e inviare notifiche push{#push-notifications-create}

Le consegne tramite app mobile ti consentono di inviare notifiche ai dispositivi iOS e Android.

Per inviare notifiche push in Adobe Campaign, devi:

1. Integra l’SDK con la tua app. [Ulteriori informazioni](#push-sdk)
1. Crea un servizio di informazioni di tipo app mobile per la tua app mobile e aggiungi le versioni iOS e Android dell’applicazione a tale servizio. [Ulteriori informazioni](#push-config)
1. Crea una consegna sia per iOS che per Android. [Ulteriori informazioni](#push-create)

## Integrare l’SDK {#push-sdk}

Per inviare notifiche push con Adobe Campaign, devi configurare l’estensione Adobe Campaign nell’interfaccia utente di raccolta dati dell’SDK di Adobe Experience Platform Mobile.

L’SDK di Adobe Experience Platform Mobile aiuta ad alimentare soluzioni e servizi di Experience Cloud di Adobe nelle app mobili. La configurazione degli SDK viene gestita tramite l’interfaccia utente di Data Collection per una configurazione flessibile e integrazioni estensibili basate su regole.

[Ulteriori informazioni sono disponibili nella documentazione di Adobe Developer](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic){target="_blank"}.


## Configurare le impostazioni app in Campaign{#push-config}

Prima di inviare le notifiche push, devi definire le impostazioni delle app iOS e Android in Adobe Campaign.

Le notifiche push vengono inviate agli utenti dell’app tramite un servizio dedicato. Quando gli utenti installano l’app, si abbonano a questo servizio: Adobe Campaign si basa su questo servizio per eseguire il targeting solo per gli abbonati dell’app. In questo servizio, devi aggiungere le app iOS e Android da inviare su dispositivi iOS e Android.

Per creare un servizio per l’invio di notifiche push, effettua le seguenti operazioni:

1. Sfoglia per **[!UICONTROL Profiles and Targets > Services and Subscriptions]** e fai clic su **[!UICONTROL Create]**.

   ![](assets/new-service-push.png){width="800" align="left"}

1. Immetti un **[!UICONTROL Label]** e un **[!UICONTROL Internal name]**, e seleziona un **[!UICONTROL Mobile application]** tipo.

   >[!NOTE]
   >
   >Il valore predefinito **[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]** la mappatura di destinazione è collegata alla tabella dei destinatari. Se desideri utilizzare una mappatura di destinazione diversa, devi creare una nuova mappatura di destinazione e immetterla nella **[!UICONTROL Target mapping]** del servizio. Ulteriori informazioni sulle mappature di destinazione in [questa pagina](../audiences/target-mappings.md).

1. Quindi utilizza **[!UICONTROL Add]** sulla destra per definire le applicazioni mobili che utilizzano questo servizio.

>[!BEGINTABS]

>[!TAB iOS]

Per creare un&#39;app per dispositivi iOS, effettua le seguenti operazioni:

1. Seleziona **[!UICONTROL Create an iOS application]** e fai clic su **[!UICONTROL Next]**.

   ![](assets/new-ios-app.png){width="600" align="left"}

1. Immetti il nome dell&#39;app in **[!UICONTROL Label]** campo.
1. (facoltativo) Puoi arricchire il contenuto di un messaggio push con alcune **[!UICONTROL Application variables]**. Questi sono completamente personalizzabili e fanno parte del payload del messaggio inviato al dispositivo mobile.

   Nell’esempio seguente, il **mediaURl** e **mediaExt** Le variabili vengono aggiunte per creare notifiche push potenziate e quindi forniscono all’applicazione l’immagine da visualizzare all’interno della notifica.

   ![](assets/ios-app-parameters.png){width="600" align="left"}

1. Accedi a **[!UICONTROL Subscription parameters]** per definire la mappatura con un’estensione del **[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]** schema.

1. Accedi a **[!UICONTROL Sounds]** per definire un suono da riprodurre. Clic **[!UICONTROL Add]** e riempimento **[!UICONTROL Internal name]** che deve contenere il nome del file incorporato nell&#39;applicazione o il nome del suono di sistema.

1. Clic **[!UICONTROL Next]** per avviare la configurazione dell&#39;applicazione di sviluppo.

1. La chiave di integrazione è specifica per ogni applicazione. Collega l’app mobile ad Adobe Campaign.

   Assicurati che lo stesso **[!UICONTROL Integration key]** è definito in Adobe Campaign e nel codice dell’applicazione tramite l’SDK.

   Ulteriori informazioni in [la documentazione per gli sviluppatori](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > Il **[!UICONTROL Integration key]** è completamente personalizzabile con un valore stringa, ma deve essere esattamente lo stesso specificato nell’SDK.
   >
   > Non è possibile utilizzare lo stesso certificato per la versione di sviluppo (sandbox) e la versione di produzione dell’applicazione.

1. Seleziona l’icona dal menu **[!UICONTROL Application icon]** per personalizzare l’app mobile nel servizio.

1. Seleziona **[!UICONTROL Authentication mode]**. Sono disponibili due modalità:

   * (Consigliato) **[!UICONTROL Token-based authentication]**: inserisci le impostazioni di connessione APNs **[!UICONTROL Key Id]**, **[!UICONTROL Team Id]** e **[!UICONTROL Bundle Id]** quindi seleziona il certificato p8 facendo clic su **[!UICONTROL Enter the private key...]**. Per ulteriori informazioni su **[!UICONTROL Token-based authentication]**, fare riferimento a [Documentazione di Apple](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns){target="_blank"}.

   * **[!UICONTROL Certificate-based authentication]**: fai clic **[!UICONTROL Enter the certificate...]**  quindi seleziona la chiave p12 e immetti la password fornita dallo sviluppatore dell’app mobile.
   Puoi modificare la modalità di autenticazione in un secondo momento nel **[!UICONTROL Certificate]** della tua app mobile.

1. Utilizza il **[!UICONTROL Test the connection]** per convalidare la configurazione.

1. Clic **[!UICONTROL Next]** per iniziare a configurare l’applicazione di produzione e seguire gli stessi passaggi descritti in precedenza.

1. Fai clic su **[!UICONTROL Finish]**.

L’applicazione iOS è ora pronta per essere utilizzata in Campaign.

>[!TAB Android]

Per creare un&#39;app per dispositivi Android, effettua le seguenti operazioni:

1. Seleziona **[!UICONTROL Create an Android application]** e fai clic su **[!UICONTROL Next]**.

   ![](assets/new-android-app.png){width="600" align="left"}

1. Immetti il nome dell&#39;app in **[!UICONTROL Label]** campo.
1. La chiave di integrazione è specifica per ogni applicazione. Collega l’app mobile ad Adobe Campaign.

   Assicurati che lo stesso **[!UICONTROL Integration key]** è definito in Adobe Campaign e nel codice dell’applicazione tramite l’SDK.

   Ulteriori informazioni in [la documentazione per gli sviluppatori](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > Il **[!UICONTROL Integration key]** è completamente personalizzabile con un valore stringa, ma deve essere esattamente lo stesso specificato nell’SDK.

1. Seleziona l’icona dal menu **[!UICONTROL Application icon]** per personalizzare l’app mobile nel servizio.
1. Seleziona **HTTP v1** in  **[!UICONTROL API version]** elenco a discesa.
1. Clic **[!UICONTROL Load project json file to extract project details...]** collegamento per caricare il file di chiave JSON. Per ulteriori informazioni su come estrarre il file JSON, consulta [Documentazione di Google Firebase](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

   È inoltre possibile immettere manualmente i seguenti dettagli:
   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

1. Utilizza il **[!UICONTROL Test the connection]** per convalidare la configurazione.

   >[!CAUTION]
   >
   >Il **[!UICONTROL Test connection]** non verifica se il server MID ha accesso al server FCM.

1. (facoltativo) Puoi arricchire il contenuto di un messaggio push con alcune **[!UICONTROL Application variables]** se necessario. Questi sono completamente personalizzabili e fanno parte del payload del messaggio inviato al dispositivo mobile.

1. Fai clic su **[!UICONTROL Finish]**, quindi su **[!UICONTROL Save]**. L’applicazione Android è ora pronta per essere utilizzata in Campaign.

Di seguito sono riportati i nomi del payload FCM per personalizzare ulteriormente la notifica push:

| Tipo di messaggio | Elemento del messaggio configurabile (nome del payload FCM) | Opzioni configurabili (nome payload FCM) |
|:-:|:-:|:-:|
| messaggio dati | N/D | validate_only |
| messaggio di notifica | titolo, corpo, android_channel_id, icona, suono, tag, colore, click_action, immagine, ticker, fisso, visibilità, notification_priority, notification_count <br> | validate_only |


>[!ENDTABS]


## Creare la prima notifica push{#push-create}

Questa sezione descrive gli elementi specifici per la consegna delle notifiche iOS e Android.

>[!CAUTION]
>
>Nell&#39;ambito di una [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), la registrazione mobile è ora **asincrono**. [Ulteriori informazioni](../architecture/staging.md)

Per creare una nuova consegna, passa a **[!UICONTROL Campaigns]** , fare clic su **[!UICONTROL Deliveries]** e fai clic su **[!UICONTROL Create]** sopra l’elenco delle consegne esistenti.

![](assets/delivery_step_1.png)

>[!BEGINTABS]

>[!TAB iOS]

Per inviare notifiche sui dispositivi iOS, effettua le seguenti operazioni:

1. Seleziona la **[!UICONTROL Deliver on iOS]** modello di consegna.

   ![](assets/push_ios_1.png)

1. Per definire il target della notifica, fai clic sul pulsante **[!UICONTROL To]** , quindi fai clic su **[!UICONTROL Add]**.

   ![](assets/push_ios_2.png)

1. Seleziona **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**, seleziona il servizio relativo all’app mobile, quindi seleziona la versione iOS dell’applicazione.

   ![](assets/push_ios_3.png)

1. Scegli il tuo **[!UICONTROL Notification type]** tra **[!UICONTROL General notification (Alert, Sound, Badge)]** o **[!UICONTROL Silent notification]**.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >Il **Push silenzioso** La modalità consente di inviare una notifica &quot;invisibile all’utente&quot; a un’app mobile. L’utente non viene informato dell’arrivo della notifica. Viene trasferito direttamente all’applicazione.

1. In **[!UICONTROL Title]** immettere l&#39;etichetta del titolo che si desidera visualizzare nell&#39;elenco delle notifiche disponibili dal centro notifiche.

   Questo campo ti consente di definire il valore del **titolo** parametro del payload di notifica di iOS.

1. Puoi aggiungere una **[!UICONTROL Subtitle]**, valore del **sottotitolo** parametro del payload di notifica di iOS.

1. Inserisci il contenuto del messaggio in **[!UICONTROL Message content]** sezione della procedura guidata.

1. Dalla sezione **[!UICONTROL Sound and Badge]** , è possibile modificare le seguenti opzioni:

   * **[!UICONTROL Clean Badge]**: abilita queste opzioni per aggiornare il valore del badge.

   * **[!UICONTROL Value]**: imposta un numero che verrà utilizzato per visualizzare direttamente sull’icona dell’applicazione il numero di nuove informazioni non lette.

   * **[!UICONTROL Critical alert mode]**: abilita questa opzione per aggiungere un suono alla notifica anche se il telefono dell’utente è impostato sulla modalità di attivazione o se l’iPhone è disattivato.

   * **[!UICONTROL Name]**: seleziona il suono che deve essere riprodotto dal terminale mobile quando viene ricevuta la notifica.

   * **[!UICONTROL Volume]**: volume del suono da 0 a 100.

      >[!NOTE]
      > 
      >I suoni devono essere inclusi nell&#39;applicazione e definiti al momento della creazione del servizio.
   ![](assets/push_ios_5.png)

1. Dalla sezione **[!UICONTROL Application variables]** , il tuo **[!UICONTROL Application variables]** vengono aggiunti automaticamente. Consentono di definire il comportamento di notifica; ad esempio, puoi configurare una schermata di un’applicazione specifica da visualizzare quando l’utente attiva la notifica.

1. Dalla sezione **[!UICONTROL Advanced]** , è possibile modificare le seguenti opzioni generali:

   * **[!UICONTROL Mutable content]**: abilita questa opzione per consentire all’app mobile di scaricare contenuti multimediali.

   * **[!UICONTROL Thread-id]**: identificatore utilizzato per raggruppare le notifiche correlate.

   * **[!UICONTROL Category]**: nome dell’ID categoria che visualizzerà i pulsanti di azione. Queste notifiche forniscono all’utente un modo più rapido per eseguire diverse attività in risposta a una notifica senza aprire o esplorare l’applicazione.

   ![](assets/push_ios_6.png)

1. Per le notifiche sensibili all’ora, puoi specificare le seguenti opzioni:

   * **[!UICONTROL Target content ID]**: identificatore utilizzato per individuare la finestra dell’applicazione da inoltrare quando viene aperta la notifica.

   * **[!UICONTROL Launch image]**: nome del file dell&#39;immagine di avvio da visualizzare. Se l’utente sceglie di avviare l’applicazione, viene visualizzata l’immagine selezionata invece della schermata di avvio dell’applicazione.

   * **[!UICONTROL Interruption level]**:

      * **[!UICONTROL Active]**: per impostazione predefinita, il sistema visualizza immediatamente la notifica, illumina lo schermo e può riprodurre un suono. Le notifiche non interrompono le modalità di attivazione.

      * **[!UICONTROL Passive]**: il sistema aggiunge la notifica all’elenco delle notifiche senza accendere lo schermo o riprodurre un suono. Le notifiche non interrompono le modalità di attivazione.

      * **[!UICONTROL Time sensitive]** Il sistema presenta immediatamente la notifica, accende lo schermo, può riprodurre un suono e interrompere le modalità di messa a fuoco. Questo livello non richiede un’autorizzazione speciale da Apple.

      * **[!UICONTROL Critical]** Il sistema visualizza immediatamente la notifica, illumina lo schermo e ignora le modalità di disattivazione audio o di messa a fuoco. Tieni presente che questo livello richiede un’autorizzazione speciale da parte di Apple.
   * **[!UICONTROL Relevance score]**: imposta un punteggio di rilevanza da 0 a 100. Il sistema utilizza questa funzione per ordinare le notifiche nel riepilogo delle notifiche.

   ![](assets/push_ios_7.png)

1. Una volta configurata la notifica, fai clic su **[!UICONTROL Preview]** per visualizzare l’anteprima della notifica.

   ![](assets/push-ios-preview.png)


>[!TAB Android]

Per inviare notifiche su dispositivi Android, effettua le seguenti operazioni:

1. Seleziona la **[!UICONTROL Deliver on Android (android)]** modello di consegna.

   ![](assets/push-template-android.png)

1. Per definire il target della notifica, fai clic sul pulsante **[!UICONTROL To]** , quindi fai clic su **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. Seleziona **[!UICONTROL Subscribers of an Android mobile application]**, scegli il servizio relativo alla tua app mobile (Neotrips, in questo caso), quindi seleziona la versione Android dell’applicazione.

   ![](assets/push-android-subscribers.png)

1. Quindi inserisci il contenuto per la notifica.

   ![](assets/push-android-content.png)

1. Fai clic su **[!UICONTROL Insert emoticon]** per inserire emoticon nella notifica push.

1. In **[!UICONTROL Application variables]** , immettere il valore di ciascuna variabile. Ad esempio, puoi configurare una schermata dell’applicazione specifica da visualizzare quando l’utente attiva la notifica.

1. Una volta configurata la notifica, fai clic su **[!UICONTROL Preview]** per visualizzare l’anteprima della notifica.

   <!--![](assets/push-android-preview.png)-->

>[!ENDTABS]


## Testare, inviare e monitorare le notifiche push

Per inviare una bozza e la consegna finale, utilizza lo stesso processo utilizzato per le altre consegne.

Scopri come convalidare una consegna in [questa pagina](preview-and-proof.md).

Scopri come confermare e inviare la consegna in [questa pagina](send.md)

Dopo aver inviato i messaggi, puoi monitorare e tenere traccia delle consegne. Ulteriori informazioni sui motivi degli errori di consegna delle notifiche push in [questa pagina](delivery-failures.md#push-error-types).

