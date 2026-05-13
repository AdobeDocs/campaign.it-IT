---
product: campaign
title: Eseguire il calcolo aggregato
description: Scopri come eseguire il calcolo aggregato nelle query
feature: Workflows
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 00e564b5-3c8e-45d4-b240-c872a8b8ccb6
TQID: https://experienceleague.adobe.com/ubtfw1irqKiD8mrRqD2L3UI-kGwhdBiSmBTjIfp-4NE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 231
ht-degree: 0%

---

# Eseguire il calcolo aggregato {#performing-aggregate-computing}

In questo esempio, vogliamo contare il numero di destinatari che vivono a Londra, in base al genere.

* Quale tabella deve essere selezionata?

  Tabella dei destinatari (**nms:recipient**)

* Quali campi devono essere selezionati nella colonna di output?

  Chiave primaria (con conteggio) e genere

* Su quali condizioni vengono filtrate le informazioni?

  In base ai destinatari che vivono a Londra

Per creare questo esempio, attieniti alla seguente procedura:

1. In **[!UICONTROL Data to extract]**, definire un conteggio per la chiave primaria (come illustrato nell&#39;esempio precedente). Aggiungi il campo **[!UICONTROL Gender]** nella colonna di output. Selezionare l&#39;opzione **[!UICONTROL Group]** nella colonna **[!UICONTROL Gender]**. In questo modo i destinatari saranno raggruppati per genere.

   ![](assets/query_editor_nveau_27.png)

1. Nella finestra **[!UICONTROL Sorting]**, fare clic su **[!UICONTROL Next]**: non è necessario alcun ordinamento.
1. Configura il filtro dei dati. In questo caso, si desidera limitare la selezione ai contatti che risiedono a Londra.

   ![](assets/query_editor_22.png)

   >[!NOTE]
   >
   >I valori fanno distinzione tra maiuscole e minuscole. Se il valore &quot;Londra&quot; viene immesso nella condizione senza una lettera maiuscola e l’elenco dei destinatari contiene la parola &quot;Londra&quot; con una lettera maiuscola, la query avrà esito negativo.

1. Nella finestra **[!UICONTROL Data formatting]**, fare clic su **[!UICONTROL Next]**: nessuna formattazione richiesta per questo esempio.
1. Nella finestra di anteprima, fare clic su **[!UICONTROL Launch data preview]**.

   Esistono tre valori distinti per ogni ordinamento in base al sesso: **2** per la donna, **1** per il maschio e **0** quando il genere è sconosciuto. In questo esempio, l&#39;elenco contiene 10 donne, 16 uomini e 2 persone il cui genere non è noto.

   ![](assets/query_editor_agregat_04.png)
