---
product: campaign
title: Query incrementale
description: Ulteriori informazioni sull’attività del flusso di lavoro Incremental query
feature: Workflows, Targeting Activity
exl-id: 3e9f92c3-080f-441b-a15a-2ec9d056d1f9
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 3%

---

# Query incrementale{#incremental-query}



Una query incrementale consente di selezionare periodicamente un target in base a un criterio, escludendo al contempo le persone già oggetto di targeting per questo criterio.

La popolazione già oggetto di targeting viene memorizzata nella memoria per istanza di flusso di lavoro e per attività, ovvero due flussi di lavoro avviati dallo stesso modello non condividono lo stesso registro. D’altro canto, due attività basate sulla stessa query incrementale per la stessa istanza di flusso di lavoro utilizzeranno lo stesso registro.

La query viene definita nello stesso modo delle query standard, ma l’esecuzione è pianificata.

**Argomenti correlati:**

* [Caso di utilizzo: Aggiornamento dell’elenco trimestrale tramite una query incrementale](quarterly-list-update.md)
* [Creazione di una query](query.md#creating-a-query)

>[!CAUTION]
>
>Se il risultato di una query incrementale è uguale a **0** durante una delle esecuzioni, il flusso di lavoro viene messo in pausa fino alla successiva esecuzione programmata della query. Le transizioni e le attività che seguono la query incrementale non vengono quindi elaborate prima dell’esecuzione seguente.

Per eseguire questa operazione:

1. In **[!UICONTROL Scheduling & History]** seleziona la scheda **[!UICONTROL Schedule execution]** opzione . L’attività rimane attiva una volta creata e verrà attivata solo nei momenti specificati dalla pianificazione per l’esecuzione della query. Tuttavia, se l’opzione è disabilitata, la query viene eseguita immediatamente **e in una sola volta**.
1. Fai clic sul pulsante **[!UICONTROL Change]**.

   In **[!UICONTROL Schedule editing wizard]** è possibile configurare il tipo di frequenza, ricorrenza degli eventi e periodo di validità degli eventi.

   ![](assets/s_user_segmentation_wizard_11.png)

1. Fai clic su **[!UICONTROL Finish]** per salvare la pianificazione.

   ![](assets/s_user_segmentation_wizard_valid.png)

1. La sezione inferiore del **[!UICONTROL Scheduling & History]** consente di selezionare il numero di giorni da considerare nella cronologia.

   ![](assets/edit_request_inc.png)

   * **[!UICONTROL History in days]**

      I destinatari già target possono essere registrati per un numero massimo di giorni dal giorno in cui sono stati oggetto del targeting. Se questo valore è zero, i destinatari non vengono mai eliminati dal registro.

   * **[!UICONTROL Keep history when starting]**

      Questa opzione consente di non eliminare il registro quando l’attività è abilitata.

   * **[!UICONTROL SQL table name]**

      Questo parametro consente di sovraccaricare la tabella SQL predefinita contenente i dati della cronologia.

## Parametri di output {#output-parameters}

* tableName
* schema
* recCount

Questo insieme di tre valori identifica la popolazione oggetto della query. **[!UICONTROL tableName]** è il nome della tabella che registra gli identificatori target, **[!UICONTROL schema]** è lo schema della popolazione (in genere nms:recipient) e **[!UICONTROL recCount]** è il numero di elementi nella tabella.
