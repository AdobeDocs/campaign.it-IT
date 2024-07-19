---
product: campaign
title: Forum di discussione
description: Scopri come utilizzare i forum di discussione di Campaign
feature: Campaigns, Resource Management
role: User
exl-id: c2336507-beea-4ddb-aa8c-1ec591eb5683
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Forum di discussione{#discussion-forums}

Gli operatori Adobe Campaign possono utilizzare i forum di discussione per condividere informazioni. Ognuno dei seguenti elementi ha un proprio forum: piani, programmi, campagne, risorse di marketing, simulazioni, stock. Ogni operatore ha anche un forum personale. Tutte le discussioni sono pubbliche, anche sui forum personali.

Gli operatori possono iscriversi a un forum per ricevere un’e-mail di notifica ogni volta che viene pubblicato un messaggio.

## Accedere a un forum {#accessing-a-forum}

Per accedere a un forum, passare a un dashboard e fare clic sul collegamento **[!UICONTROL Forum]** nell&#39;angolo superiore destro.

![](assets/mrm-forum-icon.png)

I messaggi e le relative risposte vengono visualizzati dal più recente al meno recente.

Per avviare un nuovo thread, fare clic sul pulsante **[!UICONTROL Add a discussion]** nell&#39;angolo superiore destro. Viene visualizzata la casella **[!UICONTROL Discussion forum]** (vedere di seguito).

![](assets/mrm-forum-new-thread.png)


Immettere il testo nel campo **[!UICONTROL Message]** e un titolo di discussione nel campo **[!UICONTROL Subject]**.

Gli operatori che hanno già pubblicato un messaggio in questo forum ricevono una notifica per impostazione predefinita. Puoi selezionare un operatore aggiuntivo da notificare. Per notificare più operatori, seleziona un gruppo di operatori.

È possibile aggiungere un allegato al messaggio utilizzando il pulsante **[!UICONTROL Browse...]**. L’allegato verrà incluso anche nell’e-mail di notifica. Gli allegati possono essere inviati solo singolarmente: per inviare diversi file, è necessario comprimerli in un file .zip.

>[!CAUTION]
>
>Una volta inserito nel forum, il messaggio non può più essere modificato o eliminato.

## Pubblica nel forum personale di un operatore {#posting-to-the-personal-forum-of-an-operator}

Puoi inviare un messaggio al forum di un operatore. I forum personali sono pubblici e tutti gli operatori possono visualizzare il messaggio. L’operatore riceve una notifica e-mail ogni volta che un utente pubblica sul proprio forum personale.

Per accedere al forum di un operatore, puoi effettuare le seguenti operazioni:

* Individua la cartella **[!UICONTROL Administration > Access management > Operators]** di Campaign Explorer, seleziona l’operatore per aprire il dashboard, quindi fai clic sul collegamento **[!UICONTROL Forum]** nell’angolo in alto a destra.
* Trova il nome dell’operatore nell’interfaccia utente di Adobe Campaign (tramite un messaggio inviato al forum da questo operatore, a cui viene assegnata un’attività) e fai clic su di esso per accedere al dashboard dell’operatore.

## Iscriviti a un forum {#subscribing-to-a-forum}

La sottoscrizione a un forum consente di seguire tutte le discussioni. Una volta effettuato l’abbonamento, riceverai una notifica e-mail ogni volta che un messaggio viene inviato al forum.

Per rispondere a un messaggio, fai clic sul corpo dell’e-mail, quindi accedi all’interfaccia web di Adobe Campaign.

* Per iscriversi a un forum, fare clic sul pulsante **[!UICONTROL Follow discussions]** nella sezione superiore destra sopra l&#39;elenco dei messaggi.

  La sezione diventa blu e mostra che hai effettuato l’iscrizione al forum.

* Per annullare l&#39;iscrizione a un forum, fare clic sul pulsante **[!UICONTROL Unsubscribe]**.

* Nel dashboard personale sono elencati i forum a cui sei abbonato. Fai clic sul collegamento **[!UICONTROL Subscription to discussion forums]** per visualizzare l&#39;elenco, quindi fai clic sull&#39;elemento che ti interessa per accedere al relativo forum.

  ![](assets/forum-subscribed.png)


## Risoluzione dei problemi di consegna delle notifiche {#checking-notification-delivery}

Se gli operatori abbonati a un forum non ricevono le notifiche previste:

* Verifica che gli indirizzi e-mail vengano immessi nei profili dell’operatore.
* Individua la cartella **[!UICONTROL Administration > Production > Technical workflows > Campaign processes]** di Campaign Explorer e verifica che il flusso di lavoro **[!UICONTROL Jobs in discussion forums]** sia avviato senza errori.
* Controlla i registri di consegna:

   * Nella home page di Adobe Campaign, passa a **[!UICONTROL Campaigns > Navigation > Deliveries]**, quindi apri la consegna **[!UICONTROL Discussion forum notification]**.
   * In Esplora campagne, passa a **[!UICONTROL Administration > Production > Objects created automatically > Technical deliveries > Workflow notifications]**, quindi fai clic su **[!UICONTROL Discussion forum notifications]**.

  Nella casella **[!UICONTROL Discussion forum notifications]**, i registri di consegna si trovano nella scheda **[!UICONTROL Edit > Delivery]**. È inoltre possibile visualizzare le schede **[!UICONTROL Tracking > Log]** e **[!UICONTROL Exclusion causes]**.
