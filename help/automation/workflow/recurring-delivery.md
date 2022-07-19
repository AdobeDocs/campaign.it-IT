---
product: campaign
title: Consegna ricorrente
description: Ulteriori informazioni sull’attività del flusso di lavoro di consegna ricorrente
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 14%

---

# Consegna ricorrente{#recurring-delivery}



A **[!UICONTROL Recurring delivery]** activity ti consente di configurare un&#39;occorrenza del modello di consegna specifica per una campagna.

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#recurring-delivery-video)

Questa attività è disponibile solo dal **[!UICONTROL Targeting and workflows]** in una campagna.

Per eseguire questa operazione:

1. Seleziona il modello di consegna su cui verrà basata l’attività.

   ![](assets/recurring_delivery_001.png)

1. Configura il modello di consegna.

Il processo di configurazione per questa attività è simile a quello di creazione di un modello di consegna in termini di opzioni disponibili. Per ulteriori informazioni, consulta questo articolo .

Per un esempio dell’utilizzo di questa attività, consulta [sezione](send-a-birthday-email.md#creating-a-recurring-delivery-in-a-targeting-workflow).

## Come impostare una consegna ricorrente

A **consegna ricorrente** creerà una nuova istanza di consegna ogni volta che viene eseguita. Ad esempio, se il flusso di lavoro è pianificato per essere eseguito una volta alla settimana, in un anno si otterranno 52 consegne. Ciò significa anche che i registri di registro e di tracciamento ampi saranno separati da ogni istanza di consegna.

![Consegna ricorrente](assets/delivery_recurring.jpg)

Se desideri interrompere l’esecuzione di una consegna ricorrente, devi annullare completamente la campagna o interrompere l’esecuzione del flusso di lavoro. L’arresto della consegna dal dashboard di Campaign interrompe solo l’occorrenza della consegna: le istanze successive della consegna ricorrente continueranno a essere create a ogni esecuzione del flusso di lavoro.

>[!NOTE]
>
>Non è possibile inviare una prova da un **[!UICONTROL Recurring delivery]** digitare activity.
> 
>Per creare direttamente una consegna tramite un flusso di lavoro della campagna, utilizza le attività specifiche del canale preconfigurate (ad esempio **[!UICONTROL Email delivery]**).

## Video tutorial (#ricorrenti-delivery-video)

Questo video spiega come configurare una consegna ricorrente e un’attività di pianificazione.

>[!VIDEO](https://video.tv.adobe.com/v/25040?quality=12)

Sono disponibili ulteriori video dimostrativi su Campaign Classic [qui](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/overview.html?lang=it).
