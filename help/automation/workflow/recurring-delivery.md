---
product: campaign
title: Consegna ricorrente
description: Ulteriori informazioni sull’attività del flusso di lavoro Consegna ricorrente
feature: Workflows
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 27308b0d-cbfc-4bc6-9061-d771ceac95fd
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 13%

---

# Consegna ricorrente{#recurring-delivery}



Un&#39;attività **[!UICONTROL Recurring delivery]** consente di configurare un&#39;occorrenza del modello di consegna specifica per una campagna.

![](assets/do-not-localize/how-to-video.png) [Guarda il video su questa funzione](#recurring-delivery-video)

Questa attività è disponibile solo dalla scheda **[!UICONTROL Targeting and workflows]** trovata in una campagna.

Per eseguire questa operazione:

1. Seleziona il modello di consegna su cui basare l’attività.

   ![](assets/recurring_delivery_001.png)

1. Configura il modello di consegna.

Il processo di configurazione per questa attività è simile a quello della creazione di un modello di consegna in termini di opzioni disponibili.

Per un esempio di questa attività in uso, fai riferimento a questa [sezione](send-a-birthday-email.md#creating-a-recurring-delivery-in-a-targeting-workflow).

## Come impostare la consegna ricorrente

Una **consegna ricorrente** creerà una nuova istanza di consegna ogni volta che viene eseguita. Ad esempio, se il flusso di lavoro è pianificato per essere eseguito una volta alla settimana, in un anno si otterranno 52 consegne. Ciò significa anche che i log ampi e quelli di tracciamento saranno separati per ogni istanza di consegna.

![Consegna ricorrente](assets/delivery_recurring.jpg)

Se desideri interrompere l’esecuzione di una consegna ricorrente, devi annullare completamente la campagna o interrompere l’esecuzione del flusso di lavoro. L’interruzione della consegna dal dashboard di Campaign interrompe solo l’occorrenza della consegna: le istanze successive della consegna ricorrente continueranno a essere create a ogni esecuzione del flusso di lavoro.

>[!NOTE]
>
>Impossibile inviare una bozza da un&#39;attività di tipo **[!UICONTROL Recurring delivery]**.
> 
>Per creare direttamente una consegna tramite un flusso di lavoro della campagna, utilizza le attività specifiche del canale preconfigurate (ad esempio **[!UICONTROL Email delivery]**).

## Video tutorial (#recurring-delivery-video)

Questo video spiega come configurare una consegna ricorrente e un’attività di pianificazione.

>[!VIDEO](https://video.tv.adobe.com/v/25040?quality=12)

Ulteriori video dimostrativi di Campaign sono disponibili [qui](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.
