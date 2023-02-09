---
product: campaign
title: Aggregato di aggiornamento
description: Ulteriori informazioni sull’attività del flusso di lavoro aggregato Aggiorna
feature: Workflows
role: Data Engineer
level: Beginner
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 3%

---

# Aggregato di aggiornamento{#update-aggregate}

Aggregati definiti in [cubi](../../v8/reporting/gs-cubes.md) a scopo di reporting può essere aggiornato con un’attività specifica. A **[!UICONTROL Workflow]** è disponibile durante la configurazione dell’aggregato.

Ulteriori informazioni su cubi e aggregati in [questa sezione](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates).

Per aggiornare un aggregato, modifica il **[!UICONTROL Update aggregate]** e selezionare il cubo e l&#39;aggregato da aggiornare.

Puoi configurare un **Aggiornamento completo** o **Aggiornamento parziale**.

![](assets/update-aggregate-details.png)

Per impostazione predefinita, durante ogni calcolo viene eseguito un aggiornamento completo. Per abilitare un aggiornamento parziale, seleziona l’opzione e definisci le condizioni di aggiornamento.

![](assets/update-aggregate-partial.png)

Una buona pratica è quella di aggiungere un **[!UICONTROL Scheduler]** attività per impostare la frequenza degli aggiornamenti di calcolo.
