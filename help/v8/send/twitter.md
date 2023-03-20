---
title: Messaggi su Twitter con Adobe Campaign
description: Scopri come utilizzare il modulo Adobe Campaign Social Marketing per inviare messaggi su Twitter e inviare messaggi diretti ai tuoi follower
role: User
level: Beginner, Intermediate
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: 34af97ae01f7dba418fd0a8c950fc549dfbbd98b
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 6%

---


# Messaggi su Twitter con Adobe Campaign {#post-tw-messages}

Adobe Campaign viene fornito con un **Social marketing** modulo che consente di interagire con i clienti e i potenziali clienti tramite Twitter.

Una volta configurata l’integrazione, puoi:

* Invia messaggi diretti ai tuoi follower
* Pubblica i tweet sul tuo account Twitter
* Raccogli nuovi contatti recuperando i dati del profilo, che ti consentono di eseguire campagne di targeting e, quando possibile, di implementare strategie cross-channel. Questa azione richiede il consenso dell’utente.


I passaggi di configurazione per integrare l’account Twitter con Adobe Campaign sono descritti in [questa pagina](../connect/ac-tw.md).

## Creare e pubblicare un post Twitter {#publish-on-tw}

Per inviare un messaggio sul tuo account Twitter, effettua le seguenti operazioni:

1. Creare una consegna Twitter

   Crea una nuova consegna basata su **[!UICONTROL Tweet (twitter)]** modello di consegna.

   ![](assets/tw-new-delivery.png)

1. Selezionare la destinazione principale

   Seleziona gli account a cui desideri inviare i tweet.

   ![](assets/tw-define-target.png)

   1. Fai clic sul collegamento **[!UICONTROL To]**.
   1. Fai clic sul pulsante **[!UICONTROL Add]**.
   1. Seleziona **[!UICONTROL A Twitter account]**.
   1. In **[!UICONTROL Folder]** selezionare la cartella del servizio che contiene l&#39;account Twitter. Quindi seleziona l’account Twitter a cui desideri inviare il tuo tweet.

1. Selezionare la destinazione della bozza

   La **[!UICONTROL Target of the proofs]** La scheda ti consente di definire l’account Twitter da utilizzare per testare le consegne prima della consegna finale.

   Come descritto in [passaggi di configurazione](../connect/ac-tw.md#tw-test-account), devi creare un account Twitter di prova privato dedicato all’invio di bozze.

   >[!NOTE]
   >
   >Se utilizzi lo stesso account di test Twitter per tutte le consegne, puoi salvare la destinazione della bozza nella sezione **[!UICONTROL Tweet]** modello di consegna, accessibile tramite il **[!UICONTROL Resources > Templates > Delivery templates]** nodo. Il target della bozza verrà quindi immesso per impostazione predefinita per ogni nuova consegna.

1. Definire il contenuto del post

   Immetti il contenuto del post nella **[!UICONTROL Content]** scheda .

   ![](assets/tw-delivery-content.png)

   >[!CAUTION]
   >
   >Quando pubblichi su Twitter, si applicano le limitazioni seguenti:
   >
   >* Il messaggio non può superare i 140 caratteri.
   >* Formato HTML non supportato.


1. Anteprima del post

   Sfoglia il **[!UICONTROL Preview]** per controllare il rendering del post.

   ![](assets/tw-delivery-preview.png)

   1. Fai clic sul pulsante **[!UICONTROL Preview]** scheda .
   1. Fai clic sul pulsante **[!UICONTROL Test personalization]** menu a discesa e seleziona **[!UICONTROL Service]**.
   1. In **[!UICONTROL Folder]** , seleziona la cartella del servizio che contiene il tuo account Twitter.

1. Inviare una bozza

   Prima di pubblicare il tuo tweet, assicurati di convalidarlo inviando una prova della tua pubblicazione: puoi quindi ottenere un rendering esatto della pubblicazione su una pagina di test Twitter privata.

1. Pubblica il messaggio

   1. Una volta approvato il contenuto, fai clic sul pulsante **[!UICONTROL Send]** pulsante .
   1. Seleziona **[!UICONTROL Deliver as soon as possible]** e fai clic su **[!UICONTROL Analyze]** pulsante .
   1. Al termine dell’analisi, controlla il risultato.
   1. Fai clic su **[!UICONTROL Confirm delivery]**, quindi fai clic su **[!UICONTROL Yes]**.

## Inviare messaggi diretti ai follower {#direct-tw-messages}

La **[!UICONTROL Synchronize Twitter accounts]** il flusso di lavoro tecnico recupera l’elenco dei follower di Twitter in modo da poter inviare loro messaggi diretti. [Ulteriori informazioni](../connect/ac-tw.md#synchro-tw-accounts)

Per inviare messaggi diretti ai tuoi follower, segui i passaggi seguenti:

1. Creare una consegna Twitter basata su **[!UICONTROL Tweet (Direct Message)]** modello di consegna integrato.

1. Selezionare la destinazione principale

   ![](assets/tw-dm-define-target.png)

   1. Seleziona la **[!UICONTROL To]** e **[!UICONTROL Add]** pulsante .

   1. Scegliere un tipo di targeting

      * Seleziona **[!UICONTROL Twitter subscribers]** per inviare un messaggio diretto a tutti i tuoi follower.

      * Seleziona **[!UICONTROL Filter conditions]** per definire una query e visualizzarne il risultato. Scopri come creare un filtro in [questa sezione](../audiences/create-filters.md#advanced-filters).

1. Seleziona la destinazione della bozza dal **[!UICONTROL Target of the proofs]** scheda: questo account riceverà la prova del messaggio diretto.

   Come descritto in [passaggi di configurazione](../connect/ac-tw.md#tw-test-account), devi creare un account Twitter di prova privato dedicato all’invio di bozze.


   >[!NOTE]
   >
   >Se desideri inviare tutte le bozze dei messaggi diretti allo stesso account Twitter, puoi salvare la destinazione della bozza nel **[!UICONTROL Tweet (Direct Message)]** modello di consegna, accessibile tramite il **[!UICONTROL Resources > Templates > Delivery templates]** nodo.

1. Immetti il contenuto del messaggio nel **[!UICONTROL Content]** scheda .

   ![](assets/tw-dm-content.png)

   I campi di personalizzazione possono essere utilizzati nello stesso modo delle consegne e-mail, ad esempio per aggiungere il nome del follower nel corpo del messaggio. Per ulteriori informazioni, consulta [questa sezione](../send/personalize.md).

1. Anteprima del messaggio

   Sfoglia il **[!UICONTROL Preview]** per controllare il rendering del post.

   ![](assets/tw-dm-preview.png)

   1. Fai clic sul pulsante **[!UICONTROL Preview]** scheda .
   1. Fai clic sul pulsante **[!UICONTROL Test personalization]** menu a discesa e seleziona **[!UICONTROL Visitor Subscription]**.
   1. Scegli un account Twitter con cui testare l’anteprima.

1. Inviare una bozza

   Prima di inviare il messaggio, assicurati di convalidarlo inviando una bozza a un account di prova: puoi quindi ottenere un rendering esatto del messaggio su un account Twitter privato e controllare il contenuto e la personalizzazione.

   ![](../assets/do-not-localize/book.png) [Scopri i passaggi chiave per convalidare una consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=it){target="_blank"}

1. Invia il messaggio diretto

   1. Una volta approvato il contenuto, fai clic sul pulsante **[!UICONTROL Send]** pulsante .
   1. Seleziona **[!UICONTROL Deliver as soon as possible]** e fai clic su **[!UICONTROL Analyze]** pulsante .
   1. Al termine dell’analisi, controlla il risultato.
   1. Fai clic su **[!UICONTROL Confirm delivery]**, quindi fai clic su **[!UICONTROL Yes]**.

>[!CAUTION]
>
>Non puoi inviare più di 250 messaggi diretti al giorno. Per evitare di superare questa soglia, puoi fornire ondate. Per ulteriori informazioni, consulta la [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=en#sending-using-multiple-waves){target="_blank"}.


## Accedere ai dati di tracciamento {#tw-tracking}

In **[!UICONTROL Tweet]** modello di consegna, il tracciamento è abilitato per impostazione predefinita.

I dati di tracciamento possono essere visualizzati nei rapporti di consegna e nella **[!UICONTROL Edit > Tracking]** scheda della consegna e del servizio.

La configurazione del tracciamento è la stessa di una consegna e-mail. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=it){target="_blank"}.

