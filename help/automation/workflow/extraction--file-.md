---
product: campaign
title: Estrazione dati (file)
description: Ulteriori informazioni sull’attività del flusso di lavoro Estrazione dati (file)
feature: Workflows, Data Management Activity
exl-id: 8510e879-2862-491f-bc52-ca8f56105932
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 1%

---

# Estrazione dati (file){#extraction-file}



È possibile estrarre dati da una tabella del flusso di lavoro in un file esterno utilizzando **[!UICONTROL Data extraction (file)]** attività.

>[!CAUTION]
>
>Questa attività deve sempre avere una transizione in entrata che contiene i dati da estrarre.

Per configurare l’estrazione dei dati, effettua le seguenti operazioni:

1. Specifica il nome del file di output: questo nome può contenere variabili, inserite tramite il pulsante di personalizzazione a destra del campo.
1. Clic **[!UICONTROL Edit the file format...]** per selezionare i dati da estrarre.

   ![](assets/s_advuser_extract_file_param.png)

   Il **[!UICONTROL Handle groupings (GROUP BY + HAVING)]** L’opzione aggiunge un passaggio aggiuntivo per filtrare il risultato finale dell’aggregato, ad esempio per un determinato tipo di ordine di acquisto, per clienti che hanno ordinato più di 10 volte e così via.

1. Se necessario, è possibile aggiungere nuove colonne al file di output, ad esempio il calcolo o l&#39;elaborazione dei risultati. A questo scopo, fai clic su **[!UICONTROL Add]** icona.

   ![](assets/s_advuser_extract_file_add_col.png)

   Nella riga aggiuntiva, fai clic su **[!UICONTROL Edit expression]** per definire il contenuto della nuova colonna.

   ![](assets/s_advuser_extract_file_add_exp.png)

   Sarà quindi possibile accedere alla finestra di selezione. Clic **[!UICONTROL Advanced selection]** per scegliere il processo da applicare ai dati.

   ![](assets/s_advuser_extract_file_advanced_selection.png)

   Scegliere la formula desiderata dall&#39;elenco.

   ![](assets/s_advuser_extract_file_agregate_values.png)

Puoi definire un post-processo da eseguire durante l’estrazione dei dati, per comprimere o crittografare i file. A questo scopo, il comando desiderato deve essere aggiunto nel **[!UICONTROL Script]** dell’attività.

Per ulteriori informazioni, consulta questa sezione: [Compressione o crittografia di un file](use-workflow-data.md#zipping-or-encrypting-a-file).

![](assets/postprocessing_dataextraction.png)

## Elenco delle funzioni di aggregazione {#list-of-aggregate-functions}

Di seguito è riportato un elenco delle funzioni di aggregazione disponibili:

* **[!UICONTROL Count]** per contare tutti i valori non nulli del campo da aggregare, compresi i valori duplicati (del campo aggregato),

  **[!UICONTROL Distinct]** per contare il numero totale di valori diversi e non nulli del campo da aggregare (i valori duplicati sono esclusi prima del calcolo),

* **[!UICONTROL Sum]** calcolare la somma dei valori di un campo numerico,
* **[!UICONTROL Minimum value]** calcolare i valori minimi di un campo (numerici o di altro tipo),
* **[!UICONTROL Maximum value]** calcolare i valori massimi di un campo (numerici o di altro tipo),
* **[!UICONTROL Average]** per calcolare la media dei valori di un campo numerico.
