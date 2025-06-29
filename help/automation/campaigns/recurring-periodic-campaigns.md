---
product: campaign
title: Creare campagne ricorrenti e periodiche
description: Scopri come creare ed eseguire campagne ricorrenti e periodiche
feature: Campaigns, Cross Channel Orchestration, Programs
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 68c5b903-5043-4e74-b3f6-90a7f2fb3b9a
source-git-commit: a5f7cf6e21b263f8a7fb4fa19a88bebb78390c3d
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 0%

---

# Campagne ricorrenti e periodiche {#recurring-and-periodic-campaigns}

Una **campagna ricorrente** è una campagna basata su un modello specifico, i cui flussi di lavoro sono configurati per essere eseguiti in base a una pianificazione associata. Il targeting viene duplicato su ogni esecuzione e vengono tracciati i vari processi e le popolazioni di destinazione.  Una volta configurate, le campagne ricorrenti creano automaticamente un nuovo flusso di lavoro (duplicando il modello di flusso di lavoro) ed eseguilo. Ad esempio, se devi inviare un promemoria mensile a un segmento di pubblico, configura una campagna ricorrente in modo che, all’inizio di ogni anno, crei 12 flussi di lavoro, uno per ogni mese. [Ulteriori informazioni](#create-a-recurring-campaign)

Una **campagna periodica** è una campagna basata su un modello specifico che consente di creare istanze della campagna in base a una pianificazione di esecuzione. Le istanze di Campaign vengono create automaticamente in base a un modello di campagna periodica, a seconda della frequenza definita nella pianificazione del modello. [Ulteriori informazioni](#create-a-periodic-campaign)

## Creare una campagna ricorrente {#create-a-recurring-campaign}

Le campagne ricorrenti vengono create da un modello specifico che definisce il modello di flusso di lavoro da eseguire e la pianificazione di esecuzione.

### Creare un modello per le campagne ricorrenti {#create-the-campaign-template}

Per creare un modello per le campagne ricorrenti, effettua le seguenti operazioni:

1. Apri Campaign Explorer e passa a **[!UICONTROL Resources > Templates > Campaign templates]**.
1. Duplica il modello predefinito **[!UICONTROL Recurring campaign]**.
   ![](assets/recurring-campaign-duplicate.png)
1. Inserisci il nome del modello e la durata della campagna.
1. Per questo tipo di campagna, viene aggiunta una scheda **[!UICONTROL Schedule]** per creare la pianificazione di esecuzione del modello. Utilizza questa scheda per definire le date di esecuzione delle campagne basate su questo modello.
   ![](assets/recurring-campaign-schedule.png)

   La modalità di configurazione della pianificazione di esecuzione coincide con l&#39;oggetto **[!UICONTROL Scheduler]** del flusso di lavoro. [Ulteriori informazioni](../workflow/scheduler.md).

   >[!CAUTION]
   >
   >La configurazione della pianificazione di esecuzione deve essere eseguita con attenzione. Le campagne ricorrenti duplicano i flussi di lavoro del relativo modello a seconda della pianificazione specificata. Questa operazione può sovraccaricare il database.

1. Specificare un valore nel campo **[!UICONTROL Create in advance for]** per creare i flussi di lavoro corrispondenti per il periodo indicato.
1. Nella scheda **[!UICONTROL Targeting and workflows]**, progetta il modello di flusso di lavoro da utilizzare nelle campagne basate su questo modello. Questo flusso di lavoro contiene in genere i parametri di targeting e una o più consegne.

   >[!NOTE]
   >
   >Questo flusso di lavoro deve essere salvato come modello di flusso di lavoro ricorrente. A tale scopo, modificare le proprietà del flusso di lavoro e selezionare l&#39;opzione **[!UICONTROL Recurring workflow template]** nella scheda **[!UICONTROL Execution]**.

   ![](assets/recurring-campaign-wf-properties.png)

### Creare la campagna ricorrente {#create-the-recurring-campaign}

Per creare la campagna ricorrente ed eseguire i relativi flussi di lavoro in base alla pianificazione definita nel modello, è necessario:

1. Crea una nuova campagna in base al modello di campagna ricorrente.
1. Compila la pianificazione dell&#39;esecuzione del flusso di lavoro nella scheda **[!UICONTROL Schedule]**. La pianificazione della campagna consente di inserire una data di inizio per la creazione o l’esecuzione automatica del flusso di lavoro per ogni linea.

   Per ogni riga, puoi aggiungere le seguenti opzioni aggiuntive:

   * Abilita l’opzione **[!UICONTROL To be approved]** per forzare le richieste di approvazione della consegna nel flusso di lavoro.
   * Abilita l&#39;opzione **[!UICONTROL To be started]** per avviare il flusso di lavoro quando viene raggiunta la data di inizio.

   Il campo **[!UICONTROL Create in advance for]** ti consente di creare tutti i flussi di lavoro che coprono il periodo inserito.

   All&#39;esecuzione del flusso di lavoro **[!UICONTROL Jobs on campaigns]**, i flussi di lavoro dedicati vengono creati in base alle occorrenze definite nella pianificazione della campagna. Viene quindi creato un flusso di lavoro per ogni data di esecuzione.

1. I flussi di lavoro ricorrenti vengono creati automaticamente dal modello di flusso di lavoro presente nella campagna. Sono visibili dalla scheda **[!UICONTROL Targeting and workflows]** della campagna.

   ![](assets/recurring-wf-created.png)

   L’etichetta di un’istanza di flusso di lavoro ricorrente è costituita dall’etichetta del modello e dal numero del flusso di lavoro, con il carattere # tra i due.

   I flussi di lavoro creati dalla pianificazione vengono associati automaticamente alla pianificazione nella colonna **[!UICONTROL Workflow]** della scheda **[!UICONTROL Schedule]**.

   ![](assets/recurring-wf-schedule-executed.png)

   Ogni flusso di lavoro può essere modificato da questa scheda.

   >[!NOTE]
   >
   >La data di inizio della riga di pianificazione associata al flusso di lavoro è disponibile da una variabile del flusso di lavoro con la seguente sintassi:\
   >`$date(instance/vars/@startPlanningDate)`

## Creare una campagna periodica {#create-a-periodic-campaign}

Una campagna periodica è una campagna basata su un modello specifico che consente di creare istanze della campagna in base a una pianificazione di esecuzione. Le istanze di Campaign vengono create automaticamente in base a un modello di campagna periodica, a seconda della frequenza definita nella pianificazione del modello.

### Creare il modello della campagna {#create-the-campaign-template-1}

1. Apri Campaign Explorer e passa a **[!UICONTROL Resources > Templates > Campaign templates]**.
1. Duplica il modello predefinito **[!UICONTROL Periodic campaign]**.
1. Immetti le proprietà del modello.

   >[!NOTE]
   >
   >L’operatore a cui è assegnato il modello deve disporre delle autorizzazioni appropriate per creare campagne nel programma selezionato.

1. Crea il flusso di lavoro associato a questo modello. Questo flusso di lavoro viene duplicato in ogni campagna periodica creata dal modello.

   >[!NOTE]
   >
   >Questo flusso di lavoro è un modello di workflow. Non può essere eseguito dal modello della campagna.

1. Completare la pianificazione dell&#39;esecuzione come per un modello di campagna ricorrente: fare clic sul pulsante **[!UICONTROL Add]** e definire le date di inizio e di fine oppure compilare la pianificazione dell&#39;esecuzione tramite il collegamento.

   >[!CAUTION]
   >
   >I modelli di campagna periodica creano nuove campagne in base alla pianificazione definita in precedenza. Deve quindi essere completata con attenzione, per evitare di sovraccaricare il database di Adobe Campaign.

1. Una volta raggiunta la data di inizio dell’esecuzione, la campagna corrispondente viene creata automaticamente. Assume tutte le caratteristiche del proprio modello.

   Ogni campagna può essere modificata tramite la pianificazione del modello.

   Ogni campagna periodica contiene gli stessi elementi. Una volta creata, viene gestita come una campagna standard.
