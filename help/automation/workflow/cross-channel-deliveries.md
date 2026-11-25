---
product: campaign
title: Consegne cross-channel
description: Ulteriori informazioni sulle consegne cross-channel
feature: Workflows, Channels Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: fedcffcd-cf9b-4c3d-bd25-cb87dda30192
TQID: 'https://experienceleague.adobe.com/hD15kwTxO1uHeIQjrozZmONmVWI5ZrMn40ORMwrGbf8'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: bce277d1-7efa-48d8-9a1b-b588bb45ba1c
    internal-label: Channels Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 2%
---
# Consegne cross-channel{#cross-channel-deliveries}

Le consegne cross-channel sono disponibili nella scheda **[!UICONTROL Deliveries]** delle attività del [flusso di lavoro della campagna](campaign-workflows.md).

Seleziona il modello su cui desideri basare la consegna e definirne il contenuto.

Puoi specificare un target per la consegna a monte del flusso di lavoro utilizzando le diverse attività di targeting.

Nell’esempio seguente, scopri come creare un flusso di lavoro per inviare un’e-mail o un SMS agli abbonati a notifiche push e quindi una notifica push una settimana dopo. Per eseguire questa operazione:

1. Creare una campagna.
1. Nella scheda **[!UICONTROL Targeting and workflows]** della campagna, aggiungi un&#39;attività **[!UICONTROL Query]**.
1. Configurare la query: seleziona come dimensione di destinazione i destinatari abbonati alle notifiche push.

   >[!NOTE]
   >
   >Per le notifiche push, utilizza la dimensione di destinazione **applicazioni in abbonamento**.

   ![Attività Query con lo schema delle applicazioni in abbonamento selezionato come documento su cui filtrare.](assets/cross_channel_delivery_1.png)

1. Aggiungi le condizioni del filtro alla query. In questo caso, selezioneremo i destinatari che hanno un numero di cellulare o un indirizzo e-mail.

   ![Il filtro di query con Mobile non è vuoto e una condizione Or per E-mail non è vuota.](assets/cross_channel_delivery_2.png)

1. Aggiungi un&#39;attività **[!UICONTROL Split]** al flusso di lavoro per dividere i destinatari con un numero di cellulare e quelli con un indirizzo e-mail.
1. Nella scheda **[!UICONTROL Delivery]**, seleziona una consegna per ciascuno degli oggetti.

   Crea la consegna nello stesso modo in cui crei una procedura guidata di consegna classica facendo doppio clic sull’attività di consegna nel flusso di lavoro.

   ![Flusso di lavoro della campagna con una query e una suddivisione che portano a una consegna tramite dispositivi mobili e una consegna tramite e-mail.](assets/cross_channel_delivery_3.png)

1. Aggiungere e configurare un&#39;attività **[!UICONTROL Wait]** in modo che i destinatari non ricevano troppe consegne contemporaneamente.
1. Aggiungi un&#39;attività **[!UICONTROL Split]** per dividere gli abbonati di un&#39;app mobile iOS o Android.

   Selezionare un servizio per ciascun sistema operativo.

   ![Finestra di dialogo per query con le applicazioni in abbonamento come dimensione di targeting e i sottoscrittori di un&#39;app mobile Android selezionata.](assets/cross_channel_delivery_4.png)

1. Seleziona e configura la consegna di un’app mobile per ciascuno dei sistemi operativi.

   ![Flusso di lavoro con consegne e-mail e SMS che si uniscono a un&#39;attività Attendi, quindi una suddivisione per inviare le consegne iOS e Android push.](assets/cross_channel_delivery_5.png)
