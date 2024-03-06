---
title: Utilizzare Campaign e Adobe Experience Manager
description: Scopri come utilizzare Campaign e Adobe Experience Manager
feature: Experience Manager Integration
role: Admin, User
level: Beginner
exl-id: e83893f7-a8be-48a3-a7a6-aced7b4d4f69
source-git-commit: fc461fbbae23925dd29f17c8674cc287ba360147
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 0%

---

# Utilizzare Campaign e Adobe Experience Manager {#ac-aem}

L’integrazione tra Adobe Campaign e Adobe Experience Manager consente di gestire il contenuto delle consegne e-mail e dei moduli direttamente in Adobe Experience Manager. È possibile importare **Adobe Experience Manager** contenuti in Campaign o collegare il tuo **Adobe Experience Manager as a Cloud Service** , che consente di modificare il contenuto direttamente all&#39;interno dell&#39;interfaccia Web.

![](../assets/do-not-localize/book.png) [Scopri come modificare il Adobe Experience Manager come contenuto di Cloud Service nell’interfaccia web di Campaign](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-content.html?lang=en)

![](../assets/do-not-localize/book.png) [Ulteriori informazioni su Adobe Experience Manager in questo documento](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html#aem-and-adobe-campaign-integration-workflow)

## Importa contenuto da Adobe Experience Manager {#integrating-with-aem}

![](../assets/do-not-localize/speech.png)  In qualità di utente di Managed Cloud Service, [Adobe di contatto](../start/campaign-faq.md#support) per integrare Adobe Experience Manager con Campaign.

Questa integrazione può essere utilizzata, ad esempio, per creare una newsletter in Adobe Experience Manager che verrà quindi utilizzata in Adobe Campaign come parte di una campagna e-mail.

**Da Adobe Experience Manager:**

1. Accedi al tuo [!DNL Adobe Experience Manager] istanza di authoring e fai clic su Esperienza di Adobe nell’angolo superiore sinistro della pagina. Scegli **[!UICONTROL Sites]** dal menu.

   ![](assets/aem_authoring_1.png)

1. Accesso **[!UICONTROL Campaigns > Name of your brand (here we.Shopping) > Main Area > Email]**.

1. Clic **[!UICONTROL Create]** e seleziona **[!UICONTROL Page]** dal menu a discesa.

   ![](assets/aem_authoring_2.png)

1. Seleziona la **[!UICONTROL Adobe Campaign Email]** crea un modello e assegna un nome alla newsletter.

1. Dopo aver creato la pagina, accedi a **[!UICONTROL Page information]** e fai clic su **[!UICONTROL Open Properties]**.

   ![](assets/aem_authoring_3.png)

1. Personalizza il contenuto delle e-mail aggiungendo componenti, ad esempio campi di personalizzazione di Adobe Campaign. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-manager-65/content/sites/authoring/aem-adobe-campaign/campaign.html?lang=en#editing-email-content)

1. Quando l’e-mail è pronta, accedi al **[!UICONTROL Page information]** e fai clic su **[!UICONTROL Start workflow]**.

   ![](assets/aem_authoring_4.png)

1. Dal primo elenco a discesa, seleziona **[!UICONTROL Approve Adobe Campaign]** come modello di flusso di lavoro e fai clic su **[!UICONTROL Start workflow]**.

   ![](assets/aem_authoring_5.png)

1. Nella parte superiore della pagina verrà visualizzata una liberatoria che indica: `This page is subject to the workflow Approve for Adobe Campaign`. Clic **[!UICONTROL Complete]** accanto alla liberatoria per confermare la revisione e fare clic su **[!UICONTROL Ok]**.

1. Clic **[!UICONTROL Complete]** di nuovo e seleziona **[!UICONTROL Newsletter approval]** nel **[!UICONTROL Next Step]** a discesa.

   ![](assets/aem_authoring_6.png)

La newsletter è ora pronta e sincronizzata in Adobe Campaign.

**Da Adobe Campaign:**

1. Dalla sezione **[!UICONTROL Campaigns]** , fare clic su **[!UICONTROL Deliveries]** allora **[!UICONTROL Create]**.

1. Scegli la **[!UICONTROL Email delivery with AEM content (mailAEMContent)]** modello da **[!UICONTROL Delivery template]** menu a discesa.

   ![](assets/aem_authoring_7.png)

1. Aggiungi un **[!UICONTROL Label]** alla consegna e fai clic su **[!UICONTROL Continue]**.

1. Clic **[!UICONTROL Synchronize]** per accedere alle consegne AEM.

   Se il pulsante non è visibile nell’interfaccia, passa a **[!UICONTROL Properties]** e accedere al **[!UICONTROL Advanced]** scheda. Assicurati che **[!UICONTROL Content editing mode]** campo configurato per **[!UICONTROL AEM]** e inserisci i dettagli dell’istanza AEM nella sezione **[!UICONTROL AEM account]** campo.

   ![](assets/aem_authoring_8.png)

1. Seleziona la consegna AEM creata in precedenza in [!DNL Adobe Experience Manager] e confermare facendo clic su **[!UICONTROL Ok]**.

   ![](assets/aem_authoring_11.png)

1. Assicurati di fare clic su **[!UICONTROL Refresh content]** ogni volta che vengono apportate modifiche alla consegna dell’AEM.

   ![](assets/aem_authoring_12.png)

1. Per rimuovere il collegamento tra Experience Manager e Campaign, fai clic su **[!UICONTROL Desynchronize]**.

L’e-mail è ora pronta per essere inviata al pubblico.

## Importare risorse dalla libreria Adobe Experience Manager Assets {#assets-library}

Puoi anche inserire direttamente le risorse dal tuo [!DNL Adobe Experience Manager Assets Library] durante la modifica di un’e-mail o di una pagina di destinazione in Adobe Campaign. Questa funzionalità è descritta in [Documentazione di Adobe Experience Manager Assets](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html?lang=en).

**Da Adobe Experience Manager:**

1. Accedi al tuo [!DNL Adobe Experience Manager] istanza di authoring e fai clic su Esperienza di Adobe nell’angolo superiore sinistro della pagina. Scegli **[!UICONTROL Assets]** `>` **[!UICONTROL Files]** dal menu.

   ![](assets/aem_assets_1.png)

1. Clic **Crea** allora **File** per importare la risorsa nel **Libreria Adobe Experience Manager Assets**. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html?lang=en#uploading-assets)

   ![](assets/aem_assets_2.png)

1. Se necessario, rinomina la risorsa e seleziona **Carica**.

La risorsa è ora caricata nel tuo **Libreria Adobe Experience Manager Assets**.

**Da Adobe Campaign:**

1. In Adobe Campaign, crea una nuova consegna navigando nel **Campagne** , fare clic su **Consegne** e fai clic su **Crea** sopra l’elenco delle consegne esistenti.

   ![](assets/aem_assets_3.png)

1. Seleziona un **Modello di consegna**, quindi denomina la consegna.

1. Definisci e personalizza il contenuto del messaggio. [Ulteriori informazioni](../send/email.md)

1. Per utilizzare il **Libreria Adobe Experience Manager Assets**, accedere a **[!UICONTROL Properties]** della sua consegna di AEM e selezionare **[!UICONTROL Advanced]** scheda.

   Scegli il tuo **Account AEM** e abilita **[!UICONTROL Use above AEM instance as shared asset library]** opzione.

   ![](assets/aem_authoring_9.png)

1. Dalla sezione **Immagine** , accedere al **[!UICONTROL Select a shared asset]** menu.

   ![](assets/aem_assets_4.png)

1. Nella finestra di selezione, selezionare un&#39;immagine dalla **Libreria Adobe Experience Manager Assets**, quindi **Seleziona**.

   ![](assets/aem_assets_5.png)

La risorsa viene ora caricata nella consegna e-mail. Ora puoi specificare il pubblico di destinazione, confermare la consegna e procedere con l’invio.
