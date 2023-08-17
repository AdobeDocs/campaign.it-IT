---
product: campaign
title: Controllo della consegna
description: Ulteriori informazioni sull’attività del flusso di lavoro Controllo consegna
feature: Workflows
exl-id: 09fe638d-5e1c-49d1-9196-6300c1e56703
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 2%

---

# Controllo della consegna{#delivery-control}



A **Controllo della consegna** L’azione -type ti consente di avviare, mettere in pausa o interrompere una consegna.

Può trattarsi della consegna specificata nella transizione, di una consegna selezionata esplicitamente o di una consegna calcolata da uno script. Per ulteriori informazioni, consulta [Consegna](delivery.md).

![](assets/edit_diffusion_act.png)

Se si seleziona **[!UICONTROL Start]**, l’attività eseguirà tutti i passaggi necessari per avviare la consegna (calcolo del target, preparazione dei contenuti, consegna). Se alcuni di questi passaggi sono già stati eseguiti da un’attività del flusso di lavoro precedente, non verranno eseguiti nuovamente. Ad esempio, se la stima target è già stata eseguita da un **[!UICONTROL Delivery]** attività di tipo (fare riferimento a [Consegna](delivery.md)), il **[!UICONTROL Act on the delivery]** L’attività avvierà i passaggi rimanenti (preparazione e distribuzione dei contenuti).

Sono disponibili le seguenti opzioni:

* **[!UICONTROL Generate an outbound transition]**

  Crea una transizione in uscita che verrà attivata alla fine dell’esecuzione. Puoi scegliere se recuperare o meno la destinazione della consegna in uscita.

* **[!UICONTROL Processing errors]**

  Fai riferimento a [Errori di elaborazione](monitor-workflow-execution.md#processing-errors).

## Parametri di input {#input-parameters}

* deliveryId

Identificatore della consegna, se l’azione selezionata è **[!UICONTROL Specified in the transition]**.
