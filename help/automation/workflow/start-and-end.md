---
product: campaign
title: Attività Start e End
description: Ulteriori informazioni sulle attività del flusso di lavoro Start ed End
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 1de622bc-967b-403b-86e0-2ad32cb432e3
TQID: 'https://experienceleague.adobe.com/Y6nuELN3qjtuXhruC9MgmyqxzptNTJgfZ0XLGleQ3A4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 3%
---
# Attività Start e End{#start-and-end}



Le attività **[!UICONTROL Start]** e **[!UICONTROL End]** ti consentono di contrassegnare graficamente l&#39;inizio e la fine di un flusso di lavoro. Queste attività non hanno alcun impatto funzionale e sono pertanto facoltative.

* **[!UICONTROL Start]**

  L’esecuzione di un flusso di lavoro inizia con le attività senza una transizione in entrata e le attività di tipo Start.

  ![Flusso di lavoro con attività di inizio, Consegna, Approvazione, Controllo della consegna e due attività di fine, una per risultato di approvazione.](assets/s_user_segmentation_start_stop.png)

* **[!UICONTROL End]**

  È possibile configurare l&#39;attività **[!UICONTROL End]** per interrompere tutte le attività in corso. A questo scopo, fai doppio clic sull’attività per visualizzarne le proprietà e seleziona l’opzione appropriata.

  ![Proprietà attività finale con l&#39;opzione Arresta tutte le attività in corso selezionata.](assets/s_user_segmentation_end.png)

  I dati nella tabella di lavoro vengono eliminati automaticamente quando l&#39;attività finale è abilitata. Se non è necessario e per evitare carichi superflui, puoi scegliere di disabilitare la transizione all’ultimo output dell’attività. Ad esempio, a un output di consegna, se non è pianificato alcun processo, deseleziona l’opzione pertinente come mostrato di seguito:

  ![Proprietà dell&#39;attività di consegna con l&#39;opzione Generate an outbound transition cancellata.](assets/s_advuser_delivery_option_no_output.png)
