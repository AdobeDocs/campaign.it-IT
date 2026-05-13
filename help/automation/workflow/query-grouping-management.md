---
product: campaign
title: Eseguire query tramite gestione dei raggruppamenti
description: Scopri come eseguire query utilizzando la gestione dei raggruppamenti
feature: Query Editor
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 6fc4ef67-5d75-4c8c-8bcc-41e3ed155ca2
TQID: https://experienceleague.adobe.com/-OBJg0XeJowHsyunWoCdl6K434cs-p08xMFRKJmz--4
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 244
ht-degree: 4%

---

# Eseguire query tramite gestione dei raggruppamenti {#querying-using-grouping-management}



In questo esempio, desideri eseguire una query per trovare tutti i domini e-mail target oltre 30 volte durante le consegne precedenti.

* Quale tabella deve essere selezionata?

  Tabella dei destinatari (nms:recipient)

* Campi da selezionare nelle colonne di output?

  Dominio e-mail e chiave primaria (con conteggio)

* Raggruppamento dati?

  In base al dominio e-mail con un numero di chiavi primarie superiore a 30. Questa operazione viene eseguita con l&#39;opzione **[!UICONTROL Group by + Having]**. **[!UICONTROL Group by + Having]** consente di raggruppare i dati (&quot;raggruppare per&quot;) e di selezionare ciò che è stato raggruppato (&quot;avere&quot;).

Per creare questo esempio, attieniti alla seguente procedura:

1. Apri **[!UICONTROL Generic query editor]** e scegli la tabella Destinatario (**nms:recipient**).

   ![](assets/query_editor_02.png)

1. Nella finestra **[!UICONTROL Data to extract]**, selezionare i campi **[!UICONTROL Email domain]** e **[!UICONTROL Primary key]**. Eseguire un conteggio nel campo **[!UICONTROL Primary key]**.

1. Selezionare la casella **[!UICONTROL Handle groupings (GROUP BY + HAVING)]**.

   ![](assets/query_editor_nveau_29.png)

1. Nella finestra **[!UICONTROL Sorting]**, ordina i domini e-mail in ordine decrescente. Per eseguire questa operazione, selezionare **[!UICONTROL Yes]** nella colonna **[!UICONTROL Descending sort]**. Fai clic su **[!UICONTROL Next]**.

   ![](assets/query_editor_nveau_70.png)

1. In **[!UICONTROL Data filtering]**, seleziona **[!UICONTROL Filtering conditions]**. Passare alla finestra **[!UICONTROL Target elements]** e fare clic su **[!UICONTROL Next]**.
1. Nella finestra **[!UICONTROL Data grouping]**, selezionare **[!UICONTROL Email domain]** facendo clic su **[!UICONTROL Add]**.

   Questa finestra di raggruppamento dati viene visualizzata solo se è stata selezionata la casella **[!UICONTROL Handle groupings (GROUP BY + HAVING]**).

   ![](assets/query_editor_blocklist_04.png)

1. Nella finestra **[!UICONTROL Grouping condition]**, indica un conteggio di chiavi primarie maggiore di 30 poiché si desidera che vengano restituiti come risultati solo i domini e-mail con destinazione superiore a 30 volte.

   Questa finestra viene visualizzata quando è stata selezionata la casella **[!UICONTROL Manage groupings (GROUP BY + HAVING)]**: è qui che il risultato del raggruppamento viene filtrato (HAVING).

   ![](assets/query_editor_blocklist_05.png)

1. Nella finestra **[!UICONTROL Data formatting]**, fare clic su **[!UICONTROL Next]**: non è necessaria alcuna formattazione.
1. Nella finestra di anteprima dei dati, fai clic su **[!UICONTROL Launch data preview]**: qui vengono restituiti tre diversi domini e-mail con destinazione superiore a 30 volte.

   ![](assets/query_editor_blocklist_06.png)
