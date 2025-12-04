---
product: campaign
title: Aggregato di aggiornamento
description: Ulteriori informazioni sull’attività del flusso di lavoro aggregato Aggiornamento
feature: Workflows
role: Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 3%

---

# Aggregato di aggiornamento{#update-aggregate}

Gli aggregati definiti in [cubi](../../v8/reporting/gs-cubes.md) a scopo di reporting possono essere aggiornati con un&#39;attività specifica. È disponibile una scheda **[!UICONTROL Workflow]** durante la configurazione dell&#39;aggregazione.

Ulteriori informazioni su cubi e aggregati sono disponibili in [questa sezione](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates).

Per aggiornare un aggregato, modificare l&#39;attività **[!UICONTROL Update aggregate]** e selezionare il cubo e l&#39;aggregato da aggiornare.

Puoi configurare un **aggiornamento completo** o un **aggiornamento parziale**.

![](assets/update-aggregate-details.png)

Per impostazione predefinita, durante ogni calcolo viene eseguito un aggiornamento completo. Per abilitare un aggiornamento parziale, seleziona l’opzione e definisci le condizioni di aggiornamento.

![](assets/update-aggregate-partial.png)

Si consiglia di aggiungere un&#39;attività **[!UICONTROL Scheduler]** per impostare la frequenza degli aggiornamenti del calcolo.
