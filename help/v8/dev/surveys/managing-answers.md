---
product: campaign
title: Gestire le risposte
description: Scopri come gestire le risposte ai sondaggi
feature: Surveys
version: Campaign v8, Campaign Classic v7
exl-id: 0b5dc602-e16f-4bf1-bd8f-352e0bc78996
TQID: 'https://experienceleague.adobe.com/-xjK3nxUc4Lz-mWyVoUbbIJ8HQvyLRInYk-w8zYLYE4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: 71b1c383-45b9-57e0-b8cd-ea2e98a01a26
    internal-label: Surveys
subfeature_v2:
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%
---
# Gestire le risposte{#managing-answers}

>[!AVAILABILITY]
>
>I sondaggi non sono disponibili per [distribuzioni FFDA di Campaign](../../architecture/enterprise-deployment.md).



## Memorizza le risposte raccolte {#storing-collected-answers}

Oltre alle modalità di archiviazione standard comuni a tutti i moduli web in Adobe Campaign (campo del database e variabile locale), i sondaggi consentono l’estensione dinamica del modello dati utilizzando i campi archiviati.

>[!CAUTION]
>
>Questa opzione è disponibile solo per le applicazioni Web di tipo **Sondaggio**. Non è disponibile per altri tipi di moduli Web.

### Memorizza in un campo archiviato {#storing-in-an-archived-field}

È facile estendere il modello dati aggiungendo nuovi spazi di archiviazione per salvare le risposte fornite nei sondaggi. A tale scopo, selezionare l&#39;opzione **[!UICONTROL Store answers to a question]** durante la creazione del campo di input. Fai clic sul collegamento **[!UICONTROL New field...]** e assegna le relative proprietà:

![Finestra di dialogo Archiviazione con le risposte dell&#39;archivio a una domanda selezionata e finestra di dialogo Crea nuovo campo archiviato per un campo Contratto.](assets/s_ncs_admin_survey_new_space.png)

Immettere l&#39;etichetta e il nome del campo e selezionare il tipo di campo: Testo, Booleano, Numero intero o decimale, Data e così via.

Il tipo di campo selezionato include un controllo dei dati quando le risposte vengono immesse dagli utenti. Per i campi **testo**, puoi aggiungere un vincolo (maiuscole/minuscole, formato) o un collegamento a un&#39;enumerazione esistente per forzare la selezione.

Per aggiungere un vincolo, selezionatelo dall&#39;elenco a discesa. Esistono due tipi di vincoli:

1. Maiuscole/minuscole caratteri

   Le informazioni immesse possono essere memorizzate nel campo nei seguenti formati: tutto maiuscolo, tutto minuscolo o iniziale maiuscolo. Questo vincolo non richiede all’utente di immettere i dati nel formato selezionato, ma il contenuto immesso nel campo verrà convertito al momento del salvataggio.

1. Formato dei dati

Se questo campo viene utilizzato in un elenco, i valori dell&#39;enumerazione possono essere recuperati automaticamente nella tabella dei valori utilizzando il collegamento **[!UICONTROL Initialize the list of values from the database]** sopra l&#39;elenco dei valori.

Ad esempio, puoi creare un elenco a discesa per consentire all’utente di selezionare la propria lingua nativa. Il campo archiviato corrispondente può essere associato all&#39;enumerazione **lingua** che contiene un elenco di lingue:

![Finestra di dialogo Crea nuovo campo archiviato con l&#39;enumerazione della lingua selezionata e l&#39;icona Modifica collegamento evidenziata.](assets/s_ncs_admin_survey_database_values_2b.png)

L&#39;icona **[!UICONTROL Edit link]** situata a destra del campo consente di modificare il contenuto di questa enumerazione:

![Editor Enumeration Language (lingua) che elenca i valori Inglese, Francese e Tedesco.](assets/s_ncs_admin_survey_database_values_2c.png)

Nella scheda **[!UICONTROL General]** del campo, il collegamento **[!UICONTROL Initialize the list of values from the database]** consente di immettere automaticamente l&#39;elenco di etichette offerte.

![Scheda Generale del campo a discesa, inizializzare l&#39;elenco di valori dal database link che riempie le etichette di lingua.](assets/s_ncs_admin_survey_database_values_2.png)

**Esempio**: memorizzazione dei contratti di un destinatario in un campo

Per memorizzare diversi tipi di contratti in un campo, creare un campo di input **[!UICONTROL Text]** e selezionare l&#39;opzione **[!UICONTROL Store answers to a question]**.

Fai clic sul collegamento **[!UICONTROL New field...]** e immetti le proprietà del campo. Selezionare l&#39;opzione **[!UICONTROL Multiple values]** per consentire la memorizzazione di più valori.

![Finestra di dialogo Crea nuovo campo archiviato per Contratti con l&#39;opzione Più valori selezionata.](assets/s_ncs_admin_survey_storage_multi_ex1.png)

Creare campi di immissione per gli altri contratti e archiviare i dati nello stesso campo archiviato.

![Finestra di dialogo Archiviazione e selettore di campi che collegano un campo di input al campo archiviato dei contratti.](assets/s_ncs_admin_survey_storage_multi_ex2.png)

Quando gli utenti approvano il sondaggio, le loro risposte verranno memorizzate nel campo **[!UICONTROL Contracts]**.

Nel nostro esempio, per le seguenti risposte:

![Pagina del sondaggio dei contratti con quattro campi del contratto compilati con i valori M, L, T e V.](assets/s_ncs_admin_survey_storage_multi_ex3.png)

Il profilo del rispondente conterrà i quattro contratti sottoscritti.

È possibile visualizzarli nella scheda **[!UICONTROL Answers]** del sondaggio visualizzando le colonne pertinenti.

![Scheda Risposte in cui sono elencate le risposte con le colonne da Contrat_1 a Contrat_4 che mostrano i valori delle risposte con più valori.](assets/s_ncs_admin_survey_storage_multi_ex4.png)

Puoi anche filtrare i destinatari in base alle risposte, per visualizzare solo gli utenti che ti interessano. A questo scopo, crea un flusso di lavoro di targeting e utilizza la casella **[!UICONTROL Survey responses]**.

![Flusso di lavoro di targeting con l&#39;attività Risposte al sondaggio trascinata dalla palette Targeting nel diagramma.](assets/s_ncs_admin_survey_read_responses_wf.png)

Crea la query in base ai profili che desideri recuperare. Nell’esempio seguente, la query ti consente di selezionare profili con almeno due contratti, incluso un contratto di tipo A.

![Attività risposte sondaggio e relativo filtro della finestra di dialogo Query su Contract_1 uguale a E e Contract_2 uguale a R.](assets/s_ncs_admin_survey_read_responses_edit.png)

Per ogni modulo è possibile utilizzare le risposte fornite nei campi o nelle etichette. Utilizza la seguente sintassi per il contenuto archiviato in un campo archiviato:

```html
<%= ctx.webAppLogRcpData.name of the archived field %
```

>[!NOTE]
>
>Per altri tipi di campi, la sintassi è descritta in [questa sezione](https://experienceleague.adobe.com/it/docs/campaign/campaign-v8/data/query/query-editor){target="_blank"} (documentazione di Campaign v8).

### Impostazioni di archiviazione {#storage-settings}

È possibile archiviare le risposte ai sondaggi in formato XML. Questo consente di salvare una copia non elaborata delle risposte raccolte, che può essere utile in caso di standardizzazione eccessiva dei dati in un elenco dettagliato. [Ulteriori informazioni](publish-track-and-use-collected-data.md#standardizing-data)

>[!CAUTION]
>
>L&#39;archiviazione delle risposte non elaborate influisce sullo spazio di archiviazione richiesto. Utilizza questa opzione con cautela.

Per eseguire questa operazione:

* Modificare le proprietà del sondaggio tramite il pulsante **[!UICONTROL Properties]** della scheda **[!UICONTROL Edit]**.
* Fare clic sul collegamento **[!UICONTROL Advanced parameters]** e selezionare l&#39;opzione **[!UICONTROL Save a copy of raw answers]**.

![Finestra di dialogo Parametri avanzati dell&#39;applicazione Web con l&#39;opzione Salva una copia delle risposte non elaborate selezionata.](assets/s_ncs_admin_survey_xml_archive_option.png)

Puoi abilitarla per impostazione predefinita per tutti i sondaggi (questa opzione viene applicata quando il sondaggio viene pubblicato). A tale scopo, creare l&#39;opzione **[!UICONTROL NmsWebApp_XmlBackup]** e assegnarvi il valore **[!UICONTROL 1]**, come illustrato di seguito:

![Nodo Options in Administration, Platform con l&#39;opzione NmsWebApp_XmlBackup creata con il valore 1.](assets/s_ncs_admin_survey_xml_global_option.png)

## Gestione dei punteggi {#score-management}

Puoi assegnare un punteggio alle opzioni offerte nelle pagine del modulo. I punteggi possono essere collegati solo a domande chiuse: casella di controllo, valore da un elenco a discesa, abbonamento, ecc.

![Campo casella combinata Scheda Generale in cui sono elencati i valori delle schede fedeltà Standard per VIP con una colonna Punteggio da 2.00 a 10.00.](assets/s_ncs_admin_survey_score_create.png)

I punteggi vengono accumulati e salvati sul lato server quando la pagina viene confermata, ovvero quando l&#39;utente fa clic sul pulsante **[!UICONTROL Next]** o **[!UICONTROL Finish]**.

>[!NOTE]
>
>È possibile utilizzare valori positivi o negativi, interi o non interi.

I punteggi possono essere utilizzati nei test o negli script.

>[!CAUTION]
>
>I punteggi non possono essere utilizzati nelle condizioni di visibilità per i campi che si trovano sulla stessa pagina. Tuttavia, possono essere utilizzati nelle pagine successive.

* Per utilizzare i punteggi nei test, utilizzare il campo **[!UICONTROL Score]** nella formula di calcolo del test, come illustrato di seguito:

  ![Attività di test con una condizione nel punteggio maggiore di 6, selezionando il campo Punteggio dal documento di contesto.](assets/s_ncs_admin_survey_score_in_a_test.png)

* Puoi utilizzare il punteggio in uno script.

**Esempio**: calcola un punteggio e utilizzalo come condizione per la visualizzazione della pagina successiva:

* In un sondaggio, la pagina successiva ti consente di assegnare punteggi diversi agli utenti a seconda del valore selezionato nell’elenco a discesa:

  ![Campo a discesa dei livelli di classe, dalla scuola all&#39;università, con punteggi da 2.00 a 7.00.](assets/s_ncs_admin_survey_score_exa.png)

* Puoi combinare questo punteggio con un secondo valore, a seconda dell’opzione selezionata:

  ![Campo a scelta multipla Si sta... con padre valutato 7,00 e studente valutato 2,00.](assets/s_ncs_admin_survey_score_exb.png)

* Quando l&#39;utente fa clic sul pulsante **[!UICONTROL Next]**, i due valori vengono sommati.

  ![Pagina di benvenuto con livello junior selezionato nell&#39;elenco Livello e l&#39;opzione padre selezionata in Stato.](assets/s_ncs_admin_survey_score_exe.png)

* È possibile applicare le condizioni per la visualizzazione della pagina in base al punteggio. Questa configurazione è configurata come segue:

  ![Attività di test con una condizione Edit branch: punteggio maggiore di 7.00.](assets/s_ncs_admin_survey_score_exd.png)

  ![L&#39;attività di test viene instradata al livello 1 quando il punteggio è inferiore a 7, al livello 2 quando è uguale a 7 e al livello 3 quando è superiore a 7.](assets/s_ncs_admin_survey_score_exg.png)
