---
product: campaign
title: Modificare una dimensione in un flusso di lavoro
description: Scopri come utilizzare l’attività Modifica dimensione
feature: Workflows, Targeting Activity
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 1%

---

# Cambiare dimensione{#change-dimension}

Utilizza la **[!UICONTROL Change dimension]** attività per modificare la dimensione di targeting durante la creazione di un pubblico. Questa attività sposta l’asse in base al modello di dati e alla dimensione di input. Ad esempio, puoi passare dalla dimensione &quot;contratti&quot; alla dimensione &quot;clienti&quot;.

Puoi inoltre utilizzare questa attività per definire le colonne aggiuntive della nuova destinazione e i criteri di deduplicazione dei dati.

Per configurare le **[!UICONTROL Change dimension]** , applica i seguenti passaggi:

1. Seleziona la nuova dimensione di targeting tramite il **[!UICONTROL Change dimension]** campo .

   ![](assets/s_user_change_dimension_param1.png)

1. Durante la modifica della dimensione, puoi mantenere tutti gli elementi o selezionare quelli da mantenere nell’output. Nell’esempio seguente, il valore massimo è il numero di duplicati è impostato su 2.

   ![](assets/s_user_change_dimension_limit.png)

   Quando si sceglie di conservare un solo record, nello schema di lavoro viene visualizzata una raccolta: Questa raccolta rappresenta tutti i record che non verranno inclusi nel risultato finale (poiché viene conservato un solo record). Come tutte le altre raccolte, questa ti permette di calcolare gli aggregati o recuperare le informazioni in colonne.

   Ad esempio, se modifichi la **[!UICONTROL Customers]** alla dimensione **[!UICONTROL Recipients]** È possibile eseguire il targeting dei clienti di un archivio specifico, aggiungendo al contempo il numero di acquisti effettuati.

1. Se scegli di non conservare tutte queste informazioni, puoi configurare la modalità di gestione duplicata.

   ![](assets/s_user_change_dimension_param2.png)

   Le frecce blu consentono di definire la priorità di elaborazione duplicata.

   Nell’esempio precedente, i destinatari verranno deduplicati prima sul loro indirizzo e-mail, quindi sul loro numero di account, se necessario.

1. La **[!UICONTROL Result]** consente di aggiungere ulteriori informazioni.

   Ad esempio, puoi recuperare la contea in base al codice postale utilizzando un **Substring** funzione di tipo . Per eseguire questa operazione:

   * Fai clic sul pulsante **[!UICONTROL Add data...]** collegamento e seleziona **[!UICONTROL Data linked to the filtering dimension]**.

      ![](assets/wf_change-dimension_sample_01.png)

      >[!NOTE]
      >
      >Per informazioni sulla creazione e la gestione di colonne aggiuntive, consulta [Aggiungi dati](query.md#add-data).

   * Seleziona la dimensione di targeting precedente (prima dell’interruttore dell’asse) e seleziona la **[!UICONTROL Zip Code]** del destinatario **[!UICONTROL Location]** sottoalbero, quindi fare clic su **[!UICONTROL Edit expression]**.

      ![](assets/wf_change-dimension_sample_02.png)

   * Fai clic su **[!UICONTROL Advanced selection]** e scegli **[!UICONTROL Edit the formula using an expression]**.

      ![](assets/wf_change-dimension_sample_03.png)

   * Utilizzare le funzioni offerte nell&#39;elenco e specificare il calcolo da eseguire.

      ![](assets/wf_change-dimension_sample_04.png)

   * Infine, immetti l’etichetta della colonna appena creata.

      ![](assets/wf_change-dimension_sample_05.png)

1. Esegui il flusso di lavoro per visualizzare il risultato di questa configurazione. Confronta i dati nelle tabelle prima e dopo l’attività di modifica della dimensione e confronta la struttura delle tabelle del flusso di lavoro, come illustrato negli esempi seguenti:

   ![](assets/wf_change-dimension_sample_06.png)

   ![](assets/wf_change-dimension_sample_07.png)
