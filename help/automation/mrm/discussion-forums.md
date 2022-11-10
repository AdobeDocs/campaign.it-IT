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

Gli operatori di Adobe Campaign possono utilizzare forum di discussione per condividere informazioni. I seguenti elementi hanno un proprio forum: piani, programmi, campagne, risorse di marketing, simulazioni, stock. Ogni operatore ha anche un forum personale. Tutte le discussioni sono pubbliche, anche su forum personali.

Gli operatori possono iscriversi a un forum per ricevere un’e-mail di notifica ogni volta che viene pubblicato un messaggio.

## Accedere a un forum {#accessing-a-forum}

Per accedere a un forum, individua un dashboard e fai clic su **[!UICONTROL Forum]** nell&#39;angolo in alto a destra.

![](assets/mrm-forum-icon.png)

I messaggi e le relative risposte vengono visualizzati dal più recente al meno recente.

Per avviare un nuovo thread, fai clic sul pulsante **[!UICONTROL Add a discussion]** nell&#39;angolo in alto a destra. La **[!UICONTROL Discussion forum]** viene visualizzata (vedi sotto).

![](assets/mrm-forum-new-thread.png)


Inserisci il testo nel **[!UICONTROL Message]** e un titolo di discussione nel **[!UICONTROL Subject]** campo .

Gli operatori che hanno già pubblicato un messaggio in questo forum vengono avvisati per impostazione predefinita. Puoi selezionare un operatore aggiuntivo da avvisare. Per avvisare diversi operatori, selezionare un gruppo di operatori.

Puoi aggiungere un allegato al messaggio utilizzando  **[!UICONTROL Browse...]** pulsante . L’allegato verrà incluso anche nell’e-mail di notifica. Gli allegati possono essere inviati solo singolarmente: per inviare diversi file, è necessario comprimerli in un file .zip.

>[!CAUTION]
>
>Una volta pubblicato il messaggio nel forum, non è più possibile modificarlo o eliminarlo.

## Invia al forum personale di un operatore {#posting-to-the-personal-forum-of-an-operator}

Puoi inviare un messaggio al forum di un operatore. I forum personali sono pubblici e tutti gli operatori possono vedere il messaggio. L’operatore riceve una notifica e-mail ogni volta che qualcuno invia un messaggio al proprio forum personale.

Per accedere al forum di un operatore, puoi:

* Sfoglia il **[!UICONTROL Administration > Access management > Operators]** cartella di Campaign explorer, seleziona l’operatore per aprire il suo dashboard, quindi fai clic sul **[!UICONTROL Forum]** nell&#39;angolo in alto a destra.
* Trova il nome dell’operatore nell’interfaccia utente di Adobe Campaign (tramite un messaggio inviato al forum da questo operatore, un’attività che viene loro assegnata) e fai clic su di esso per accedere al dashboard dell’operatore.

## Iscriviti a un forum {#subscribing-to-a-forum}

La sottoscrizione a un forum consente di seguire tutte le discussioni. Una volta effettuato l’abbonamento, ricevi una notifica e-mail ogni volta che un messaggio viene inviato al forum.

Per rispondere a un messaggio, fai clic su nel corpo dell’e-mail, quindi accedi all’interfaccia web di Adobe Campaign.

* Per iscriverti a un forum, fai clic sul pulsante **[!UICONTROL Follow discussions]** nella sezione in alto a destra sopra l’elenco dei messaggi.

   La sezione diventa blu e mostra che sei iscritto al forum.

* Per annullare l’iscrizione a un forum, fai clic sul pulsante **[!UICONTROL Unsubscribe]** pulsante .

* Il dashboard personale elenca i forum a cui ti sei iscritto. Fai clic sul pulsante **[!UICONTROL Subscription to discussion forums]** per visualizzare l’elenco, quindi fare clic sull’elemento che interessa l’accesso al relativo forum.

   ![](assets/forum-subscribed.png)


## Risoluzione dei problemi di consegna delle notifiche {#checking-notification-delivery}

Se gli operatori abbonati a un forum non ricevono le notifiche come previsto:

* Verifica che gli indirizzi e-mail siano inseriti nei profili dell’operatore.
* Sfoglia il **[!UICONTROL Administration > Production > Technical workflows > Campaign processes]** cartella di Campaign explorer e controlla la **[!UICONTROL Jobs in discussion forums]** il flusso di lavoro viene avviato senza errori.
* Controlla i registri di consegna:

   * Nella home page di Adobe Campaign, seleziona **[!UICONTROL Campaigns > Navigation > Deliveries]**, quindi apri la **[!UICONTROL Discussion forum notification]** consegna.
   * In Campaign explorer, cerca **[!UICONTROL Administration > Production > Objects created automatically > Technical deliveries > Workflow notifications]**, quindi fai clic su **[!UICONTROL Discussion forum notifications]**.
   In **[!UICONTROL Discussion forum notifications]** i registri di consegna si trovano nella **[!UICONTROL Edit > Delivery]** scheda . È inoltre possibile visualizzare le **[!UICONTROL Tracking > Log]** e **[!UICONTROL Exclusion causes]** schede.
