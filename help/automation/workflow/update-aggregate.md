---
product: campaign
title: Aggregato di aggiornamento
description: Ulteriori informazioni sull’attività del flusso di lavoro aggregato Aggiornamento
feature: Workflows
role: Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
TQID: https://experienceleague.adobe.com/k0rl6aa1U0pK2z1dP7aGkDYk15ML3o8I0y-VwspH4mw
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 108
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
