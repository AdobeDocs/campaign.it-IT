---
title: Inviare e-mail con Adobe Campaign
description: Introduzione alle e-mail in Adobe Campaign. Inviare e-mail personalizzate a una popolazione target.
feature: Email
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 96f1518f252be7ffa27ba8157b8a090bf4d4510d
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 9%

---

# Progettazione e invio di e-mail

Con Adobe Campaign, crea consegne e-mail per inviare e-mail personalizzate alla popolazione target. [Ulteriori informazioni](../send/send.md)

>[!NOTE]
>
>Per creare e-mail accattivanti e personalizzate, passa all&#39;[interfaccia utente Web](../start/campaign-ui.md#campaign-web-user-interface-ac-web-ui). Adobe Campaign viene fornito con E-mail Designer, un’interfaccia di trascinamento intuitiva che consente di progettare e perfezionare tutti i contenuti per ogni e-mail.


Scopri i passaggi chiave per creare e configurare una consegna in [questa pagina](../start/create-message.md).

## Creare una consegna e-mail

Crea e-mail personalizzate e contestualmente pertinenti, coerenti con il resto dell’esperienza del cliente.

![](assets/new-email-content.png)


Nell’esempio seguente, scoprirai i passaggi per progettare una consegna e-mail in Adobe Campaign che contiene dati personalizzati, collegamenti a un URL esterno e un collegamento alla pagina speculare.

1. **Crea la consegna**

   Per creare una nuova consegna, passa alla scheda **Campagne**, fai clic su **Consegne** e fai clic sul pulsante **Crea** sopra l&#39;elenco delle consegne esistenti.

   ![](assets/delivery_step_1.png)

1. **Seleziona il modello**

   Seleziona un modello di consegna, quindi assegna un nome alla consegna. Questo nome sarà visibile solo agli utenti della console Adobe Campaign e non ai destinatari, tuttavia questa intestazione verrà visualizzata nell’elenco delle consegne. Fai clic su **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. **Importa il contenuto**

   Fai clic sulla scheda **Source** per incollare il contenuto di HTML.

   ![](assets/paste-content.png)

   >[!NOTE]
   >
   >Per evitare problemi di prestazioni, le immagini incluse nelle e-mail non possono superare i 100 KB.

1. **Personalizza il messaggio**

   * Aggiungi nome e cognome dei destinatari

     Per inserire il nome e il cognome dei profili di destinazione nel contenuto del messaggio, posizionare il cursore nel punto in cui si desidera inserirli e fare clic sull&#39;ultima icona nella barra degli strumenti, quindi fare clic su **[!UICONTROL Include]** e selezionare **[!UICONTROL Greetings]**.

     ![](assets/include-greetings.png)

     Passa alla scheda anteprima per verificare la personalizzazione selezionando un destinatario.

     ![](assets/perso-check.png)

     Ulteriori informazioni sulle opzioni di personalizzazione in [questa sezione](personalize.md).

   * Inserire un collegamento tracciato

     Per portare i destinatari della consegna a un indirizzo esterno tramite un&#39;immagine o un testo, selezionarlo e fare clic sull&#39;icona **[!UICONTROL Add a link]** nella barra degli strumenti.

     Immetti l&#39;URL per il collegamento nel campo **URL** utilizzando il seguente formato **https://www.myURL.com**, quindi conferma.

     ![](assets/add-a-link.png)

   * Aggiungere una pagina mirror

     Per consentire ai destinatari di visualizzare il contenuto della consegna in un browser Web, aggiungi un collegamento alla [pagina mirror](mirror-page.md) del messaggio.

     Posizionare il cursore nel punto in cui si desidera inserire il collegamento e fare clic sull&#39;ultima icona nella barra degli strumenti, quindi fare clic su **[!UICONTROL Include]** e selezionare **[!UICONTROL link to mirror page]**.

     Ulteriori informazioni sulla gestione della pagina mirror in [questa sezione](mirror-page.md#link-to-mirror-page).

1. Puoi definire parametri aggiuntivi per l’e-mail, ad esempio l’invio di una copia dei messaggi a un indirizzo BBC, la modifica del formato del messaggio, l’impostazione di una codifica specifica e così via. Per ulteriori informazioni, consulta [questa sezione](email-parameters.md).

1. Quando il contenuto è pronto, fai clic su **Salva**: verrà ora visualizzato nell&#39;elenco delle consegne, nella scheda **[!UICONTROL Campaigns > Deliveries]**.

La prima consegna e-mail è pronta. Ora devi definire il pubblico, convalidare la consegna e inviarla.

Scopri come creare un flusso di lavoro per importare un contenuto e-mail in questo [caso d&#39;uso](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html){target="_blank"}.

>[!MORELIKETHIS]
>
>* [Creare una consegna](../start/create-message.md)
>* [Creare e utilizzare un modello di posta elettronica](create-templates.md)
>* [Seleziona il pubblico della tua e-mail](../audiences/gs-audiences.md)
>* [Convalidare una consegna e inviare bozze](preview-and-proof.md)
>* [Configura e invia la consegna](configure-and-send.md)
>* [Best practice per la consegna](https://experienceleague.adobe.com/docs/campaign/campaign-v8/send/delivery-best-practices.html){target="_blank"}

## Verifica e convalida le e-mail

Campaign offre diversi modi per testare e convalidare le e-mail prima di inviarle al pubblico. Scopri come visualizzare in anteprima e verificare il contenuto delle e-mail in [questa sezione](../send/preview-and-proof.md).

Puoi eseguire le seguenti azioni:

* [Inviare bozze](preview-and-proof.md)
* [Aggiungere indirizzi seed](../audiences/test-profiles.md)
* [Controllare i registri di analisi della consegna](delivery-analysis.md)

