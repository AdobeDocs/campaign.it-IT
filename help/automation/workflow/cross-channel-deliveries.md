---
product: campaign
title: Consegne cross-channel
description: Ulteriori informazioni sulle consegne cross-channel
feature: Workflows, Channels Activity
role: User
exl-id: fedcffcd-cf9b-4c3d-bd25-cb87dda30192
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '249'
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

   ![](assets/cross_channel_delivery_1.png)

1. Aggiungi le condizioni del filtro alla query. In questo caso, selezioneremo i destinatari che hanno un numero di cellulare o un indirizzo e-mail.

   ![](assets/cross_channel_delivery_2.png)

1. Aggiungi un&#39;attività **[!UICONTROL Split]** al flusso di lavoro per dividere i destinatari con un numero di cellulare e quelli con un indirizzo e-mail.
1. Nella scheda **[!UICONTROL Delivery]**, seleziona una consegna per ciascuno degli oggetti.

   Crea la consegna nello stesso modo in cui crei una procedura guidata di consegna classica facendo doppio clic sull’attività di consegna nel flusso di lavoro.

   ![](assets/cross_channel_delivery_3.png)

1. Aggiungere e configurare un&#39;attività **[!UICONTROL Wait]** in modo che i destinatari non ricevano troppe consegne contemporaneamente.
1. Aggiungi un&#39;attività **[!UICONTROL Split]** per dividere gli abbonati di un&#39;app mobile iOS o Android.

   Selezionare un servizio per ciascun sistema operativo.

   ![](assets/cross_channel_delivery_4.png)

1. Seleziona e configura la consegna di un’app mobile per ciascuno dei sistemi operativi.

   ![](assets/cross_channel_delivery_5.png)
