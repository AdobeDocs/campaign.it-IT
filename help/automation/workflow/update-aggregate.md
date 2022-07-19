---
product: campaign
title: Aggregato di aggiornamento
description: Ulteriori informazioni sull’attività del flusso di lavoro aggregato Aggiorna
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 3%

---

# Aggregato di aggiornamento{#update-aggregate}

Gli aggregati sono definiti a livello di cubo a scopo di reporting. A **[!UICONTROL Workflow]** è disponibile durante la configurazione di un aggregato.

Per ulteriori informazioni sui cubi e sull’utilizzo degli aggregati in Adobe Campaign, consulta [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/designing-reports-with-cubes/about-cubes.html){target=&quot;_blank&quot;}.


Per aggiornare un aggregato, modifica il **[!UICONTROL Update aggregate]** e seleziona il cubo e l’aggregato da aggiornare.

È possibile eseguire un **Aggiornamento completo** o **Aggiornamento parziale**.

Per impostazione predefinita, durante ogni calcolo viene eseguito un aggiornamento completo. Per abilitare un aggiornamento parziale, seleziona l’opzione pertinente e definisci le condizioni di aggiornamento.

**Buone pratiche**: a **[!UICONTROL Scheduler]** l’attività può essere utilizzata per specificare la frequenza degli aggiornamenti di calcolo.

![](assets/scheduler-and-cube-aggregate.png)
