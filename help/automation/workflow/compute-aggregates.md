---
product: campaign
title: Eseguire il calcolo aggregato
description: Scopri come eseguire il calcolo aggregato nelle query
feature: Workflows
role: User, Developer
exl-id: 00e564b5-3c8e-45d4-b240-c872a8b8ccb6
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%

---

# Eseguire il calcolo aggregato {#performing-aggregate-computing}

In questo esempio, vogliamo contare il numero di destinatari che vivono a Londra, in base al genere.

* Quale tabella deve essere selezionata?

  Tabella dei destinatari (**nms:destinatario**)

* Quali campi devono essere selezionati nella colonna di output?

  Chiave primaria (con conteggio) e genere

* Su quali condizioni vengono filtrate le informazioni?

  In base ai destinatari che vivono a Londra

Per creare questo esempio, attieniti alla seguente procedura:

1. In entrata **[!UICONTROL Data to extract]**, definisci un conteggio per la chiave primaria (come mostrato nell’esempio precedente). Aggiungi il **[!UICONTROL Gender]** nella colonna di output. Controlla la **[!UICONTROL Group]** opzione in **[!UICONTROL Gender]** colonna. In questo modo i destinatari saranno raggruppati per genere.

   ![](assets/query_editor_nveau_27.png)

1. In **[!UICONTROL Sorting]** finestra, fai clic su **[!UICONTROL Next]**: non è necessario eseguire alcun ordinamento in questo punto.
1. Configura il filtro dei dati. In questo caso, si desidera limitare la selezione ai contatti che risiedono a Londra.

   ![](assets/query_editor_22.png)

   >[!NOTE]
   >
   >I valori fanno distinzione tra maiuscole e minuscole. Se il valore &quot;Londra&quot; viene immesso nella condizione senza una lettera maiuscola e l’elenco dei destinatari contiene la parola &quot;Londra&quot; con una lettera maiuscola, la query avrà esito negativo.

1. In **[!UICONTROL Data formatting]** finestra, fai clic su **[!UICONTROL Next]**: per questo esempio non è richiesta alcuna formattazione.
1. Nella finestra di anteprima, fai clic su **[!UICONTROL Launch data preview]**.

   Esistono tre valori distinti per ogni ordinamento in base al sesso: **2** per le femmine, **1** per i maschi e **0** quando il sesso è sconosciuto. In questo esempio, l&#39;elenco contiene 10 donne, 16 uomini e 2 persone il cui genere non è noto.

   ![](assets/query_editor_agregat_04.png)
