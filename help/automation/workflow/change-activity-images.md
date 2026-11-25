---
product: campaign
title: Modificare le immagini dell’attività
description: Scopri come modificare l’immagine dell’attività
feature: Workflows
role: Admin
version: Campaign v8, Campaign Classic v7
exl-id: f5580401-3305-4915-88a2-3400a32aa7aa
TQID: 'https://experienceleague.adobe.com/9i-2gtfWr0ghkIif2S-ORoXk-hTlSMHgkeRAmMW0msg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 2%
---
# Modificare le immagini dell’attività{#change-activity-images}



È possibile modificare le immagini utilizzate nei diagrammi dei vari flussi di lavoro. Essi devono tuttavia rispettare determinati vincoli. Di seguito sono riportate le fasi di implementazione:

* Per modificare l&#39;immagine di sfondo, selezionare il flusso di lavoro di destinazione desiderato, quindi fare clic sulla scheda **[!UICONTROL Properties]**.

  ![Proprietà flusso di lavoro, scheda Avanzate: campo Immagine di sfondo con l&#39;icona Seleziona collegamento evidenziata.](assets/s_user_segmentation_properties_tab.png)

  Per selezionare l&#39;immagine da utilizzare, fare clic sull&#39;icona **[!UICONTROL Select link]** a destra del campo **[!UICONTROL Background image]**.

  >[!NOTE]
  >
  >La larghezza in pixel dell&#39;immagine di sfondo deve essere un multiplo di 4.

  ![Finestra di selezione delle immagini in cui sono elencate le immagini di sfondo, ad esempio backgrounds/grid.png, con OK per confermare.](assets/s_user_segmentation_background_select.png)

  L&#39;icona **[!UICONTROL Edit link]** consente di visualizzare l&#39;immagine selezionata.

* Per modificare l&#39;immagine associata a un&#39;attività, fare doppio clic sull&#39;oggetto e quindi sulla scheda **[!UICONTROL Advanced]**.

  Per selezionare l&#39;immagine da utilizzare, fare clic sull&#39;icona **[!UICONTROL Select link]** a destra del campo **[!UICONTROL Image]**.

  ![Scheda avanzata di un&#39;attività con il campo Immagine evidenziato, impostata su activities/dedup.png.](assets/s_user_segmentation_activity_image.png)

  L&#39;icona **[!UICONTROL Edit link]** consente di visualizzare l&#39;immagine selezionata.

  ![Anteprima dell&#39;immagine selezionata nms:activities/dedup.png, visualizzata con l&#39;icona Modifica collegamento.](assets/s_user_segmentation_activity_image_select.png)

>[!NOTE]
>
>Le immagini salvate nel nodo **[!UICONTROL Administration > Configuration > Images]** della struttura sono disponibili per la selezione.
>  
>Le immagini devono essere in formato PNG, con 48x48 pixel, 16 milioni di colori e uno sfondo trasparente.
