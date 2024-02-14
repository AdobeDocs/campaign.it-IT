---
title: Impostazioni dell’interfaccia di Campaign
description: Scopri come personalizzare le impostazioni dell’interfaccia di Campaign
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner
exl-id: 9fa6fc42-45be-41db-9b4a-19b3b0c40dcd
source-git-commit: 09db0cc1a14bffefe8d1b8d0d5a06d5b6517a5bb
workflow-type: tm+mt
source-wordcount: '1848'
ht-degree: 0%

---

# Impostazioni dell’interfaccia utente di Campaign {#ui-settings}

## Unità predefinite {#default-units}

In Adobe Campaign, per i campi che esprimono una durata (ad esempio periodo di validità delle risorse, scadenza dell’approvazione per un’attività, ecc.), i valori possono essere espressi come segue **unità**:

* **[!UICONTROL s]** per secondi
* **[!UICONTROL mn]** per minuti
* **[!UICONTROL h]** per ore
* **[!UICONTROL d]** per giorni

## Personalizzare Campaign Explorer{#customize-explorer}

Puoi aggiungere cartelle a Esplora campagne, creare visualizzazioni e assegnare autorizzazioni.

Scopri come gestire cartelle e visualizzazioni in [questa pagina](../audiences/folders-and-views.md)

## Gestire e personalizzare gli elenchi{#customize-lists}

Nella console client di Campaign, i dati vengono visualizzati in elenchi. È possibile adattare questi elenchi alle proprie esigenze. Ad esempio, puoi aggiungere colonne, filtrare dati, contare record, salvare e condividere le impostazioni.

Inoltre, puoi creare e salvare i filtri.  Ulteriori informazioni sui filtri in [questa pagina](../audiences/create-filters.md).

### Numero di record {#number-of-records}

Per impostazione predefinita, Adobe Campaign carica i primi 200 record di un elenco. Ciò significa che la visualizzazione non mostra necessariamente tutti i record della tabella visualizzata. È possibile eseguire un conteggio del numero di record nell&#39;elenco e caricare altri record.

Nella parte in basso a destra della schermata dell’elenco, **contatore** mostra quanti record sono stati caricati e il numero totale di record nel database (dopo l’applicazione di eventuali filtri):

![Visualizza il numero totale di record in un elenco](assets/number-of-records.png)

Se viene visualizzato un punto interrogativo invece del numero a destra, ad esempio `240/?`, fare clic sul contatore per avviare il calcolo.

Per caricare e visualizzare record aggiuntivi, fare clic su **[!UICONTROL Continue loading]**. Per impostazione predefinita, vengono caricati 200 record. Per modificare il numero predefinito di record da caricare, utilizzare **[!UICONTROL Configure list]** nell’angolo in basso a destra dell’elenco. Nella finestra di configurazione dell’elenco, fai clic su **[!UICONTROL Advanced parameters]** (in basso a sinistra) e cambia il numero di righe da recuperare.

Per caricare tutti i record, fare clic con il pulsante destro del mouse sull&#39;elenco e selezionare **[!UICONTROL Load all]**.

>[!CAUTION]
>
>Quando un elenco contiene un elevato volume di record, il caricamento completo può richiedere un po&#39; di tempo.
>

### Aggiungere e rimuovere colonne {#add-columns}

Per ogni elenco, la configurazione di colonna incorporata può essere adattata per visualizzare ulteriori informazioni o nascondere le colonne non utilizzate.

Quando i dati sono visibili nei dettagli di un record, fare clic con il pulsante destro del mouse sul campo e selezionare **[!UICONTROL Add in the list]**.

![Aggiungere un campo nell&#39;elenco](assets/add-in-the-list.png)

La colonna viene aggiunta a destra delle colonne esistenti.

![Aggiungi una colonna di campo](assets/add-a-column.png)

Puoi anche utilizzare la schermata di configurazione dell’elenco per aggiungere e rimuovere colonne:

1. Da un elenco di record, fare clic su **[!UICONTROL Configure list]** nella sezione in basso a destra.
1. Fare doppio clic sui campi da aggiungere nel **[!UICONTROL Available fields]** : vengono aggiunti al **[!UICONTROL Output columns]** elenco.

   ![Schermata di configurazione elenco](assets/list-config-screen.png)


   >[!NOTE]
   >
   >Per impostazione predefinita, i campi avanzati non vengono visualizzati. Per visualizzarli, fai clic su **Visualizza campi avanzati** nella sezione inferiore destra dell’elenco dei campi disponibili.
   >
   >I campi sono identificati da icone specifiche: campi SQL, tabelle collegate, campi calcolati e così via. Per ogni campo selezionato, la descrizione viene visualizzata nell’elenco dei campi disponibili.
   >

1. Utilizza le frecce su/giù per modificare **ordine di visualizzazione**.

1. Clic **[!UICONTROL OK]** per confermare la configurazione e visualizzare il risultato.

Per rimuovere una colonna, selezionarla e fare clic sul pulsante **Cestino** icona.

È possibile utilizzare **[!UICONTROL Distribution of values]** per visualizzare la ripartizione dei valori per il campo selezionato nella cartella corrente.

![](assets/value-distribution.png)


### Crea una nuova colonna {#create-a-new-column}

È possibile creare nuove colonne per visualizzare ulteriori campi nell&#39;elenco.

Per creare una colonna, effettua le seguenti operazioni:

1. Da un elenco di record, fare clic su **[!UICONTROL Configure list]** nella sezione in basso a destra.
1. Fai clic su **[!UICONTROL Add]** per visualizzare un nuovo campo nell’elenco.
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
1. Clic **[!UICONTROL Advanced settings]** e quindi specifica un nome nel **[!UICONTROL Configuration]** campo.
1. Clic **[!UICONTROL OK]** e quindi fare clic su **[!UICONTROL Save]**.

Puoi quindi applicare questa configurazione a qualsiasi altra cartella dello stesso tipo. Ulteriori informazioni sulle cartelle in [questa pagina](../audiences/folders-and-views.md).

### Esportare un elenco {#exporting-a-list}

Per esportare dati da un elenco, è necessario utilizzare una procedura guidata di esportazione. Per accedervi, seleziona gli elementi da esportare dall’elenco, fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Export...]**.

<!--The use of the import and export functions is explained in [Generic imports and exports](../../platform/using/about-generic-imports-exports.md).-->

>[!CAUTION]
>
>Gli elementi di un elenco non devono essere esportati utilizzando la funzione Copia/Incolla.

### Ordinare un elenco {#sorting-a-list}

Gli elenchi possono contenere una grande quantità di dati. Puoi ordinare questi dati o applicare filtri semplici o avanzati. L’ordinamento consente di visualizzare i dati in ordine crescente o decrescente. I filtri ti consentono di definire e combinare criteri per visualizzare solo i dati selezionati.

Fai clic sull’intestazione della colonna per applicare un ordinamento crescente o decrescente oppure per annullare l’ordinamento dei dati. Lo stato e l’ordinamento attivi sono indicati da una freccia blu prima dell’etichetta della colonna. Un trattino rosso prima dell’etichetta della colonna indica che l’ordinamento viene applicato ai dati indicizzati dal database. Questo metodo di ordinamento viene utilizzato per ottimizzare i processi di ordinamento.

È inoltre possibile configurare criteri di ordinamento o combinare criteri di ordinamento. A questo scopo, segui la procedura indicata di seguito:

1. **[!UICONTROL Configure list]** in basso e a destra dell&#39;elenco.
1. Nella finestra di configurazione dell’elenco, fai clic su **[!UICONTROL Sorting]** scheda.
1. Selezionare i campi da ordinare e la direzione di ordinamento (crescente o decrescente).
1. La priorità di ordinamento è definita dall&#39;ordine delle colonne di ordinamento. Per modificare la priorità, utilizzare le icone appropriate per modificare l&#39;ordine delle colonne.

   La priorità di ordinamento non influisce sulla visualizzazione delle colonne nell’elenco.

1. Clic **[!UICONTROL Ok]** per confermare questa configurazione e visualizzare il risultato nell’elenco.




## Utilizzare le enumerazioni {#enumerations}

Un’enumerazione (nota anche come &quot;elenco dettagliato&quot;) è un elenco di valori suggeriti dal sistema per compilare i campi. Utilizza le enumerazioni per standardizzare i valori di questi campi, aiutarti con l’input di dati o utilizzare all’interno di query.

L&#39;elenco di valori viene visualizzato come elenco a discesa dal quale è possibile selezionare il valore da immettere nel campo. L’elenco a discesa consente inoltre l’input predittivo: inserisci le prime lettere e l’applicazione compila le altre.

I valori per questo tipo di campo sono definiti e l’amministrazione complessiva di questi campi (aggiunta/eliminazione di un valore) viene eseguita tramite **[!UICONTROL Administration > Platform > Enumerations]** dell&#39;albero.

![Enumerazioni di accesso](assets/enumerations-menu.png)

### Tipi di enumerazioni {#types-of-enum}

Le enumerazioni vengono memorizzate in **[!UICONTROL Administration > Platform > Enumerations]** cartella dell&#39;elenco delle cartelle.

Possono essere: Aperto, Sistema, Emoticon o Chiuso.

* Un **Apri** consente agli utenti di aggiungere nuovi valori direttamente nei campi basati su questa enumerazione.
* A **Chiuso** L&#39;enumerazione dispone di un elenco fisso di valori che possono essere modificati solo dal **[!UICONTROL Administration > Platform > Enumerations]** cartella dell&#39;elenco delle cartelle.
* Un **Emoticon** L’enumerazione viene utilizzata per aggiornare l’elenco delle emoticon. Ulteriori informazioni
* A **Sistema** L&#39;enumerazione è associata ai campi di sistema e viene fornita con un nome interno.

Per **Apri** e **Chiuso** enumerazioni, sono disponibili opzioni specifiche:

* **Enumerazione semplice** è il tipo standard predefinito.
* **Pulizia alias** L&#39;enumerazione viene utilizzata per armonizzare i valori di enumerazione memorizzati nel database. [Ulteriori informazioni](#alias-cleansing)
* **Riservato per binning** è un’opzione che consente di collegare i valori del cubo a questa enumerazione. [Ulteriori informazioni](../reporting/gs-cubes.md)


### Pulizia alias {#alias-cleansing}

Nei campi di enumerazione è possibile selezionare un valore o immettere un valore personalizzato non disponibile nell&#39;elenco a discesa. I valori personalizzati possono essere aggiunti ai valori delle enumerazioni esistenti, come valori nuovi, in questo caso **[!UICONTROL Open]** deve essere selezionata. Questi valori personalizzati possono essere puliti utilizzando le funzionalità di pulizia degli alias. Ad esempio, se un utente immette `Adob` invece di `Adobe`, il processo di pulizia degli alias può automaticamente sostituirlo con il termine corretto.

>[!CAUTION]
>
>La pulizia dei dati è un processo critico che influisce sui dati presenti nel database. Adobe Campaign esegue aggiornamenti di massa dei dati, che potrebbero causare l’eliminazione di alcuni valori. Questa operazione è pertanto riservata agli utenti esperti.

Abilita **[!UICONTROL Alias cleansing]** opzione per utilizzare le funzionalità di pulizia dati per un’enumerazione. Quando questa opzione è selezionata, il **[!UICONTROL Alias]** nella parte inferiore della finestra.

Quando un utente immette un valore che non esiste in un’enumerazione di pulizia Alias, questo viene aggiunto al **Valori** elenco. È possibile [crea alias da questi valori](#convert-to-alias), o [creare nuovi alias da zero](#create-alias).

#### Creare un alias{#create-alias}

Per creare un alias, eseguire la procedura seguente:

1. Clic **[!UICONTROL Add]** pulsante della **[!UICONTROL Alias]** scheda.
1. Immettere l&#39;alias da convertire e selezionare il valore da applicare nell&#39;elenco a discesa.

   ![Crea un nuovo alias](assets/new-alias.png)

1. Clic **[!UICONTROL Ok]** e confermare.

1. Salva le modifiche. La sostituzione dei valori viene eseguita da **Pulizia alias** flusso di lavoro che viene eseguito ogni notte. Fai riferimento a [Esegui pulizia dati](#running-data-cleansing).

Per tutti i campi basati su questa enumerazione, quando un utente immette il valore **Adobe** in un campo &quot;azienda&quot; (nella console client di Adobe Campaign, in un modulo web), verrà automaticamente sostituito dal valore **Adobe**.

#### Convertire un valore errato in un alias{#convert-to-alias}

È inoltre possibile convertire un valore di enumerazione esistente in un alias. Per eseguire questa operazione:

1. Nell’elenco dei valori di un’enumerazione, fai clic con il pulsante destro del mouse e individua **[!UICONTROL Actions... > Convert values into aliases...]**.

   ![Convertire un valore in un alias](assets/convert-into-aliases.png)

1. Selezionare i valori da convertire in alias e fare clic su **[!UICONTROL Next]**.
1. Clic **[!UICONTROL Start]** per eseguire la conversione.

   Una volta completata l’esecuzione, gli alias vengono aggiunti all’elenco, nel **Alias** scheda. È possibile associare un valore corretto per sostituire le voci errate. Per eseguire questa operazione:

1. Selezionate un valore da pulire.
1. Fai clic su **Dettagli...** pulsante.
1. Seleziona il nuovo valore nell’elenco a discesa.

   ![Crea un nuovo alias](assets/define-new-alias.png)


>[!NOTE]
>
>È possibile tenere traccia delle occorrenze di un alias nel **[!UICONTROL Hits]** colonna nella **[!UICONTROL Alias]** scheda secondaria. Può visualizzare il numero di volte in cui il valore è stato immesso.  [Ulteriori informazioni](#calculate-entry-occurrences).

#### Esegui pulizia dati {#running-data-cleansing}

La pulizia dei dati viene eseguita da **[!UICONTROL Alias cleansing]** flusso di lavoro tecnico. Per impostazione predefinita, viene eseguito su base giornaliera.

La pulizia può essere attivata anche tramite **[!UICONTROL Cleanse values...]** collegamento.

Il **[!UICONTROL Advanced parameters...]** Questo collegamento ti consente di impostare la data a partire dalla quale i valori raccolti vengono presi in considerazione.

Fai clic su **[!UICONTROL Start]** per eseguire la pulizia dei dati.

##### Monitorare le occorrenze {#calculate-entry-occurrences}

Il **[!UICONTROL Alias]** scheda secondaria di un’enumerazione può visualizzare il numero di occorrenze di un alias tra tutti i valori immessi. Queste informazioni sono una stima e verranno visualizzate nel **[!UICONTROL Hits]** colonna.

>[!CAUTION]
>
>Il calcolo delle occorrenze della voce alias può richiedere molto tempo.
>

Puoi eseguire il calcolo degli hit manualmente tramite **[!UICONTROL Cleanse values...]** collegamento. A questo scopo, fai clic su **[!UICONTROL Advanced parameters...]** collega e seleziona le opzioni.

* **[!UICONTROL Update the number of alias hits]**: questo ti consente di aggiornare gli hit che sono già stati calcolati, in base alla data immessa.
* **[!UICONTROL Recalculate the number of alias hits from the start]**: consente di eseguire calcoli sull’intera piattaforma Adobe Campaign.

Puoi anche creare un flusso di lavoro dedicato per consentire l’esecuzione automatica del calcolo per un determinato periodo, ad esempio una volta alla settimana.

A questo scopo, crea una copia di **[!UICONTROL Alias cleansing]** , modificare la pianificazione e utilizzare le impostazioni seguenti nel **[!UICONTROL Enumeration value cleansing]** attività:

* **-updateHits** per aggiornare il numero di hit alias,
* **-updateHits:completo** per ricalcolare tutti gli hit alias.
