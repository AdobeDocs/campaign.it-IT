---
product: campaign
title: Oggetti Jump (punto iniziale e punto finale)
description: Oggetti Jump (punto iniziale e punto finale)
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: b96ebf8c-9846-44c3-bd9b-9d617e389b1c
TQID: 'https://experienceleague.adobe.com/-EMtfOTZ2xklfuPoQ9ORXe8YVOFTxYF197vrw3zT4D4'
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
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 11%
---
# Oggetti Jump (punto iniziale e punto finale){#jump-start-point-and-end-point}



Gli oggetti grafici di tipo **[!UICONTROL Jump]** vengono utilizzati per migliorare la leggibilità di un diagramma complesso, in particolare quello con transizioni incrociate.

I salti sono transizioni senza frecce.

Passano da un’attività all’altra, come nell’esempio seguente:

![Flusso di lavoro in cui i salti del punto iniziale sostituiscono le transizioni lunghe a due salti dell&#39;endpoint che alimentano un&#39;unione e una deduplicazione.](assets/s_user_segmentation_jump_sample.png)

Per ogni transizione di tipo &quot;punto iniziale&quot;, è necessario posizionare una transizione di tipo &quot;punto finale&quot;.

Nello stesso flusso di lavoro è possibile inserire più salti di punti iniziali e finali. Sono identificati da un numero che deve essere inserito nei parametri:

![Attività Salta (punto iniziale) con i campi Etichetta e Numero salta impostati su 1.](assets/s_user_segmentation_jump_in.png)

Per migliorare la leggibilità del diagramma, è possibile modificare l&#39;immagine associata ai salti per visualizzare il numero correlato. Vedi [Cambia immagini attività](change-activity-images.md).
