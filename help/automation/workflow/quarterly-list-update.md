---
product: campaign
title: Aggiornamento dell’elenco trimestrale tramite una query incrementale
description: In questo caso d’uso, viene utilizzata una query incrementale per aggiornare automaticamente un elenco di destinatari.
feature: Workflows
role: User
exl-id: eedc796a-865f-47a8-8807-5980546b8adf
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 5%

---

# Aggiornamento dell’elenco trimestrale tramite una query incrementale {#quarterly-list-update}



Nell’esempio seguente, un’ [query incrementale](incremental-query.md) viene utilizzato per aggiornare automaticamente un elenco di destinatari. Questi destinatari sono destinatari delle campagne di marketing stagionali.

Poiché tali campagne sono lanciate all’inizio di ogni stagione per offrire attività sportive pertinenti, tali elenchi sono aggiornati ogni trimestre. Tuttavia, un destinatario in questo caso deve essere oggetto di targeting solo una volta ogni 9 mesi per questa campagna. Questo ti consente di intervallare la frequenza di idoneità del destinatario e di offrire attività per diverse stagioni nel corso degli anni.

![](assets/incremental_query_example.png)

1. Aggiungi una query incrementale e un’attività di aggiornamento elenco in un nuovo flusso di lavoro.
1. Configurare **[!UICONTROL Incremental query]** scheda dell’attività come specificato in [Creare una query](query.md#creating-a-query).
1. Seleziona la **[!UICONTROL Scheduling & History]** e quindi specificare una cronologia di 270 giorni. Un destinatario che è già stato oggetto di targeting non sarà più oggetto di targeting per un periodo di 270 giorni, o circa 9 mesi.

   Quindi fai clic su **[!UICONTROL Change...]** pulsante.

1. Per aggiornare l’elenco prima dell’inizio di ogni stagione, seleziona **[!UICONTROL Monthly]**.
1. Nella schermata successiva, selezionare Marzo, Giugno, Settembre e Dicembre. Scegli il 20 del mese e scegli l’ora in cui desideri avviare il flusso di lavoro.
1. Quindi, seleziona il periodo di validità per la query. Ad esempio, se desideri che questa attività sia attiva in modo permanente, seleziona **[!UICONTROL Permanent validity]**.

1. Dopo aver approvato la query incrementale, configura l’attività di aggiornamento dell’elenco come spiegato in [Aggiornamento elenco](list-update.md).

Il flusso di lavoro verrà quindi avviato automaticamente poco prima dell&#39;inizio di ogni stagione. L’elenco verrà aggiornato con i nuovi destinatari idonei a ricevere le offerte.
