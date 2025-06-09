---
title: Pubblicare messaggi su X (Twitter) con Adobe Campaign
description: Scopri come utilizzare il modulo Adobe Campaign Social Marketing per pubblicare messaggi su X (precedentemente noto come Twitter) e inviare messaggi diretti ai tuoi follower
role: User
level: Beginner, Intermediate
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: f463c5747b844544ba561a63e4cb0359c0c258c8
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 4%

---


# Pubblicare messaggi su X (Twitter) con Adobe Campaign {#post-tw-messages}

Adobe Campaign viene fornito con un modulo **Social Marketing** che consente di interagire con i clienti attuali e potenziali tramite X (precedentemente noto come Twitter).

Una volta configurata l’integrazione, puoi:

* Inviare messaggi diretti ai propri follower
* Pubblica sul tuo account X
* Raccogliere nuovi contatti recuperando i dati del profilo, che consente di eseguire campagne di targeting e, quando possibile, di implementare strategie cross-channel. Questa azione richiede il consenso dell’utente.


I passaggi di configurazione per integrare il tuo account X con Adobe Campaign sono descritti in [questa pagina](../connect/ac-tw.md).

## Creare e pubblicare un post X {#publish-on-tw}

Segui i passaggi seguenti per pubblicare un messaggio sul tuo account X:

1. Creare una consegna X

   Creare una nuova consegna basata sul modello di consegna **[!UICONTROL Tweet (twitter)]**.

   ![](assets/tw-new-delivery.png)

1. Seleziona la destinazione principale

   Seleziona gli account a cui inviare i post.

   ![](assets/tw-define-target.png)

   1. Fai clic sul collegamento **[!UICONTROL To]**.
   1. Fai clic sul pulsante **[!UICONTROL Add]**.
   1. Seleziona **[!UICONTROL A Twitter account]**.
   1. Nel campo **[!UICONTROL Folder]** selezionare la cartella del servizio che contiene l&#39;account X. Quindi seleziona l’account X a cui inviare il tweet.

1. Seleziona la destinazione della bozza

   La scheda **[!UICONTROL Target of the proofs]** ti consente di definire l’account X da utilizzare per le consegne di test prima della consegna finale.

   Come descritto nei [passaggi di configurazione](../connect/ac-tw.md#tw-test-account), devi creare un account X di test privato dedicato all&#39;invio delle bozze.

   >[!NOTE]
   >
   >Se utilizzi lo stesso account di test X per tutte le consegne, puoi salvare la destinazione della bozza nel modello di consegna **[!UICONTROL Tweet]**, accessibile tramite il nodo **[!UICONTROL Resources > Templates > Delivery templates]**. La destinazione della bozza verrà quindi inserita per impostazione predefinita per ogni nuova consegna.

1. Definire il contenuto del post

   Immettere il contenuto del post nella scheda **[!UICONTROL Content]**.

   ![](assets/tw-delivery-content.png)

   >[!CAUTION]
   >
   >Quando si pubblica su X, si applicano le seguenti limitazioni:
   >
   >* Il messaggio non può superare i 140 caratteri.
   >* Formato HTML non supportato.
   >

1. Anteprima del post

   Sfoglia la scheda **[!UICONTROL Preview]** per controllare il rendering del post.

   ![](assets/tw-delivery-preview.png)

   1. Fare clic sulla scheda **[!UICONTROL Preview]**.
   1. Fare clic sul menu a discesa **[!UICONTROL Test personalization]** e selezionare **[!UICONTROL Service]**.
   1. Nel campo **[!UICONTROL Folder]** selezionare la cartella del servizio che contiene l&#39;account X.

1. Inviare una bozza

   Prima di pubblicare il tweet, assicurati di convalidarlo inviando una prova della pubblicazione: potrai quindi ottenere un rendering esatto della pubblicazione su una pagina di test X privata.

1. Pubblica il messaggio

   1. Una volta approvato il contenuto, fare clic sul pulsante **[!UICONTROL Send]**.
   1. Selezionare **[!UICONTROL Deliver as soon as possible]** e fare clic sul pulsante **[!UICONTROL Analyze]**.
   1. Al termine dell’analisi, verifica il risultato.
   1. Fare clic su **[!UICONTROL Confirm delivery]**, quindi su **[!UICONTROL Yes]**.

## Inviare messaggi diretti ai follower {#direct-tw-messages}

Il flusso di lavoro tecnico **[!UICONTROL Synchronize Twitter accounts]** recupera l&#39;elenco degli X follower in modo da poter inviare loro messaggi diretti. [Ulteriori informazioni](../connect/ac-tw.md#synchro-tw-accounts)

Per inviare messaggi diretti ai tuoi follower, segui i passaggi seguenti:

1. Creare una consegna X basata sul modello di consegna incorporato **[!UICONTROL Tweet (Direct Message)]**.

1. Seleziona la destinazione principale

   ![](assets/tw-dm-define-target.png)

   1. Selezionare il collegamento **[!UICONTROL To]** e il pulsante **[!UICONTROL Add]**.

   1. Scegli un tipo di targeting

      * Seleziona **[!UICONTROL Twitter subscribers]** per inviare un messaggio diretto a tutti i tuoi follower.

      * Selezionare **[!UICONTROL Filter conditions]** per definire una query e visualizzarne il risultato. Scopri come creare un filtro in [questa sezione](../audiences/create-filters.md#advanced-filters).

1. Seleziona la destinazione della bozza dalla scheda **[!UICONTROL Target of the proofs]**: questo account riceverà la bozza del tuo messaggio diretto.

   Come descritto nei [passaggi di configurazione](../connect/ac-tw.md#tw-test-account), devi creare un account X di test privato dedicato all&#39;invio delle bozze.


   >[!NOTE]
   >
   >Se desideri inviare tutte le bozze dei messaggi diretti allo stesso account X, puoi salvare la destinazione della bozza nel modello di consegna **[!UICONTROL Tweet (Direct Message)]**, accessibile tramite il nodo **[!UICONTROL Resources > Templates > Delivery templates]**.

1. Immettere il contenuto del messaggio nella scheda **[!UICONTROL Content]**.

   ![](assets/tw-dm-content.png)

   I campi di personalizzazione possono essere utilizzati come per le consegne e-mail, ad esempio per aggiungere il nome del follower nel corpo del messaggio. Per ulteriori informazioni, consulta [questa sezione](../send/personalize.md).

1. Anteprima del messaggio

   Sfoglia la scheda **[!UICONTROL Preview]** per controllare il rendering del post.

   ![](assets/tw-dm-preview.png)

   1. Fare clic sulla scheda **[!UICONTROL Preview]**.
   1. Fare clic sul menu a discesa **[!UICONTROL Test personalization]** e selezionare **[!UICONTROL Visitor Subscription]**.
   1. Scegli un account X con cui desideri verificare l’anteprima.

1. Inviare una bozza

   Prima di inviare il messaggio, assicurati di convalidarlo inviando [una bozza a un account di prova](../send/preview-and-proof.md): potrai quindi ottenere un rendering esatto del messaggio su un account X privato e controllare il contenuto e la personalizzazione.

1. Inviare il messaggio diretto

   1. Una volta approvato il contenuto, fare clic sul pulsante **[!UICONTROL Send]**.
   1. Selezionare **[!UICONTROL Deliver as soon as possible]** e fare clic sul pulsante **[!UICONTROL Analyze]**.
   1. Al termine dell’analisi, verifica il risultato.
   1. Fare clic su **[!UICONTROL Confirm delivery]**, quindi su **[!UICONTROL Yes]**.

>[!CAUTION]
>
>Non puoi inviare più di 250 messaggi diretti al giorno. Per evitare di superare questa soglia, è possibile effettuare la consegna in ondate. Per ulteriori informazioni, consulta la [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#sending-using-multiple-waves){target="_blank"}.


## Accedere ai dati di tracciamento {#tw-tracking}

Nel modello di consegna **[!UICONTROL Tweet]** incorporato, il tracciamento è abilitato per impostazione predefinita.

I dati di tracciamento possono essere visualizzati nei report di consegna e nella scheda **[!UICONTROL Edit > Tracking]** della consegna e del servizio.

La configurazione di tracciamento è la stessa di una consegna e-mail. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=it){target="_blank"}.

