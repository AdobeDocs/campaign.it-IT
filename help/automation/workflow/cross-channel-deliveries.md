---
product: campaign
title: Consegne cross-channel
description: Ulteriori informazioni sulle consegne cross-channel
feature: Workflows, Channels Activity
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 3%

---

# Consegne cross-channel{#cross-channel-deliveries}

Le consegne cross-channel sono disponibili nel **[!UICONTROL Deliveries]** scheda di [flusso di lavoro della campagna](campaign-workflows.md) attività.

Seleziona il modello su cui desideri basare la consegna e definirne il contenuto.

Puoi specificare un target per la consegna a monte del flusso di lavoro utilizzando le diverse attività di targeting.

Nell’esempio seguente, scopri come creare un flusso di lavoro per inviare un’e-mail o un SMS per gli abbonati alle notifiche push e quindi una notifica push una settimana dopo. Per eseguire questa operazione:

1. Creare una campagna.
1. In **[!UICONTROL Targeting and workflows]** scheda della campagna, aggiungi una **[!UICONTROL Query]** attività.
1. Configura la query: seleziona i destinatari abbonati alle notifiche push come dimensione di destinazione.

   >[!NOTE]
   >
   >Per le notifiche push, utilizza il **applicazioni abbonato** dimensione target.

   ![](assets/cross_channel_delivery_1.png)

1. Aggiungi le condizioni del filtro alla query. In questo caso, selezioneremo i destinatari che hanno un numero mobile o un indirizzo e-mail.

   ![](assets/cross_channel_delivery_2.png)

1. Aggiungi un **[!UICONTROL Split]** al flusso di lavoro per dividere i destinatari con un numero di cellulare e quelli con un indirizzo e-mail.
1. In **[!UICONTROL Delivery]** seleziona una consegna per ciascuna delle tue destinazioni.

   Crea la consegna come con una procedura guidata di consegna classica facendo doppio clic sull’attività di consegna nel flusso di lavoro. Per ulteriori informazioni, consulta questo articolo .

   ![](assets/cross_channel_delivery_3.png)

1. Aggiungi e configura un **[!UICONTROL Wait]** affinché i destinatari non ricevano troppe consegne alla volta.
1. Aggiungi un **[!UICONTROL Split]** attività per dividere gli abbonati di un’app mobile iOS o Android.

   Selezionare un servizio per ciascuno dei sistemi operativi. Per ulteriori informazioni sulla creazione di un servizio, consulta questo .

   ![](assets/cross_channel_delivery_4.png)

1. Seleziona e configura una consegna di app mobili per ciascuno dei sistemi operativi.

   ![](assets/cross_channel_delivery_5.png)
