---
product: campaign
title: Controllo della consegna
description: Ulteriori informazioni sull’attività del flusso di lavoro Controllo consegna
feature: Workflows
role: User
exl-id: 09fe638d-5e1c-49d1-9196-6300c1e56703
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 2%

---

# Controllo della consegna{#delivery-control}



Un&#39;azione di tipo **Controllo di consegna** consente di avviare, mettere in pausa o interrompere una consegna.

Può trattarsi della consegna specificata nella transizione, di una consegna selezionata esplicitamente o di una consegna calcolata da uno script. Per ulteriori informazioni, consulta [Consegna](delivery.md).

![](assets/edit_diffusion_act.png)

Se si seleziona **[!UICONTROL Start]**, l&#39;attività eseguirà tutti i passaggi necessari per avviare la consegna (calcolo del target, preparazione del contenuto, consegna). Se alcuni di questi passaggi sono già stati eseguiti da un’attività del flusso di lavoro precedente, non verranno eseguiti nuovamente. Ad esempio, se la stima di destinazione è già stata eseguita da un&#39;attività di tipo **[!UICONTROL Delivery]** (fare riferimento a [Consegna](delivery.md)), l&#39;attività di tipo **[!UICONTROL Act on the delivery]** avvierà i passaggi rimanenti (preparazione e consegna dei contenuti).

Sono disponibili le seguenti opzioni:

* **[!UICONTROL Generate an outbound transition]**

  Crea una transizione in uscita che verrà attivata alla fine dell’esecuzione. Puoi scegliere se recuperare o meno la destinazione della consegna in uscita.

* **[!UICONTROL Processing errors]**

  Consulta [Errori di elaborazione](monitor-workflow-execution.md#processing-errors).

## Parametri di input {#input-parameters}

* deliveryId

Identificatore di consegna, se l&#39;azione selezionata è **[!UICONTROL Specified in the transition]**.
