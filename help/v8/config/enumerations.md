---
title: Gestire le enumerazioni
description: Scopri come utilizzare le enumerazioni
feature: Configuration, Application Settings
role: Developer
version: Campaign v8, Campaign Classic v7
level: Intermediate, Experienced
source-git-commit: 2898fe400e9bf53fc2fe8fde26ccc61ec43bc69e
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 1%

---

# Utilizzare le enumerazioni {#enumerations}

Un’enumerazione (detta anche elenco dettagliato) è un elenco predefinito di valori che è possibile utilizzare per compilare determinati campi. Le enumerazioni consentono di standardizzare i valori dei campi, rendendo più coerente l&#39;immissione dei dati e semplificando le query.

Se disponibili, i valori vengono visualizzati in un elenco a discesa. Puoi selezionare direttamente un valore o iniziare a digitare; l’input predittivo suggerisce i valori corrispondenti e li completa automaticamente.

![](assets/enum_values.png)

Alcuni campi della console sono configurati con enumerazioni. Se un&#39;enumerazione è **open**, è anche possibile aggiungere nuovi valori direttamente nel campo.

![Enumerazioni di accesso](../config/assets/enumerations-menu.png)

## Tipi di enumerazioni {#types-of-enum}

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


## Pulizia alias {#alias-cleansing}

Nei campi di enumerazione è possibile selezionare un valore o immettere un valore personalizzato non disponibile nell&#39;elenco a discesa. È possibile aggiungere valori personalizzati alle enumerazioni esistenti come valori nuovi. In questo caso, è necessario selezionare l&#39;opzione **[!UICONTROL Open]**. Questi valori personalizzati possono essere puliti utilizzando le funzionalità di pulizia degli alias. Ad esempio, se un utente immette `Adob` invece di `Adobe`, il processo di pulizia degli alias può automaticamente sostituirlo con il termine corretto.

>[!CAUTION]
>
>La pulizia dei dati è un processo critico che influisce sui dati presenti nel database. Adobe Campaign esegue aggiornamenti di massa dei dati, che potrebbero causare l’eliminazione di alcuni valori. Questa operazione è pertanto riservata agli utenti esperti.

Abilitare l&#39;opzione **[!UICONTROL Alias cleansing]** per utilizzare le funzionalità di pulizia dati per un&#39;enumerazione. Quando questa opzione è selezionata, nella parte inferiore della finestra viene visualizzata la scheda **[!UICONTROL Alias]**.

Quando un utente immette un valore che non esiste in un&#39;enumerazione di pulizia Alias, questo viene aggiunto all&#39;elenco **Valori**. È possibile [creare alias da questi valori](#convert-to-alias) o [creare nuovi alias da zero](#create-alias).

### Creare un alias{#create-alias}

Per creare un alias, eseguire la procedura seguente:

1. Fare clic sul pulsante **[!UICONTROL Add]** della scheda **[!UICONTROL Alias]**.
1. Immettere l&#39;alias da convertire e selezionare il valore da applicare nell&#39;elenco a discesa.

   ![Crea un nuovo alias](assets/new-alias.png)

1. Fai clic su **[!UICONTROL Ok]** e conferma.

1. Salva le modifiche. La sostituzione dei valori viene eseguita dal flusso di lavoro **Pulizia alias** che viene eseguito ogni notte. Consulta [Eseguire la pulizia dei dati](#running-data-cleansing).

Per tutti i campi basati su questa enumerazione, quando un utente immette il valore **Adobe** in un campo &quot;company&quot; (nella console client di Adobe Campaign, in un modulo web), verrà automaticamente sostituito dal valore **Adobe**.

### Convertire un valore errato in un alias{#convert-to-alias}

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

### Esegui pulizia dati {#running-data-cleansing}

La pulizia dei dati viene eseguita dal flusso di lavoro tecnico **[!UICONTROL Alias cleansing]**. Per impostazione predefinita, viene eseguito su base giornaliera.

La pulizia può essere attivata anche tramite il collegamento **[!UICONTROL Cleanse values...]**.

Il collegamento **[!UICONTROL Advanced parameters...]** consente di impostare la data a partire dalla quale i valori raccolti vengono presi in considerazione.

Fare clic sul pulsante **[!UICONTROL Start]** per eseguire la pulizia dei dati.

### Monitorare le occorrenze {#calculate-entry-occurrences}

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
