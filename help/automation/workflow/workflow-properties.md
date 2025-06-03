---
product: campaign
title: Proprietà del flusso di lavoro
description: Ulteriori informazioni sulle proprietà del flusso di lavoro di Campaign
feature: Workflows
exl-id: 7fef434e-f6bd-46a4-9ec2-0182f081c928
source-git-commit: 24ecf598d3d01f7fb59c70e1c8c81e9c086e653e
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 33%

---

# Proprietà del flusso di lavoro{#workflow-properties}

## Scheda Esecuzione {#execution-tab}

La scheda **[!UICONTROL Execution]** della finestra **[!UICONTROL Properties]** in un flusso di lavoro è suddivisa in 3 sezioni:

![](assets/wf_execution_tab.png)

### Modulo di pianificazione {#scheduler}

Questa sezione viene visualizzata solo nei flussi di lavoro delle campagne.

* **[!UICONTROL Priority]**

  Il motore del flusso di lavoro elabora i flussi di lavoro da eseguire in base al criterio di priorità definito in questo campo. Ad esempio, tutti i flussi di lavoro con priorità **[!UICONTROL Average]** verranno eseguiti prima di quelli con priorità **[!UICONTROL Low]**.

* **[!UICONTROL Schedule execution for a time of low activity]**

  Questa opzione posticipa l’inizio del flusso di lavoro a un periodo meno occupato. Alcuni flussi di lavoro possono essere costosi in termini di risorse per il modulo di gestione di database. Consigliamo di pianificare l’esecuzione per un periodo di bassa attività (ad esempio di notte). I periodi di bassa attività sono definiti nel flusso di lavoro tecnico **[!UICONTROL Processes on campaigns]**.

### Execution {#execution}

* **[!UICONTROL Default affinity]**

  Se l’installazione include diversi server per il flusso di lavoro, utilizza questo campo per scegliere il computer su cui verrà eseguito il flusso di lavoro. Se il valore definito in questo campo non esiste su alcun server, il flusso di lavoro rimarrà in sospeso.

* **[!UICONTROL History in days]**

  Le tabelle di lavoro del database conservano una cronologia delle esecuzioni (attività, eventi, registro). Qui puoi definire il numero di giorni da archiviare per questo flusso di lavoro: il processo di pulizia eliminerà gli archivi più vecchi una volta al giorno. Se il valore in questo campo è zero, l’archivio non verrà mai eliminato.

* **[!UICONTROL Log SQL queries in the journal]**

  Questa funzionalità è riservata agli utenti avanzati. Riguarda i flussi di lavoro che contengono attività di targeting (query, unione, intersezione, ecc.). Quando questa opzione è selezionata, le query SQL inviate al database durante l’esecuzione del flusso di lavoro vengono visualizzate in Adobe Campaign: potrai quindi analizzarle per ottimizzare le query o diagnosticare eventuali problemi.

  Le query vengono visualizzate in una scheda **[!UICONTROL SQL logs]** che viene aggiunta al flusso di lavoro (ad eccezione dei flussi di lavoro della campagna) e all&#39;attività **[!UICONTROL Properties]** quando l&#39;opzione è abilitata. La scheda **[!UICONTROL Audit]** include anche le query SQL.

  ![](assets/wf_tab_log_sql.png)

* **[!UICONTROL Execute in the engine]**

  Questa opzione può essere utilizzata solo per il debug e mai in produzione. Quando è abilitato, il flusso di lavoro ha la priorità e tutti gli altri flussi di lavoro vengono interrotti fino al termine di questo.

* **[!UICONTROL Enable watchdog supervisor to keep workflow running permanently]**

  Questa opzione forza il riavvio automatico dei flussi di lavoro in seguito a un errore. Quando è attivato, il riavvio controlla ogni 30 secondi lo stato del flusso di lavoro e lo riavvia quando necessario. Per regolare l&#39;intervallo di 30 secondi, è possibile creare l&#39;opzione tecnica `XtkWorkflow_WatchdogRestartTimerTimeout` e utilizzare un tipo di dati integer per specificare il ritardo desiderato.

  >[!NOTE]
  >
  >* Questa opzione è disponibile a partire dalla versione v8.6.4.
  >
  >* Questa opzione è destinata agli utenti avanzati e deve essere abilitata solo per **flussi di lavoro tecnici**.
  >
  >* Questa opzione è abilitata per impostazione predefinita per i flussi di lavoro di replica centralizzata disponibili nel contesto di una distribuzione [Enterprise (FFDA)](../../v8/architecture/enterprise-deployment.md). [Ulteriori informazioni](../../v8/architecture/replication.md)

### Gestione degli errori {#error-management}

* **[!UICONTROL Troubleshooting]**

  Questo campo consente di definire le azioni da eseguire in caso di errori in un’attività del flusso di lavoro. Sono disponibili due opzioni possibili:

   * **[!UICONTROL Stop the process]**: il flusso di lavoro viene sospeso automaticamente. lo stato del flusso di lavoro diventa **[!UICONTROL Failed]**. Una volta risolto il problema, riavviare il flusso di lavoro utilizzando i pulsanti **[!UICONTROL Start]** o **[!UICONTROL Restart]**.
   * **[!UICONTROL Ignore]**: lo stato dell&#39;attività che ha attivato l&#39;errore diventa **[!UICONTROL Failed]**, ma il flusso di lavoro mantiene lo stato **[!UICONTROL Started]**. Questa configurazione è pertinente per le attività ricorrenti: se il ramo include un modulo di pianificazione, si avvia normalmente alla successiva esecuzione del flusso di lavoro.

* **[!UICONTROL Consecutive errors]**

  Questo campo diventa disponibile quando il valore **[!UICONTROL Ignore]** è selezionato nel campo **[!UICONTROL In case of errors]**. È possibile specificare il numero di errori che possono essere ignorati prima dell’interruzione del processo. Una volta raggiunto questo numero, lo stato del flusso di lavoro diventa **[!UICONTROL Failed]**. Se il valore di questo campo è 0, il flusso di lavoro non verrà mai interrotto indipendentemente dal numero di errori.

* **[!UICONTROL Template]**

  Questo campo consente di selezionare il modello di notifica da inviare ai supervisori del flusso di lavoro quando lo stato cambia in **[!UICONTROL Failed]**.

  Gli operatori interessati riceveranno una notifica via e-mail, se nel loro profilo è presente un indirizzo e-mail. Per definire i supervisori del flusso di lavoro, passare al campo **[!UICONTROL Supervisor(s)]** delle proprietà (**[!UICONTROL General]** scheda).

  ![](assets/wf-properties_select-supervisors.png)

  Il modello predefinito di **[!UICONTROL Notification to a workflow supervisor]** include un collegamento per accedere alla console client di Adobe Campaign tramite il Web in modo che il destinatario possa occuparsi del problema una volta effettuato l&#39;accesso.

  Per creare un modello personalizzato, passa a **[!UICONTROL Administration>Campaign management>Technical deliveries and templates]**.
