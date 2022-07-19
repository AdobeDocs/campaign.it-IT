---
product: campaign
title: Best practice per i flussi di lavoro
description: Scopri le best practice per i flussi di lavoro per Campaign
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '1664'
ht-degree: 5%

---

# Best practice per i flussi di lavoro{#workflow-best-practices}

Di seguito sono elencate le linee guida generali per ottimizzare le prestazioni del flusso di lavoro di Campaign, migliorare la progettazione del flusso di lavoro e selezionare le impostazioni corrette.

## Cartelle del flusso di lavoro {#workflow-folders}

Adobe consiglia di creare i flussi di lavoro in una cartella dedicata.

Se il flusso di lavoro influisce sull’intera piattaforma (ad esempio, i processi di pulizia), puoi aggiungere una sottocartella nel **[!UICONTROL Technical Workflows]** cartella.

## Denominazione del flusso di lavoro {#workflow-naming}

Poiché ciò ne semplifica la ricerca e la risoluzione dei problemi se non stanno ottenendo le prestazioni previste, Adobe consiglia di assegnare ai flussi di lavoro nomi ed etichette corretti: compila il campo di descrizione del flusso di lavoro per riepilogare il processo da eseguire in modo tale che l’operatore possa comprenderlo facilmente.

Se il flusso di lavoro fa parte di un processo che coinvolge più flussi di lavoro, puoi essere esplicito quando inserisci un’etichetta; l’utilizzo dei numeri è un ottimo modo per ordinare i flussi di lavoro (per Etichetta).

Ad esempio:

* 001 - Importazione - Destinatari importazione
* 002 - Importazione - Vendite all&#39;importazione
* 003 - Importazione - Dettagli delle vendite all&#39;importazione
* 010 - Esportazione - Registri di consegna delle esportazioni
* 011 - Esportazione - Registri di tracciamento delle esportazioni

## Gravità del flusso di lavoro {#workflow-severity}

Puoi configurare la gravità di un flusso di lavoro nelle proprietà del flusso di lavoro, nella **[!UICONTROL Execution]** scheda:

* Normale
* Produzione
* Critico

Fornire queste informazioni durante la creazione di un flusso di lavoro ti aiuterà a comprendere la gravità del processo configurato.

Questa opzione non ha alcun impatto funzionale sui flussi di lavoro diversi dai flussi di lavoro delle campagne.

I flussi di lavoro delle campagne (flussi di lavoro creati come parte di una campagna/operazione) con una gravità maggiore vengono eseguiti in priorità nel caso in cui la campagna abbia molti processi che dovrebbero essere eseguiti contemporaneamente. Per impostazione predefinita, solo 10 processi possono essere eseguiti contemporaneamente in una campagna, in base all&#39;opzione NmsOperation_LimitConcurrency. Ad esempio, se una campagna contiene 25 flussi di lavoro, i flussi di lavoro con una maggiore gravità verranno eseguiti nel primo pool di 10 processi.

## Monitoraggio del flusso di lavoro {#workflow-monitoring}

Per ricevere avvisi in caso di errore, è necessario monitorare tutti i flussi di lavoro pianificati in esecuzione su ambienti di produzione.

Nelle proprietà del flusso di lavoro, seleziona un gruppo di supervisori, o il valore predefinito **[!UICONTROL Workflow supervisors]** o un gruppo personalizzato. Assicurati che almeno un operatore appartenga a questo gruppo, con un&#39;e-mail impostata.

Prima di iniziare a creare un flusso di lavoro, ricorda di definire i supervisori del flusso di lavoro. In caso di errori, verranno notificati per e-mail. Per ulteriori informazioni, consulta [Gestione degli errori](monitor-workflow-execution.md#managing-errors).

Controllare regolarmente il **[!UICONTROL Monitoring]** per visualizzare lo stato generale dei flussi di lavoro attivi. Per ulteriori informazioni, consulta [Sorveglianza d&#39;istanza](monitor-workflow-execution.md#instance-supervision).

Workflow HeatMap consente agli amministratori della piattaforma Adobe Campaign di monitorare il carico sull&#39;istanza e pianificare i flussi di lavoro di conseguenza. Per ulteriori informazioni, consulta [Monitoraggio del flusso di lavoro](heatmap.md).

## Attività {#using-activities}

>[!CAUTION]
>
>Puoi copiare e incollare le attività all’interno di uno stesso flusso di lavoro. Tuttavia, si sconsiglia di copiare e incollare le attività tra flussi di lavoro diversi. Alcune impostazioni collegate ad attività come Consegne e Scheduler potrebbero causare conflitti ed errori durante l’esecuzione del flusso di lavoro di destinazione. Invece, ti abbiamo consigliato di  **Duplica** flussi di lavoro. Per ulteriori informazioni, consulta [Duplicazione dei flussi di lavoro](build-a-workflow.md#duplicate-workflows).

### Nome dell’attività {#name-of-the-activity}

Durante lo sviluppo del flusso di lavoro, tutte le attività avranno un nome, così come tutti gli oggetti Adobe Campaign. Anche se il nome viene generato dallo strumento, al momento della configurazione è consigliabile rinominarlo con un nome esplicito. Il rischio di farlo in un secondo momento è che possa interrompere il flusso di lavoro con le attività utilizzando il nome di un’altra attività precedente. Quindi sarebbe difficile aggiornare i nomi in seguito.

Il nome dell’attività si trova nella **[!UICONTROL Advanced]** scheda . Non lasciarli chiamati **[!UICONTROL query]**, **[!UICONTROL query1]**, **[!UICONTROL query11]**, ma fornisci loro nomi espliciti quali **[!UICONTROL querySubscribedRecipients]**. Questo nome verrà visualizzato nel giornale di registrazione e, se applicabile, nei log SQL, e questo aiuterà a eseguire il debug del flusso di lavoro durante la configurazione.

### Prima e ultima attività {#first-and-last-activities}

* Avvia sempre il flusso di lavoro con un **[!UICONTROL Start]** attività o **[!UICONTROL Scheduler]** attività. Se necessario, puoi anche utilizzare un **[!UICONTROL External signal]** attività.
* Durante la creazione del flusso di lavoro, utilizza solo un **[!UICONTROL Scheduler]** attività per ramo. Se lo stesso ramo di un flusso di lavoro include più pianificatori (collegati tra loro), il numero di attività da eseguire verrà moltiplicato in modo esponenziale, il che sovraccaricherebbe notevolmente il database. Questa regola si applica anche a tutte le attività con un **[!UICONTROL Scheduling & History]** scheda . Ulteriori informazioni su [Pianificazione](scheduler.md).

   ![](assets/wf-scheduler.png)

* Utilizzo **[!UICONTROL End]** per ogni flusso di lavoro. Questo consente ad Adobe Campaign di liberare spazio temporaneo utilizzato per i calcoli all’interno dei flussi di lavoro. Per ulteriori informazioni, consulta: [Start ed End](start-and-end.md).

### Javascript all’interno di un’attività {#javascript-within-an-activity}

È possibile aggiungere JavaScript durante l’inizializzazione di un’attività del flusso di lavoro. Questo può essere fatto in un’ attività di **[!UICONTROL Advanced]** scheda dell’attività.

Per semplificare lo spotting del flusso di lavoro, è consigliabile utilizzare trattini doppi all’inizio e alla fine dell’etichetta dell’attività, come segue: — La mia etichetta —

### Segnale {#signal}

Nella maggior parte dei casi, non si sa da dove viene richiamato il segnale. Per evitare questo problema, utilizza il **[!UICONTROL Comment]** all&#39;interno del campo **[!UICONTROL Advanced]** scheda dell&#39;attività del segnale per documentare l&#39;origine prevista di un segnale per questa attività.

## Aggiornamenti dei flussi di lavoro {#workflow-update}

Un flusso di lavoro di produzione non deve essere aggiornato direttamente. A meno che il processo non consista nella creazione di una campagna con flussi di lavoro basati su modelli, i processi devono prima essere testati in un ambiente di sviluppo. Dopo questa convalida, il flusso di lavoro può essere distribuito e avviato in produzione.

Esegui tutti i test negli ambienti di sviluppo o di staging, non negli ambienti di produzione. In tal caso non si può garantire la prestazione.

I flussi di lavoro archiviati possono essere conservati su piattaforme di sviluppo o di test, in una cartella archiviata, ma l&#39;ambiente di produzione dovrebbe rimanere il più pulito possibile. I vecchi flussi di lavoro devono essere rimossi dall’ambiente di produzione se sono inattivi.

## Esecuzione e prestazioni {#execution-and-performance}

### Registri {#logs}

Metodo JavaScript **[!UICONTROL logInfo()]** è una soluzione per il debug di un flusso di lavoro. Tuttavia deve essere utilizzato con attenzione, soprattutto per le attività che vengono spesso eseguite: può sovraccaricare i registri e aumentare significativamente le dimensioni della tabella di registro.

### Mantieni popolazioni provvisorie

La **Mantenere il risultato delle popolazioni intermedie tra due esecuzioni** consente di mantenere tabelle temporanee tra due esecuzioni di un flusso di lavoro.

È disponibile nelle proprietà del flusso di lavoro **[!UICONTROL General]** e può essere utilizzato a scopo di sviluppo e test per monitorare i dati e controllare i risultati. Puoi utilizzare questa opzione negli ambienti di sviluppo ma non mai negli ambienti di produzione. Mantenere tabelle temporanee potrebbe comportare un aumento significativo delle dimensioni del database e, in ultima analisi, il raggiungimento del limite di dimensione. Inoltre, rallenterà il backup.

Vengono mantenute solo le tabelle di lavoro dell’ultima esecuzione del flusso di lavoro. Le tabelle di lavoro delle esecuzioni precedenti vengono eliminate dal **[!UICONTROL cleanup]** , che viene eseguito su base giornaliera.

>[!CAUTION]
>
>Questa opzione deve essere **mai** essere controllati in un **produzione** workflow. Questa opzione viene utilizzata per analizzare i risultati ed è progettata solo a scopo di test e quindi deve essere utilizzata solo negli ambienti di sviluppo o di staging.


### Query SQL di log

La **Registra query SQL nel giornale di registrazione** è disponibile nella **[!UICONTROL Execution]** scheda delle proprietà del flusso di lavoro. Questa opzione registra tutte le query SQL dalle diverse attività e fornisce un modo per vedere cosa viene effettivamente eseguito dalla piattaforma. Tuttavia, questa opzione deve essere utilizzata solo **temporaneamente** durante lo sviluppo e **non attivato in produzione**.

Si consiglia di eliminare i registri quando non sono più necessari. La cronologia del flusso di lavoro non viene eliminata automaticamente: tutti i messaggi vengono conservati per impostazione predefinita. La cronologia può essere eliminata tramite **[!UICONTROL File > Actions]** oppure facendo clic sul pulsante Azioni nella barra degli strumenti sopra l’elenco. Selezionare Elimina cronologia.
Per informazioni su come eliminare i log, consulta questo [documentazione](start-a-workflow.md).

### Pianificazione del flusso di lavoro {#workflow-planning}

È necessario applicare ulteriori best practice alla pianificazione dell’esecuzione dei flussi di lavoro per evitare problemi:

* Mantenere un livello di attività stabile durante il giorno ed evitare picchi per evitare che l&#39;istanza si sovraccarichi. A questo scopo, distribuisci gli orari di inizio del flusso di lavoro in modo uniforme durante l’intera giornata.
* Pianifica il caricamento dei dati in un giorno per ridurre il contenzioso sulle risorse.
* I flussi di lavoro lunghi possono avere un impatto potenzialmente sulle risorse del server e del database. Dividi i flussi di lavoro più lunghi per ridurre il tempo di elaborazione.
* Per ridurre i tempi di esecuzione generali, sostituisci le attività che richiedono molto tempo con attività semplificate e più veloci.
* Evita di eseguire più di 20 flussi di lavoro contemporaneamente. Quando vengono eseguiti contemporaneamente troppi flussi di lavoro, la piattaforma può essere sovraccaricata e diventare instabile.

### Esecuzione di un flusso di lavoro {#workflow-execution}

Migliora la stabilità dell’istanza implementando le seguenti best practice:

* **Non pianificare un flusso di lavoro da eseguire più di ogni 15 minuti** perché potrebbe impedire le prestazioni complessive del sistema e creare blocchi nel database.

* **Evita di lasciare i flussi di lavoro in pausa**. Se crei un flusso di lavoro temporaneo, assicurati che sia in grado di terminare correttamente e di non rimanere in un **[!UICONTROL paused]** stato. Se viene messo in pausa, significa che è necessario mantenere le tabelle temporanee e quindi aumentare le dimensioni del database. Assegna le autorità di vigilanza del flusso di lavoro in Proprietà flusso di lavoro per inviare un avviso in caso di errore o interruzione di un flusso di lavoro da parte del sistema.

   Per evitare che i flussi di lavoro siano in pausa:

   * Controlla regolarmente i tuoi flussi di lavoro per assicurarti che non ci siano errori imprevisti.
   * Semplifica i tuoi flussi di lavoro, ad esempio suddividendoli in flussi di lavoro di grandi dimensioni in diversi flussi di lavoro. È possibile utilizzare **[!UICONTROL External signal]** le attività attivano la loro esecuzione in base all’esecuzione di altri flussi di lavoro.
   * Evita di disabilitare le attività con i flussi nei flussi di lavoro lasciando i thread aperti e portando a numerose tabelle temporanee che possono occupare molto spazio. Non mantenere le attività in **[!UICONTROL Do not enable]** o **[!UICONTROL Enable but do not execute]** nei flussi di lavoro.

* **Interrompere i flussi di lavoro non utilizzati**. I flussi di lavoro che continuano a essere in esecuzione mantengono le connessioni al database.

* **Utilizza solo l’arresto incondizionato nei casi più rari**. Non utilizzare questa azione regolarmente. La mancata chiusura delle connessioni generate dai flussi di lavoro al database influisce sulle prestazioni.

* **Non eseguire più richieste di arresto sullo stesso flusso di lavoro**. L’arresto di un flusso di lavoro è un processo asincrono: La richiesta viene registrata, quindi il server del flusso di lavoro o i server annullano le operazioni in corso. L’arresto di un’istanza di flusso di lavoro può richiedere del tempo, specialmente se il flusso di lavoro è in esecuzione su più server, ciascuno dei quali deve assumere il controllo per annullare le attività in corso. Per evitare problemi, attendi che l’operazione di arresto sia completata ed evita di interrompere un flusso di lavoro più volte.

### Esegui nell’opzione del motore {#execute-in-the-engine-option}

In un ambiente di produzione, evita di eseguire flussi di lavoro nel motore. Quando il **[!UICONTROL Execute in the engine]** è selezionata l’opzione **[!UICONTROL Workflow properties]**, il flusso di lavoro ha la priorità e tutti gli altri flussi di lavoro vengono interrotti dal motore del flusso di lavoro fino al termine di questo.

![](assets/wf-execute-in-engine.png)