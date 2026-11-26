---
title: Utilizzare Campaign e Adobe Experience Manager
description: Scopri come utilizzare Campaign e Adobe Experience Manager
feature: Experience Manager Integration
role: Admin, User
level: Beginner
exl-id: e83893f7-a8be-48a3-a7a6-aced7b4d4f69
TQID: 'https://experienceleague.adobe.com/LM635Kjl7bucy1SMcEPuhCElUI7MNrO4B3fwo9fpyFQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: df0d6518-6f49-46e2-b46e-3bcc513f553f
    internal-label: Experience Manager integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 765af3342eb29f27dafa12f72634f5d91361bed5
workflow-type: tm+mt
source-wordcount: '982'
ht-degree: 0%
---
# Utilizzare Campaign e Adobe Experience Manager {#ac-aem}

L’integrazione tra Adobe Campaign e Adobe Experience Manager consente di gestire il contenuto delle consegne e-mail e dei moduli direttamente in Adobe Experience Manager.

## Utilizzare Adobe Experience Manager as a Cloud Service con l’interfaccia utente di Campaign Web {#aem-cs-web-ui}

Con l’interfaccia utente di Campaign Web, puoi collegare il tuo ambiente Adobe Experience Manager as a Cloud Service per centralizzare i contenuti. Un’unica fonte di verità per le risorse e i modelli mantiene le e-mail coerenti tra i diversi canali ed evita la duplicazione dei contenuti tra le due soluzioni.

* **Assets**: gestisci le risorse in Adobe Experience Manager Assets e riutilizzale direttamente nel contenuto dell&#39;e-mail. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/campaign-web/v8/integrations/aem-assets){target="_blank"}
* **Modelli**: crea e approva modelli e-mail in Adobe Experience Manager as a Cloud Service, quindi utilizzali come modelli di contenuto nelle consegne. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/campaign-web/v8/integrations/aem-content){target="_blank"}

La connessione si basa su un account esterno **[!UICONTROL AEM]** configurato nella console client. Vedi [Account esterni](../config/external-accounts.md).

## Utilizzare Adobe Experience Manager con la console client {#aem-console}

Le sezioni seguenti descrivono l’integrazione nella console client di Campaign.

[Ulteriori informazioni su Adobe Experience Manager in questo documento](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html#aem-and-adobe-campaign-integration-workflow){target="_blank"}.


>[!NOTE]
>
>In qualità di utente di Managed Cloud Services, [contatta Adobe](../start/campaign-faq-comprehensive.md#support) per integrare Adobe Experience Manager con Campaign.

## Importa contenuto da Adobe Experience Manager {#integrating-with-aem}

Questa integrazione può essere utilizzata, ad esempio, per creare una newsletter in Adobe Experience Manager che verrà quindi utilizzata in Adobe Campaign come parte di una campagna e-mail.

**Da Adobe Experience Manager:**

1. Passa all&#39;istanza dell&#39;autore [!DNL Adobe Experience Manager] e fai clic su Adobe Experience nell&#39;angolo superiore sinistro della pagina. Scegliere **[!UICONTROL Sites]** dal menu.

   ![Menu di navigazione di Adobe Experience Manager con l&#39;opzione Sites evidenziata](assets/aem_authoring_1.png)

1. Accedi a **[!UICONTROL Campaigns > Name of your brand (here we.Shopping) > Main Area > Email]**.

1. Fare clic su **[!UICONTROL Create]** e selezionare **[!UICONTROL Page]** dal menu a discesa.

   ![Cartella e-mail AEM Sites con il menu Crea aperto e Pagina selezionata](assets/aem_authoring_2.png)

1. Seleziona il modello **[!UICONTROL Adobe Campaign Email]** e assegna un nome alla newsletter.

1. Dopo aver creato la pagina, accedere al menu **[!UICONTROL Page information]** e fare clic su **[!UICONTROL Open Properties]**.

   ![Editor pagina newsletter con menu Informazioni pagina aperto ed Proprietà aperte evidenziate](assets/aem_authoring_3.png)

1. Personalizza il contenuto delle e-mail aggiungendo componenti, ad esempio campi di personalizzazione di Adobe Campaign. Ulteriori informazioni sono disponibili nella [documentazione di Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-65/content/sites/authoring/aem-adobe-campaign/campaign.html#editing-email-content){target="_blank"}.

1. Quando l&#39;e-mail è pronta, passa al menu **[!UICONTROL Page information]** e fai clic su **[!UICONTROL Start workflow]**.

   ![Editor pagina newsletter con menu Informazioni pagina aperto ed Avvia flusso di lavoro evidenziato](assets/aem_authoring_4.png)

1. Dal primo elenco a discesa, selezionare **[!UICONTROL Approve Adobe Campaign]** come modello di flusso di lavoro e fare clic su **[!UICONTROL Start workflow]**.

   ![Avvia finestra di dialogo flusso di lavoro con Approva per Adobe Campaign selezionato come modello di flusso di lavoro](assets/aem_authoring_5.png)

1. Nella parte superiore della pagina verrà visualizzata una dichiarazione di non responsabilità che indica `This page is subject to the workflow Approve for Adobe Campaign`. Fare clic su **[!UICONTROL Complete]** accanto alla liberatoria per confermare la revisione e fare clic su **[!UICONTROL Ok]**.

1. Fare di nuovo clic su **[!UICONTROL Complete]** e selezionare **[!UICONTROL Newsletter approval]** nel menu a discesa **[!UICONTROL Next Step]**.

   ![Finestra di dialogo Completa elemento di lavoro con Approvazione newsletter selezionata nell&#39;elenco Passaggio successivo e pulsante OK](assets/aem_authoring_6.png)

La newsletter è ora pronta e sincronizzata in Adobe Campaign.

**Da Adobe Campaign:**

1. Dalla scheda **[!UICONTROL Campaigns]**, fai clic su **[!UICONTROL Deliveries]** e quindi su **[!UICONTROL Create]**.

1. Scegliere il modello **[!UICONTROL Email delivery with AEM content (mailAEMContent)]** dal menu a discesa **[!UICONTROL Delivery template]**.

   ![Elenco modelli di consegna campagna con consegna e-mail con contenuto AEM (mailAEMContent) selezionato](assets/aem_authoring_7.png)

1. Aggiungi **[!UICONTROL Label]** alla consegna e fai clic su **[!UICONTROL Continue]**.

1. Fai clic su **[!UICONTROL Synchronize]** per accedere alle tue consegne AEM.

   Se il pulsante non è visibile nell&#39;interfaccia, passare al pulsante **[!UICONTROL Properties]** e accedere alla scheda **[!UICONTROL Advanced]**. Assicurati che il campo **[!UICONTROL Content editing mode]** sia configurato per **[!UICONTROL AEM]** e inserisci i dettagli dell&#39;istanza di AEM nel campo **[!UICONTROL AEM account]**.

   ![Barra degli strumenti di consegna e-mail di Campaign con il pulsante Sincronizza evidenziato](assets/aem_authoring_8.png)

1. Selezionare la consegna AEM creata in precedenza in [!DNL Adobe Experience Manager] e confermare facendo clic su **[!UICONTROL Ok]**.

   ![Sincronizza con la finestra di dialogo del contenuto di AEM in cui sono elencate le e-mail AEM approvate con la riga Newsletter selezionata](assets/aem_authoring_11.png)

1. Assicurati di fare clic sul pulsante **[!UICONTROL Refresh content]** ogni volta che vengono apportate modifiche alla consegna AEM.

   ![Consegna e-mail sincronizzata con il pulsante Aggiorna contenuto evidenziato e il pulsante Desincronizza](assets/aem_authoring_12.png)

1. Per rimuovere il collegamento tra Experience Manager e Campaign, fare clic su **[!UICONTROL Desynchronize]**.

L’e-mail è ora pronta per essere inviata al pubblico.

## Importare risorse dalla libreria Adobe Experience Manager Assets {#assets-library}

Puoi anche inserire direttamente le risorse da [!DNL Adobe Experience Manager Assets Library] durante la modifica di un&#39;e-mail o di una pagina di destinazione in Adobe Campaign. Questa funzionalità è descritta nella [documentazione di Adobe Experience Manager Assets](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html){target="_blank"}.

**Da Adobe Experience Manager:**

1. Passa all&#39;istanza dell&#39;autore [!DNL Adobe Experience Manager] e fai clic su Adobe Experience nell&#39;angolo superiore sinistro della pagina. Scegliere **[!UICONTROL Assets]** `>` **[!UICONTROL Files]** dal menu.

   ![Menu di navigazione di AEM Assets con l&#39;opzione File evidenziata](assets/aem_assets_1.png)

1. Fai clic su **Crea** e quindi su **File** per importare la risorsa nella **Libreria Adobe Experience Manager Assets**. Ulteriori informazioni sono disponibili nella [documentazione di Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html#uploading-assets){target="_blank"}.

   ![Visualizzazione file di AEM Assets con il menu Crea aperto e File selezionati per caricare una risorsa](assets/aem_assets_2.png)

1. Se necessario, rinomina la risorsa e seleziona **Carica**.

La risorsa è stata caricata nella **libreria Adobe Experience Manager Assets**.

**Da Adobe Campaign:**

1. In Adobe Campaign, crea una nuova consegna sfogliando la scheda **Campagne**, fai clic su **Consegne** e fai clic sul pulsante **Crea** sopra l&#39;elenco delle consegne esistenti.

   ![Elenco consegne campagna nella scheda Campagne con il pulsante Crea evidenziato](assets/aem_assets_3.png)

1. Seleziona un **modello di consegna**, quindi assegna un nome alla consegna.

1. Definisci e personalizza il contenuto del messaggio. [Ulteriori informazioni](../send/email.md)

1. Per utilizzare la **libreria Adobe Experience Manager Assets**, accedi a **[!UICONTROL Properties]** della consegna AEM e seleziona la scheda **[!UICONTROL Advanced]**.

   Scegli il tuo account **AEM** e abilita l&#39;opzione **[!UICONTROL Use above AEM instance as shared asset library]**.

   ![Scheda Avanzate delle proprietà di consegna con l&#39;account AEM impostato e l&#39;opzione della libreria di risorse condivise abilitata](assets/aem_authoring_9.png)

1. Dall&#39;icona **Immagine**, accedere al menu **[!UICONTROL Select a shared asset]**.

   ![Menu immagine dell&#39;editor e-mail di Campaign con Seleziona una risorsa condivisa evidenziato](assets/aem_assets_4.png)

1. Dalla finestra di selezione, seleziona un&#39;immagine dalla **libreria Adobe Experience Manager Assets**, quindi **Seleziona**.

   ![Seleziona una finestra di risorse condivise in cui sono elencati i file della libreria AEM Assets con jogging-newsletter.jpg selezionato](assets/aem_assets_5.png)

La risorsa viene ora caricata nella consegna e-mail. Ora puoi specificare il pubblico di destinazione, confermare la consegna e procedere con l’invio.
