---
product: campaign
title: Avviare un flusso di lavoro
description: Scopri come avviare un flusso di lavoro e scoprire la barra delle azioni dei flussi di lavoro e fai clic con il pulsante destro del mouse sul menu
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 1%

---

# Avviare un flusso di lavoro {#starting-a-workflow}

Un flusso di lavoro viene sempre avviato manualmente. Quando viene avviato, può tuttavia rimanere inattivo a seconda delle informazioni specificate tramite una pianificazione (vedi [Scheduler](scheduler.md)) o la pianificazione delle attività.

Azioni relative all’esecuzione del flusso di lavoro di targeting (avvio, arresto, pausa, ecc.) sono **asincrono** processi: l&#39;ordine viene registrato e avrà effetto non appena il server sarà disponibile ad applicarlo.

La barra degli strumenti ti consente di avviare e tenere traccia dell’esecuzione del flusso di lavoro.

L’elenco delle opzioni disponibili nel **[!UICONTROL Actions]** di seguito sono riportati i dettagli relativi al menu di scelta rapida e al menu di scelta rapida.

>[!IMPORTANT]
>
>Tieni presente che quando un operatore esegue un’azione su un flusso di lavoro (avvio, arresto, pausa, ecc.), l’azione non viene eseguita immediatamente, ma inserita in una coda per essere elaborata dal modulo del flusso di lavoro.

## Barra delle azioni {#actions-toolbar}

I pulsanti della barra degli strumenti sono descritti in questa sezione . La **[!UICONTROL Actions]** Questo pulsante ti consente di accedere a opzioni di esecuzione aggiuntive per l’azione sui flussi di lavoro selezionati. È inoltre possibile utilizzare **[!UICONTROL File > Actions]** oppure fai clic con il pulsante destro del mouse su un flusso di lavoro e seleziona **[!UICONTROL Actions]**.

![](assets/purge_historique.png)

* **[!UICONTROL Start]**

   Questa azione ti consente di avviare l’esecuzione di un flusso di lavoro: un flusso di lavoro **Completato**, **In corso di modifica** o **In pausa** cambia lo stato in **Avviato**. Il motore del flusso di lavoro gestisce quindi l’esecuzione di questo flusso di lavoro. Se il flusso di lavoro è stato messo in pausa, viene ripreso, altrimenti il flusso di lavoro viene avviato dall’inizio e le attività iniziali vengono attivate.

   L&#39;avvio è un processo asincrono: La richiesta viene salvata ed elaborata il prima possibile da un server del flusso di lavoro.

* **[!UICONTROL Pause]**

   Questa azione imposta lo stato del flusso di lavoro su **In pausa**. Nessuna attività viene attivata finché il flusso di lavoro non viene ripreso; tuttavia, le operazioni in corso non vengono messe in pausa.

* **[!UICONTROL Stop]**

   Questa azione interrompe l&#39;esecuzione di un flusso di lavoro. Lo stato dell’istanza è impostato su **Completato**. Le operazioni in corso vengono interrotte, se possibile. Le importazioni e le query SQL vengono annullate immediatamente.

   >[!IMPORTANT]
   >
   >L’arresto di un flusso di lavoro è un processo asincrono: La richiesta viene registrata, quindi il server del flusso di lavoro o i server annullano le operazioni in corso. L’arresto di un’istanza di flusso di lavoro può richiedere del tempo, specialmente se il flusso di lavoro è in esecuzione su più server, ciascuno dei quali deve assumere il controllo per annullare le attività in corso. Per evitare problemi, attendi il completamento dell’operazione di arresto e non esegui più richieste di arresto sullo stesso flusso di lavoro.

* **[!UICONTROL Restart]**

   Questa azione si interrompe e quindi riavvia il flusso di lavoro. Nella maggior parte dei casi, è possibile riavviare più velocemente. È inoltre utile automatizzare il riavvio quando l&#39;arresto richiede un certo tempo: questo perché il comando &#39;Stop&#39; non è disponibile quando il flusso di lavoro viene arrestato.

   I caratteri ** .

* **[!UICONTROL Purge history]**

   Questa azione ti consente di eliminare la cronologia del flusso di lavoro. Per ulteriori informazioni, consulta [Eliminazione dei registri](monitor-workflow-execution.md#purging-the-logs).

* **[!UICONTROL Start in simulation mode]**

   Questa opzione consente di avviare il flusso di lavoro in modalità di simulazione anziché in modalità reale. Ciò significa che quando si attiva questa modalità, vengono eseguite solo le attività che non hanno alcun impatto sul database o sul file system (ad esempio **[!UICONTROL Query]**, **[!UICONTROL Union]**, **[!UICONTROL Intersection]**, ecc.). Attività che hanno un impatto (ad es. **[!UICONTROL Export]**, **[!UICONTROL Import]**, ecc.) e quelli successivi (nello stesso ramo) non vengono eseguiti.

* **[!UICONTROL Execute pending tasks now]**

   Questa azione consente di avviare tutte le attività in sospeso il prima possibile. Per avviare un’attività specifica, fai clic con il pulsante destro del mouse sulla relativa attività e seleziona **[!UICONTROL Execute pending task(s) now]**.

* **[!UICONTROL Unconditional stop]**

   Questa opzione modifica lo stato del flusso di lavoro in **[!UICONTROL Finished]**. Questa azione deve essere utilizzata come ultima risorsa solo se il normale processo di arresto non riesce dopo diversi minuti. Utilizza l’arresto incondizionato solo se sei sicuro che non siano presenti processi di flusso di lavoro effettivi in corso.

   >[!CAUTION]
   >
   >Questa opzione è riservata agli utenti esperti.

* **[!UICONTROL Save as template]**

   Questa azione crea un nuovo modello di flusso di lavoro basato sul flusso di lavoro selezionato. È necessario specificare la cartella in cui verrà salvata (nel **[!UICONTROL Folder]** (campo).

   I caratteri ** .

## Menu di scelta rapida {#right-click-menu}

Quando selezioni una o più attività del flusso di lavoro, puoi fare clic con il pulsante destro del mouse per intervenire sulla selezione.

![](assets/contextual_menu.png)

Nel menu di scelta rapida sono disponibili le seguenti opzioni:

**[!UICONTROL Open]**: questa opzione ti consente di accedere alle proprietà dell’attività.

**[!UICONTROL Display logs:]** questa opzione ti consente di visualizzare il registro di esecuzione dell’attività per l’attività selezionata. Fai riferimento a [Visualizzazione dei registri](monitor-workflow-execution.md#displaying-logs).

**[!UICONTROL Execute pending task(s) now:]** questa azione consente di iniziare le attività in sospeso il prima possibile.

**[!UICONTROL Workflow restart from a task:]** questa opzione ti consente di riavviare il flusso di lavoro utilizzando i risultati memorizzati in precedenza per questa attività.

**[!UICONTROL Cut/Copy/Paste/Delete:]** queste opzioni consentono di tagliare, copiare, incollare ed eliminare le attività.

**[!UICONTROL Copy as bitmap:]** questa opzione ti consente di scattare una schermata di tutte le attività.

**[!UICONTROL Normal execution / Enable but do not execute / Do not enable:]** queste opzioni sono disponibili anche nella **[!UICONTROL Advanced]** scheda delle proprietà dell’attività. Essi sono descritti in [Esecuzione](advanced-parameters.md#execution).

**[!UICONTROL Save / Cancel:]** consente di salvare o annullare le modifiche apportate a un flusso di lavoro.

>[!NOTE]
>
>È possibile selezionare un gruppo di attività e applicarvi uno di questi comandi.

Il menu di scelta rapida è descritto anche in questo .
