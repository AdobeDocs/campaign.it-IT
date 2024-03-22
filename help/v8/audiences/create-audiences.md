---
title: Creare tipi di pubblico di profilo in Campaign
description: Scopri come creare elenchi e creare un pubblico
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 6fbe5616-7b8b-4504-988b-2bbbfd062548
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 3%

---

# Creare un pubblico in un elenco{#create-segments}

Utilizza gli elenchi di Campaign per creare e organizzare i tipi di pubblico.

Un elenco è un set statico di contatti che possono essere targetizzati nelle azioni di consegna o aggiornati durante un’importazione o un’altra azione del flusso di lavoro. Ad esempio, una popolazione estratta dal database tramite una query può essere memorizzata come elenco.

Gli elenchi vengono creati e gestiti tramite **[!UICONTROL Lists]** collegamento in **[!UICONTROL Profiles and targets]** scheda. Questi elenchi sono basati sulla tabella del profilo di Adobe Campaign predefinita (nms:recipient). [Ulteriori informazioni](../dev/datamodel.md#ootb-profiles.md)

![](assets/list-dashboard.png)

È possibile creare un elenco utilizzando **Aggiorna elenco** attività in un flusso di lavoro. Questa attività memorizza la popolazione risultante in un elenco. Utilizzalo per creare un nuovo elenco o aggiornarne uno esistente. Per creare elenchi contenenti tipi di dati diversi dalla tabella di profilo incorporata, è necessario eseguire un flusso di lavoro. Ad esempio, utilizzando una query nella tabella dei visitatori e aggiornando l’elenco, puoi creare un elenco di visitatori. [Ulteriori informazioni](#create-a-list-wf).

Guarda questo video per ulteriori informazioni sulla gestione degli elenchi in Adobe Campaign.

>[!VIDEO](https://video.tv.adobe.com/v/334909?quality=12)


## Creare un elenco di contatti {#create-a-list-of-contacts}

Per creare un elenco di contatti, effettuare le seguenti operazioni:

1. Fai clic su **[!UICONTROL Create]** e seleziona **[!UICONTROL New list]**.

   ![](assets/new-list.png)

1. Immettere le informazioni in **[!UICONTROL Edit]** della finestra di creazione dell’elenco.

   ![](assets/list-details.png)

   * Inserisci il nome dell’elenco in **[!UICONTROL Label]** e, se necessario, modificare il nome interno.
   * Aggiungere una descrizione per l&#39;elenco.
   * Puoi specificare una data di scadenza: una volta raggiunta tale data, l’elenco viene eliminato e rimosso automaticamente.


1. In **[!UICONTROL Content]** , fare clic su **[!UICONTROL Add]** per selezionare i profili appartenenti all’elenco.

   ![](assets/add-profiles-to-a-list.png)

   Puoi creare un nuovo profilo e aggiungerlo all’elenco direttamente da questa finestra utilizzando **[!UICONTROL Create]** icona. Il profilo verrà aggiunto al database.

1. Clic **[!UICONTROL Save]** per salvare l&#39;elenco. Viene quindi aggiunto alla panoramica degli elenchi.


## Convertire i contatti filtrati in un elenco {#convert-data-to-a-list}

Puoi selezionare i profili e aggiungerli a un elenco. A tale scopo, segui i passaggi indicati di seguito:

1. Da Campaign Explorer, seleziona i profili e fai clic con il pulsante destro del mouse.

   Questi profili possono essere filtrati per soddisfare criteri specifici.

1. Seleziona **[!UICONTROL Actions > Associate selection with a list...]**.

   ![](assets/add-selection-to-a-list.png)

1. Seleziona un elenco esistente o creane uno nuovo, quindi fai clic su **[!UICONTROL Next]**.

   ![](assets/select-the-list.png)

1. Fai clic sul pulsante **[!UICONTROL Start]**.

   ![](assets/record-a-list.png)

Seleziona la **[!UICONTROL Recreate the list]** opzione per eliminare il contenuto esistente dall’elenco e ottimizzare la creazione dell’elenco (non è necessaria alcuna query per verificare se i profili sono già collegati all’elenco).

Se deselezioni la **[!UICONTROL No trace of this job is saved in the database]** , è possibile selezionare (o creare) la cartella di esecuzione in cui verranno memorizzate le informazioni collegate al processo.

La sezione superiore della finestra consente di monitorare l’esecuzione. Il **[!UICONTROL Stop]** consente di interrompere il processo. I contatti già elaborati verranno collegati all&#39;elenco.

Al termine dell’esecuzione, accedi a **[!UICONTROL Profiles and Targets > Lists]** e selezionare l&#39;elenco: **[!UICONTROL Content]** mostra i profili collegati a questo elenco.


## Creare un elenco con un flusso di lavoro  {#create-a-list-wf}

È possibile utilizzare **[!UICONTROL List update]** attività per creare un elenco o aggiungere una popolazione a un elenco di destinatari.

Nell’esempio seguente, crea un elenco di tutti i destinatari tra 25 e 40.

1. Seleziona **[!UICONTROL Profiles and targets]**, e **[!UICONTROL Targeting workflows]**, quindi crea un nuovo flusso di lavoro da **[!UICONTROL Create]** pulsante.
1. Inserisci un’etichetta per questo flusso di lavoro, ad esempio &quot;Contatti 25-40&quot;, aggiungi una descrizione e fai clic su **[!UICONTROL Next]**.

   ![](assets/targeting-wf-sample.png)

1. Inserisci un **[!UICONTROL Query]** per definire la popolazione target e modificare la query.

   ![](assets/targeting-wf-edit-query.png)

1. Definisci le condizioni del filtro come segue:

   ![](assets/targeting-wf-age-filter.png)

   Scopri come creare una query in un flusso di lavoro in [questa sezione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}.

1. Aggiungi un’etichetta per questa query e salva le modifiche.
1. Aggiungi un **[!UICONTROL List update]** e modificarla.

   ![](assets/list-update-activity.png)

1. Immetti un’etichetta per l’attività.
1. Seleziona la **[!UICONTROL Create the list if necessary (Computed name)]** per mostrare che l’elenco verrà creato una volta eseguito il primo flusso di lavoro, quindi aggiornato con le esecuzioni seguenti.
1. Seleziona una cartella e immetti un’etichetta per l’elenco.
1. Seleziona la **[!UICONTROL Database of the targeting dimension]** per memorizzare la tabella.
1. Lascia **[!UICONTROL Purge the list if it exists (otherwise add to the list)]** opzione selezionata per eliminare i destinatari che non corrispondono ai criteri di targeting e per inserire i nuovi destinatari nell’elenco.
1. Lascia anche **[!UICONTROL Create or use a list with its own table]** opzione selezionata.
1. Lascia **[!UICONTROL Generate an outbound transition]** deselezionata.
1. Clic **[!UICONTROL Ok]** e salva il flusso di lavoro.
1. Avvia il flusso di lavoro.

   Viene quindi creato l’elenco dei destinatari corrispondenti. Puoi accedere a questo elenco da **[!UICONTROL Lists]** voce della home page.

   ![](assets/access-new-list.png)

   Puoi rendere ricorrente questo flusso di lavoro aggiungendo una pianificazione al flusso di lavoro. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/scheduler.html){target="_blank"}.

## Rimuovere un profilo da un elenco {#remove-a-profile-from-a-list}

Per rimuovere un profilo da un elenco, modificalo, seleziona il profilo in **[!UICONTROL Content]** , quindi fare clic sulla scheda **[!UICONTROL Delete]** icona.

## Eliminare un elenco di profili {#delete-a-list-of-profiles}

Per eliminare un elenco, selezionalo da Esplora campagne, selezionalo e fai clic con il pulsante destro del mouse. Scegli **[!UICONTROL Delete]**. Viene visualizzato un messaggio di avviso che richiede di confermare l&#39;eliminazione.

>[!NOTE]
>
>Quando elimini un elenco, i profili presenti nell’elenco non vengono interessati, ma i dati contenuti nel profilo vengono aggiornati.
