---
product: campaign
title: Aggiornamento dell’elenco trimestrale tramite una query incrementale
description: In questo caso d’uso, viene utilizzata una query incrementale per aggiornare automaticamente un elenco di destinatari.
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: eedc796a-865f-47a8-8807-5980546b8adf
TQID: 'https://experienceleague.adobe.com/0C-z3NZX9SMcI4Zl2dxUKwf4l3welUfwGQijq3H5K6A'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%
---
# Aggiornamento dell’elenco trimestrale tramite una query incrementale {#quarterly-list-update}



Nell&#39;esempio seguente viene utilizzata una [query incrementale](incremental-query.md) per aggiornare automaticamente un elenco di destinatari. Questi destinatari sono destinatari delle campagne di marketing stagionali.

Poiché tali campagne sono lanciate all’inizio di ogni stagione per offrire attività sportive pertinenti, tali elenchi sono aggiornati ogni trimestre. Tuttavia, un destinatario in questo caso deve essere oggetto di targeting solo una volta ogni 9 mesi per questa campagna. Questo ti consente di intervallare la frequenza di idoneità del destinatario e di offrire attività per diverse stagioni nel corso degli anni.

![](assets/incremental_query_example.png)

1. Aggiungi una query incrementale e un’attività di aggiornamento elenco in un nuovo flusso di lavoro.
1. Configura la scheda **[!UICONTROL Incremental query]** dell&#39;attività come specificato in [Crea una query](query.md#creating-a-query).
1. Selezionare la scheda **[!UICONTROL Scheduling & History]** e quindi specificare una cronologia di 270 giorni. Un destinatario che è già stato oggetto di targeting non sarà più oggetto di targeting per un periodo di 270 giorni, o circa 9 mesi.

   Quindi fare clic sul pulsante **[!UICONTROL Change...]**.

1. Per assicurarsi che l&#39;elenco venga aggiornato prima dell&#39;inizio di ogni stagione, selezionare **[!UICONTROL Monthly]**.
1. Nella schermata successiva, selezionare Marzo, Giugno, Settembre e Dicembre. Scegli il 20 del mese e scegli l’ora in cui desideri avviare il flusso di lavoro.
1. Quindi, seleziona il periodo di validità per la query. Ad esempio, se desideri che questa attività sia attiva in modo permanente, seleziona **[!UICONTROL Permanent validity]**.

1. Dopo aver approvato la query incrementale, configura l&#39;attività di aggiornamento dell&#39;elenco come descritto in [Aggiornamento elenco](list-update.md).

Il flusso di lavoro verrà quindi avviato automaticamente poco prima dell&#39;inizio di ogni stagione. L’elenco verrà aggiornato con i nuovi destinatari idonei a ricevere le offerte.
