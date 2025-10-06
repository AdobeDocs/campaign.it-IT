---
title: Impostazioni dell’interfaccia di Campaign
description: Scopri come personalizzare le impostazioni dell’interfaccia di Campaign
feature: Application Settings
role: Admin, Developer
level: Beginner
exl-id: 9fa6fc42-45be-41db-9b4a-19b3b0c40dcd
source-git-commit: fbde111671fb972f6c96ba45eba4c8a88dbcac64
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 0%

---

# Impostazioni dell’interfaccia utente di Campaign {#ui-settings}

## Unità predefinite {#default-units}

In Adobe Campaign, per i campi che esprimono una durata (ad esempio periodo di validità delle risorse, scadenza dell&#39;approvazione per un&#39;attività, ecc.), i valori possono essere espressi nelle seguenti **unità**:

* **[!UICONTROL s]** per secondi
* **[!UICONTROL mn]** per minuti
* **[!UICONTROL h]** per ore
* **[!UICONTROL d]** per giorni

## Personalizzare Campaign Explorer{#customize-explorer}

Puoi aggiungere cartelle a Esplora campagne, creare visualizzazioni e assegnare autorizzazioni.

Scopri come gestire cartelle e visualizzazioni in [questa pagina](../audiences/folders-and-views.md)

## Gestire e personalizzare gli elenchi {#customize-lists}

Nella console client di Campaign, i dati vengono visualizzati in elenchi. È possibile adattare questi elenchi alle proprie esigenze. Ad esempio, puoi aggiungere colonne, filtrare dati, contare record, salvare e condividere le impostazioni.

Inoltre, puoi creare e salvare i filtri.  Ulteriori informazioni sui filtri in [questa pagina](../audiences/create-filters.md).

### Numero di record {#number-of-records}

Per impostazione predefinita, Adobe Campaign carica i primi 200 record di un elenco. Ciò significa che la visualizzazione non mostra necessariamente tutti i record della tabella visualizzata. È possibile eseguire un conteggio del numero di record nell&#39;elenco e caricare altri record.

Nella parte in basso a destra della schermata dell&#39;elenco, un **contatore** mostra quanti record sono stati caricati e il numero totale di record nel database (dopo l&#39;applicazione di filtri):

![Visualizza il numero totale di record in un elenco](assets/number-of-records.png)

Se viene visualizzato un punto interrogativo invece del numero a destra, ad esempio `240/?`, fare clic sul contatore per avviare il calcolo.

Per caricare e visualizzare record aggiuntivi, fare clic su **[!UICONTROL Continue loading]**. Per impostazione predefinita, vengono caricati 200 record. Per modificare il numero predefinito di record da caricare, utilizzare l&#39;icona **[!UICONTROL Configure list]** nell&#39;angolo inferiore destro dell&#39;elenco. Nella finestra di configurazione dell&#39;elenco, fare clic su **[!UICONTROL Advanced parameters]** (in basso a sinistra) e modificare il numero di righe da recuperare.

Per caricare tutti i record, fare clic con il pulsante destro del mouse sull&#39;elenco e selezionare **[!UICONTROL Load all]**.

>[!CAUTION]
>
>Quando un elenco contiene un elevato volume di record, il caricamento completo può richiedere un po&#39; di tempo.
>

### Aggiungere e rimuovere colonne {#add-columns}

Per ogni elenco, la configurazione di colonna incorporata può essere adattata per visualizzare ulteriori informazioni o nascondere le colonne non utilizzate.

Quando i dati sono visibili nel dettaglio di un record, fare clic con il pulsante destro del mouse sul campo e selezionare **[!UICONTROL Add in the list]**.

![Aggiungere un campo nell&#39;elenco](assets/add-in-the-list.png)

La colonna viene aggiunta a destra delle colonne esistenti.

![Aggiungi una colonna di campo](assets/add-a-column.png)

Puoi anche utilizzare la schermata di configurazione dell’elenco per aggiungere e rimuovere colonne:

1. Da un elenco di record, fare clic sull&#39;icona **[!UICONTROL Configure list]** nella sezione in basso a destra.
1. Fare doppio clic sui campi da aggiungere all&#39;elenco **[!UICONTROL Available fields]**: verranno aggiunti all&#39;elenco **[!UICONTROL Output columns]**.

   ![Schermata di configurazione elenco](assets/list-config-screen.png)


   >[!NOTE]
   >
   >Per impostazione predefinita, i campi avanzati non vengono visualizzati. Per visualizzarli, fare clic sull&#39;icona **Visualizza campi avanzati** nella sezione inferiore destra dell&#39;elenco dei campi disponibili.
   >
   >I campi sono identificati da icone specifiche: campi SQL, tabelle collegate, campi calcolati e così via. Per ogni campo selezionato, la descrizione viene visualizzata nell’elenco dei campi disponibili.
   >

1. Utilizza le frecce su/giù per modificare l&#39;**ordine di visualizzazione**.

1. Fare clic su **[!UICONTROL OK]** per confermare la configurazione e visualizzare il risultato.

Se devi rimuovere una colonna, selezionala e fai clic sull&#39;icona **Elimina**.

È possibile utilizzare l&#39;icona **[!UICONTROL Distribution of values]** per visualizzare la partizione dei valori per il campo selezionato nella cartella corrente.

![](assets/value-distribution.png)


### Crea una nuova colonna {#create-a-new-column}

È possibile creare nuove colonne per visualizzare ulteriori campi nell&#39;elenco.

Per creare una colonna, effettua le seguenti operazioni:

1. Da un elenco di record, fare clic sull&#39;icona **[!UICONTROL Configure list]** nella sezione in basso a destra.
1. Fare clic sull&#39;icona **[!UICONTROL Add]** per visualizzare un nuovo campo nell&#39;elenco.
1. Configura il campo da aggiungere nella colonna.


### Visualizza dati in sottocartelle {#display-sub-folders-records}

Gli elenchi possono essere visualizzati:

* Tutti i record contenuti nella cartella selezionata (impostazione predefinita)
* Tutti i record contenuti nella cartella selezionata e nelle relative sottocartelle

Per passare da una modalità di visualizzazione all&#39;altra, fare clic su **[!UICONTROL Display sub-levels]** nella barra degli strumenti di Campaign.

### Salvare una configurazione elenco {#saving-a-list-configuration}

Le configurazioni dell’elenco sono definite localmente per ogni utente. Quando la cache locale viene cancellata, le configurazioni locali vengono disabilitate.

Per impostazione predefinita, i parametri di impostazione si applicano a tutti gli elenchi con il tipo di cartella corrispondente. Quando modifichi la modalità di visualizzazione dell’elenco dei destinatari da una cartella, questa configurazione viene applicata a tutte le altre cartelle dei destinatari.

È possibile salvare più configurazioni da applicare a cartelle diverse dello stesso tipo. La configurazione viene salvata con le proprietà della cartella contenente i dati e può essere riapplicata.

Per salvare una configurazione di elenco in modo che possa essere riutilizzata, effettua le seguenti operazioni:

1. In Esplora risorse fare clic con il pulsante destro del mouse sulla cartella contenente i dati visualizzati.
1. Seleziona **[!UICONTROL Properties]**.
1. Fare clic su **[!UICONTROL Advanced settings]** e quindi specificare un nome nel campo **[!UICONTROL Configuration]**.
1. Fare clic su **[!UICONTROL OK]** e quindi su **[!UICONTROL Save]**.

Puoi quindi applicare questa configurazione a qualsiasi altra cartella dello stesso tipo. Ulteriori informazioni sulle cartelle in [questa pagina](../audiences/folders-and-views.md).

### Esportare un elenco {#exporting-a-list}

Per esportare dati da un elenco, è necessario utilizzare una procedura guidata di esportazione. Per accedervi, selezionare gli elementi da esportare dall&#39;elenco, fare clic con il pulsante destro del mouse e selezionare **[!UICONTROL Export...]**.

<!--The use of the import and export functions is explained in [Generic imports and exports](../../platform/using/about-generic-imports-exports.md).-->

>[!CAUTION]
>
>Gli elementi di un elenco non devono essere esportati utilizzando la funzione Copia/Incolla.

### Ordinare un elenco {#sorting-a-list}

Gli elenchi possono contenere una grande quantità di dati. Puoi ordinare questi dati o applicare filtri semplici o avanzati. L’ordinamento consente di visualizzare i dati in ordine crescente o decrescente. I filtri ti consentono di definire e combinare criteri per visualizzare solo i dati selezionati.

Fai clic sull’intestazione della colonna per applicare un ordinamento crescente o decrescente oppure per annullare l’ordinamento dei dati. Lo stato e l’ordinamento attivi sono indicati da una freccia blu prima dell’etichetta della colonna. Un trattino rosso prima dell’etichetta della colonna indica che l’ordinamento viene applicato ai dati indicizzati dal database. Questo metodo di ordinamento viene utilizzato per ottimizzare i processi di ordinamento.

È inoltre possibile configurare criteri di ordinamento o combinare criteri di ordinamento. A questo scopo, segui la procedura indicata di seguito:

1. **[!UICONTROL Configure list]** di seguito e a destra dell&#39;elenco.
1. Nella finestra di configurazione dell&#39;elenco fare clic sulla scheda **[!UICONTROL Sorting]**.
1. Selezionare i campi da ordinare e la direzione di ordinamento (crescente o decrescente).
1. La priorità di ordinamento è definita dall&#39;ordine delle colonne di ordinamento. Per modificare la priorità, utilizzare le icone appropriate per modificare l&#39;ordine delle colonne.

   La priorità di ordinamento non influisce sulla visualizzazione delle colonne nell’elenco.

1. Fare clic su **[!UICONTROL Ok]** per confermare questa configurazione e visualizzare il risultato nell&#39;elenco.


## Risorse aggiuntive

* **[Inizia con l&#39;interfaccia utente di Campaign](../start/campaign-ui.md)**: scopri come accedere all&#39;interfaccia di Adobe Campaign e come esplorarla.
* **[Operazioni con le enumerazioni](../dev/enumerations.md)** - Standardizzazione dei valori dei campi con elenchi a discesa predefiniti per un&#39;immissione più rapida e coerente dei dati.
