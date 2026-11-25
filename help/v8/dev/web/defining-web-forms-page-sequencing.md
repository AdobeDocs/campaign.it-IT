---
product: campaign
title: Definire la sequenza di pagine dei moduli web
description: Definire la sequenza di pagine dei moduli web
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: c5b5c398-c13b-4ebe-88b2-8ff84741422e
TQID: 'https://experienceleague.adobe.com/G1sd0NfOozlAyvMZpi6R8IEbfr6ZHE2ibhnfttEd7J8'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '938'
ht-degree: 0%
---
# Definire la sequenza di pagine dei moduli web{#defining-web-forms-page-sequencing}



Il modulo può contenere una o più pagine. Viene creato tramite un diagramma che consente di sequenziare le pagine, testare, eseguire script, passare da una pagina all’altra e registrare i passaggi. La modalità di progettazione dei diagrammi globali è la stessa di un flusso di lavoro di Campaign.

## Informazioni sulla pagina precedente e su quella successiva {#about-previous-page-and-next-page}

Per ogni pagina è possibile eliminare i pulsanti **[!UICONTROL Next]** o **[!UICONTROL Previous]**. A tale scopo, selezionare la pagina interessata e selezionare l&#39;opzione **[!UICONTROL Disable next page]** o **[!UICONTROL Disallow returning to the previous page]**.

![Proprietà pagina, scheda Generale, con l&#39;opzione Disattiva pagina successiva selezionata nella sezione Navigazione.](assets/s_ncs_admin_survey_no_next_page.png)

È possibile sostituire questi pulsanti con collegamenti. Vedere [Inserimento di contenuto HTML](static-elements-in-a-web-form.md#inserting-html-content).

## Inserimento di un salto {#inserting-a-jump}

L&#39;oggetto **[!UICONTROL Jump]** consente l&#39;accesso a un&#39;altra pagina o a un altro modulo quando l&#39;utente fa clic su **[!UICONTROL Next]**.

La destinazione può essere:

* Un&#39;altra pagina del modulo. A tale scopo, selezionare **[!UICONTROL Internal activity]** e quindi specificare la pagina desiderata, come indicato di seguito:

  ![Finestra di dialogo Salta con l&#39;attività interna selezionata e l&#39;elenco Attività che mostra le pagine del modulo a cui passare.](assets/s_ncs_admin_jump_param1.png)

* Un altro modulo. A tale scopo, selezionare l&#39;opzione **[!UICONTROL Explicit]** e specificare il modulo di destinazione.

  ![Finestra di dialogo Salta con esplicito selezionato e modulo di destinazione scelto nel campo dell&#39;applicazione Web di destinazione.](assets/s_ncs_admin_jump_param2.png)

* La destinazione può essere memorizzata in una variabile. In questo caso, selezionalo dall’elenco a discesa, come illustrato di seguito:

  ![Finestra di dialogo Salta con Archiviato in una variabile selezionata e l&#39;elenco a discesa Variabile locale è aperto.](assets/s_ncs_admin_jump_param3.png)

* La scheda **[!UICONTROL Comment]** consente di immettere informazioni che saranno visibili dall&#39;operatore quando farà clic sull&#39;oggetto nel diagramma.

  ![Scheda Commento della finestra di dialogo Salta; il testo viene visualizzato come descrizione comando sull&#39;oggetto Salta nel diagramma modulo.](assets/s_ncs_admin_survey_jump_comment.png)

## Esempio: accesso a un altro modulo in base a un parametro dell’URL {#example--accessing-another-form-according-to-a-parameter-of-the-url}

Nell’esempio seguente, vogliamo configurare un modulo web che, se approvato, visualizzerà un altro modulo designato da un parametro dell’URL. A questo scopo, esegui i seguenti passaggi:

1. Inserisce un salto alla fine di un modulo: sostituisce la casella **[!UICONTROL End]**.

   ![Diagramma del modulo con un oggetto Jump inserito dopo l&#39;archiviazione alla fine del modulo, sostituendo la casella Fine.](assets/s_ncs_admin_survey_jump_sample1.png)

1. Nelle proprietà del modulo, aggiungi un parametro (**next**) memorizzato in una variabile locale (**next**). Le variabili locali sono descritte in dettaglio in [Memorizzazione dei dati in una variabile locale](web-forms-answers.md#storing-data-in-a-local-variable).

   ![Scheda Parametri proprietà modulo con aggiunta del parametro successivo, archiviato nella variabile locale next.](assets/s_ncs_admin_survey_jump_sample2.png)

1. Modifica l&#39;oggetto **[!UICONTROL Jump]**, seleziona l&#39;opzione **[!UICONTROL Stored in a variable]** e seleziona la variabile **next** dalla casella a discesa.

   ![Finestra di dialogo Salta con Archiviata in una variabile selezionata e la variabile successiva scelta nell&#39;elenco delle variabili locali.](assets/s_ncs_admin_survey_jump_sample3.png)

1. L’URL di consegna deve includere il nome interno del modulo di destinazione, ad esempio:

   ```text
   https://[myserver]/webForm/APP62?&next=APP22
   ```

   Quando l&#39;utente fa clic sul pulsante **[!UICONTROL Approve]**, viene visualizzato il modulo **APP22**.

## Inserimento di un collegamento a un&#39;altra pagina del modulo {#inserting-a-link-to-another-page-of-the-form}

È possibile inserire collegamenti ad altre pagine del modulo. Per eseguire questa operazione, aggiungere alla pagina un elemento statico di tipo **[!UICONTROL Link]**. Per ulteriori informazioni, consulta [Inserimento di un collegamento](static-elements-in-a-web-form.md#inserting-a-link).

## Visualizzazione pagina condizionale {#conditional-page-display}

### Visualizza in base alle risposte {#display-based-on-responses}

La casella **[!UICONTROL Test]** consente di condizionare la sequenza delle pagine in un modulo. Consente di definire varie linee di diramazione in base ai risultati del test. Questo consente di visualizzare pagine diverse a seconda delle risposte fornite dagli utenti.

Ad esempio, puoi visualizzare una pagina diversa per i clienti che hanno già effettuato un ordine online e un’altra per quelli che hanno effettuato più di dieci ordini. A tale scopo, nella prima pagina del modulo inserire un campo di input di tipo **[!UICONTROL Number]** in modo che l&#39;utente possa indicare il numero di ordini che ha effettuato.

![Pagina modulo I tuoi dettagli e ordini con titolo, nome, campi e-mail e un quante volte ordini sulla domanda web.](assets/s_ncs_admin_survey_test_ex0.png)

È possibile memorizzare queste informazioni in un campo del database oppure utilizzare una variabile locale.

>[!NOTE]
>
>Le modalità di archiviazione sono descritte in dettaglio nei [campi di archiviazione delle risposte](web-forms-answers.md#response-storage-fields).

Nel nostro esempio, vogliamo utilizzare una variabile:

![Campo Conteggio ordini della pagina con archiviazione impostata sull&#39;opzione Variabile e la variabile Ordini selezionata.](assets/s_ncs_admin_survey_test_ex1.png)

Nel diagramma del modulo inserire una casella di prova per definire le condizioni. Per ogni condizione, verrà aggiunto un nuovo ramo all’output della casella di test.

![Finestra di dialogo di test con i rami Ordini +10 e Ordini 1—>9 e finestra di dialogo Modifica ramo che definiscono le relative condizioni.](assets/s_ncs_admin_survey_test_ex2.png)

Selezionare l&#39;opzione **[!UICONTROL Activate the default branching]** per aggiungere una transizione per i casi in cui nessuna delle condizioni è vera. Questa opzione non è necessaria se le condizioni definite riguardano tutti i casi possibili.

Quindi, definisci la sequenza di pagine quando una delle due condizioni è vera, ad esempio:

![Diagramma modulo: gli ordini? il test conduce a pagine New, Standard o Gold, che portano tutte a Storage e End.](assets/s_ncs_admin_survey_test_ex3.png)

### Visualizza in base ai parametri {#display-based-on-parameters}

È inoltre possibile personalizzare la sequenza di pagine in base ai parametri di inizializzazione del modulo Web o ai valori memorizzati nel database. Vedi [Parametri URL modulo](defining-web-forms-properties.md#form-url-parameters).

## Aggiunta di script {#adding-scripts}

L&#39;oggetto **[!UICONTROL Script]** consente di immettere direttamente uno script JavaScript, ad esempio per modificare il valore di un campo, recuperare dati dal database o chiamare un&#39;API Adobe Campaign.

## Personalizzazione della pagina finale {#personalizing-the-end-page}

Inserire una pagina finale alla fine del diagramma. La pagina finale viene visualizzata quando l&#39;utente fa clic sul pulsante **[!UICONTROL Approve]** nel modulo Web.

Per personalizzare la pagina, fare doppio clic su **[!UICONTROL End]** e immettere il contenuto della pagina nell&#39;editor centrale.

![Finestra di dialogo di fine con il titolo della pagina finale e l&#39;editor dei contenuti, in cui viene visualizzato un messaggio di ringraziamento per il completamento del sondaggio.](assets/s_ncs_admin_survey_end_page_edit.png)

* Puoi copiare e incollare contenuti HTML esistenti. A tale scopo, fare clic su **[!UICONTROL Display source code]** e inserire il codice HTML.
* Puoi utilizzare un URL esterno; a questo scopo, seleziona l’opzione corrispondente e immetti l’URL della pagina da visualizzare.
