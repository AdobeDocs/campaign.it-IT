---
product: campaign
title: Creare un flusso di lavoro
description: Scopri come creare un flusso di lavoro
feature: Workflows
role: User
exl-id: a6003fdb-1035-4b80-8831-73f30a0b4fb2
source-git-commit: b7fa3dfb1e596d2ea41674278cbe315199264611
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 1%

---

# Creare un flusso di lavoro {#build-a-workflow}

## Crea un nuovo flusso di lavoro {#create-a-new-workflow}

Il flusso di creazione del flusso di lavoro dipende dal tipo di flussi di lavoro. Puoi eseguire le seguenti azioni:

* Crea [Workflow di targeting](#targeting-workflows) dal **[!UICONTROL Profiles and Targets]** > **[!UICONTROL Jobs]** > **[!UICONTROL Targeting workflows]** dell&#39;Explorer o dal **[!UICONTROL Profiles and Targets]** della home page, tramite la scheda **[!UICONTROL Targeting workflows]** scheda secondaria.

  ![](assets/create-targeting-wf.png)

* Crea [Flussi di lavoro per campagne](#campaign-workflows) dal **[!UICONTROL Targeting and workflows]** scheda di una campagna

* Crea [Flussi di lavoro tecnici](#technical-workflows) dal **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]** nodo di Explorer. Si consiglia di creare una cartella di flusso di lavoro specifica per salvare i flussi di lavoro tecnici.

Fai clic su **[!UICONTROL New]** si trova sopra l’elenco dei flussi di lavoro.

![](assets/create_a_wf_icon.png)

Inserisci un’etichetta e fai clic su **[!UICONTROL Save]**.

## Aggiungere e collegare attività {#add-and-link-activities}

Ora devi definire le varie attività e collegarle nel diagramma. In questa fase della configurazione, è possibile visualizzare l’etichetta del diagramma e lo stato del flusso di lavoro (Modifica in corso). La sezione inferiore della finestra viene utilizzata solo per modificare il diagramma. Contiene una barra degli strumenti, una palette di attività (a sinistra) e il diagramma stesso (a destra).

![](assets/new-workflow-2.png)

>[!NOTE]
>
>Se la palette non viene visualizzata, fai clic sul primo pulsante sulla barra degli strumenti del flusso di lavoro per visualizzarla.

Le attività sono raggruppate per categoria nelle diverse schede della palette. Le schede e le attività disponibili possono variare a seconda del tipo di flusso di lavoro (tecnico, di targeting o del flusso di lavoro della campagna).

* La prima scheda contiene attività di targeting e manipolazione dei dati. Queste attività sono descritte in dettaglio [Attività di targeting](targeting-activities.md).
* La seconda scheda contiene le attività di pianificazione, utilizzate principalmente per coordinare altre attività. Queste attività sono descritte in dettaglio [Attività di controllo del flusso](flow-control-activities.md).
* La terza scheda contiene gli strumenti e le azioni che possono essere utilizzati nel flusso di lavoro. Queste attività sono descritte in dettaglio [Attività azione](action-activities.md).
* La quarta scheda contiene attività che dipendono da un dato evento, ad esempio la ricezione di un messaggio e-mail o l’arrivo di un file su un server. Queste attività sono descritte in dettaglio [Attività di eventi](event-activities.md).

Per creare il diagramma

1. Aggiungi un’attività selezionandola nella palette e spostandola nel diagramma con un’operazione di trascinamento della selezione.

   Aggiungi un **Inizio** attività e quindi un **Consegna** attività nel diagramma.

   ![](assets/new-workflow-3.png)

1. Collega le attività trascinando la **Inizio** transizione di attività e rilasciarla sulla **Consegna** attività.

   ![](assets/new-workflow-4.png)

   Puoi collegare automaticamente un’attività alla precedente inserendo la nuova attività alla fine della transizione.

1. Aggiungi le attività necessarie e collegale come mostrato nel diagramma seguente.

   ![](assets/new-workflow-5.png)

>[!CAUTION]
>
>Puoi copiare e incollare le attività all’interno dello stesso flusso di lavoro. Tuttavia, si sconsiglia di copiare e incollare le attività tra flussi di lavoro diversi. Alcune impostazioni associate ad attività come Consegne e Modulo di pianificazione potrebbero causare conflitti ed errori durante l’esecuzione del flusso di lavoro di destinazione. Ti consigliamo invece di  **Duplica** flussi di lavoro. Per ulteriori informazioni, consulta [Flussi di lavoro duplicati](#duplicate-workflows).

È possibile modificare la visualizzazione e il layout del grafico utilizzando i seguenti elementi:

* **Utilizzare la barra degli strumenti**

  La barra degli strumenti di modifica del diagramma consente di accedere alle funzioni di layout ed esecuzione del flusso di lavoro.

  ![](assets/wf-toolbar.png)

  Questo consente di adattare il layout dello strumento di modifica: visualizzazione della palette e panoramica, dimensioni e allineamento degli oggetti grafici.

  ![](assets/s_user_segmentation_toolbar.png)

  Le icone relative all’avanzamento e alla visualizzazione dei registri sono descritte in dettaglio nelle sezioni seguenti:

   * [Avanzamento visualizzazione](monitor-workflow-execution.md#displaying-progress)
   * [Visualizza registri](monitor-workflow-execution.md#displaying-logs)

* **Allineamento degli oggetti**

  Per allineare le icone, selezionarle e fare clic sul pulsante **[!UICONTROL Align vertically]** o **[!UICONTROL Align horizontally]** icona.

  Utilizza il **CTRL** chiave per selezionare più attività sparse o per deselezionare una o più attività. Fare clic sullo sfondo del diagramma per deselezionare tutto.

* **Gestione delle immagini**

  Puoi personalizzare l’immagine di sfondo del diagramma e quelle relative alle varie attività. Fai riferimento a [Modificare le immagini dell’attività](change-activity-images.md).

## Configurare le attività {#configure-activities}

Fai doppio clic su un’attività per configurarla oppure fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Open...]**.

>[!NOTE]
>
>Le attività del flusso di lavoro di Campaign sono descritte in dettaglio [questa sezione](activities.md).

La prima scheda contiene la configurazione di base. Il **[!UICONTROL Advanced]** La scheda contiene i parametri aggiuntivi, utilizzati in particolare per definire il comportamento in caso di errore, specificare la durata di esecuzione di un’attività e immettere uno script di inizializzazione.

Per comprendere meglio le attività e migliorare la leggibilità del flusso di lavoro, puoi inserire commenti nelle attività.

![](assets/example1-comment.png)

Questi commenti vengono visualizzati automaticamente quando gli operatori scorrono sull’attività.

![](assets/example2-comment.png)


## Modelli di flusso di lavoro {#workflow-templates}

I modelli di flusso di lavoro contengono la configurazione generale delle proprietà e possibilmente una serie di attività concatenate all’interno di un diagramma. Questa configurazione può essere riutilizzata per creare nuovi flussi di lavoro contenenti un certo numero di elementi preconfigurati

Puoi creare nuovi modelli di flusso di lavoro basati su modelli esistenti o modificare direttamente un flusso di lavoro in un modello.

I modelli di flusso di lavoro sono memorizzati nel **[!UICONTROL Resources > Templates > Workflow templates]** nodo di Explorer.

Oltre alle consuete proprietà del flusso di lavoro, le proprietà del modello consentono di specificare il file di esecuzione per i flussi di lavoro creati in base a questo modello.

![](assets/wf-template-properties.png)

## Flussi di lavoro duplicati {#duplicate-workflows}

Puoi duplicare diversi tipi di flussi di lavoro. Una volta eseguita la duplicazione, le modifiche del flusso di lavoro non vengono riportate nella copia del flusso di lavoro.

>[!CAUTION]
>
>La funzione di copia e incolla è disponibile nei flussi di lavoro, ma si consiglia di utilizzare **Duplica**. Una volta copiata un’attività, ne viene mantenuta l’intera configurazione. Per le attività di consegna (e-mail, SMS, notifica push...), viene copiato anche l’oggetto di consegna associato all’attività, che può causare l’arresto anomalo.

1. Fai clic con il pulsante destro del mouse su un flusso di lavoro.
1. Clic **Duplica**.

   ![](assets/duplicate-workflows.png)

1. Nella finestra del flusso di lavoro, modifica l’etichetta del flusso di lavoro.
1. Fai clic su **Salva**.

