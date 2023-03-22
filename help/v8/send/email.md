---
title: Inviare e-mail con Adobe Campaign
description: Introduzione alle e-mail in Adobe Campaign. Inviare e-mail personalizzate a una popolazione target.
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 9%

---

# Progettazione e invio di e-mail

Le consegne e-mail ti consentono di inviare e-mail personalizzate alla popolazione target. [Ulteriori informazioni](../send/send.md).

## Creare la prima consegna e-mail

Crea e-mail personalizzate e contestualmente pertinenti, coerenti con il resto dell’esperienza del cliente.

![](assets/new-email-content.png)


Nell’esempio seguente, imparerai a progettare una consegna e-mail in Adobe Campaign che contiene dati personalizzati, collegamenti a un URL esterno e un collegamento alla pagina speculare.

1. **Creare la consegna**

   Per creare una nuova consegna, seleziona **Campagne** scheda , fai clic su **Consegne** e fai clic su **Crea** , sopra l’elenco delle consegne esistenti.

   ![](assets/delivery_step_1.png)

1. **Selezionare il modello**

   Seleziona un modello di consegna, quindi assegna un nome alla consegna. Questo nome sarà visibile solo agli utenti della console Adobe Campaign e non ai destinatari, tuttavia questa intestazione verrà visualizzata nell’elenco delle consegne. Fai clic su **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. **Importare il contenuto**

   Fai clic sul pulsante **Origine** per incollare il contenuto di HTML.

   ![](assets/paste-content.png)


1. **Personalizzare il messaggio**

   * Aggiungi il nome e il cognome dei destinatari

      Per inserire il nome e il cognome dei profili di destinazione nel contenuto del messaggio, posiziona il cursore nel punto in cui desideri inserirli, quindi fai clic sull’ultima icona nella barra degli strumenti, quindi fai clic su **[!UICONTROL Include]** e seleziona **[!UICONTROL Greetings]**.

      ![](assets/include-greetings.png)

      Passa alla scheda Anteprima per controllare la personalizzazione selezionando un destinatario.

      ![](assets/perso-check.png)

      Ulteriori informazioni sulle opzioni di personalizzazione in [questa sezione](personalize.md).

   * Inserire un collegamento tracciato

      Per indirizzare i destinatari della consegna a un indirizzo esterno tramite un’immagine o un testo, selezionalo e fai clic sul pulsante **[!UICONTROL Add a link]** nella barra degli strumenti.

      Immetti l’URL del collegamento nel **URL** utilizzando il formato seguente **https://www.myURL.com**, quindi conferma.

      ![](assets/add-a-link.png)

   * Aggiungere una pagina speculare

      Per consentire ai destinatari di visualizzare il contenuto della consegna in un browser web, aggiungi un collegamento al [pagina speculare](../send/mirror-page.md) del tuo messaggio.

      Posiziona il cursore nel punto in cui desideri inserire il collegamento, fai clic sull’ultima icona nella barra degli strumenti, quindi fai clic su **[!UICONTROL Include]** e seleziona **[!UICONTROL link to mirror page]**.
   Quando il contenuto è pronto, fai clic su **Salva**: verrà ora visualizzato nell’elenco delle consegne, nel **[!UICONTROL Campaigns > Deliveries]** scheda . La tua prima consegna e-mail è pronta. Ora devi definire il pubblico, convalidare la consegna e inviarla.


Scopri come importare un contenuto e-mail in questo [caso d&#39;uso](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html).

Ulteriori informazioni nelle sezioni seguenti:

* [Progettazione di un’e-mail in Campaign](../send/email.md)
* [Creare e utilizzare un modello e-mail](../send/create-templates.md)
* [Selezionare il pubblico dell’e-mail](../audiences/gs-audiences.md)
* [Convalidare una consegna e inviare bozze](../send/preview-and-proof.md)

## Verifica e-mail

Campaign offre diversi modi per testare e convalidare le e-mail prima di inviarle al pubblico. Scopri come visualizzare in anteprima e testare il contenuto delle e-mail in [questa pagina](../send/preview-and-proof.md).

È possibile eseguire le seguenti operazioni:

* Controlla i registri di analisi della consegna
* Invia bozze
* Aggiungere indirizzi seed

[Ulteriori informazioni](../send/delivery-analysis.md)
