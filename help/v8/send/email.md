---
product: Adobe Campaign
title: Inviare e-mail con Adobe Campaign
description: Guida introduttiva alle e-mail in Campaign
feature: Panoramica
role: Data Engineer
level: Beginner
source-git-commit: d1e96b1311d9de24ceb918230186cd3cad609ab2
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 4%

---

# Progettazione e invio di e-mail

Le consegne e-mail ti consentono di inviare e-mail personalizzate alla popolazione target.

[!DNL :arrow_upper_right:] Ulteriori informazioni sono disponibili nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html).

## Creare la prima consegna e-mail

Crea e-mail personalizzate e contestualmente pertinenti, coerenti con il resto dell’esperienza del cliente.

![](assets/new-email-content.png)

[!DNL :arrow_upper_right:] [Scopri come creare una consegna e-mail nella documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/editing-html-content/use-case--creating-an-email-delivery.html)


Nell’esempio seguente, vengono descritti i passaggi necessari per progettare una consegna e-mail in Adobe Campaign che contiene dati personalizzati, collegamenti a un URL esterno, un collegamento alla pagina speculare e un collegamento a un modulo web.

1. Creare la consegna

   Per creare una nuova consegna, passa alla scheda **Campagne** , fai clic su **Consegne** e fai clic sul pulsante **Crea** sopra l’elenco delle consegne esistenti.

   ![](assets/delivery_step_1.png)

1. Selezionare il modello

   Seleziona un modello di consegna, quindi assegna un nome alla consegna. Questo nome sarà visibile solo agli utenti della console Adobe Campaign e non ai destinatari, tuttavia questa intestazione verrà visualizzata nell’elenco delle consegne. Fai clic su **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. Importare il contenuto

   Fai clic sulla scheda **Origine** per incollare il contenuto HTML.

   ![](assets/paste-content.png)


1. Personalizzare il messaggio


   * Visualizza il nome e il secondo nome dei destinatari

      Per inserire il nome e il nome dei destinatari in un campo di testo nella consegna, fai clic sul campo di testo scelto, quindi posiziona il cursore nel punto in cui desideri visualizzarli. Fai clic sulla prima icona nella barra degli strumenti a comparsa, quindi fai clic su **[!UICONTROL Personalization block]**. Seleziona **[!UICONTROL Greetings]**, quindi fai clic su **[!UICONTROL OK]**.

   * Inserire un collegamento in un’immagine

      Per portare i destinatari a un indirizzo esterno tramite un’immagine, fai clic sull’immagine corrispondente per visualizzare la barra degli strumenti a comparsa, posiziona il cursore sulla prima icona e fai clic su **[!UICONTROL Link to an external URL]**.

      Immetti l&#39;URL del collegamento nel campo **URL** utilizzando il seguente formato **https://www.myURL.com**, quindi conferma.

      Il collegamento può essere modificato in qualsiasi momento utilizzando la sezione a destra della finestra.

   * Inserire un collegamento nel testo

      Per integrare un collegamento esterno nel testo della consegna, seleziona un testo o un blocco di testo, quindi fai clic sulla prima icona nella barra degli strumenti a comparsa. Fai clic su **[!UICONTROL Link to an external URL]**, immetti l’indirizzo del collegamento nel campo **[!UICONTROL URL]** .

      Il collegamento può essere modificato in qualsiasi momento utilizzando la sezione a destra della finestra.

   * Aggiungere una pagina speculare

      Per consentire ai destinatari di visualizzare il contenuto della consegna in un browser Web, puoi integrare nella consegna un collegamento a una pagina speculare.

      Fare clic sul campo di testo in cui si desidera visualizzare il collegamento pubblicato. Fai clic sulla prima icona nella barra degli strumenti a comparsa, seleziona **[!UICONTROL Personalization block]**, quindi **[!UICONTROL Link to Mirror Page (MirrorPage)]**. Fai clic su **[!UICONTROL Save]** per confermare.

   * Integrare un collegamento a un’applicazione Web

      L’editor di contenuti digitali consente di integrare i collegamenti alle applicazioni Web dalla console Adobe Campaign, ad esempio una pagina di destinazione o una pagina del modulo. Per ulteriori informazioni, consulta [Collegamento a un&#39;applicazione Web](../../web/using/editing-content.md#link-to-a-web-application).

      Selezionare un campo di testo per il collegamento a un&#39;applicazione Web, quindi fare clic sulla prima icona. Scegli **[!UICONTROL Link to a Web application]**, quindi seleziona l&#39;applicazione desiderata facendo clic sull&#39;icona alla fine del campo **Applicazione web**.

1. Inviare messaggi

   Una volta integrato il contenuto, salva la consegna facendo clic su **Salva**. Ora verrà visualizzato nell’elenco delle consegne, disponibile nella scheda **[!UICONTROL Campaigns > Deliveries]** .


## Creare contenuti e selezionare il pubblico

Puoi creare direttamente in Campaign o importare il pubblico, nonché il contenuto dell’e-mail. Utilizza i collegamenti seguenti per scoprire come:

* Progettazione di un’e-mail in Campaign
   [!DNL :arrow_upper_right:] [Scopri come progettare un’e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html)
* Importare un contenuto e-mail
   [!DNL :arrow_upper_right:] [Caso di utilizzo: Creare un flusso di lavoro per caricare un contenuto di consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)
* Creare e utilizzare un modello e-mail
   [!DNL :arrow_upper_right:] [Ulteriori informazioni sui modelli e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)
* Selezionare il pubblico dell’e-mail
   [!DNL :arrow_upper_right:] [Scopri come definire la popolazione target](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)
* Convalidare una consegna e inviare bozze
   [!DNL :arrow_upper_right:] [Scopri i passaggi chiave per convalidare una consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
* Aggiungi [indirizzi di seed](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html)

## Verifica e-mail

Campaign offre diversi modi per testare e convalidare le e-mail prima di inviarle al pubblico.

[!DNL :arrow_upper_right:] [Applicare le best practice elencate nella documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html)

Puoi:

* Controlla i registri di analisi della consegna
* Invia bozze
* Aggiungere indirizzi seed
* Utilizzare i gruppi di controllo
* Controllare il rendering delle e-mail

[!DNL :arrow_upper_right:] [Ulteriori informazioni nella documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)

## Monitorare le e-mail

Dopo l’invio, controlla lo stato di consegna nel dashboard di consegna e accedi ai registri di consegna e ai rapporti di conferma del corretto invio dei messaggi.

[!DNL :arrow_upper_right:] [Ulteriori informazioni nella documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html)

