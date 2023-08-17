---
product: campaign
title: Unione AND
description: Unione AND
feature: Workflows
exl-id: c70a106d-3518-4eac-9944-6f7c93d85bac
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 21%

---

# Unione AND{#and-join}



Un join attiva la relativa transizione in uscita solo quando vengono attivate tutte le transizioni in entrata, ovvero quando tutte le attività precedenti sono state completate. Questo consente di verificare che alcune attività siano state completate prima di continuare a eseguire il flusso di lavoro.

Ad esempio, puoi utilizzare un’attività AND-join nel contesto della creazione di contenuti e dell’automazione dell’invio della consegna, per assicurarti che una consegna venga avviata solo una volta completati i passaggi di query di destinazione e aggiornamenti dei contenuti. Un caso d’uso dedicato è disponibile in

![](assets/and-join-usage.png)

>[!NOTE]
>
>Tieni presente che le transizioni in entrata configurate con dimensioni di targeting diverse non possono essere unite tra loro utilizzando una **[!UICONTROL AND-join]** attività.

La popolazione in uscita inviata dell’attività è determinata scegliendo un set principale tra le transizioni in entrata nell’attività.

La transizione in uscita può contenere solo una delle popolazioni di transizione in entrata. Se l’attività non è configurata, la transizione in uscita selezionerà in modo casuale una delle popolazioni in entrata.

>[!CAUTION]
>
>Nel caso di **Unione AND** attività di tipo, le variabili evento vengono unite ma se una stessa variabile viene definita due volte, si verifica un conflitto e il valore rimane indeterminato. Per ulteriori informazioni al riguardo, consulta [questa sezione](javascript-scripts-and-templates.md#event-variables).
