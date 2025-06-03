---
title: Impostazioni dell’interfaccia di Campaign
description: Scopri come personalizzare le impostazioni dell’interfaccia di Campaign
feature: Application Settings
role: Admin, Developer
level: Beginner
exl-id: 9fa6fc42-45be-41db-9b4a-19b3b0c40dcd
source-git-commit: 24ecf598d3d01f7fb59c70e1c8c81e9c086e653e
workflow-type: tm+mt
source-wordcount: '1848'
ht-degree: 1%

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




## Utilizzare le enumerazioni {#enumerations}

Un’enumerazione (nota anche come &quot;elenco dettagliato&quot;) è un elenco di valori suggeriti dal sistema per compilare i campi. Le enumerazioni possono essere utilizzate per standardizzare i valori di tali campi, aiutare con l’input di dati o l’uso all’interno delle query.

L&#39;elenco di valori viene visualizzato come elenco a discesa dal quale è possibile selezionare il valore da immettere nel campo. L’elenco a discesa consente inoltre l’input predittivo: inserisci le prime lettere e l’applicazione compila le altre.

I valori per questo tipo di campo sono definiti e l&#39;amministrazione complessiva di questi campi (aggiunta/eliminazione di un valore) viene eseguita tramite il nodo **[!UICONTROL Administration > Platform > Enumerations]** della struttura.

![Enumerazioni di accesso](assets/enumerations-menu.png)

### Tipi di enumerazioni {#types-of-enum}

Le enumerazioni sono archiviate nella cartella **[!UICONTROL Administration > Platform > Enumerations]** dell&#39;elenco delle cartelle.

Possono essere: Aperto, Sistema, Emoticon o Chiuso.

* Un&#39;enumerazione **Open** consente agli utenti di aggiungere nuovi valori direttamente nei campi basati su questa enumerazione.
* Un&#39;enumerazione **Closed** ha un elenco fisso di valori che possono essere modificati solo dalla cartella **[!UICONTROL Administration > Platform > Enumerations]** dell&#39;Explorer.
* Enumerazione **Emoticon** utilizzata per aggiornare l&#39;elenco delle emoticon. Ulteriori informazioni
* Un&#39;enumerazione **System** è associata ai campi di sistema e viene fornita con un nome interno.

Per le enumerazioni **Open** e **Closed** sono disponibili opzioni specifiche:

* **Enumerazione semplice** è il tipo standard predefinito.
* L&#39;enumerazione **Alias cleansing** viene utilizzata per armonizzare i valori di enumerazione archiviati nel database. [Ulteriori informazioni](#alias-cleansing)
* **Riservato per il binning** è un&#39;opzione che consente di collegare i valori del cubo a questa enumerazione. [Ulteriori informazioni](../reporting/gs-cubes.md)


### Pulizia alias {#alias-cleansing}

Nei campi di enumerazione è possibile selezionare un valore o immettere un valore personalizzato non disponibile nell&#39;elenco a discesa. È possibile aggiungere valori personalizzati alle enumerazioni esistenti come valori nuovi. In questo caso, è necessario selezionare l&#39;opzione **[!UICONTROL Open]**. Questi valori personalizzati possono essere puliti utilizzando le funzionalità di pulizia degli alias. Ad esempio, se un utente immette `Adob` invece di `Adobe`, il processo di pulizia degli alias può automaticamente sostituirlo con il termine corretto.

>[!CAUTION]
>
>La pulizia dei dati è un processo critico che influisce sui dati presenti nel database. Adobe Campaign esegue aggiornamenti di massa dei dati, che potrebbero causare l’eliminazione di alcuni valori. Questa operazione è pertanto riservata agli utenti esperti.

Abilitare l&#39;opzione **[!UICONTROL Alias cleansing]** per utilizzare le funzionalità di pulizia dati per un&#39;enumerazione. Quando questa opzione è selezionata, nella parte inferiore della finestra viene visualizzata la scheda **[!UICONTROL Alias]**.

Quando un utente immette un valore che non esiste in un&#39;enumerazione di pulizia Alias, questo viene aggiunto all&#39;elenco **Valori**. È possibile [creare alias da questi valori](#convert-to-alias) o [creare nuovi alias da zero](#create-alias).

#### Creare un alias{#create-alias}

Per creare un alias, eseguire la procedura seguente:

1. Fare clic sul pulsante **[!UICONTROL Add]** della scheda **[!UICONTROL Alias]**.
1. Immettere l&#39;alias da convertire e selezionare il valore da applicare nell&#39;elenco a discesa.

   ![Crea un nuovo alias](assets/new-alias.png)

1. Fai clic su **[!UICONTROL Ok]** e conferma.

1. Salva le modifiche. La sostituzione dei valori viene eseguita dal flusso di lavoro **Pulizia alias** che viene eseguito ogni notte. Consulta [Eseguire la pulizia dei dati](#running-data-cleansing).

Per tutti i campi basati su questa enumerazione, quando un utente immette il valore **Adobe** in un campo &quot;company&quot; (nella console client di Adobe Campaign, in un modulo web), verrà automaticamente sostituito dal valore **Adobe**.

#### Convertire un valore errato in un alias{#convert-to-alias}

È inoltre possibile convertire un valore di enumerazione esistente in un alias. Per eseguire questa operazione:

1. Nell&#39;elenco dei valori di un&#39;enumerazione, fare clic con il pulsante destro del mouse e selezionare **[!UICONTROL Actions... > Convert values into aliases...]**.

   ![Convertire un valore in un alias](assets/convert-into-aliases.png)

1. Selezionare i valori da convertire in alias e fare clic su **[!UICONTROL Next]**.
1. Fare clic su **[!UICONTROL Start]** per eseguire la conversione.

   Al termine dell&#39;esecuzione, gli alias vengono aggiunti all&#39;elenco nella scheda **Alias**. È possibile associare un valore corretto per sostituire le voci errate. Per eseguire questa operazione:

1. Selezionate un valore da pulire.
1. Fare clic sul pulsante **Dettagli...**.
1. Seleziona il nuovo valore nell’elenco a discesa.

   ![Crea un nuovo alias](assets/define-new-alias.png)


>[!NOTE]
>
>È possibile tenere traccia delle occorrenze di un alias nella colonna **[!UICONTROL Hits]** nella scheda secondaria **[!UICONTROL Alias]**. Può visualizzare il numero di volte in cui il valore è stato immesso.  [Ulteriori informazioni](#calculate-entry-occurrences).

#### Esegui pulizia dati {#running-data-cleansing}

La pulizia dei dati viene eseguita dal flusso di lavoro tecnico **[!UICONTROL Alias cleansing]**. Per impostazione predefinita, viene eseguito su base giornaliera.

La pulizia può essere attivata anche tramite il collegamento **[!UICONTROL Cleanse values...]**.

Il collegamento **[!UICONTROL Advanced parameters...]** consente di impostare la data a partire dalla quale i valori raccolti vengono presi in considerazione.

Fare clic sul pulsante **[!UICONTROL Start]** per eseguire la pulizia dei dati.

##### Monitorare le occorrenze {#calculate-entry-occurrences}

Nella scheda secondaria **[!UICONTROL Alias]** di un&#39;enumerazione è possibile visualizzare il numero di occorrenze di un alias tra tutti i valori immessi. Queste informazioni sono una stima e verranno visualizzate nella colonna **[!UICONTROL Hits]**.

>[!CAUTION]
>
>Il calcolo delle occorrenze della voce alias può richiedere molto tempo.
>

Puoi eseguire il calcolo degli hit manualmente tramite il collegamento **[!UICONTROL Cleanse values...]**. A questo scopo, fai clic sul collegamento **[!UICONTROL Advanced parameters...]** e seleziona le opzioni.

* **[!UICONTROL Update the number of alias hits]**: consente di aggiornare gli hit già calcolati in base alla data immessa.
* **[!UICONTROL Recalculate the number of alias hits from the start]**: consente di eseguire calcoli sull&#39;intera piattaforma Adobe Campaign.

Puoi anche creare un flusso di lavoro dedicato per consentire l’esecuzione automatica del calcolo per un determinato periodo, ad esempio una volta alla settimana.

Per eseguire questa operazione, creare una copia del flusso di lavoro **[!UICONTROL Alias cleansing]**, modificare la pianificazione e utilizzare le impostazioni seguenti nell&#39;attività **[!UICONTROL Enumeration value cleansing]**:

* **-updateHits** per aggiornare il numero di hit alias,
* **-updateHits:full** per ricalcolare tutti gli hit alias.
