---
product: campaign
title: Modificare la dimensione in un flusso di lavoro
description: Scopri come utilizzare l’attività Modifica dimensione
feature: Workflows, Targeting Activity
exl-id: 71f36413-377a-4be6-921c-9e794fe882fd
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 1%

---

# Cambiare dimensione{#change-dimension}

Utilizza il **[!UICONTROL Change dimension]** attività per modificare la dimensione di targeting durante la creazione di un pubblico. Questa attività sposta l’asse a seconda del modello di dati e della dimensione di input. Ad esempio, puoi passare dalla dimensione &quot;contratti&quot; alla dimensione &quot;clienti&quot;.

Puoi inoltre utilizzare questa attività per definire le colonne aggiuntive della nuova destinazione e i criteri di deduplicazione dei dati.

Per configurare **[!UICONTROL Change dimension]** attività, esegui i seguenti passaggi:

1. Seleziona la nuova dimensione di targeting tramite **[!UICONTROL Change dimension]** campo.

   ![](assets/s_user_change_dimension_param1.png)

1. Durante la modifica della quota, potete mantenere tutti gli elementi o selezionarli da mantenere nell&#39;output. Nell&#39;esempio seguente, il valore massimo. numero di duplicati impostato su 2.

   ![](assets/s_user_change_dimension_limit.png)

   Quando si sceglie di mantenere un solo record, nello schema di lavoro viene visualizzata una raccolta: questa raccolta rappresenta tutti i record che non verranno inclusi nel risultato finale (poiché viene mantenuto un solo record). Come tutte le altre raccolte, questo consente di calcolare aggregati o recuperare informazioni nelle colonne.

   Ad esempio, se modifichi il **[!UICONTROL Customers]** dimensione al **[!UICONTROL Recipients]** sarà possibile rivolgersi ai clienti di un negozio specifico, aggiungendo il numero di acquisti effettuati.

1. Se scegli di non conservare tutte queste informazioni, puoi configurare la modalità di gestione dei duplicati.

   ![](assets/s_user_change_dimension_param2.png)

   Le frecce blu ti consentono di definire la priorità di elaborazione dei duplicati.

   Nell’esempio precedente, i destinatari verranno deduplicati prima sul loro indirizzo e-mail e, se necessario, poi sul loro numero di account.

1. Il **[!UICONTROL Result]** consente di aggiungere ulteriori informazioni.

   Ad esempio, puoi recuperare la provincia in base al codice postale utilizzando una **Sottostringa** funzione di testo. Per eseguire questa operazione:

   * Fai clic su **[!UICONTROL Add data...]** collega e seleziona **[!UICONTROL Data linked to the filtering dimension]**.

     ![](assets/wf_change-dimension_sample_01.png)

     >[!NOTE]
     >
     >Per informazioni sulla creazione e la gestione di colonne aggiuntive, fare riferimento a [Aggiungi dati](query.md#add-data).

   * Selezionare la dimensione di targeting precedente (prima del cambio asse) e selezionare **[!UICONTROL Zip Code]** nel campo del destinatario **[!UICONTROL Location]** sottostruttura, quindi fai clic su **[!UICONTROL Edit expression]**.

     ![](assets/wf_change-dimension_sample_02.png)

   * Clic **[!UICONTROL Advanced selection]** e scegli **[!UICONTROL Edit the formula using an expression]**.

     ![](assets/wf_change-dimension_sample_03.png)

   * Utilizzare le funzioni offerte nell&#39;elenco e specificare il calcolo da eseguire.

     ![](assets/wf_change-dimension_sample_04.png)

   * Infine, immetti l’etichetta della colonna appena creata.

     ![](assets/wf_change-dimension_sample_05.png)

1. Esegui il flusso di lavoro per visualizzare il risultato di questa configurazione. Confronta i dati nelle tabelle prima e dopo l’attività di modifica della dimensione e confronta la struttura delle tabelle del flusso di lavoro, come illustrato negli esempi seguenti:

   ![](assets/wf_change-dimension_sample_06.png)

   ![](assets/wf_change-dimension_sample_07.png)
