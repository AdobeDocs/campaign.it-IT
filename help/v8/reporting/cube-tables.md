---
product: campaign
title: Utilizzare i cubi per creare rapporti sui dati
description: Scopri come utilizzare i cubi per creare rapporti
feature: Reporting
role: User, Developer
level: Beginner
exl-id: 7dbc66ab-a468-40ff-9db2-b33e4fd27754
TQID: 'https://experienceleague.adobe.com/fVo8tGw-kPgGgB7djOQr8tv5MoRvrPr-MF2bzYYKDgI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 82ae202007873dab2324bfa4b13a6014efd19887
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 1%
---
# Usare i cubi per esplorare i dati{#use-cubes-to-create-reports}

Utilizza i cubi per creare rapporti e per identificare e selezionare dati dal database. Puoi eseguire le seguenti azioni:

* Crea rapporti basati su cubi. [Ulteriori informazioni](#explore-the-data-in-a-report).
* Raccogli i dati nel database e raggruppali in elenchi, ad esempio per identificare e creare destinazioni e consegne. [Ulteriori informazioni](#build-a-target-population).
* Inserire una tabella pivot in un report, fare riferimento a un cubo esistente al suo interno. [Ulteriori informazioni](#insert-a-pivot-table-into-a-report).

## Esplorare i dati in un rapporto {#explore-the-data-in-a-report}

### Passaggio 1: creare un rapporto basato su un cubo {#step-1---create-a-report-based-on-a-cube}

Una volta configurato il cubo [&#128279;](cube-indicators.md), è possibile utilizzarlo come modello per la creazione di un nuovo report.

Per creare un report basato su un cubo esistente, effettuare le seguenti operazioni:

1. Fare clic sul pulsante **[!UICONTROL Create]** della scheda **[!UICONTROL Reports]** e selezionare il cubo appena creato.

   ![Creazione di una nuova pagina di report con il modello di cubo Nuovo profilo client selezionato e il pulsante Crea](assets/new-report-based-on-cube.png)

1. Fare clic sul pulsante **[!UICONTROL Create]** per confermare: verrà visualizzata la pagina Configurazione e visualizzazione del report.

   Per impostazione predefinita, le prime due dimensioni disponibili sono offerte in linee e colonne, ma nella tabella non viene visualizzato alcun valore. Per generare la tabella, fai clic sull’icona principale:

   ![Nuovo report Profilo client con assi di età e data di creazione e l&#39;icona per visualizzare la tabella pivot](assets/cube-report-config.png)

1. Potete cambiare gli assi della quota, eliminarli, aggiungere nuove misure e così via. A questo scopo, utilizza le icone appropriate.

   ![Dimensione data di creazione trascinata dall&#39;asse sinistro all&#39;asse superiore accanto a Età nel report Nuovo profilo client](assets/cube-switch-axis.png)

   Tali operazioni sono descritte di seguito.

### Passaggio 2: selezionare righe e colonne {#step-2---select-lines-and-columns}

La visualizzazione predefinita mostra le prime due dimensioni del cubo (età e città, in questo caso).

I pulsanti **[!UICONTROL Add]** su ciascun asse consentono di aggiungere dimensioni.

![Pulsante Aggiungi sull&#39;asse delle righe del report Nuovo profilo client per l&#39;aggiunta di una dimensione](assets/cube-switch.png)

1. Selezionate le quote da visualizzare nelle linee e nelle colonne della tabella. A questo scopo, trascina e rilascia le dimensioni disponibili.
1. Seleziona dall’elenco le dimensioni da aggiungere alla tabella:
   ![Aggiungi una dimensione alla finestra di dialogo della colonna in cui sono elencati Città, Paese, Data ultimo acquisto e Importo acquisti](assets/cube-select-dimension.png)

1. Selezionate quindi i parametri di questa quota.

   ![Impostazioni Dimension per Città: Etichetta, Espandi durante il caricamento, Ordina dati, ordine e numero di righe visualizzate](assets/cube-dimension-param.png)

   Questi parametri dipendono dal tipo di dati della dimensione selezionata.

   Ad esempio, per le date, possono essere disponibili diversi livelli. Per ulteriori informazioni, consulta [Misure di visualizzazione](customize-cubes.md#display-measures).

   In tal caso, sono disponibili le seguenti opzioni:

   ![Impostazioni dimensione data per livello, anno e mese, incluso formato lungo o breve](assets/cube-config.png)

   Puoi effettuare le seguenti operazioni:

   * Espandi dati durante il caricamento: i valori vengono visualizzati per impostazione predefinita a ogni aggiornamento del rapporto (valore predefinito: no).
   * Visualizzare il totale alla fine della riga: quando i dati vengono visualizzati in colonne, un’opzione aggiuntiva consente di visualizzare il totale alla fine della riga: viene aggiunta una colonna alla tabella (valore predefinito: yes).
   * Applica un ordinamento: i valori della colonna possono essere ordinati in base al valore, all’etichetta o a una misura (valore predefinito: per valore).
   * Visualizza i valori in ordine crescente (a-z, 0-9) o decrescente (z-a, 9-0).
   * Modifica il numero di colonne da visualizzare al caricamento (per impostazione predefinita: 200).

1. Fare clic su **[!UICONTROL Ok]** per confermare: la dimensione viene aggiunta alle dimensioni esistenti.

   Il banner giallo sopra la tabella mostra che sono state apportate modifiche: fai clic sul pulsante **[!UICONTROL Save]** per salvarle.

   ![Città aggiunta all&#39;asse delle righe, con il banner giallo che richiede di salvare le modifiche del report](assets/cube-in-report.png)

### Passaggio 3: configurare le misure da visualizzare {#step-3---configure-the-measures-to-display}

Una volta definite le linee e le colonne, selezionare le misure da visualizzare. Per impostazione predefinita, viene visualizzata una sola misura.

Per aggiungere e configurare le misure, attieniti alla procedura seguente:

1. Fai clic sul pulsante **[!UICONTROL Measures]**.

   ![Pulsante Misure che apre la finestra di dialogo Configura misure con le opzioni Etichetta, Formattazione e Unità](assets/cube-measure-button.png)

1. Con il pulsante **[!UICONTROL Use a measure]**, selezionare una delle misure esistenti.

   ![Aggiungi una misura esistente alla finestra di dialogo della tabella pivot in cui sono elencati francese, tedesco, uomini e donne](assets/cube-add-measure.png)

   Scegliere le informazioni da visualizzare e le opzioni di formattazione. L’elenco delle opzioni dipende dal tipo di misura.

   ![Finestra di dialogo Configura misure con le opzioni di formattazione Numero e percentuale e Modifica il pulsante di misura dinamico](assets/cube-measure-options.png)

   La configurazione generale delle misure è disponibile anche tramite l&#39;icona **[!UICONTROL Edit the configuration of the pivot table]** nell&#39;intestazione.

   ![Modifica l&#39;icona di configurazione della tabella pivot nella barra degli strumenti del report](assets/cube-pivot-table-config.png)

   È quindi possibile scegliere se visualizzare o meno le etichette delle misure. [Ulteriori informazioni](customize-cubes.md#configuring-the-display).

1. Puoi creare nuove misure in base a quelle esistenti. A tale scopo, fare clic su **[!UICONTROL Create a measure]** e configurarlo.

   ![Creazione di una finestra di dialogo di misura dinamica con la combinazione di tipo di misure, operatore e due misure](assets/cube-create-new-measure.png)

   Sono disponibili i seguenti tipi di misure:

   * Combinazione di misure: questo tipo di misura consente di creare la nuova misura utilizzando quelle esistenti:

     Gli operatori disponibili sono: somma, differenza, moltiplicazione e tasso.

   * Proporzione: questo tipo di misura consente di calcolare il numero di record misurati per una determinata dimensione. Puoi calcolare la proporzionalità in base a una dimensione o a una dimensione secondaria.
   * Variante: questa misura consente di calcolare la variazione dei valori di un livello.
   * Deviazione standard: questo tipo di misura consente di calcolare le deviazioni all&#39;interno di ogni gruppo di celle rispetto alla media dei valori. Ad esempio, puoi confrontare il volume di acquisto per tutti i segmenti esistenti.

   Una volta creata, la misura viene aggiunta al rapporto.

   ![Tabella pivot che mostra la nuova misura in tedesco e inglese accanto a Uomini e donne, per società](assets/cube-display-new-measure.png)

   Dopo aver creato una misura, potete modificarla e modificarne la configurazione. A tale scopo, fare clic sul pulsante **[!UICONTROL Measures]**, quindi passare alla scheda della misura da modificare.

   Quindi fare clic su **[!UICONTROL Edit the dynamic measure]** per accedere al menu delle impostazioni.

## Creare una popolazione target {#build-a-target-population}

I rapporti creati utilizzando cubi consentono di raccogliere dati dalla tabella e salvarli in un elenco.

Per raggruppare una popolazione in un elenco, effettua le seguenti operazioni:

1. Fare clic sulle celle che contengono la popolazione da raccogliere per selezionarle, quindi fare clic sull&#39;icona **[!UICONTROL Add to cart]**.

   ![Icona Aggiungi al carrello nella barra degli strumenti della tabella pivot CLIENT con celle selezionate](assets/cube-add-to-cart.png)

   Esegui questa operazione tutte le volte necessarie per raccogliere vari profili.

1. Fare clic sul pulsante **[!UICONTROL Show cart]** per visualizzarne il contenuto prima di eseguire l&#39;esportazione.

   ![Mostra pulsante carrello all&#39;apertura della finestra di dialogo dei dettagli del carrello con gli elementi del carrello e il pulsante Esporta](assets/cube-show-cart.png)

1. Utilizza il pulsante **[!UICONTROL Export]** per raggruppare gli elementi nel carrello in un elenco.

   Immettere il nome dell&#39;elenco e selezionare il tipo di esportazione da eseguire.

   ![Finestra di dialogo Esporta carrello 1/2 con esportazione in un nuovo elenco, Etichetta, Cartella e Tipo di esportazione e pulsante Start](assets/cube-export-report.png)

   Fare clic su **[!UICONTROL Start]** per eseguire l&#39;esportazione.

1. Una volta completata l’esportazione, un messaggio conferma l’esecuzione e il numero di record elaborati.

   ![Finestra di dialogo Esporta carrello 2/2 che conferma il completamento dell&#39;esportazione con il numero di record e i pulsanti Chiudi](assets/cube-export-confirm.png)

   Puoi salvare il contenuto del carrello o svuotarlo.

   Il nuovo elenco è disponibile tramite la scheda **[!UICONTROL Profiles and targets]**.

   ![Pagina Elenca profili e destinazioni con il nuovo elenco destinatari GOLD](assets/cube-list-available.png)

## Inserire una tabella pivot in un report {#insert-a-pivot-table-into-a-report}

Per creare una tabella ed esplorare i dati in un cubo, effettuare le seguenti operazioni:

1. Crea un nuovo rapporto con una singola pagina e inserisci una tabella pivot al suo interno.

   ![Editor di rapporti con un&#39;attività di pagina e l&#39;opzione Tabella pivot nel menu della barra degli strumenti](assets/cube-insert-in-report.png)

1. Nella scheda **[!UICONTROL Data]** della pagina, selezionare un cubo per elaborare le dimensioni in esso contenute e visualizzare le misure calcolate.

   ![Scheda dati della tabella pivot con il cubo Nuovo profilo client selezionato nel campo Cubo](assets/cube-selected-in-report.png)

   Questo ti consente di creare il rapporto da visualizzare. Per ulteriori informazioni, consulta [Passaggio 2 - Selezionare righe e colonne](#step-2---select-lines-and-columns).
