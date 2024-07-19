---
audience: end-user
title: Progettare una consegna di notifiche push potenziata
description: Scopri come progettare una consegna di notifiche push potenziata da Android con Adobe Campaign Web
feature: Push
role: User
level: Beginner
exl-id: 42e3623b-b401-4fcc-80a7-ea38347fddc6
source-git-commit: 5236cc94e78db11b8975ad84c49594b282fdecf3
workflow-type: tm+mt
source-wordcount: '1157'
ht-degree: 31%

---

# Progettare una consegna push potenziata per Android {#rich-push}

>[!AVAILABILITY]
>
>Questa funzionalità si trova in **Disponibilità limitata** (LA).

Con Firebase Cloud Messaging puoi scegliere tra due tipi di messaggi:

* **[!UICONTROL Data message]** è gestito dall&#39;app client. Questi messaggi vengono inviati direttamente all’app mobile, che genera e visualizza una notifica Android sul dispositivo. I messaggi di dati contengono solo variabili dell’applicazione personalizzate.

* **[!UICONTROL Notification message]**, gestito automaticamente dall&#39;SDK FCM. FCM mostra automaticamente il messaggio sui dispositivi degli utenti per conto dell’app client. I messaggi di notifica contengono un set preimpostato di parametri e opzioni, ma possono ancora essere personalizzati con variabili personalizzate dell’applicazione.

## Definisci il contenuto della notifica {#push-message}

>[!IMPORTANT]
>
>Prima di progettare una notifica push potenziata, è necessario configurare il connettore. Per la procedura dettagliata, consulta [questa pagina](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android#configuring-external-account-android).

Una volta creata la consegna push, puoi definirne il contenuto. Sono disponibili tre modelli:

* **Modello predefinito** ti consente di inviare notifiche con una semplice icona e un&#39;immagine associata.

* **Modello base** può includere testo, immagini e pulsanti nelle notifiche.

* **Modello carosello** consente di inviare notifiche con testo e più immagini scorrevoli.

Sfoglia le schede seguenti per scoprire come comporre il messaggio per ciascun modello.

>[!BEGINTABS]

>[!TAB Modello predefinito]

1. Dall&#39;elenco a discesa **[!UICONTROL Notification type]**, selezionare **[!UICONTROL Default]**.

   ![](assets/rich_push_default.png)

1. Per comporre il messaggio, immettere il testo nei campi **[!UICONTROL Title]** e **[!UICONTROL Message]**.

   ![](assets/rich_push_default_2.png)

1. Utilizza i campi di personalizzazione dinamica per definire il contenuto, personalizzare i dati e aggiungere contenuto dinamico. [Ulteriori informazioni](../send/personalize.md)

1. Per personalizzare ulteriormente la notifica push, configurare **[!UICONTROL Notification options]** e **[!UICONTROL HTTPv1 additional options]** della notifica push. [Ulteriori informazioni](#push-advanced)

   ![](assets/rich_push_default_3.png)

Dopo aver definito il contenuto del messaggio, puoi utilizzare gli abbonati di prova per visualizzare in anteprima e verificare il messaggio.

>[!TAB Modello base]

1. Dall&#39;elenco a discesa **[!UICONTROL Notification Type]**, selezionare **[!UICONTROL Basic]**.

   ![](assets/rich_push_basic.png)

1. Per comporre il messaggio, immettere il testo nei campi **[!UICONTROL Title]**, **[!UICONTROL Message]** e **[!UICONTROL Expanded message]**.

   Il testo **[!UICONTROL Message]** viene visualizzato nella visualizzazione compressa mentre **[!UICONTROL Expanded message]** viene visualizzato quando la notifica viene espansa.

   ![](assets/rich_push_basic_2.png)

1. Utilizza i campi di personalizzazione dinamica per definire il contenuto, personalizzare i dati e aggiungere contenuto dinamico. [Ulteriori informazioni](../send/personalize.md)

1. Nel menu **[!UICONTROL Color options]** immettere i codici colore esadecimali per **[!UICONTROL Title]**, **[!UICONTROL Message]** e **[!UICONTROL Background]**.

1. Aggiungi **[!UICONTROL Remind later button]** se necessario. Immetti **[!UICONTROL Reminder Text]** e **Data** nei campi corrispondenti.

   Nel campo **[!UICONTROL Reminder Date]** è previsto un valore che rappresenta un&#39;epoca in secondi.

1. Fai clic su **[!UICONTROL Add button]** e compila i campi seguenti:

   * **[!UICONTROL Label]**: testo visualizzato sul pulsante.
   * **[!UICONTROL Link URI]**: specificare l&#39;URI da eseguire facendo clic sul pulsante.

   È possibile includere fino a tre pulsanti nella notifica push. Se si sceglie **[!UICONTROL Remind later button]**, è possibile includere solo un massimo di due pulsanti.

1. Seleziona **[!UICONTROL Link type]** dell&#39;URL collegato del pulsante:

   * **[!UICONTROL Web URL]**: gli URL Web indirizzano gli utenti al contenuto online. Facendo clic su, viene richiesto al browser Web predefinito del dispositivo di aprire e passare all&#39;URL designato.

   * **[!UICONTROL Deeplink]**: i collegamenti profondi sono URL che indirizzano gli utenti a sezioni specifiche all&#39;interno di un&#39;app, anche se l&#39;app è chiusa. Facendo clic su di esso, può essere visualizzata una finestra di dialogo che consente agli utenti di scegliere tra varie app in grado di gestire il collegamento.

   * **[!UICONTROL Open App]**: gli URL aperti dell&#39;app consentono di connettersi direttamente al contenuto di un&#39;applicazione. Consente all’applicazione di impostarsi come gestore predefinito per un tipo specifico di collegamento, ignorando la finestra di dialogo per la disambiguazione.

   Per ulteriori informazioni su come gestire i collegamenti alle app Android, consulta la [documentazione per sviluppatori di Android](https://developer.android.com/training/app-links).

   ![](assets/rich_push_basic_3.png)

1. Per personalizzare ulteriormente la notifica push, configurare **[!UICONTROL Notification options]** e **[!UICONTROL HTTPv1 additional options]** della notifica push. [Ulteriori informazioni](#push-advanced)

   ![](assets/rich_push_basic_4.png)

Dopo aver definito il contenuto del messaggio, puoi utilizzare gli abbonati di prova per visualizzare in anteprima e verificare il messaggio.

>[!TAB Modello carosello]

1. Dall&#39;elenco a discesa **[!UICONTROL Notification Type]**, selezionare **[!UICONTROL Carousel]**.

   ![](assets/rich_push_carousel.png)

1. Per comporre il messaggio, immettere il testo nei campi **[!UICONTROL Title]**, **[!UICONTROL Message]** e **[!UICONTROL Expanded message]**.

   Il testo **[!UICONTROL Message]** viene visualizzato nella visualizzazione compressa mentre **[!UICONTROL Expanded message]** viene visualizzato quando la notifica viene espansa.

   ![](assets/rich_push_carousel_1.png)

1. Utilizza l’editor espressioni per definire il contenuto, personalizzare i dati e aggiungere contenuto dinamico. [Ulteriori informazioni](../send/personalize.md)

1. Nel menu **[!UICONTROL Color options]** immettere i codici colore esadecimali per **[!UICONTROL Title]**, **[!UICONTROL Message]** e **[!UICONTROL Background]**.

1. Scegli come funziona **[!UICONTROL Carousel]**:

   * **[!UICONTROL Auto]**: passa automaticamente da un&#39;immagine all&#39;altra sotto forma di diapositive, passando a intervalli predefiniti.
   * **[!UICONTROL Manual]**: consente agli utenti di scorrere manualmente tra le diapositive per spostarsi tra le immagini.

1. Dall&#39;elenco a discesa **[!UICONTROL Layout]**, selezionare l&#39;opzione **[!UICONTROL Filmstrip]** per includere anteprime delle immagini precedenti e successive insieme alla diapositiva principale.

1. Fai clic su **[!UICONTROL Add image]** e immetti l&#39;URL dell&#39;immagine, il testo e l&#39;URL dell&#39;azione.

   Assicurati di includere un minimo di tre immagini e un massimo di cinque.

   ![](assets/rich_push_carousel_2.png)

1. Per personalizzare ulteriormente la notifica push, configurare **[!UICONTROL Notification options]** e **[!UICONTROL HTTPv1 additional options]** della notifica push. [Ulteriori informazioni](#push-advanced)

   ![](assets/rich_push_carousel_3.png)

Dopo aver definito il contenuto del messaggio, puoi utilizzare gli abbonati di prova per visualizzare in anteprima e verificare il messaggio.

>[!ENDTABS]

## Impostazioni avanzate della notifica push {#push-advanced}

### Opzioni di notifica {#notification-options}

| Parametro | Descrizione |
|---------|---------|
| **[!UICONTROL Channel ID]** | Imposta l’ID canale della notifica. L’app deve creare un canale con questo ID canale prima di ricevere qualsiasi notifica con questo ID canale. |
| **[!UICONTROL Icon]** | Imposta l’icona della notifica da visualizzare sui dispositivi dei profili. |
| **[!UICONTROL Sound]** | Imposta l’audio da riprodurre quando il dispositivo riceve la notifica. |
| **[!UICONTROL Tag]** | Imposta un identificatore utilizzato per sostituire le notifiche esistenti nella barra delle notifiche. In questo modo si evita l’accumulo di notifiche multiple e si garantisce che venga visualizzata solo la notifica pertinente più recente. |
| **[!UICONTROL Color]** | Imposta il colore dell’icona della notifica con codice colore esadecimale. |
| **[!UICONTROL Click action]** | Imposta l’azione associata a un utente che fa clic sulla notifica. |
| **[!UICONTROL Notification background color]** | Imposta il colore dello sfondo della notifica con i codici di colore esadecimali. |
| **[!UICONTROL Link type]** | <ul><li>URL web: gli URL web indirizzano gli utenti al contenuto online. Facendo clic su, viene richiesto al browser Web predefinito del dispositivo di aprire e passare all&#39;URL designato.</li><li>Deeplink: i collegamenti profondi sono URL che guidano gli utenti verso sezioni specifiche all&#39;interno di un&#39;app, anche se l&#39;app è chiusa. Facendo clic su di esso, può essere visualizzata una finestra di dialogo che consente agli utenti di scegliere tra varie app in grado di gestire il collegamento.</li><li> App aperta: gli URL aperti dell’app ti consentono di connettersi direttamente al contenuto all’interno di un’applicazione. Consente all’applicazione di impostarsi come gestore predefinito per un tipo specifico di collegamento, ignorando la finestra di dialogo per la disambiguazione.</li></ul> |

### Opzioni aggiuntive HTTPv1 {#additional-options}

| Parametro | Descrizione |
|---------|---------|
| **[!UICONTROL Ticker]** | Imposta il testo del segno di spunta della notifica. Disponibile solo per i dispositivi impostati su Android 5.0 Lollipop. |
| **[!UICONTROL Sticky]** | Quando è attivata, la notifica rimane visibile anche dopo che l’utente fa clic su di essa. <br>Se è disattivata, la notifica viene automaticamente ignorata quando l’utente interagisce con essa. Il comportamento permanente consente alle notifiche importanti di rimanere sullo schermo per periodi più lunghi. |
| **[!UICONTROL Image]** | Imposta l&#39;URL dell&#39;immagine da visualizzare nella notifica. |
| **[!UICONTROL Notification Priority]** | Imposta il livello di priorità della notifica, che può essere predefinito, minimo, basso o alto. Il livello di priorità determina l’importanza e l’urgenza della notifica, influenzandone la modalità di visualizzazione e la possibilità di ignorare determinate impostazioni di sistema. Per ulteriori informazioni, consulta la [documentazione FCM ](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#notificationpriority). |
| **[!UICONTROL Notification Count]** | Imposta il numero di nuove informazioni non lette da visualizzare direttamente sull’icona dell’applicazione. Questo consente all’utente di visualizzare rapidamente il numero di notifiche in sospeso. |
| **[!UICONTROL Visibility]** | Imposta il livello di visibilità della notifica, che può essere pubblica, privata o segreta. Il livello di visibilità determina la quantità di contenuto della notifica viene visualizzata nella schermata di blocco e in altre aree sensibili. Per ulteriori informazioni, consulta la [documentazione FCM](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#visibility). |
| **[!UICONTROL Application variables]** | Consente di definire il comportamento di notifica. Queste variabili sono completamente personalizzabili e sono incluse nel payload del messaggio inviato al dispositivo mobile. |
