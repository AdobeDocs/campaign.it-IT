---
title: Impostazioni dell’interfaccia di Campaign
description: Scopri come personalizzare le impostazioni dell’interfaccia di Campaign
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner, Intermediate, Experienced
source-git-commit: 0b4483e0f16f14582a1a4bc28b0e1ff719823ef3
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 1%

---

# Impostazioni dell’interfaccia utente di Campaign {#ui-settings}

## Enumerazioni {#enumerations}

Un’enumerazione (nota anche come &quot;elenco dettagliato&quot;) è un elenco di valori suggeriti dal sistema per compilare i campi. Utilizza le enumerazioni per standardizzare i valori di questi campi, aiuto con l’input di dati o utilizzo all’interno delle query.

L’elenco dei valori viene visualizzato come elenco a discesa dal quale è possibile selezionare il valore da immettere nel campo. L’elenco a discesa abilita anche l’input predittivo: inserire le prime lettere e l&#39;applicazione riempie il resto.

I valori per questo tipo di campo sono definiti e l’amministrazione complessiva di questi campi (aggiunta/eliminazione di un valore) viene eseguita tramite la **[!UICONTROL Administration > Platform > Enumerations]** nodo dell&#39;albero.

![Enumerazione degli accessi](assets/enumerations-menu.png)

### Tipi di enumerazioni {#types-of-enum}

Le enumerazioni sono memorizzate nel **[!UICONTROL Administration > Platform > Enumerations]** cartella dell&#39;esploratore.

Possono essere: Aperto, Sistema, Emoticon o Chiuso.

* Un **Apri** l’enumerazione consente agli utenti di aggiungere nuovi valori direttamente nei campi in base a questa enumerazione.
* A **Chiuso** l&#39;enumerazione ha un elenco fisso di valori che possono essere modificati solo dal **[!UICONTROL Administration > Platform > Enumerations]** cartella dell&#39;esploratore.
* Un **Emoticon** l’enumerazione viene utilizzata per aggiornare l’elenco di emoticon. Ulteriori informazioni
* A **Sistema** l&#39;enumerazione è associata ai campi di sistema ed è in arrivo con un nome interno.

Per **Apri** e **Chiuso** enumerazioni, sono disponibili opzioni specifiche:

* **Enumerazione semplice** è il tipo standard predefinito.
* **Pulizia degli alias** l&#39;enumerazione viene utilizzata per armonizzare i valori di enumerazione memorizzati nel database. [Ulteriori informazioni](#alias-cleansing)
* **Riservato per la legatura** è un&#39;opzione che consente di collegare i valori del cubo a questa enumerazione. [Ulteriori informazioni](../reporting/gs-cubes.md)


### Pulizia alias {#alias-cleansing}

Nei campi di enumerazione è possibile selezionare un valore oppure immettere un valore personalizzato non disponibile nell’elenco a discesa. I valori personalizzati possono essere aggiunti ai valori di enumerazione esistenti come nuovo - in questo caso, il **[!UICONTROL Open]** deve essere selezionata. Questi valori personalizzati possono essere puliti utilizzando le funzionalità di pulizia degli alias. Ad esempio, se un utente immette `Adob` anziché `Adobe`, il processo di pulizia degli alias può sostituirlo automaticamente con il termine corretto.

>[!CAUTION]
>
>La pulizia dei dati è un processo critico che influisce sui dati presenti nel database. Adobe Campaign esegue aggiornamenti di massa dei dati, che possono causare l’eliminazione di alcuni valori. Questa operazione è pertanto riservata agli utenti esperti.

Abilita la **[!UICONTROL Alias cleansing]** opzione per utilizzare le funzionalità di pulizia dei dati per un&#39;enumerazione. Quando questa opzione è selezionata, la **[!UICONTROL Alias]** viene visualizzata nella parte inferiore della finestra.

Quando un utente immette un valore che non esiste in un&#39;enumerazione di pulizia alias, viene aggiunto al **Valori** elenco. È possibile [creare alias da questi valori](#convert-to-alias)oppure [creare nuovi alias da zero](#create-alias).

#### Creare un alias{#create-alias}

Per creare un alias, effettua le seguenti operazioni:

1. Fai clic su **[!UICONTROL Add]** pulsante **[!UICONTROL Alias]** scheda .
1. Immettere l&#39;alias da convertire e selezionare il valore da applicare nell&#39;elenco a discesa.

   ![Crea un nuovo alias](assets/new-alias.png)

1. Fai clic su **[!UICONTROL Ok]** e confermare.

1. Salva le modifiche. La sostituzione dei valori viene eseguita dal **Pulizia degli alias** flusso di lavoro che viene eseguito ogni notte. Fai riferimento a [Eseguire la pulizia dei dati](#running-data-cleansing).

Per tutti i campi basati su questa enumerazione, quando un utente immette il valore **Adobe** in un campo &quot;azienda&quot; (nella console Adobe Campaign, in un modulo web), viene automaticamente sostituito dal valore **Adobe**.

#### Convertire un valore errato in un alias{#convert-to-alias}

Puoi anche convertire un valore di enumerazione esistente in un alias. Per eseguire questa operazione:

1. Nell’elenco dei valori di un’enumerazione, fai clic con il pulsante destro del mouse e sfoglia per **[!UICONTROL Actions... > Convert values into aliases...]**.

   ![Convertire un valore in un alias](assets/convert-into-aliases.png)

1. Seleziona i valori da convertire in alias e fai clic su **[!UICONTROL Next]**.
1. Fai clic su **[!UICONTROL Start]** per eseguire la conversione.

   Una volta completata l’esecuzione, gli alias vengono aggiunti all’elenco, nella **Alias** scheda . È possibile associare un valore corretto per sostituire voci errate. Per eseguire questa operazione:

1. Seleziona un valore da pulire.
1. Fai clic sul pulsante **Dettagli...** pulsante .
1. Seleziona il nuovo valore nell’elenco a discesa.

   ![Crea un nuovo alias](assets/define-new-alias.png)


>[!NOTE]
>
>Puoi tenere traccia delle occorrenze di un alias nella **[!UICONTROL Hits]** nella colonna **[!UICONTROL Alias]** sottoscheda . Può visualizzare il numero di volte in cui questo valore è stato immesso.  [Ulteriori informazioni](#calculate-entry-occurrences).

#### Eseguire la pulizia dei dati {#running-data-cleansing}

La pulizia dei dati viene eseguita dal **[!UICONTROL Alias cleansing]** flusso di lavoro tecnico. Per impostazione predefinita viene eseguito su base giornaliera.

La pulizia può essere attivata anche tramite il **[!UICONTROL Cleanse values...]** link.

La **[!UICONTROL Advanced parameters...]** link ti consente di impostare la data a partire dalla quale vengono presi in considerazione i valori raccolti.

Fai clic sul pulsante **[!UICONTROL Start]** pulsante per eseguire la pulizia dei dati.

##### Monitorare le occorrenze {#calculate-entry-occurrences}

La **[!UICONTROL Alias]** la sottoscheda di un’enumerazione può visualizzare il numero di occorrenze di un alias tra tutti i valori immessi. Queste informazioni sono una stima e verranno visualizzate nella **[!UICONTROL Hits]** colonna.

>[!CAUTION]
>
>Il calcolo delle occorrenze delle voci di alias può richiedere molto tempo.

Puoi eseguire manualmente il calcolo degli hit tramite **[!UICONTROL Cleanse values...]** link. A questo scopo, fai clic sul pulsante **[!UICONTROL Advanced parameters...]** e seleziona le opzioni.

* **[!UICONTROL Update the number of alias hits]**: questo consente di aggiornare gli hit già calcolati in base alla data immessa.
* **[!UICONTROL Recalculate the number of alias hits from the start]**: consente di eseguire il calcolo sull’intera piattaforma Adobe Campaign.

È inoltre possibile creare un flusso di lavoro dedicato affinché il calcolo venga eseguito automaticamente per un determinato periodo, ad esempio una volta alla settimana.

A questo scopo, crea una copia del **[!UICONTROL Alias cleansing]** , modifica la pianificazione e utilizza le seguenti impostazioni nel **[!UICONTROL Enumeration value cleansing]** attività:

* **-updateHits** per aggiornare il numero di hit di alias,
* **-updateHits:full** per ricalcolare tutti gli hit di alias.
