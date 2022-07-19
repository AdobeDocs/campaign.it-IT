---
product: campaign
title: Attività AND-join
description: Attività AND-join
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 5%

---

# Attività AND-join{#and-join}



Un join attiva la relativa transizione in uscita solo quando vengono attivate tutte le transizioni in entrata, ad esempio al termine di tutte le attività precedenti. Questo ti consente di verificare che alcune attività siano state completate prima di continuare a eseguire il flusso di lavoro.

Ad esempio, puoi utilizzare un’attività AND-join nel contesto dell’automazione della creazione e dell’invio dei contenuti, per assicurarti che una consegna venga avviata solo una volta completati i passaggi di query di destinazione e aggiornamenti dei contenuti. È disponibile un caso d’uso dedicato in

![](assets/and-join-usage.png)

>[!NOTE]
>
>Tieni presente che le transizioni in entrata configurate con dimensioni di targeting diverse non possono essere unite utilizzando un **[!UICONTROL AND-join]** attività.

La popolazione in uscita inviata dell’attività è determinata scegliendo un set principale tra le transizioni in entrata nell’attività.

La transizione in uscita può contenere solo una delle popolazioni di transizione in entrata. Se l’attività non è configurata, la transizione in uscita selezionerà in modo casuale una delle popolazioni in entrata.

>[!CAUTION]
>
>Nel caso di **AND-join** attività di tipo , le variabili dell’evento vengono unite ma se una stessa variabile viene definita due volte, si verifica un conflitto e il valore rimane indeterminato. Per ulteriori informazioni al riguardo, consulta [questa sezione](javascript-scripts-and-templates.md#event-variables).
