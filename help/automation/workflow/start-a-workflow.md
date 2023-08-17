---
product: campaign
title: Avviare un flusso di lavoro
description: Scopri come avviare un flusso di lavoro e scoprire i flussi di lavoro, la barra degli strumenti delle azioni e il menu di scelta rapida
feature: Workflows
exl-id: 6d9789e3-d721-4ffd-b3fb-a0c522ab1c0a
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 0%

---

# Avviare un flusso di lavoro {#starting-a-workflow}

Un workflow viene sempre avviato manualmente. Quando viene avviato, può tuttavia rimanere inattivo a seconda delle informazioni specificate tramite una pianificazione (vedi [Scheduler](scheduler.md)) o pianificazione delle attività.

Azioni relative all’esecuzione del flusso di lavoro di targeting (avvio, arresto, pausa, ecc.) sono **asincrono** processi: l’ordine viene registrato e diventa effettivo non appena il server è disponibile per applicarlo.

La barra degli strumenti consente di avviare e tenere traccia dell’esecuzione del flusso di lavoro.

L’elenco delle opzioni disponibili nella sezione **[!UICONTROL Actions]** e il menu di scelta rapida sono descritti di seguito.

>[!IMPORTANT]
>
>Tieni presente che, quando un operatore esegue un’azione su un flusso di lavoro (avvio, arresto, pausa, ecc.), l’azione non viene eseguita immediatamente, ma viene inserita in una coda per essere elaborata dal modulo del flusso di lavoro.

## Barra delle azioni {#actions-toolbar}

Il **[!UICONTROL Actions]** sulla barra degli strumenti consente di accedere a opzioni di esecuzione aggiuntive sui flussi di lavoro selezionati. È inoltre possibile utilizzare **[!UICONTROL File > Actions]** oppure fare clic con il pulsante destro del mouse su un flusso di lavoro e selezionare **[!UICONTROL Actions]**.

![](assets/purge_historique.png)

* **[!UICONTROL Start]**

  Questa azione ti consente di avviare l’esecuzione di un flusso di lavoro: un flusso di lavoro che **Completato**, **In fase di modifica** o **In pausa** modifica lo stato in **Avviato**. Il motore del flusso di lavoro gestisce quindi l’esecuzione di questo flusso di lavoro. Se il flusso di lavoro è stato sospeso, viene ripreso; in caso contrario, il flusso di lavoro viene avviato dall’inizio e le attività iniziali vengono attivate.

  L’avvio è asincrono: la richiesta viene salvata ed elaborata il prima possibile da un server del flusso di lavoro.

* **[!UICONTROL Pause]**

  Questa azione imposta lo stato del flusso di lavoro su **In pausa**. Nessuna attività viene attivata finché il flusso di lavoro non viene ripreso; tuttavia, le operazioni in corso non vengono sospese.

* **[!UICONTROL Stop]**

  Questa azione interrompe un flusso di lavoro attualmente in esecuzione. Lo stato dell’istanza è impostato su **Completato**. Se possibile, le operazioni in corso vengono interrotte. Le importazioni e le query SQL vengono annullate immediatamente.

  >[!IMPORTANT]
  >
  >L’arresto di un flusso di lavoro è un processo asincrono: la richiesta viene registrata, quindi il server o i server del flusso di lavoro annullano le operazioni in corso. L&#39;arresto di un&#39;istanza del flusso di lavoro può quindi richiedere tempo, soprattutto se il flusso di lavoro è in esecuzione su più server, ognuno dei quali deve assumere il controllo per annullare le attività in corso. Per evitare problemi, attendi il completamento dell’operazione di arresto e non eseguire più richieste di arresto sullo stesso flusso di lavoro.

* **[!UICONTROL Restart]**

  Questa azione si interrompe e riavvia il flusso di lavoro. Nella maggior parte dei casi, consente un riavvio più rapido. È inoltre utile automatizzare il riavvio quando l’arresto richiede un certo periodo di tempo, perché il comando &quot;Interrompi&quot; non è disponibile quando il flusso di lavoro viene arrestato.

* **[!UICONTROL Purge history]**

  Questa azione ti consente di eliminare la cronologia del flusso di lavoro. Per ulteriori informazioni, consulta [Rimozione dei registri](monitor-workflow-execution.md#purging-the-logs).

* **[!UICONTROL Start in simulation mode]**

  Questa opzione consente di avviare il flusso di lavoro in modalità simulazione anziché in modalità reale. Ciò significa che quando si attiva questa modalità, vengono eseguite solo le attività che non influiscono sul database o sul file system (ad esempio **[!UICONTROL Query]**, **[!UICONTROL Union]**, **[!UICONTROL Intersection]**, ecc.). Attività che hanno un impatto (ad es. **[!UICONTROL Export]**, **[!UICONTROL Import]**, ecc.) così come quelli successivi (nello stesso ramo) non vengono eseguiti.

* **[!UICONTROL Execute pending tasks now]**

  Questa azione ti consente di avviare tutte le attività in sospeso il prima possibile. Per avviare un’attività specifica, fai clic con il pulsante destro del mouse sulla relativa attività e seleziona **[!UICONTROL Execute pending task(s) now]**.

* **[!UICONTROL Unconditional stop]**

  Questa opzione cambia lo stato del flusso di lavoro in **[!UICONTROL Finished]**. Questa azione deve essere utilizzata solo come ultima risorsa se il normale processo di arresto non riesce dopo alcuni minuti. Utilizzare l&#39;interruzione incondizionata solo se si è certi che non vi siano processi di flusso di lavoro effettivi in corso.

  >[!CAUTION]
  >
  >Questa opzione è riservata agli utenti esperti.

* **[!UICONTROL Save as template]**

  Questa azione consente di creare un nuovo modello di workflow basato sul workflow selezionato. È necessario specificare la cartella in cui verrà salvata (nel **[!UICONTROL Folder]** ).

## Menu di scelta rapida {#right-click-menu}

Quando sono selezionate una o più attività del flusso di lavoro, puoi fare clic con il pulsante destro del mouse per intervenire sulla selezione.

![](assets/contextual_menu.png)

Nel menu di scelta rapida sono disponibili le seguenti opzioni:

**[!UICONTROL Open]**: questa opzione ti consente di accedere alle proprietà dell’attività.

**[!UICONTROL Display logs:]** questa opzione consente di visualizzare il registro di esecuzione dell’attività per l’attività selezionata. Fai riferimento a [Visualizzazione dei registri](monitor-workflow-execution.md#displaying-logs).

**[!UICONTROL Execute pending task(s) now:]** questa azione ti consente di avviare le attività in sospeso il prima possibile.

**[!UICONTROL Workflow restart from a task:]** questa opzione consente di riavviare il flusso di lavoro utilizzando i risultati precedentemente archiviati per questa attività.

**[!UICONTROL Cut/Copy/Paste/Delete:]** queste opzioni consentono di tagliare, copiare, incollare ed eliminare le attività.

**[!UICONTROL Copy as bitmap:]** questa opzione ti consente di acquisire una schermata di tutte le attività.

**[!UICONTROL Normal execution / Enable but do not execute / Do not enable:]** queste opzioni sono disponibili anche nel **[!UICONTROL Advanced]** delle proprietà dell’attività. Sono descritte in dettaglio [Esecuzione](advanced-parameters.md#execution).

**[!UICONTROL Save / Cancel:]** consente di salvare o annullare le modifiche apportate a un flusso di lavoro.

>[!NOTE]
>
>Puoi selezionare un gruppo di attività e applicare uno di questi comandi.

