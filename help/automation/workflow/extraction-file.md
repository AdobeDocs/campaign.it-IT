---
product: campaign
title: Estrazione dati (file)
description: Ulteriori informazioni sull’attività del flusso di lavoro Estrazione dati (file)
feature: Workflows, Data Management Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8510e879-2862-491f-bc52-ca8f56105932
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 1%

---

# Estrazione dati (file){#extraction-file}

È possibile estrarre dati da una tabella del flusso di lavoro in un file esterno utilizzando l&#39;attività **[!UICONTROL Data extraction (file)]**.

>[!CAUTION]
>
>Questa attività deve sempre avere una transizione in entrata che contiene i dati da estrarre.

Per configurare l’estrazione dei dati, effettua le seguenti operazioni:

1. Specifica il nome del file di output: questo nome può contenere variabili, inserite tramite il pulsante di personalizzazione a destra del campo.
1. Fare clic su **[!UICONTROL Edit the file format...]** per selezionare i dati da estrarre.

   ![](assets/s_advuser_extract_file_param.png)

   L&#39;opzione **[!UICONTROL Handle groupings (GROUP BY + HAVING)]** aggiunge un ulteriore passaggio per filtrare il risultato finale dell&#39;aggregato, ad esempio per un determinato tipo di ordine di acquisto, clienti che hanno ordinato più di 10 volte e così via.

1. Se necessario, è possibile aggiungere nuove colonne al file di output, ad esempio il calcolo o l&#39;elaborazione dei risultati. A tale scopo, fare clic sull&#39;icona **[!UICONTROL Add]**.

   ![](assets/s_advuser_extract_file_add_col.png)

   Nella riga aggiuntiva fare clic sull&#39;icona **[!UICONTROL Edit expression]** per definire il contenuto della nuova colonna.

   ![](assets/s_advuser_extract_file_add_exp.png)

   Sarà quindi possibile accedere alla finestra di selezione. Fare clic su **[!UICONTROL Advanced selection]** per scegliere il processo da applicare ai dati.

   ![](assets/s_advuser_extract_file_advanced_selection.png)

   Scegliere la formula desiderata dall&#39;elenco.

   ![](assets/s_advuser_extract_file_agregate_values.png)

Puoi definire un post-processo da eseguire durante l’estrazione dei dati, per comprimere o crittografare i file. A questo scopo, è necessario aggiungere il comando desiderato nella scheda **[!UICONTROL Script]** dell&#39;attività.

![](assets/postprocessing_dataextraction.png)

## Elenco delle funzioni di aggregazione {#list-of-aggregate-functions}

Di seguito è riportato un elenco delle funzioni di aggregazione disponibili:

* **[!UICONTROL Count]** per contare tutti i valori non nulli del campo da aggregare, inclusi i valori duplicati (del campo aggregato),

  **[!UICONTROL Distinct]** per contare il numero totale di valori diversi e non nulli del campo da aggregare (i valori duplicati vengono esclusi prima del calcolo),

* **[!UICONTROL Sum]** per calcolare la somma dei valori di un campo numerico,
* **[!UICONTROL Minimum value]** per calcolare i valori minimi di un campo (numerico o meno),
* **[!UICONTROL Maximum value]** per calcolare i valori massimi di un campo (numerico o meno),
* **[!UICONTROL Average]** per calcolare la media dei valori di un campo numerico.
