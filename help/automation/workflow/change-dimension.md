---
product: campaign
title: Modificare la dimensione in un flusso di lavoro
description: Scopri come utilizzare l’attività Modifica dimensione
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 71f36413-377a-4be6-921c-9e794fe882fd
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 1%

---

# Cambiare dimensione{#change-dimension}

Utilizza l&#39;attività **[!UICONTROL Change dimension]** per modificare la dimensione di targeting durante la creazione di un pubblico. Questa attività sposta l’asse a seconda del modello di dati e della dimensione di input. Ad esempio, puoi passare dalla dimensione &quot;contratti&quot; alla dimensione &quot;clienti&quot;.

Puoi inoltre utilizzare questa attività per definire le colonne aggiuntive della nuova destinazione e i criteri di deduplicazione dei dati.

>[!IMPORTANT]
>
>Le attività **[!UICONTROL Change Dimension]** e **[!UICONTROL Change Data source]** non devono essere aggiunte in una riga. Se è necessario utilizzare entrambe le attività in sequenza, assicurarsi di includere un&#39;attività **[!UICONTROL Enrichement]** tra di esse. In questo modo si garantisce la corretta esecuzione e si evitano potenziali conflitti o errori.

Per configurare l&#39;attività **[!UICONTROL Change dimension]**, attenersi alla seguente procedura:

1. Selezionare la nuova dimensione di targeting tramite il campo **[!UICONTROL Change dimension]**.

   ![](assets/s_user_change_dimension_param1.png)

1. Durante la modifica della quota, potete mantenere tutti gli elementi o selezionarli da mantenere nell&#39;output. Nell&#39;esempio seguente, il valore massimo. numero di duplicati impostato su 2.

   ![](assets/s_user_change_dimension_limit.png)

   Quando si sceglie di mantenere un solo record, nello schema di lavoro viene visualizzata una raccolta: questa raccolta rappresenta tutti i record che non verranno inclusi nel risultato finale (poiché viene mantenuto un solo record). Come tutte le altre raccolte, questo consente di calcolare aggregati o recuperare informazioni nelle colonne.

   Ad esempio, se modifichi la dimensione **[!UICONTROL Customers]** in **[!UICONTROL Recipients]**, sarà possibile eseguire il targeting dei clienti di uno specifico store, aggiungendo il numero di acquisti effettuati.

1. Se scegli di non conservare tutte queste informazioni, puoi configurare la modalità di gestione dei duplicati.

   ![](assets/s_user_change_dimension_param2.png)

   Le frecce blu ti consentono di definire la priorità di elaborazione dei duplicati.

   Nell’esempio precedente, i destinatari verranno deduplicati prima sul loro indirizzo e-mail e, se necessario, poi sul loro numero di account.

1. La scheda **[!UICONTROL Result]** consente di aggiungere ulteriori informazioni.

   Ad esempio, puoi ripristinare la provincia in base al codice postale utilizzando una funzione di tipo **Substring**. Per eseguire questa operazione:

   * Fare clic sul collegamento **[!UICONTROL Add data...]** e selezionare **[!UICONTROL Data linked to the filtering dimension]**.

     ![](assets/wf_change-dimension_sample_01.png)

     >[!NOTE]
     >
     >Per informazioni sulla creazione e la gestione di colonne aggiuntive, consultare [Aggiungi dati](query.md#add-data).

   * Selezionare la dimensione di targeting precedente (prima del cambio asse) e selezionare **[!UICONTROL Zip Code]** nella sottostruttura **[!UICONTROL Location]** del destinatario, quindi fare clic su **[!UICONTROL Edit expression]**.

     ![](assets/wf_change-dimension_sample_02.png)

   * Fare clic su **[!UICONTROL Advanced selection]** e scegliere **[!UICONTROL Edit the formula using an expression]**.

     ![](assets/wf_change-dimension_sample_03.png)

   * Utilizzare le funzioni offerte nell&#39;elenco e specificare il calcolo da eseguire.

     ![](assets/wf_change-dimension_sample_04.png)

   * Infine, immetti l’etichetta della colonna appena creata.

     ![](assets/wf_change-dimension_sample_05.png)

1. Esegui il flusso di lavoro per visualizzare il risultato di questa configurazione. Confronta i dati nelle tabelle prima e dopo l’attività di modifica della dimensione e confronta la struttura delle tabelle del flusso di lavoro, come illustrato negli esempi seguenti:

   ![](assets/wf_change-dimension_sample_06.png)

   ![](assets/wf_change-dimension_sample_07.png)
