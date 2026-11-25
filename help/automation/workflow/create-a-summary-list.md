---
product: campaign
title: Creare un elenco di riepilogo
description: Creare un elenco di riepilogo
feature: Workflows, Data Management
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 86dee66a-357a-4927-916e-51cde6c006d5
TQID: 'https://experienceleague.adobe.com/-pe9wOpEgZGYZg-mC5EBSQ6sH-pxsLC1HvUEnVxVBPM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '1246'
ht-degree: 1%
---
# Creare un elenco di riepilogo{#creating-a-summary-list}

Questo caso d’uso descrive la creazione di un flusso di lavoro che, dopo aver raccolto i file e seguito diversi arricchimenti, ti consente di creare un elenco di riepilogo. L&#39;esempio si basa su un elenco di contatti che hanno effettuato acquisti in un negozio.

![Diagramma del flusso di lavoro: agente di raccolta file, caricamento dati (file), arricchimento, aggiornamento dati, arricchimento 2, aggiornamento elenco e attesa.](assets/uc2_enrich_overview.png)

Viene utilizzata la seguente struttura di dati:

![Struttura dati: tabelle di acquisti e contatti collegate e una tabella Negozi separata con refStoreName e zipCodeRef.](assets/uc2_enrich_data.png)

Il suo obiettivo è:

* Per utilizzare le varie opzioni dell’attività di arricchimento
* Per aggiornare i dati nel database dopo una riconciliazione
* Creare una &quot;visualizzazione&quot; globale dei dati arricchiti

Per creare un elenco di riepilogo, è necessario seguire questi passaggi:

1. Raccolta e caricamento di un file &quot;Purchases&quot; nella tabella di lavoro del flusso di lavoro
1. Arricchimento dei dati importati creando un collegamento a una tabella di riferimento
1. Aggiornamento della tabella &quot;Acquisti&quot; con i dati arricchiti
1. Arricchimento dei dati &quot;Contatti&quot; con un calcolo aggregato dalla tabella &quot;Acquisti&quot;
1. Creazione di un elenco di riepilogo

## Passaggio 1: caricare il file e riconciliare i dati importati {#step-1--loading-the-file-and-reconciling-the-imported-data}

I dati da caricare sono dati relativi all’&quot;acquisto&quot; con il seguente formato:

```
Product Name;Product price;Store
Computer;2000;London 3
Tablet;600;Cambridge
Computer;2000;London 5
Computer;2000;London 8
Tablet;600;Cambridge
Phone;500;London 5
```

Questi dati sono contenuti in un file di testo &quot;Purchases.txt&quot;.

1. Aggiungi le attività **Raccolta file** e **Caricamento dati (file)** al flusso di lavoro.

   L&#39;attività dell&#39;**Agente di raccolta file** consente di raccogliere e inviare file da e al server Adobe Campaign.

   L&#39;attività **Caricamento dati(file)** ti consente di arricchire la tabella di lavoro del flusso di lavoro con i dati raccolti. Per ulteriori informazioni su questa attività, fare riferimento a [Caricamento dati (file)](data-loading-file.md).

1. Configurare l&#39;attività **Raccoglitore file** per raccogliere i file di tipo testo (&#42;.txt) dalla directory selezionata.

   ![Attività dell&#39;agente di raccolta file: scheda Directory con il filtro *.txt e l&#39;opzione di inesistenza del file di processo selezionata.](assets/uc2_enrich_collecteur.png)

   L&#39;attività **Raccoglitore file** consente di gestire l&#39;assenza di un file nella directory di origine. Per eseguire questa operazione, selezionare l&#39;opzione **[!UICONTROL Process file nonexistence]**. In questo flusso di lavoro, è stata aggiunta un&#39;attività **Attendi** per provare un&#39;altra raccolta di file, se non è presente nella directory al momento della raccolta.

1. Configurare l&#39;attività **Caricamento dati (file)** utilizzando un file di esempio con lo stesso formato dei dati da importare.

   ![Attività di caricamento dati (file) con Purchases.txt come file di esempio e un&#39;anteprima di productName, productPrice, storeName.](assets/uc2_enrich_chargement1.png)

   Fare clic sul collegamento **[!UICONTROL Click here to change the file format...]** per rinominare le colonne utilizzando i nomi e le etichette interni della tabella &quot;Purchases&quot;.

   ![Finestra in formato file con colonne productName, productPrice e storeName, separatore punto e virgola e prima riga come intestazione.](assets/uc2_enrich_chargement2.png)

Una volta importati i dati, l’arricchimento viene eseguito creando un collegamento a una tabella di riferimento corrispondente allo schema &quot;Archivi&quot;.

Aggiungi l’attività Enrichment e configurala come segue:

1. Selezionare il set principale costituito dai dati dell&#39;attività **Caricamento dati (file)**.

   ![Attività di arricchimento con caricamento dei dati (file) come set principale, più i collegamenti Aggiungi dati e Modifica dati aggiuntivi.](assets/uc2_enrich_enrich1.png)

1. Fare clic su **[!UICONTROL Add data]**, quindi selezionare l&#39;opzione **[!UICONTROL A link]**.

   ![Selezionare il tipo di dati da aggiungere alla finestra con l&#39;opzione di collegamento A selezionata.](assets/uc2_enrich_enrich2.png)

1. Seleziona l’opzione **[!UICONTROL Define a collection]**.
1. Seleziona lo schema &quot;Archivi&quot; come destinazione.

   ![Definizione collegamento: definire una raccolta selezionata come tipo di collegamento, con lo schema Archivi come schema di destinazione.](assets/uc2_enrich_enrich3.png)

Per ulteriori informazioni sui vari tipi di collegamenti, vedere [Arricchimento e modifica dei dati](targeting-workflows.md#enrich-and-modify-data).

Nella finestra seguente, è necessario creare una condizione di join selezionando il campo di origine (nel set principale) e il campo di destinazione (appartenente allo schema &quot;Archivi&quot;) per configurare la riconciliazione dei dati.

![Condizioni di join della definizione del collegamento corrispondenti al campo di origine storeName con il campo di destinazione refStoreName.](assets/uc2_enrich_enrich4.png)

Ora che il collegamento è stato creato, aggiungeremo una colonna alla tabella di lavoro del flusso di lavoro dallo schema &quot;Archivi&quot;: il campo &quot;Riferimento Codice postale&quot;.

1. Apri l’attività di arricchimento.
1. Fai clic su **[!UICONTROL Edit additional data]**.
1. Aggiungere il campo &quot;Riferimento Codice postale&quot; a **[!UICONTROL Output columns]**.

![Campo di riferimento del codice postale dal collegamento Archivi aggiunto alle colonne Output dell&#39;arricchimento.](assets/uc2_enrich_enrich5.png)

I dati nella tabella di lavoro del flusso di lavoro dopo questo arricchimento saranno i seguenti:

![Dati della tabella di lavoro dopo l&#39;arricchimento, con la colonna Riferimento codice postale accanto a productName, productPrice e storeName.](assets/uc2_enrich_population1.png)

## Passaggio 2: scrittura di dati arricchiti nella tabella &#39;Acquisti&#39; {#step-2--writing-enriched-data-to-the--purchases--table}

Questo passaggio descrive come scrivere i dati importati e arricchiti nella tabella &quot;Purchases&quot;. A tale scopo, è necessario utilizzare un&#39;attività **Aggiorna dati**.

È necessario eseguire una riconciliazione tra i dati nella tabella di lavoro del flusso di lavoro e la dimensione di targeting **Purchases** prima di aggiornare i dati nella tabella **Purchases**.

1. Fare clic sulla scheda **[!UICONTROL Reconciliation]** dell&#39;attività di arricchimento.
1. In questo caso, seleziona la dimensione di targeting, lo schema &quot;Purchases&quot;.
1. Selezionare un&#39;&quot;espressione Source&quot; per i dati nella tabella del flusso di lavoro (in questo caso il campo &quot;storeName&quot;).
1. Selezionare un&#39;&quot;Espressione di destinazione&quot; per i dati nella tabella &quot;Acquisti&quot; (in questo caso il campo &quot;nome dello storename&quot;).
1. Seleziona l’opzione **[!UICONTROL Keep unreconciled data coming from the work table]**.

![Scheda Riconciliazione con la dimensione di targeting Purchases e storeName corrispondenti a @storeName.](assets/uc2_enrich_reconciliation.png)

Nell&#39;attività **Aggiorna dati** è necessaria la seguente configurazione:

1. Selezionare l&#39;opzione **[!UICONTROL Insert or update]** nel campo **[!UICONTROL Operation type]** per evitare la creazione di nuovi record ogni volta che il file viene raccolto.
1. Selezionare il valore **[!UICONTROL By directly using the targeting dimension]** per l&#39;opzione **[!UICONTROL Record identification]**.
1. Selezionare lo schema &quot;Acquisti&quot; come **[!UICONTROL Document type]**.
1. Specifica l’elenco dei campi da aggiornare. La colonna **[!UICONTROL Destination]** consente di definire i campi dello schema &quot;Purchases&quot;. La colonna **[!UICONTROL Expression]** consente di selezionare i campi nella tabella di lavoro per eseguire una mappatura.
1. Fare clic sull&#39;opzione **[!UICONTROL Generate an outbound transition]**.


## Passaggio 3: arricchire i dati dei contatti {#step-3--enriching--contact--data-}

Lo schema &quot;Contatti&quot; è fisicamente collegato allo schema &quot;Acquisti&quot;. Ciò significa che puoi utilizzare un’altra opzione dell’opzione &quot;Enrichment&quot;: aggiungere dati collegati alla dimensione di filtro.

Lo scopo di questo secondo arricchimento è quello di creare un aggregato sullo schema di acquisto per calcolare la quantità totale di acquisti per ciascun contatto identificato.

1. Aggiungi un&#39;attività di tipo **query** che consente di recuperare tutti i **contatti** archiviati.
1. Aggiungi un&#39;attività **Enrichment**, quindi seleziona il set principale risultante dalla query precedente.
1. Fare clic su Aggiungi **[!UICONTROL Data]**.
1. Fare clic sull&#39;opzione **[!UICONTROL Data linked to the targeting dimension]**.
1. Fare clic sull&#39;opzione **[!UICONTROL Data linked to the filtering dimension]** nella finestra **[!UICONTROL Select fields to add]**.
1. Selezionare il nodo **[!UICONTROL Purchases]** e fare clic su **[!UICONTROL Next]**.

   ![Selezionare i campi da aggiungere alla finestra con i dati collegati alla dimensione di filtro selezionata ed evidenziato il nodo Purchases.](assets/uc2_enrich_enrich9.png)

1. Modificare il campo **[!UICONTROL Collected data]** selezionando l&#39;opzione **[!UICONTROL Aggregates]**.

   ![Parametri generali della raccolta Purchases con il campo Data collection impostato su Aggregates.](assets/uc2_enrich_enrich10.png)

1. Fai clic su **[!UICONTROL Next]**.
1. Aggiungi la seguente espressione per calcolare il totale degli acquisti per ciascun contatto: &quot;Sum(@prodprice)&quot;.

   ![Dati da aggiungere nella finestra con l&#39;espressione Somma(prezzo prodotto) definita come colonna di output per gli acquisti totali.](assets/uc2_enrich_enrich6.png)

Per preparare l&#39;elenco di riepilogo, è necessario aggiungere campi dai campi &quot;Purchases&quot; e dal primo arricchimento: il campo &quot;ZipCode Reference&quot;.

1. Fare clic sul collegamento **[!UICONTROL Edit additional data...]** nell&#39;attività di arricchimento.
1. Aggiungi i campi &quot;Nome store&quot; e &quot;Purchases / Zip Code Reference&quot;.

   ![Colonne di output dell&#39;arricchimento 2: collegamento Acquisti, Sum(productPrice), storeName e il campo Riferimento CAP.](assets/uc2_enrich_enrich7.png)

1. Fare clic sulla scheda **[!UICONTROL Properties]**.
1. Modifica il secondo collegamento per creare una sola riga.

## Passaggio 4: creare e aggiungere a un elenco di riepilogo {#step-4--creating-and-adding-to-a-summary-list}

L’ultimo passaggio prevede la scrittura di tutti i dati arricchiti in un elenco.

1. Aggiungi un&#39;attività **Aggiornamento elenco** al flusso di lavoro. Questa attività deve essere collegata alla transizione in uscita della seconda attività di arricchimento.
1. Seleziona l’opzione **[!UICONTROL Create the list if necessary (Calculated name)]**.
1. Selezionare un valore per il nome calcolato. L&#39;etichetta scelta per l&#39;elenco è la data corrente: &lt;%= formatDate(new Date(), &quot;%2D/%2M/%2Y&quot;) %>.

Una volta eseguito il flusso di lavoro, l’elenco include:

* un elenco di contatti,
* una colonna &quot;Acquisti totali&quot;,
* una colonna &quot;Nome del negozio&quot;,
* una colonna &quot;Riferimento codice postale&quot; immessa per tutti gli archivi contenuti nello schema di riferimento dello store.

![Contenuto elenco finale con le colonne Contatti, Somma(prezzoProdotto), Nome store e Codice postale.](assets/uc2_enrich_listfinal.png)
