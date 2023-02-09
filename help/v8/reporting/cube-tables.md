---
product: campaign
title: Utilizzare i cubi per creare rapporti sui dati
description: Scopri come utilizzare i cubi per creare rapporti
feature: Reporting
exl-id: 7dbc66ab-a468-40ff-9db2-b33e4fd27754
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '941'
ht-degree: 1%

---

# Usare i cubi per esplorare i dati{#use-cubes-to-create-reports}

Utilizza i cubi per creare rapporti e per identificare e selezionare i dati dal database. È possibile eseguire le seguenti operazioni:

* Crea report basati su cubi. [Ulteriori informazioni](#explore-the-data-in-a-report).
* Raccogliere i dati nel database e raggrupparli in elenchi, ad esempio per identificare e creare destinazioni e consegne. [Ulteriori informazioni](#build-a-target-population).
* Inserire una tabella pivot in un report, fare riferimento a un cubo esistente al suo interno. [Ulteriori informazioni](#insert-a-pivot-table-into-a-report).

## Esplorare i dati in un rapporto {#explore-the-data-in-a-report}

### Passaggio 1: creare un report basato su un cubo {#step-1---create-a-report-based-on-a-cube}

Una volta che [cubo configurato](cube-indicators.md), può essere utilizzato come modello per creare un nuovo rapporto.

Per creare un report basato su un cubo esistente, segui i passaggi seguenti:

1. Fai clic sul pulsante **[!UICONTROL Create]** pulsante **[!UICONTROL Reports]** e selezionare il cubo appena creato.

   ![](assets/new-report-based-on-cube.png)

1. Fai clic sul pulsante **[!UICONTROL Create]** pulsante per confermare: questo ti porterà alla configurazione del report e alla pagina di visualizzazione.

   Per impostazione predefinita, le prime due dimensioni disponibili sono offerte in righe e colonne, ma non viene visualizzato alcun valore nella tabella. Per generare la tabella, fai clic sull’icona principale:

   ![](assets/cube-report-config.png)

1. Potete cambiare gli assi della dimensione, eliminarli, aggiungere nuove misure, ecc. A questo scopo, utilizza le icone appropriate.

   ![](assets/cube-switch-axis.png)

   Queste operazioni sono descritte in dettaglio di seguito.

### Passaggio 2: selezionare linee e colonne {#step-2---select-lines-and-columns}

La visualizzazione predefinita mostra le prime due dimensioni del cubo (età e città, in questo caso).

La **[!UICONTROL Add]** i pulsanti su ciascun asse consentono di aggiungere dimensioni.

![](assets/cube-switch.png)

1. Selezionare le dimensioni da visualizzare nelle righe e nelle colonne della tabella. A questo scopo, trascina e rilascia le dimensioni disponibili.
1. Seleziona dall’elenco le dimensioni da aggiungere alla tabella:
   ![](assets/cube-select-dimension.png)

1. Quindi seleziona i parametri di questa dimensione.

   ![](assets/cube-dimension-param.png)

   Questi parametri dipendono dal tipo di dati della dimensione selezionata.

   Ad esempio, per le date, possono essere disponibili diversi livelli. Per ulteriori informazioni, consulta [Misure di visualizzazione](customize-cubes.md#display-measures).

   In tal caso, sono disponibili le seguenti opzioni:

   ![](assets/cube-config.png)

   Puoi effettuare le seguenti operazioni:

   * Espandi i dati durante il caricamento: i valori verranno visualizzati per impostazione predefinita ogni volta che il rapporto viene aggiornato (valore predefinito: no).
   * Visualizza il totale alla fine della riga: quando i dati vengono visualizzati in colonne, un’opzione aggiuntiva consente di visualizzare il totale alla fine della riga: alla tabella viene aggiunta una colonna (valore predefinito: sì).
   * Applica un ordinamento: i valori della colonna possono essere ordinati in base al valore, all’etichetta o a una misura (valore predefinito: per valore).
   * Visualizza i valori in ordine crescente (a-z, 0-9) o decrescente (z-a, 9-0).
   * Modifica il numero di colonne da visualizzare al caricamento (per impostazione predefinita: 200).

1. Fai clic su **[!UICONTROL Ok]** per confermare: la dimensione viene aggiunta alle dimensioni esistenti.

   Il banner giallo sopra la tabella indica che sono state apportate modifiche: fai clic su **[!UICONTROL Save]** per salvarli.

   ![](assets/cube-in-report.png)

### Passaggio 3: configurare le misure da visualizzare {#step-3---configure-the-measures-to-display}

Una volta definite le linee e le colonne, selezionare le misure da visualizzare. Per impostazione predefinita viene visualizzata una sola misura.

Per aggiungere e configurare le misure, segui i passaggi seguenti:

1. Fai clic sul pulsante **[!UICONTROL Measures]**.

   ![](assets/cube-measure-button.png)

1. Con la **[!UICONTROL Use a measure]** selezionare una delle misure esistenti.

   ![](assets/cube-add-measure.png)

   Scegliere le informazioni da visualizzare e le opzioni di formattazione. L’elenco delle opzioni dipende dal tipo di misura.

   ![](assets/cube-measure-options.png)

   La configurazione complessiva delle misure è disponibile anche tramite **[!UICONTROL Edit the configuration of the pivot table]** nell’intestazione.

   ![](assets/cube-pivot-table-config.png)

   È quindi possibile scegliere se visualizzare o meno le etichette delle misure. [Ulteriori informazioni](customize-cubes.md#configure-the-display).

1. Puoi creare nuove misure basate su quelle esistenti. A questo scopo, fai clic su **[!UICONTROL Create a measure]** e configuralo.

   ![](assets/cube-create-new-measure.png)

   Sono disponibili i seguenti tipi di misure:

   * Combinazione di misure: questo tipo di misura consente di creare la nuova misura utilizzando quelle esistenti:

      Gli operatori disponibili sono: somma, differenza, moltiplicazione e tasso.

   * Proporzione: questo tipo di misura consente di calcolare il numero di record misurati per una determinata dimensione. Puoi calcolare la proporzionalità in base a una dimensione o a una dimensione secondaria.
   * Variazione: questa misura consente di calcolare la variazione dei valori di un livello.
   * Deviazione standard: questo tipo di misura consente di calcolare le deviazioni all’interno di ciascun gruppo di celle rispetto alla media dei valori. Ad esempio, puoi confrontare il volume di acquisto per tutti i segmenti esistenti.

   Una volta creata, la misura viene aggiunta al rapporto.

   ![](assets/cube-display-new-measure.png)

   Dopo aver creato una misura, puoi modificarla e modificarne la configurazione. A questo scopo, fai clic sul pulsante **[!UICONTROL Measures]** quindi passare alla scheda della misura da modificare.

   Quindi fai clic su **[!UICONTROL Edit the dynamic measure]** per accedere al menu impostazioni.

## Creare una popolazione target {#build-a-target-population}

La generazione di rapporti tramite cubi consente di raccogliere i dati dalla tabella e salvarli in un elenco.

Per raggruppare una popolazione in un elenco, effettua le seguenti operazioni:

1. Fai clic sulle celle che contengono la popolazione da raccogliere per selezionarle, quindi fai clic sul pulsante **[!UICONTROL Add to cart]** icona.

   ![](assets/cube-add-to-cart.png)

   A questo scopo il numero di volte necessario per raccogliere vari profili

1. Fai clic sul pulsante **[!UICONTROL Show cart]** per visualizzarne il contenuto prima di eseguire l’esportazione.

   ![](assets/cube-show-cart.png)

1. Utilizza la **[!UICONTROL Export]** per raggruppare gli elementi nel carrello in un elenco.

   Immettere il nome dell’elenco e selezionare il tipo di esportazione da eseguire.

   ![](assets/cube-export-report.png)

   Fai clic su **[!UICONTROL Start]** per eseguire l&#39;esportazione.

1. Una volta completata l’esportazione, un messaggio conferma la relativa esecuzione e il numero di record elaborati.

   ![](assets/cube-export-confirm.png)

   Puoi salvare il contenuto del carrello o svuotarlo.

   Il nuovo elenco è disponibile tramite **[!UICONTROL Profiles and targets]** scheda .

   ![](assets/cube-list-available.png)

## Inserire una tabella pivot in un report {#insert-a-pivot-table-into-a-report}

Per creare una tabella ed esplorare i dati in un cubo, segui i passaggi seguenti:

1. Crea un nuovo report con una singola pagina e inserisci una tabella pivot.

   ![](assets/cube-insert-in-report.png)

1. In **[!UICONTROL Data]** scheda della pagina, selezionare un cubo per elaborare le dimensioni che contiene e visualizzare le misure calcolate.

   ![](assets/cube-selected-in-report.png)

   In questo modo puoi creare il rapporto da visualizzare. Per ulteriori informazioni, consulta [Passaggio 2: selezionare linee e colonne](#step-2---select-lines-and-columns).
