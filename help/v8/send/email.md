---
product: Adobe Campaign
title: Inviare e-mail con Adobe Campaign
description: Guida introduttiva alle e-mail in Campaign
feature: Panoramica
role: Data Engineer
level: Beginner
source-git-commit: dc99c00f68e53a308f8c869f07aa93baed3a5129
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 5%

---

# Progettazione e invio di e-mail

Le consegne e-mail ti consentono di inviare e-mail personalizzate alla popolazione target.

[!DNL :arrow_upper_right:] Ulteriori informazioni sono disponibili nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html).

## Creare la prima consegna e-mail

Crea e-mail personalizzate e contestualmente pertinenti, coerenti con il resto dell’esperienza del cliente.

![](assets/new-email-content.png)


Nell’esempio seguente, imparerai a progettare una consegna e-mail in Adobe Campaign che contiene dati personalizzati, collegamenti a un URL esterno e un collegamento alla pagina speculare.

1. **Creare la consegna**

   Per creare una nuova consegna, passa alla scheda **Campagne** , fai clic su **Consegne** e fai clic sul pulsante **Crea** sopra l’elenco delle consegne esistenti.

   ![](assets/delivery_step_1.png)

1. **Selezionare il modello**

   Seleziona un modello di consegna, quindi assegna un nome alla consegna. Questo nome sarà visibile solo agli utenti della console Adobe Campaign e non ai destinatari, tuttavia questa intestazione verrà visualizzata nell’elenco delle consegne. Fai clic su **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. **Importare il contenuto**

   Fai clic sulla scheda **Origine** per incollare il contenuto HTML.

   ![](assets/paste-content.png)


1. **Personalizzare il messaggio**


   * Aggiungi il nome e il cognome dei destinatari

      Per inserire il nome e il cognome dei profili di destinazione nel contenuto del messaggio, posiziona il cursore nel punto in cui desideri inserirli, quindi fai clic sull’ultima icona nella barra degli strumenti, quindi fai clic su **[!UICONTROL Include]** e seleziona **[!UICONTROL Greetings]**.

      ![](assets/include-greetings.png)

      Passa alla scheda Anteprima per controllare la personalizzazione selezionando un destinatario.

      ![](assets/perso-check.png)

   * Inserire un collegamento tracciato

      Per indirizzare i destinatari a un indirizzo esterno tramite un’immagine o un testo, selezionalo e fai clic sull’icona **[!UICONTROL Add a link]** nella barra degli strumenti.

      Immetti l&#39;URL del collegamento nel campo **URL** utilizzando il seguente formato **https://www.myURL.com**, quindi conferma.

      ![](assets/add-a-link.png)

   * Aggiungere una pagina speculare

      Per consentire ai destinatari di visualizzare il contenuto della consegna in un browser web, aggiungi un collegamento alla pagina speculare del messaggio.

      Posizionare il cursore nel punto in cui si desidera inserire il collegamento e fare clic sull&#39;ultima icona nella barra degli strumenti, quindi fare clic su **[!UICONTROL Include]** e selezionare **[!UICONTROL link to mirror page]**.
   Quando il contenuto è pronto, fai clic su **Salva**: verrà ora visualizzato nell’elenco delle consegne, nella scheda **[!UICONTROL Campaigns > Deliveries]** . La tua prima consegna e-mail è pronta. Ora devi definire il pubblico, convalidare la consegna e inviarla.


Ulteriori informazioni sono disponibili nelle seguenti sezioni della documentazione di Campaign Classic v7:

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

