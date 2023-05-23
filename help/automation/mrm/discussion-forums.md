---
product: campaign
title: Forum di discussione
description: Scopri come utilizzare i forum di discussione di Campaign
exl-id: c2336507-beea-4ddb-aa8c-1ec591eb5683
source-git-commit: 72fc29c49fca5767133be4a9927b57b3cfb51a14
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Forum di discussione{#discussion-forums}

Gli operatori Adobe Campaign possono utilizzare i forum di discussione per condividere informazioni. Ognuno dei seguenti elementi ha un proprio forum: piani, programmi, campagne, risorse di marketing, simulazioni, stock. Ogni operatore ha anche un forum personale. Tutte le discussioni sono pubbliche, anche sui forum personali.

Gli operatori possono iscriversi a un forum per ricevere un’e-mail di notifica ogni volta che viene pubblicato un messaggio.

## Accedere a un forum {#accessing-a-forum}

Per accedere a un forum, individua un dashboard e fai clic su **[!UICONTROL Forum]** nell’angolo in alto a destra.

![](assets/mrm-forum-icon.png)

I messaggi e le relative risposte vengono visualizzati dal più recente al meno recente.

Per avviare un nuovo thread, fare clic su **[!UICONTROL Add a discussion]** nell’angolo in alto a destra. Il **[!UICONTROL Discussion forum]** (vedere sotto).

![](assets/mrm-forum-new-thread.png)


Inserisci il testo in **[!UICONTROL Message]** e un titolo di discussione nel **[!UICONTROL Subject]** campo.

Gli operatori che hanno già pubblicato un messaggio in questo forum ricevono una notifica per impostazione predefinita. Puoi selezionare un operatore aggiuntivo da notificare. Per notificare più operatori, seleziona un gruppo di operatori.

È possibile aggiungere un allegato al messaggio utilizzando  **[!UICONTROL Browse...]** pulsante. L’allegato verrà incluso anche nell’e-mail di notifica. Gli allegati possono essere inviati solo singolarmente: per inviare diversi file, è necessario comprimerli in un file .zip.

>[!CAUTION]
>
>Una volta inserito nel forum, il messaggio non può più essere modificato o eliminato.

## Pubblica nel forum personale di un operatore {#posting-to-the-personal-forum-of-an-operator}

Puoi inviare un messaggio al forum di un operatore. I forum personali sono pubblici e tutti gli operatori possono visualizzare il messaggio. L’operatore riceve una notifica e-mail ogni volta che un utente pubblica sul proprio forum personale.

Per accedere al forum di un operatore, puoi effettuare le seguenti operazioni:

* Accedi a **[!UICONTROL Administration > Access management > Operators]** cartella di Campaign explorer, seleziona l’operatore per aprire il dashboard, quindi fai clic su **[!UICONTROL Forum]** nell’angolo in alto a destra.
* Trova il nome dell’operatore nell’interfaccia utente di Adobe Campaign (tramite un messaggio inviato al forum da questo operatore, a cui viene assegnata un’attività) e fai clic su di esso per accedere al dashboard dell’operatore.

## Iscriviti a un forum {#subscribing-to-a-forum}

La sottoscrizione a un forum consente di seguire tutte le discussioni. Una volta effettuato l’abbonamento, riceverai una notifica e-mail ogni volta che un messaggio viene inviato al forum.

Per rispondere a un messaggio, fai clic sul corpo dell’e-mail, quindi accedi all’interfaccia web di Adobe Campaign.

* Per iscriversi a un forum, fare clic su **[!UICONTROL Follow discussions]** nella sezione in alto a destra sopra l’elenco dei messaggi.

   La sezione diventa blu e mostra che hai effettuato l’iscrizione al forum.

* Per annullare l’abbonamento a un forum, fai clic su **[!UICONTROL Unsubscribe]** pulsante.

* Nel dashboard personale sono elencati i forum a cui sei abbonato. Fai clic su **[!UICONTROL Subscription to discussion forums]** per visualizzare l’elenco, quindi fai clic sull’elemento di tuo interesse per accedere al forum.

   ![](assets/forum-subscribed.png)


## Risoluzione dei problemi di consegna delle notifiche {#checking-notification-delivery}

Se gli operatori abbonati a un forum non ricevono le notifiche previste:

* Verifica che gli indirizzi e-mail vengano immessi nei profili dell’operatore.
* Accedi a **[!UICONTROL Administration > Production > Technical workflows > Campaign processes]** cartella di Campaign explorer e controlla **[!UICONTROL Jobs in discussion forums]** il flusso di lavoro viene avviato senza errori.
* Controlla i registri di consegna:

   * Nella home page di Adobe Campaign, passa a **[!UICONTROL Campaigns > Navigation > Deliveries]**, quindi aprire **[!UICONTROL Discussion forum notification]** consegna.
   * In Esplora campagne, passa a **[!UICONTROL Administration > Production > Objects created automatically > Technical deliveries > Workflow notifications]**, quindi fai clic su **[!UICONTROL Discussion forum notifications]**.
   In **[!UICONTROL Discussion forum notifications]** , i registri di consegna si trovano nella sezione **[!UICONTROL Edit > Delivery]** scheda. È inoltre possibile visualizzare **[!UICONTROL Tracking > Log]** e **[!UICONTROL Exclusion causes]** schede.
