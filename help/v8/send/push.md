---
title: Inviare notifiche push con Adobe Campaign
description: Introduzione alle notifiche push in Campaign
feature: Push
role: User
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 6d54f072ad0e67b435cd6e03433fa9ddd0794dea
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 11%

---

# Creare e inviare notifiche push{#push-notifications-create}

Le consegne tramite app mobile ti consentono di inviare notifiche ai dispositivi iOS e Android.

Prima di iniziare a inviare notifiche push con Adobe Campaign, è necessario assicurarsi che le configurazioni e le integrazioni siano attive nell’app mobile e per i tag in Adobe Experience Platform. [Ulteriori informazioni sulla configurazione push.](push-settings.md)

>[!CAUTION]
>
>Alcune modifiche importanti al servizio Android Firebase Cloud Messaging (FCM) saranno rilasciate nel 2024 e potrebbero influire sull’implementazione di Adobe Campaign. Per supportare questa modifica, potrebbe essere necessario aggiornare la configurazione dei servizi di abbonamento per i messaggi push Android. Puoi già verificare ed eseguire azioni. [Ulteriori informazioni](../../technotes/upgrades/push-technote.md).


## Creare la prima notifica push{#push-create}

Questa sezione descrive gli elementi specifici per la consegna delle notifiche iOS e Android.

>[!IMPORTANT]
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
   >Il **Push silenzioso** La modalità consente di inviare una notifica &quot;invisibile all’utente&quot; a un’app mobile. L’utente non viene informato dell’arrivo della notifica. Viene trasferita direttamente all’applicazione.

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
     >

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

      * **[!UICONTROL Active]**: per impostazione predefinita, il sistema visualizza immediatamente la notifica, illumina lo schermo e può riprodurre un suono. Le notifiche non interrompono le modalità Focus.

      * **[!UICONTROL Passive]**: il sistema aggiunge la notifica all’elenco delle notifiche senza accendere lo schermo o riprodurre un suono. Le notifiche non interrompono le modalità Focus.

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

