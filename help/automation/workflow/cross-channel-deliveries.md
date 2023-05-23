---
product: campaign
title: Consegne cross-channel
description: Ulteriori informazioni sulle consegne cross-channel
feature: Workflows, Channels Activity
exl-id: fedcffcd-cf9b-4c3d-bd25-cb87dda30192
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 4%

---

# Consegne cross-channel{#cross-channel-deliveries}

Le consegne cross-channel sono disponibili nel **[!UICONTROL Deliveries]** scheda di [flusso di lavoro campagna](campaign-workflows.md) attività.

Seleziona il modello su cui desideri basare la consegna e definirne il contenuto.

Puoi specificare un target per la consegna a monte del flusso di lavoro utilizzando le diverse attività di targeting.

Nell’esempio seguente, scopri come creare un flusso di lavoro per inviare un’e-mail o un SMS agli abbonati a notifiche push e quindi una notifica push una settimana dopo. Per eseguire questa operazione:

1. Creare una campagna.
1. In **[!UICONTROL Targeting and workflows]** della campagna, aggiungi un **[!UICONTROL Query]** attività.
1. Configurare la query: seleziona come dimensione di destinazione i destinatari abbonati alle notifiche push.

   >[!NOTE]
   >
   >Per le notifiche push, utilizza **applicazioni in abbonamento** dimensione di destinazione.

   ![](assets/cross_channel_delivery_1.png)

1. Aggiungi le condizioni del filtro alla query. In questo caso, selezioneremo i destinatari che hanno un numero di cellulare o un indirizzo e-mail.

   ![](assets/cross_channel_delivery_2.png)

1. Aggiungi un **[!UICONTROL Split]** attività nel flusso di lavoro per dividere i destinatari che hanno un numero di cellulare e quelli che hanno un indirizzo e-mail.
1. In **[!UICONTROL Delivery]** , seleziona una consegna per ciascuna delle destinazioni.

   Crea la consegna nello stesso modo in cui crei una procedura guidata di consegna classica facendo doppio clic sull’attività di consegna nel flusso di lavoro.

   ![](assets/cross_channel_delivery_3.png)

1. Aggiungere e configurare un **[!UICONTROL Wait]** affinché i destinatari non ricevano troppe consegne contemporaneamente.
1. Aggiungi un **[!UICONTROL Split]** attività per suddividere gli abbonati di un’app mobile iOS o Android.

   Selezionare un servizio per ciascun sistema operativo.

   ![](assets/cross_channel_delivery_4.png)

1. Seleziona e configura la consegna di un’app mobile per ciascuno dei sistemi operativi.

   ![](assets/cross_channel_delivery_5.png)
