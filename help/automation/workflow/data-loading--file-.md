---
product: campaign
title: Caricamento dati (file)
description: Ulteriori informazioni sull’attività del flusso di lavoro di caricamento dati (file)
feature: Workflows, Data Management Activity
exl-id: 10351620-115c-4bd8-b216-e5ad6f205ef3
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 14%

---

# Caricamento dati (file){#data-loading-file}



## Utilizzo {#use}

La **[!UICONTROL Data loading (File)]** consente di accedere direttamente a un’origine di dati esterni e di utilizzarla in Adobe Campaign. In effetti, tutti i dati necessari per le operazioni di targeting non si trovano sempre nel database Adobe Campaign: può essere reso disponibile in file esterni.

Il file da caricare può essere specificato dalla transizione o calcolato durante l’esecuzione di questa attività. Ad esempio, può essere l’elenco dei 10 prodotti preferiti di un cliente i cui acquisti vengono gestiti in un database esterno.

La sezione superiore della finestra di configurazione per questa attività ti consente di definire il formato di file. A questo scopo, utilizza un file di esempio con lo stesso formato di quello da importare. Questo file può essere archiviato localmente o sul server.

>[!CAUTION]
>
>Sono supportati solo i file con struttura &quot;flat&quot; (ad esempio CSV, TXT, ecc.). Si sconsiglia di utilizzare il formato XML.

![](assets/s_advuser_wf_etl_file.png)

È possibile definire un processo preliminare da eseguire durante l’importazione dei file, ad esempio per non decomprimere il file sul server (e quindi risparmiare spazio per il file decompresso) ma per includere la decompressione nell’elaborazione dei file. Seleziona la **[!UICONTROL Pre-process the file]** e scegli una delle 3 opzioni disponibili: **[!UICONTROL None]**, **[!UICONTROL Decompression]** (zcat) o **[!UICONTROL Decrypt]** (gpg).

![](assets/preprocessing-dataloading.png)

## Definizione del formato del file {#defining-the-file-format}

Quando carichi un file, il formato della colonna viene rilevato automaticamente con i parametri predefiniti per ciascun tipo di dati. È possibile modificare questi parametri predefiniti al fine di specificare i processi specifici da applicare ai dati, in particolare in caso di errore o di valore vuoto.

A questo scopo, seleziona **[!UICONTROL Click here to change the file format...]** nella finestra principale del **[!UICONTROL Data loading (file)]** attività. Viene quindi aperta la finestra di dettaglio del formato.

![](assets/file_loading_columns_format.png)

È quindi possibile modificare la formattazione generale del file e la formattazione di ogni colonna.

La formattazione generale dei file ti consente di definire il modo in cui verranno riconosciute le colonne (codifica file, separatori utilizzati, ecc.).

La formattazione della colonna ti consente di definire il valore di elaborazione di ciascuna colonna:

* **[!UICONTROL Ignore column]**: non elabora questa colonna durante il caricamento dei dati.
* **[!UICONTROL Data type]**: specifica il tipo di dati previsto per ogni colonna.
* **[!UICONTROL Allow NULLs]**: specifica come gestire i valori vuoti.

   * **[!UICONTROL Adobe Campaign default]**: genera un errore solo per i campi numerici, altrimenti inserisce un valore NULL.
   * **[!UICONTROL Empty value allowed]**: autorizza valori vuoti. Pertanto, viene inserito il valore NULL.
   * **[!UICONTROL Always populated]**: se un valore è vuoto, genera un errore.

* **[!UICONTROL Length]**: specifica il numero massimo di caratteri per il **string** tipo di dati.
* **[!UICONTROL Format]**: definisce il formato di ora e data.
* **[!UICONTROL Data transformation]**: definisce se è necessario applicare un processo relativo alle maiuscole/minuscole dei caratteri su un **string**.

   * **[!UICONTROL None]**: la stringa importata non viene modificata.
   * **[!UICONTROL First letter in upper case]**: la prima lettera di ciascuna parola della stringa inizia con una maiuscola.
   * **[!UICONTROL Upper case]**: tutti i caratteri nella stringa sono in maiuscolo.
   * **[!UICONTROL Lower case]**: tutti i caratteri nella stringa sono in minuscolo.

* **[!UICONTROL White space management]**: specifica se alcuni spazi devono essere ignorati in una stringa. La **[!UICONTROL Ignore spaces]** consente di ignorare solo gli spazi all&#39;inizio e alla fine di una stringa.
* **[!UICONTROL Error processings]**: definisce il comportamento in caso di errore.

   * **[!UICONTROL Ignore the value]**: il valore viene ignorato. Nel registro di esecuzione del flusso di lavoro viene generato un avviso.
   * **[!UICONTROL Reject line]**: l’intera linea non viene elaborata.
   * **[!UICONTROL Use a default value in case of error]**: sostituisce il valore che causava l’errore con uno predefinito, definito nel campo **[!UICONTROL Default value]**.
   * **[!UICONTROL Reject the line when there is no remapping value]**: l&#39;intera linea viene elaborata solo se è stata definita una mappatura per il valore errato (vedi **[!UICONTROL Mapping]** (sotto).
   * **[!UICONTROL Use a default value in case the value is not remapped]**: sostituisce il valore che causava l’errore con un valore predefinito, definito in **[!UICONTROL Default value]** , a meno che non sia stata definita una mappatura per il valore errato (vedi **[!UICONTROL Mapping]** (sotto).

* **[!UICONTROL Default value]**: specifica il valore predefinito in base all’elaborazione dell’errore selezionata.
* **[!UICONTROL Mapping]**: questo campo è disponibile solo nella configurazione dei dettagli delle colonne (accessibile tramite doppio clic o tramite le opzioni a destra dell’elenco delle colonne). In questo modo alcuni valori vengono trasformati al momento dell’importazione. Ad esempio, puoi trasformare &quot;tre&quot; in &quot;3&quot;.

## Esempio: Raccolta e caricamento dei dati nel database {#example--collecting-data-and-loading-it-in-the-database}

L’esempio seguente consente di raccogliere un file sul server ogni giorno, caricarne il contenuto e aggiornare i dati nel database in base alle informazioni in esso contenute. Il file da raccogliere contiene informazioni sui clienti che possono aver effettuato acquisti (per più o meno di 3.000 Euro), chiesto un rimborso su un acquisto o visitato il negozio senza acquistare nulla. A seconda di queste informazioni, diversi processi verranno applicati al profilo nel database.

![](assets/s_advuser_load_file_sample_0.png)

1. Il raccoglitore di file consente di recuperare i file memorizzati in una directory, a seconda della frequenza specificata.

   La **[!UICONTROL Directory]** la scheda contiene informazioni sui file da recuperare. Nel nostro esempio, tutti i file in formato testo i cui nomi contengono la parola &#39;clienti&#39; e che sono memorizzati nella directory tmp/Adobe/Data/files del server verranno recuperati.

   Utilizzo della **[!UICONTROL File collector]** è descritto in [Raccoglitore file](file-collector.md) sezione .

   ![](assets/s_advuser_load_file_sample_1.png)

   La **[!UICONTROL Schedule]** tab consente di pianificare l’esecuzione del raccoglitore, cioè di specificare la frequenza con cui verrà controllata la presenza di questi file.

   Qui vogliamo attivare il collettore ogni giorno alle 9 di sera.

   ![](assets/s_advuser_load_file_sample_2.png)

   A questo scopo, fai clic sul pulsante **[!UICONTROL Change...]** nella sezione in basso a destra dello strumento di modifica e configura la pianificazione.

   Per ulteriori informazioni, consulta [Scheduler](scheduler.md).

1. Quindi configura l’attività di caricamento dei dati (file) per indicare la modalità di lettura dei file raccolti. A questo scopo, selezionare un file di esempio con la stessa struttura dei file da caricare.

   ![](assets/s_advuser_load_file_sample_3.png)

   In questo caso, il file contiene cinque colonne:

   * la prima colonna contiene un codice che coincide con l’evento : acquisto (più o meno di 3.000 euro), nessun acquisto o rimborso su uno o più acquisti.
   * le quattro colonne seguenti contengono il nome, il cognome, l’indirizzo e-mail e il numero di account del cliente.

   La configurazione del formato del file da caricare coincide con quella definita durante un’importazione di dati in Adobe Campaign.

1. Nell’attività divisa, specifica i sottoinsiemi da creare, in base alla **Evento** valore colonna.

   L’attività Split è descritta nella sezione .

   ![](assets/s_advuser_load_file_sample_4.png)

   Per ogni sottoinsieme, specifica uno dei valori nel **Evento** colonna.

   ![](assets/s_advuser_load_file_sample_5.png)

   La **[!UICONTROL Split]** L’attività conterrà pertanto le seguenti informazioni:

   ![](assets/s_advuser_load_file_sample_6.png)

1. Quindi specificare i processi da eseguire per ogni tipo di popolazione. Nel nostro esempio, **[!UICONTROL Update the data]** nel database. Per eseguire questa operazione, posizionare un **[!UICONTROL Update data]** attività alla fine di ogni transizione in uscita dall’attività divisa.

   La **[!UICONTROL Update data]** l’attività è descritta in [Update data](update-data.md) sezione .
