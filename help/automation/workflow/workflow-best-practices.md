---
product: campaign
title: Best practice per i flussi di lavoro
description: Scopri le best practice per i flussi di lavoro di Campaign
feature: Workflows
exl-id: 8bcaf367-5b1f-4d31-80c9-c77df43c6ed1
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '1664'
ht-degree: 11%

---

# Best practice per i flussi di lavoro{#workflow-best-practices}

Di seguito sono elencate le linee guida generali per ottimizzare le prestazioni del flusso di lavoro di Campaign, migliorarne la progettazione e selezionare le impostazioni corrette.

## Cartelle del flusso di lavoro {#workflow-folders}

L’Adobe consiglia di creare i flussi di lavoro in una cartella dedicata.

Se il flusso di lavoro influisce sull’intera piattaforma (ad esempio sui processi di pulizia), puoi considerare l’aggiunta di una sottocartella nella **[!UICONTROL Technical Workflows]** cartella.

## Denominazione flusso di lavoro {#workflow-naming}

Poiché ciò ne semplifica la ricerca e la risoluzione dei problemi se non stanno ottenendo le prestazioni previste, Adobe consiglia di assegnare ai flussi di lavoro nomi ed etichette corretti: compila il campo di descrizione del flusso di lavoro per riepilogare il processo da eseguire in modo tale che l’operatore possa comprenderlo facilmente.

Se il flusso di lavoro fa parte di un processo che coinvolge più flussi di lavoro, puoi essere esplicito quando inserisci un’etichetta; l’utilizzo dei numeri è un ottimo modo per ordinare i flussi di lavoro (per Etichetta).

Ad esempio:

* 001 - Importazione - Destinatari importazione
* 002 - Importazione - Vendite all’importazione
* 003 - Importazione - Dettagli delle vendite all’importazione
* 010 - Esportazione - Registri di consegna delle esportazioni
* 011 - Esportazione - Registri di tracciamento delle esportazioni

## Gravità del flusso di lavoro {#workflow-severity}

È possibile configurare la gravità di un flusso di lavoro nelle proprietà del flusso di lavoro in **[!UICONTROL Execution]** scheda:

* Normale
* Produzione
* Critico

L’indicazione di queste informazioni durante la creazione di un flusso di lavoro consente di comprendere la gravità del processo configurato.

Questa opzione non ha alcun impatto funzionale sui flussi di lavoro diversi da quelli delle campagne.

I flussi di lavoro delle campagne (flussi di lavoro creati come parte di una campagna/operazione) con una gravità più elevata vengono eseguiti in priorità nel caso in cui la campagna abbia molti processi che dovrebbero essere eseguiti contemporaneamente. Per impostazione predefinita, solo 10 processi possono essere eseguiti contemporaneamente in una campagna, in base all’opzione NmsOperation_LimitConcurrency. Ad esempio, se una campagna contiene 25 flussi di lavoro, quelli con una gravità maggiore verranno eseguiti nel primo pool di 10 processi.

## Monitoraggio del flusso di lavoro {#workflow-monitoring}

Tutti i flussi di lavoro pianificati in esecuzione negli ambienti di produzione devono essere monitorati per ricevere un avviso in caso di errore.

Nelle proprietà del flusso di lavoro, selezionare un gruppo Supervisore, che può essere **[!UICONTROL Workflow supervisors]** o un gruppo personalizzato. Assicurati che almeno un operatore appartenga a questo gruppo, con un messaggio e-mail configurato.

Prima di iniziare a creare un flusso di lavoro, ricorda di definire i supervisori del flusso di lavoro. In caso di errori, verranno avvisati via e-mail. Per ulteriori informazioni, consulta [Gestione degli errori](monitor-workflow-execution.md#managing-errors).

Controlla regolarmente la **[!UICONTROL Monitoring]** per visualizzare lo stato generale dei flussi di lavoro attivi. Per ulteriori informazioni, consulta [Supervisione istanza](monitor-workflow-execution.md#instance-supervision).

Workflow HeatMap consente agli amministratori della piattaforma Adobe Campaign di monitorare il carico sull’istanza e pianificare i flussi di lavoro di conseguenza. Per ulteriori informazioni, consulta [Monitoraggio dei flussi di lavoro](heatmap.md).

## Attività {#using-activities}

>[!CAUTION]
>
>Puoi copiare e incollare le attività all’interno dello stesso flusso di lavoro. Tuttavia, si sconsiglia di copiare e incollare le attività tra flussi di lavoro diversi. Alcune impostazioni associate ad attività come Consegne e Modulo di pianificazione potrebbero causare conflitti ed errori durante l’esecuzione del flusso di lavoro di destinazione. Ti consigliamo invece di  **Duplica** flussi di lavoro. Per ulteriori informazioni, consulta [Duplicazione dei flussi di lavoro](build-a-workflow.md#duplicate-workflows).

### Nome dell’attività {#name-of-the-activity}

Durante lo sviluppo del flusso di lavoro, tutte le attività avranno un nome, così come tutti gli oggetti di Adobe Campaign. Mentre il nome viene generato dallo strumento, è consigliabile rinominarlo con un nome esplicito durante la configurazione. Se lo facesse in un secondo momento, potrebbe interrompere il flusso di lavoro con le attività che utilizzano il nome di un’altra attività precedente. Sarebbe quindi difficile aggiornare i nomi in seguito.

Il nome dell’attività si trova nella sezione **[!UICONTROL Advanced]** scheda. Non lasciarle con il nome **[!UICONTROL query]**, **[!UICONTROL query1]**, **[!UICONTROL query11]**, ma assegna loro nomi espliciti quali **[!UICONTROL querySubscribedRecipients]**. Questo nome verrà visualizzato nel giornale di registrazione e, se applicabile, nei registri SQL e sarà utile per eseguire il debug del flusso di lavoro durante la configurazione.

### Prima e ultima attività {#first-and-last-activities}

* Avvia sempre il flusso di lavoro con un **[!UICONTROL Start]** attività o un **[!UICONTROL Scheduler]** attività. Se necessario, puoi anche utilizzare un’ **[!UICONTROL External signal]** attività.
* Durante la creazione del flusso di lavoro, utilizza un solo **[!UICONTROL Scheduler]** attività per ramo. Se lo stesso ramo di un flusso di lavoro include più pianificatori (collegati tra loro), il numero di attività da eseguire verrà moltiplicato in modo esponenziale, il che sovraccaricherebbe notevolmente il database. Questa regola si applica anche a tutte le attività con **[!UICONTROL Scheduling & History]** scheda. Ulteriori informazioni su [Pianificazione](scheduler.md).

  ![](assets/wf-scheduler.png)

* Utilizzare **[!UICONTROL End]** per ogni flusso di lavoro. Questo consente ad Adobe Campaign di liberare spazio temporaneo utilizzato per i calcoli all’interno dei flussi di lavoro. Per ulteriori informazioni, consulta: [Inizio e fine](start-and-end.md).

### JavaScript all&#39;interno di un&#39;attività {#javascript-within-an-activity}

È possibile aggiungere JavaScript durante l’inizializzazione di un’attività del flusso di lavoro. Questa operazione può essere eseguita nel di **[!UICONTROL Advanced]** dell’attività.

Per semplificare l’individuazione del flusso di lavoro, si consiglia di utilizzare i doppi trattini all’inizio e alla fine dell’etichetta di attività, come segue: — La mia etichetta —.

### Segnale {#signal}

Nella maggior parte dei casi, non saprai da dove viene chiamato il segnale. Per evitare questo problema, utilizza **[!UICONTROL Comment]** campo all&#39;interno del **[!UICONTROL Advanced]** scheda dell’attività del segnale per documentare l’origine prevista di un segnale per questa attività.

## Aggiornamenti del flusso di lavoro {#workflow-update}

Un flusso di lavoro di produzione non deve essere aggiornato direttamente. A meno che il processo non consista nella creazione di una campagna con flussi di lavoro basati su modelli, i processi devono prima essere testati in un ambiente di sviluppo. Dopo questa convalida, il flusso di lavoro può essere distribuito e avviato in produzione.

Eseguire tutti i test in ambienti di sviluppo o di staging, non in ambienti di produzione. In tal caso, non è possibile garantire la prestazione.

I flussi di lavoro archiviati possono essere mantenuti su piattaforme di sviluppo o di test, in una cartella Archiviata, ma l’ambiente di produzione deve rimanere il più pulito possibile. I flussi di lavoro precedenti devono essere rimossi dall’ambiente di produzione se sono inattivi.

## Esecuzione e prestazioni {#execution-and-performance}

### Registri {#logs}

Il metodo JavaScript **[!UICONTROL logInfo()]** è una soluzione per il debug di un flusso di lavoro. Tuttavia, deve essere utilizzato con attenzione, in particolare per le attività che vengono eseguite di frequente: può sovraccaricare i registri e aumentare in modo significativo le dimensioni della tabella dei registri.

### Mantenere le popolazioni ad interim

Il **Mantieni il risultato delle popolazioni provvisorie tra due esecuzioni** mantiene le tabelle temporanee tra due esecuzioni di un flusso di lavoro.

È disponibile nelle proprietà del flusso di lavoro&quot; **[!UICONTROL General]** e può essere utilizzato a scopo di sviluppo e test per monitorare i dati e verificare i risultati. Puoi utilizzare questa opzione negli ambienti di sviluppo ma mai negli ambienti di produzione. Mantenere tabelle temporanee potrebbe comportare un aumento significativo delle dimensioni del database e, in ultima analisi, il raggiungimento del limite consentito. Inoltre, rallenterà il backup.

Vengono mantenute solo le tabelle di lavoro dell’ultima esecuzione del flusso di lavoro. Le tabelle di lavoro delle esecuzioni precedenti vengono eliminate dal **[!UICONTROL cleanup]** flusso di lavoro, eseguito su base giornaliera.

>[!CAUTION]
>
>Questa opzione non deve **mai** essere selezionata in un flusso di lavoro di **produzione**. Viene utilizzata per analizzare i risultati ed è progettata solo a scopo di test e quindi deve essere utilizzata solo in ambienti di sviluppo o di staging.


### Registra query SQL

Il **Registra le query SQL nel giornale di registrazione** è disponibile nella **[!UICONTROL Execution]** scheda delle proprietà del flusso di lavoro. Questa opzione registra tutte le query SQL dalle diverse attività e fornisce un modo per visualizzare cosa viene effettivamente eseguito dalla piattaforma. Tuttavia, questa opzione deve essere utilizzata solo **temporaneamente** durante lo sviluppo e **non attivato in produzione**.

Si consiglia di eliminare i registri quando non sono più necessari. La cronologia del flusso di lavoro non viene eliminata automaticamente: tutti i messaggi vengono conservati per impostazione predefinita. La cronologia può essere eliminata tramite **[!UICONTROL File > Actions]** oppure facendo clic sul pulsante Azioni nella barra degli strumenti sopra l&#39;elenco. Selezionare Rimuovi cronologia.
Per informazioni su come eliminare i registri, consulta questa [documentazione](start-a-workflow.md).

### Pianificazione del flusso di lavoro {#workflow-planning}

Per evitare problemi, nella pianificazione dell’esecuzione dei flussi di lavoro devono essere applicate ulteriori best practice:

* Mantenere un livello stabile di attività durante il giorno ed evitare picchi per evitare il sovraccarico dell’istanza. A tal fine, distribuisci gli orari di inizio del flusso di lavoro in modo uniforme nell’arco della giornata.
* Pianifica il caricamento dei dati durante la notte per ridurre il conflitto tra risorse.
* I flussi di lavoro lunghi possono potenzialmente avere un impatto sulle risorse del server e del database. Dividi i flussi di lavoro più lunghi per ridurre i tempi di elaborazione.
* Per ridurre i tempi di esecuzione complessivi, sostituisci le attività che richiedono tempo con attività semplificate e più veloci.
* Evita di eseguire più di 20 flussi di lavoro simultaneamente. Quando troppi flussi di lavoro vengono eseguiti contemporaneamente, la piattaforma può essere sovraccarica e diventare instabile.

### Esecuzione di un flusso di lavoro {#workflow-execution}

Migliora la stabilità dell’istanza implementando le seguenti best practice:

* **Non pianificare l&#39;esecuzione di un flusso di lavoro ogni 15 minuti** perché potrebbe ostacolare le prestazioni complessive del sistema e creare blocchi nel database.

* **Evitare di lasciare i flussi di lavoro in stato di pausa**. Se crei un flusso di lavoro temporaneo, assicurati che possa terminare correttamente e non rimanere in un **[!UICONTROL paused]** stato. Se viene messo in pausa, implicherebbe la necessità di mantenere le tabelle temporanee e quindi aumentare le dimensioni del database. Assegna supervisori flusso di lavoro in Proprietà flusso di lavoro per inviare un avviso quando un flusso di lavoro non riesce o viene messo in pausa dal sistema.

  Per evitare che i flussi di lavoro si trovino in stato di pausa:

   * Controlla i flussi di lavoro regolarmente per assicurarti che non si verifichino errori imprevisti.
   * Mantieni i flussi di lavoro il più semplici possibile, ad esempio suddividendo flussi di lavoro di grandi dimensioni in diversi flussi di lavoro. È possibile utilizzare **[!UICONTROL External signal]** Le attività attivano la loro esecuzione in base all’esecuzione di altri flussi di lavoro.
   * Evita di disabilitare le attività con i flussi nei flussi di lavoro, lasciando aperti i thread e portando a molte tabelle temporanee che possono occupare molto spazio. Non mantenere le attività in **[!UICONTROL Do not enable]** o **[!UICONTROL Enable but do not execute]** nei flussi di lavoro.

* **Interrompere i flussi di lavoro inutilizzati**. I flussi di lavoro in esecuzione gestiscono le connessioni al database.

* **Utilizza l’interruzione incondizionata solo nei casi più rari**. Non utilizzi questa azione regolarmente. La mancata esecuzione di una chiusura pulita delle connessioni generate dai flussi di lavoro al database influisce sulle prestazioni.

* **Non eseguire più richieste di arresto sullo stesso flusso di lavoro**. L’arresto di un flusso di lavoro è un processo asincrono: la richiesta viene registrata, quindi il server o i server del flusso di lavoro annullano le operazioni in corso. L&#39;arresto di un&#39;istanza del flusso di lavoro può quindi richiedere tempo, soprattutto se il flusso di lavoro è in esecuzione su più server, ognuno dei quali deve assumere il controllo per annullare le attività in corso. Per evitare problemi, attendi il completamento dell’operazione di arresto ed evita di arrestare più volte un flusso di lavoro.

### Esegui nel motore, opzione {#execute-in-the-engine-option}

In un ambiente di produzione, evita di eseguire flussi di lavoro nel motore. Quando **[!UICONTROL Execute in the engine]** l&#39;opzione è selezionata in **[!UICONTROL Workflow properties]**, il flusso di lavoro ha la priorità e tutti gli altri flussi di lavoro vengono interrotti dal motore del flusso di lavoro fino al termine di questo.

![](assets/wf-execute-in-engine.png)
