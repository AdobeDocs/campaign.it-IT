---
product: campaign
title: Attività Start e End
description: Ulteriori informazioni sulle attività del flusso di lavoro Start ed End
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 1de622bc-967b-403b-86e0-2ad32cb432e3
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 4%

---

# Attività Start e End{#start-and-end}



Le attività **[!UICONTROL Start]** e **[!UICONTROL End]** ti consentono di contrassegnare graficamente l&#39;inizio e la fine di un flusso di lavoro. Queste attività non hanno alcun impatto funzionale e sono pertanto facoltative.

* **[!UICONTROL Start]**

  L’esecuzione di un flusso di lavoro inizia con le attività senza una transizione in entrata e le attività di tipo Start.

  ![](assets/s_user_segmentation_start_stop.png)

* **[!UICONTROL End]**

  È possibile configurare l&#39;attività **[!UICONTROL End]** per interrompere tutte le attività in corso. A questo scopo, fai doppio clic sull’attività per visualizzarne le proprietà e seleziona l’opzione appropriata.

  ![](assets/s_user_segmentation_end.png)

  I dati nella tabella di lavoro vengono eliminati automaticamente quando l&#39;attività finale è abilitata. Se non è necessario e per evitare carichi superflui, puoi scegliere di disabilitare la transizione all’ultimo output dell’attività. Ad esempio, a un output di consegna, se non è pianificato alcun processo, deseleziona l’opzione pertinente come mostrato di seguito:

  ![](assets/s_advuser_delivery_option_no_output.png)
