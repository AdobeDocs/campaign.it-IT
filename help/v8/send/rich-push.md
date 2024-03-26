---
audience: end-user
title: Progettare una consegna di notifiche push potenziata
description: Scopri come progettare una consegna di notifiche push potenziata per Android con Adobe Campaign Web
feature: Push
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 42e3623b-b401-4fcc-80a7-ea38347fddc6
source-git-commit: 5f1ffd5d59791a0e6ff8a67feb08c8eed128cc1e
workflow-type: tm+mt
source-wordcount: '1128'
ht-degree: 32%

---

# Progettare una consegna push potenziata per Android {#rich-push}

Con Firebase Cloud Messaging puoi scegliere tra due tipi di messaggi:

* Il **[!UICONTROL Data message]** è gestito dall’app client. Questi messaggi vengono inviati direttamente all’app mobile, che genera e visualizza una notifica Android sul dispositivo. I messaggi di dati contengono solo variabili dell’applicazione personalizzate.

* Il **[!UICONTROL Notification message]**, gestito automaticamente dall’SDK FCM. FCM mostra automaticamente il messaggio sui dispositivi degli utenti per conto dell’app client. I messaggi di notifica contengono un set preimpostato di parametri e opzioni, ma possono ancora essere personalizzati con variabili personalizzate dell’applicazione.

## Definisci il contenuto della notifica {#push-message}

Una volta creata la consegna push, puoi definirne il contenuto. Sono disponibili tre modelli:

* **Modello predefinito** consente di inviare notifiche con una semplice icona e un’immagine associata.

* **Modello di base** può includere testo, immagini e pulsanti nelle notifiche.

* **Modello carosello** consente di inviare notifiche con testo e più immagini scorrevoli dagli utenti.

Sfoglia le schede seguenti per scoprire come comporre il messaggio per ciascun modello.

>[!BEGINTABS]

>[!TAB Modello predefinito]

1. Dalla sezione **[!UICONTROL Notification type]** a discesa, seleziona **[!UICONTROL Default]**.

   ![](assets/rich_push_default.png)

1. Per comporre il messaggio, immetti il testo nella **[!UICONTROL Title]** e **[!UICONTROL Message]** campi.

   ![](assets/rich_push_default_2.png)

1. Utilizza i campi di personalizzazione dinamica per definire il contenuto, personalizzare i dati e aggiungere contenuto dinamico. [Ulteriori informazioni](../send/personalize.md)

1. Per personalizzare ulteriormente la notifica push, configura **[!UICONTROL Notification options]** e **[!UICONTROL HTTPv1 additional options]** della notifica push. [Ulteriori informazioni](#push-advanced)

   ![](assets/rich_push_default_3.png)

Dopo aver definito il contenuto del messaggio, puoi utilizzare gli abbonati di prova per visualizzare in anteprima e verificare il messaggio.

>[!TAB Modello di base]

1. Dalla sezione **[!UICONTROL Notification Type]** a discesa, seleziona **[!UICONTROL Basic]**.

   ![](assets/rich_push_basic.png)

1. Per comporre il messaggio, immetti il testo nella **[!UICONTROL Title]**, **[!UICONTROL Message]** e **[!UICONTROL Expanded message]** campi.

   Il **[!UICONTROL Message]** il testo viene visualizzato nella vista compressa mentre **[!UICONTROL Expanded message]** viene visualizzato quando la notifica viene espansa.

   ![](assets/rich_push_basic_2.png)

1. Utilizza i campi di personalizzazione dinamica per definire il contenuto, personalizzare i dati e aggiungere contenuto dinamico. [Ulteriori informazioni](../send/personalize.md)

1. Sotto **[!UICONTROL Color options]** , immettere i codici colore esadecimali per il **[!UICONTROL Title]**, **[!UICONTROL Message]** e **[!UICONTROL Background]**.

1. Aggiungi un **[!UICONTROL Remind later button]** se necessario. Immetti il **[!UICONTROL Reminder Text]** e **Data** nei campi corrispondenti.

   Il **[!UICONTROL Reminder Date]** Il campo richiede un valore che rappresenta un’epoca in secondi.

1. Clic **[!UICONTROL Add button]** e compilare i campi seguenti:

   * **[!UICONTROL Label]**: testo visualizzato sul pulsante.
   * **[!UICONTROL Link URI]**: specifica l’URI da eseguire facendo clic sul pulsante.

   È possibile includere fino a tre pulsanti nella notifica push. Se scegli il **[!UICONTROL Remind later button]**, è possibile includere solo un massimo di due pulsanti.

1. Seleziona la **[!UICONTROL Link type]** dell’URL collegato del pulsante:

   * **[!UICONTROL Web URL]**: gli URL web indirizzano gli utenti al contenuto online. Facendo clic su, viene richiesto al browser Web predefinito del dispositivo di aprire e passare all&#39;URL designato.

   * **[!UICONTROL Deeplink]**: i collegamenti profondi sono URL che indirizzano gli utenti a sezioni specifiche all’interno di un’app, anche se l’app è chiusa. Facendo clic su di esso, può essere visualizzata una finestra di dialogo che consente agli utenti di scegliere tra varie app in grado di gestire il collegamento.

   * **[!UICONTROL Open App]**: gli URL aperti dell’app ti consentono di connettersi direttamente al contenuto all’interno di un’applicazione. Consente all’applicazione di impostarsi come gestore predefinito per un tipo specifico di collegamento, ignorando la finestra di dialogo per la disambiguazione.

   Per ulteriori informazioni su come gestire i collegamenti alle app Android, consulta [Documentazione per sviluppatori Android](https://developer.android.com/training/app-links).

   ![](assets/rich_push_basic_3.png)

1. Per personalizzare ulteriormente la notifica push, configura **[!UICONTROL Notification options]** e **[!UICONTROL HTTPv1 additional options]** della notifica push. [Ulteriori informazioni](#push-advanced)

   ![](assets/rich_push_basic_4.png)

Dopo aver definito il contenuto del messaggio, puoi utilizzare gli abbonati di prova per visualizzare in anteprima e verificare il messaggio.

>[!TAB Modello carosello]

1. Dalla sezione **[!UICONTROL Notification Type]** a discesa, seleziona **[!UICONTROL Carousel]**.

   ![](assets/rich_push_carousel.png)

1. Per comporre il messaggio, immetti il testo nella **[!UICONTROL Title]**, **[!UICONTROL Message]** e **[!UICONTROL Expanded message]** campi.

   Il **[!UICONTROL Message]** il testo viene visualizzato nella vista compressa mentre **[!UICONTROL Expanded message]** viene visualizzato quando la notifica viene espansa.

   ![](assets/rich_push_carousel_1.png)

1. Utilizza l’editor espressioni per definire il contenuto, personalizzare i dati e aggiungere contenuto dinamico. [Ulteriori informazioni](../send/personalize.md)

1. Sotto **[!UICONTROL Color options]** , immettere i codici colore esadecimali per il **[!UICONTROL Title]**, **[!UICONTROL Message]** e **[!UICONTROL Background]**.

1. Scegli come **[!UICONTROL Carousel]** viene azionato:

   * **[!UICONTROL Auto]**: passa automaticamente da un’immagine all’altra sotto forma di diapositive, con una transizione a intervalli predefiniti.
   * **[!UICONTROL Manual]**: consente agli utenti di scorrere manualmente tra le diapositive per spostarsi tra le immagini.

1. Dalla sezione **[!UICONTROL Layout]** a discesa, seleziona **[!UICONTROL Filmstrip]** opzione per includere anteprime delle immagini precedenti e successive accanto alla diapositiva principale.

1. Clic **[!UICONTROL Add image]** e inserisci l’URL dell’immagine, il Testo e l’URL dell’azione.

   Assicurati di includere un minimo di tre immagini e un massimo di cinque.

   ![](assets/rich_push_carousel_2.png)

1. Per personalizzare ulteriormente la notifica push, configura **[!UICONTROL Notification options]** e **[!UICONTROL HTTPv1 additional options]** della notifica push. [Ulteriori informazioni](#push-advanced)

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
