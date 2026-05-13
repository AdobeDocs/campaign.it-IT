---
product: campaign
title: AND-join
description: AND-join
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: c70a106d-3518-4eac-9944-6f7c93d85bac
TQID: https://experienceleague.adobe.com/1ChXl3Rlm93ftFFaD7Z-PcoO7CwUcxRHm2JdCFzIOZs
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 193
ht-degree: 22%

---

# AND-join{#and-join}



Un join attiva la relativa transizione in uscita solo quando vengono attivate tutte le transizioni in entrata, ovvero quando tutte le attività precedenti sono state completate. Questo consente di verificare che alcune attività siano state completate prima di continuare a eseguire il flusso di lavoro.

Ad esempio, puoi utilizzare un’attività AND-join nel contesto della creazione di contenuti e dell’automazione dell’invio della consegna, per assicurarti che una consegna venga avviata solo una volta completati i passaggi di query di destinazione e aggiornamenti dei contenuti. Un caso d’uso dedicato è disponibile in

![](assets/and-join-usage.png)

>[!NOTE]
>
>Le transizioni in entrata configurate con dimensioni di targeting diverse non possono essere unite insieme utilizzando un&#39;attività **[!UICONTROL AND-join]**.

La popolazione in uscita inviata dell’attività è determinata scegliendo un set principale tra le transizioni in entrata nell’attività.

La transizione in uscita può contenere solo una delle popolazioni di transizione in entrata. Se l’attività non è configurata, la transizione in uscita selezionerà in modo casuale una delle popolazioni in entrata.

>[!CAUTION]
>
>Nel caso di attività di tipo **AND-join**, le variabili evento vengono unite ma se viene definita due volte la stessa variabile, si verifica un conflitto e il valore rimane indeterminato. Per ulteriori informazioni al riguardo, consulta [questa sezione](javascript-scripts-and-templates.md#event-variables).
