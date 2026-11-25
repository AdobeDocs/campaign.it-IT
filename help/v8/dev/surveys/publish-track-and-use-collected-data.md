---
product: campaign
title: Pubblicare, tracciare e utilizzare i dati raccolti
description: Scopri come pubblicare, tracciare e utilizzare i dati raccolti in un sondaggio
feature: Surveys
version: Campaign v8, Campaign Classic v7
exl-id: 3cf3c486-6640-4d67-95cf-50d5767deb60
TQID: 'https://experienceleague.adobe.com/5faTMQayKA-bxeGrKlNlk7fxZUV2-TO-eVCSe3iRrgA'
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
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 2%
---
# Pubblicare, tracciare e utilizzare i dati raccolti{#publish-track-and-use-collected-data}

>[!AVAILABILITY]
>
>I sondaggi non sono disponibili per [distribuzioni FFDA di Campaign](../../architecture/enterprise-deployment.md).



Una volta creato, configurato e pubblicato il modulo, puoi condividere il collegamento con il pubblico e tenere traccia delle risposte.

>[!NOTE]
>
>Il ciclo di vita di un sondaggio in Adobe Campaign e le relative modalità di pubblicazione e consegna sono simili a quelli dei moduli web: sono descritti in [Introduzione ai moduli web](../web/about-web-forms.md).

## Dashboard sondaggio {#survey-dashboard}

Ogni sondaggio ha una propria dashboard che consente di visualizzarne lo stato, la descrizione, l’URL pubblico e la pianificazione della disponibilità. Consente inoltre di visualizzare i rapporti disponibili. [Ulteriori informazioni](#reports-on-surveys).

L’URL pubblico del sondaggio viene visualizzato sulla dashboard:

![Dashboard del sondaggio che mostra lo stato Online e una freccia che punta all&#39;URL pubblico utilizzato per accedere al sondaggio](assets/survey_public_url.png)

## Tracciamento delle risposte {#response-tracking}

Puoi tenere traccia delle risposte al sondaggio nei registri e nei rapporti.

### Registri del sondaggio {#survey-logs}

Per ogni sondaggio consegnato, è possibile tenere traccia delle risposte nella scheda **[!UICONTROL Logs]**. In questa scheda viene visualizzato l’elenco degli utenti che hanno completato il sondaggio e la loro origine:

![Scheda Risposte del sondaggio che elenca la data, il destinatario e l&#39;origine di ogni risposta](assets/s_ncs_admin_survey_logs.png)

Fare doppio clic su una riga per visualizzare il modulo del sondaggio compilato dal partecipante. È possibile sfogliare l&#39;intero sondaggio e accedere alle risposte complete. Possono essere esportati in un file esterno. Per ulteriori informazioni, consulta [Esportazione delle risposte](#exporting-answers).

L’origine è indicata nell’URL del sondaggio aggiungendo i seguenti caratteri:

```text
?origin=xxx
```

durante la modifica del sondaggio, l&#39;URL contiene il parametro **[!UICONTROL __uuid]**, che indica che si trova in una fase di test e non è ancora online. Quando accedi al sondaggio tramite questo URL, i record creati non vengono presi in considerazione nel tracciamento (rapporti). Origine forzata al valore **[!UICONTROL Adobe Campaign]**.

Per ulteriori informazioni sui parametri URL, consulta [Parametri URL modulo](../web/defining-web-forms-properties.md#form-url-parameters).

### Relazioni sulle indagini {#reports-on-surveys}

La scheda della dashboard ti consente di accedere ai rapporti dei sondaggi. Fai clic sul nome di un rapporto per visualizzarlo.

![Visualizzazione report del dashboard sondaggi con raggruppamento dei report di analisi delle risposte, Generale, Documentazione e Micrositi](assets/s_ncs_admin_survey_report_doc.png)

La struttura del sondaggio è visibile nel report **[!UICONTROL Documentation]**.

Nella scheda **[!UICONTROL Reports]** dei sondaggi sono disponibili altri due rapporti sui sondaggi Web: **[!UICONTROL General]** e **[!UICONTROL Breakdown of responses]**.

* Generale

  Questo rapporto contiene informazioni generali sul sondaggio: come cambia il numero di risposte nel tempo e la distribuzione per origine e lingua.

  Esempio di rapporto generale:

  ![Rapporto generale con data di inizio, numero di risposte e un grafico delle risposte nel tempo](assets/s_ncs_admin_survey_report_0.png)

* Raggruppamento delle risposte

  Questo rapporto mostra il raggruppamento delle risposte per ogni domanda. Questo raggruppamento è disponibile solo per le risposte date ai campi memorizzati nei contenitori di tipo **[!UICONTROL Question]**. È valida solo per i controlli di selezione (ad esempio, nessuna suddivisione nei campi di testo).

  ![Rapporto Analisi delle risposte con il conteggio e la percentuale di ogni risposta a una domanda](assets/s_ncs_admin_survey_report_2.png)

## Esportazione delle risposte {#exporting-answers}

Le risposte a un sondaggio possono essere esportate in un file esterno per essere elaborate in un secondo momento. Esistono due modi per farlo:

1. Esportazione dei dati del rapporto

   Per esportare i dati del report, fare clic sul pulsante **[!UICONTROL Export]** e scegliere il formato di esportazione.

   Per ulteriori informazioni sull&#39;esportazione dei dati del report, consultare [questa sezione](https://experienceleague.adobe.com/en/docs/campaign-classic/using/reporting/creating-new-reports/about-reports-creation-in-campaign){target="_blank"}.

1. Esportazione delle risposte

   Per esportare le risposte, fare clic sulla scheda **[!UICONTROL Responses]** del sondaggio e fare clic con il pulsante destro del mouse. Seleziona **[!UICONTROL Export...]**.

   ![Scheda Risposte con tutte le risposte selezionate e il menu di scelta rapida che mostra l&#39;opzione Esporta](assets/s_ncs_admin_survey_logs_export_menu.png)

   Immettere quindi le informazioni che si desidera esportare e il file di archiviazione.

   È possibile configurare il contenuto e il formato del file di output nell&#39;Assistente all&#39;esportazione.

   Questo consente di:

   * aggiungere colonne al file di output e recuperare le informazioni sul destinatario (memorizzate nel database),
   * formattare i dati esportati,
   * selezionare il formato di codifica per le informazioni contenute nel file.

   Se il sondaggio che si desidera esportare contiene diversi campi **[!UICONTROL Multi-line text]** o **[!UICONTROL HTML text]**, deve essere esportato in formato **[!UICONTROL XML]**. A tale scopo, selezionare questo formato nell&#39;elenco a discesa del campo **[!UICONTROL Output format]**, come illustrato di seguito:

   ![Esportazione guidata elenco con il menu a discesa Formato di output aperto e XML selezionato](assets/s_ncs_admin_survey_logs_export_xml.png)

   Fare clic su **[!UICONTROL Start]** per eseguire l&#39;esportazione.

   >[!NOTE]
   >
   >Le esportazioni di dati e le fasi della loro configurazione sono descritte in [questa sezione](https://experienceleague.adobe.com/it/docs/campaign/campaign-v8/data/import){target="_blank"} (documentazione di Campaign v8).

## Utilizzo dei dati raccolti {#using-the-collected-data}

Le informazioni raccolte tramite sondaggi online possono essere recuperate nel quadro di un flusso di lavoro di targeting. A tale scopo, utilizzare la casella **[!UICONTROL Survey responses]**.

Nell’esempio seguente, vogliamo fare un’offerta Web appositamente per i cinque destinatari con almeno due figli e con i punteggi più elevati in un sondaggio online. Le risposte a questo sondaggio sono le seguenti:

![Scheda Risposte di un sondaggio che elenca ogni partecipante con punteggio, numero di figli e tipo di contatto](assets/s_ncs_admin_survey_responses_wf_box_4.png)

Nel flusso di lavoro di targeting, **[!UICONTROL Survey responses]** verrà configurato come segue:

![Casella delle risposte al sondaggio in un flusso di lavoro di targeting, con il sondaggio selezionato e il collegamento per selezionare le colonne da estrarre](assets/s_ncs_admin_survey_responses_wf_box_1.png)

Inizia selezionando il sondaggio interessato, quindi i dati da estrarre nella sezione centrale della finestra. In questo caso, è necessario estrarre almeno la colonna di punteggio, in quanto verrà utilizzata nella casella di divisione per recuperare i cinque punteggi più elevati.

Indicare le condizioni di filtro per le risposte facendo clic sul collegamento **[!UICONTROL Edit query...]**.

![Casella risposte sondaggio con una query che filtra le risposte in base al numero di elementi figlio e un punteggio maggiore di 50](assets/s_ncs_admin_survey_responses_wf_box_2.png)

Avvia il flusso di lavoro di targeting. La query recupera 8 destinatari.

![Menu di scelta rapida per la transizione dei risultati del flusso di lavoro con l&#39;opzione Visualizza destinazione evidenziata](assets/s_ncs_admin_survey_responses_wf_box_5.png)

Fare clic con il pulsante destro del mouse sulla transizione di output della casella di raccolta per visualizzarle.

![Visualizza la finestra di popolazione in cui sono elencati gli 8 destinatari restituiti dalla query di risposta al sondaggio con i relativi punteggi](assets/s_ncs_admin_survey_responses_wf_box_6.png)

Quindi inserisci una casella di divisione nel flusso di lavoro per recuperare i 5 destinatari con il punteggio più alto.

Modifica la casella di divisione per configurarla:

* Iniziare selezionando lo schema adeguato nella scheda **[!UICONTROL General]**, quindi configurare il sottoinsieme:

  ![Scheda Generale della casella di divisione con Usa solo i dati aggiuntivi selezionati, dopo la casella Risposte al sondaggio](assets/s_ncs_admin_survey_responses_wf_box_6b.png)

* Vai alla scheda **[!UICONTROL Sub-sets]** e seleziona l&#39;opzione **[!UICONTROL Limit the selected records]**, quindi fai clic sul collegamento **[!UICONTROL Edit...]**.

  ![Scheda Sottoinsiemi casella divisa con l&#39;opzione Limita i record selezionati e il collegamento Modifica](assets/s_ncs_admin_survey_responses_wf_box_7.png)

* Selezionare l&#39;opzione **[!UICONTROL Keep only the first records after sorting]** e la colonna di ordinamento. Seleziona l’opzione **[!UICONTROL Descending sort]**.

  ![Procedura guidata di limitazione del conteggio dei record con Mantieni solo i primi record dopo l&#39;ordinamento e un ordinamento decrescente per Punteggio](assets/s_ncs_admin_survey_responses_wf_box_8.png)

* Fare clic sul pulsante **[!UICONTROL Next]** e limitare il numero di record a 5.

  ![Passaggio Limitazione conteggio record con dimensione massima impostata su 5 e pulsante Fine](assets/s_ncs_admin_survey_responses_wf_box_9.png)

* Fai clic su **[!UICONTROL Finish]**, quindi riavvia il flusso di lavoro per approvare il targeting.

## Standardizzazione dei dati {#standardizing-data}

È possibile impostare processi di standardizzazione in Adobe Campaign per i dati raccolti utilizzando gli alias. Ciò ti consente di standardizzare i dati memorizzati nel database: a questo scopo, definisci gli alias negli elenchi dettagliati che contengono le informazioni pertinenti. Scopri come **utilizzare le enumerazioni** nella [documentazione di Adobe Campaign v8 (console)](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/config/settings/enumerations){target=_blank}.