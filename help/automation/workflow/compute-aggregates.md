---
product: campaign
title: Eseguire il calcolo aggregato
description: Scopri come eseguire il calcolo aggregato nelle query
feature: Workflows
exl-id: 00e564b5-3c8e-45d4-b240-c872a8b8ccb6
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%

---

# Eseguire il calcolo aggregato {#performing-aggregate-computing}

In questo esempio, vogliamo contare il numero di destinatari che vivono a Londra, in base al sesso.

* Quale tabella deve essere selezionata?

   La tabella dei destinatari (**nms:recipient**)

* Quali campi devono essere selezionati nella colonna di output?

   Chiave primaria (con conteggio) e genere

* A quali condizioni vengono filtrate le informazioni?

   Basato sui destinatari che vivono a Londra

Per creare questo esempio, esegui i seguenti passaggi:

1. In **[!UICONTROL Data to extract]**, definisci un conteggio per la chiave primaria (come mostrato nell’esempio precedente). Aggiungi il **[!UICONTROL Gender]** nella colonna di output. Controlla la **[!UICONTROL Group]** in **[!UICONTROL Gender]** colonna. In questo modo i destinatari saranno raggruppati per genere.

   ![](assets/query_editor_nveau_27.png)

1. In **[!UICONTROL Sorting]** finestra, fai clic su **[!UICONTROL Next]**: qui non è necessaria alcuna selezione.
1. Configura il filtro dati. Qui, si desidera limitare la selezione ai contatti che vivono a Londra.

   ![](assets/query_editor_22.png)

   >[!NOTE]
   >
   >I valori sono sensibili all’uso di maiuscole e minuscole. Se il valore &quot;Londra&quot; è inserito nella condizione senza lettera maiuscola e l’elenco dei destinatari contiene la parola &quot;Londra&quot; con una lettera maiuscola, la query non riuscirà.

1. In **[!UICONTROL Data formatting]** finestra, fai clic su **[!UICONTROL Next]**: per questo esempio non è necessaria alcuna formattazione.
1. Nella finestra di anteprima, fai clic su **[!UICONTROL Launch data preview]**.

   Ci sono tre valori distinti per ogni tipo di genere: **2** per le donne, **1** per i maschi e **0** quando il genere è sconosciuto. In questo esempio, l&#39;elenco contiene 10 donne, 16 uomini e 2 persone il cui genere non è conosciuto.

   ![](assets/query_editor_agregat_04.png)
