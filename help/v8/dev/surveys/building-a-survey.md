---
product: campaign
title: Progettare un sondaggio
description: Scopri i passaggi chiave per progettare un sondaggio
feature: Surveys
version: Campaign v8, Campaign Classic v7
exl-id: 8d83dfd5-70ec-4656-965b-f6b5e6f9eec1
TQID: https://experienceleague.adobe.com/aeRP0GoE5lu3eUsJ4kg8DoUnqFeipazoax--zX8Lv60
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 2%
---
# Progettare un sondaggio{#building-a-survey}

>[!AVAILABILITY]
>
>I sondaggi non sono disponibili per [distribuzioni FFDA di Campaign](../../architecture/enterprise-deployment.md).



## Crea un nuovo sondaggio {#creating-a-new-survey}

Questo capitolo descrive la progettazione di un modulo di tipo **Sondaggio** tramite Adobe Campaign, nonché le opzioni e le configurazioni disponibili. Adobe Campaign consente di rendere questo sondaggio disponibile agli utenti e di raccogliere e archiviare le risposte nel database.

I moduli Web sono accessibili tramite il nodo **[!UICONTROL Resources > Online > Web applications]** della struttura. Per creare un sondaggio, fare clic sul pulsante **[!UICONTROL New]** sopra l&#39;elenco delle applicazioni oppure fare clic con il pulsante destro del mouse sull&#39;elenco e scegliere **[!UICONTROL New]**.

Selezionare il modello di sondaggio (**[!UICONTROL newSurvey]** per impostazione predefinita).

![Viene aperta la finestra di dialogo Nuova applicazione Web con l&#39;elenco dei modelli per la scelta di un sondaggio o di un modello di modulo Web.](assets/s_ncs_admin_survey_select_template.png)

Le pagine del modulo vengono create utilizzando un editor speciale che consente di definire e configurare campi di input (testo), campi di selezione (elenchi, caselle di controllo, ecc.) ed elementi statici (immagini, contenuti HTML, ecc.). Essi possono essere raccolti in &quot;contenitori&quot; e disposti secondo i requisiti. [Ulteriori informazioni](#adding-questions).

>[!NOTE]
>
>Per ulteriori informazioni su come definire il contenuto e creare layout di schermo per un modulo Web, fare riferimento a [questo documento](../web/about-web-forms.md).

## Aggiungi campi {#adding-fields}

I campi di un modulo consentono agli utenti di immettere informazioni e selezionare opzioni. Per ogni pagina del modulo vengono create tramite il primo pulsante della barra degli strumenti tramite il menu **[!UICONTROL Add using the assistant]**.

![Creazione guidata campi aperta da Aggiungi tramite la procedura guidata, con quattro opzioni di campo da Rispondi a una domanda all&#39;importazione.](assets/s_ncs_admin_survey_add_field_menu.png)

>[!NOTE]
>
>È inoltre possibile fare clic con il pulsante destro del mouse e inserire un&#39;area di input. Per impostazione predefinita, la zona viene inserita alla fine della struttura selezionata. Utilizza le frecce nella barra degli strumenti per spostarla.

### Tipi di campi {#types-of-fields}

Quando si aggiunge un campo a un sondaggio, è necessario selezionarne il tipo. Sono disponibili le seguenti opzioni:

1. **[!UICONTROL Answer a question]**: questa opzione consente di dichiarare un nuovo campo (noto come &quot;campo archiviato&quot;) per archiviare le risposte. In questo caso, tutti i valori raccolti vengono salvati, anche quando un partecipante compila il modulo più di una volta. Questa modalità di archiviazione è disponibile solo in **sondaggi**. [Ulteriori informazioni](managing-answers.md#storing-collected-answers).
1. **[!UICONTROL Edit a recipient]**: consente di selezionare un campo nel database. In questo caso, le risposte dell&#39;utente verranno memorizzate in questo campo. Per ogni partecipante, viene mantenuto solo l’ultimo valore salvato e aggiunto ai dati del profilo.
1. **[!UICONTROL Add a variable]**: questa opzione consente di creare una configurazione in modo che le informazioni non vengano memorizzate nel database. Le variabili locali possono essere dichiarate a monte. Puoi anche aggiungerli direttamente durante la creazione del campo.
1. **[!UICONTROL Import an existing question]**: questa opzione consente di importare le domande esistenti create in altri sondaggi.

   >[!NOTE]
   >
   >Le modalità di archiviazione e le importazioni dei campi sono descritte in dettaglio in [Memorizzare le risposte raccolte](managing-answers.md#storing-collected-answers).

La natura del campo da aggiungere (elenco a discesa, campo di testo, caselle di controllo e così via) si adatta alla modalità di archiviazione selezionata. Puoi modificarlo utilizzando il campo **[!UICONTROL Type]** della scheda **[!UICONTROL General]**, ma assicurati di rimanere coerente con il tipo di dati.

![Scheda Generale dell&#39;Editor pagine con l&#39;elenco Tipo aperto, che mostra Scelta multipla, Casella combinata e altri tipi di campi.](assets/s_ncs_admin_survey_change_type.png)

I vari tipi di campi disponibili sono descritti in dettaglio in [Introduzione ai moduli Web](../web/about-web-forms.md).

## Elementi specifici del sondaggio {#survey-specific-elements}

I sondaggi online si basano sulle funzionalità delle applicazioni web. Le funzionalità specifiche del sondaggio sono descritte di seguito.

### Scelte multiple {#multiple-choice}

Per i controlli di tipo **[!UICONTROL Multiple choice]**, è possibile definire un numero minimo e massimo di selezioni. Ad esempio, questa opzione consente di forzare la selezione ad almeno **2** valori e al massimo a **4** valori dalle opzioni disponibili:

![Pagina del sondaggio Seleziona i tuoi interessi con le caselle di controllo, selezionate da tre a quattro opzioni.](assets/s_ncs_admin_survey_multichoice_ex1.png)

Se il numero di selezioni è troppo grande o troppo piccolo, viene visualizzato il messaggio appropriato.

![Nella pagina del sondaggio Interests viene visualizzato il messaggio di errore Non scegliere più di quattro interessi.](assets/s_ncs_admin_survey_multichoice_ex2.png)

>[!NOTE]
>
>In questo caso, le opzioni vengono selezionate utilizzando le caselle di controllo. Quando è possibile utilizzare una sola opzione, vengono utilizzati i pulsanti di scelta.

La configurazione corrispondente è la seguente:

![Campo a scelta multipla impostato per consentire selezioni multiple, con 2 selezioni richieste e 4 consentite.](assets/s_ncs_admin_survey_multichoice_ex3.png)

Inoltre, il percorso di archiviazione per questo campo di input deve essere un **campo archiviato** di tipo **[!UICONTROL Multiple values]**:

![Finestra di dialogo Crea nuovo campo archiviato con l&#39;opzione Più valori selezionata per il campo Interests.](assets/s_ncs_admin_survey_multiple_values_field.png)

>[!CAUTION]
>
>* Questa funzionalità è disponibile solo per i moduli di tipo **Sondaggio**.
>* Questa opzione non è compatibile con la visualizzazione casuale delle domande. [Ulteriori informazioni](#adding-questions).

### Aggiungi domande {#adding-questions}

Esistono due tipi di contenitori: standard e domanda. I contenitori Standard vengono utilizzati per configurare il layout di pagina e la visualizzazione condizionale in una pagina. [Ulteriori informazioni](../web/about-web-forms.md).

Utilizza un contenitore **Domanda** per aggiungere una domanda alla pagina e inserire le possibili risposte di seguito nella gerarchia. Le risposte degli utenti alle domande poste in questo tipo di contenitore possono essere analizzate nei rapporti.

>[!CAUTION]
>
>Non inserire mai un contenitore **Domanda** sotto un altro contenitore **Domanda** nella gerarchia.

![Scheda Generale del contenitore delle domande con l&#39;opzione Immetti il titolo in formato HTML selezionata e l&#39;editor di HTML visualizzato.](assets/s_ncs_admin_question_label.png)

L&#39;etichetta della domanda viene immessa nel campo etichetta. In questo caso, verrà applicato lo stile del foglio di stile del modulo. Selezionare l&#39;opzione **[!UICONTROL Enter the title in HTML format]** per personalizzarla. In questo modo potrai accedere all’editor di HTML.

>[!NOTE]
>
>Fai riferimento a [questo documento](../web/about-web-forms.md) per ulteriori informazioni sull&#39;utilizzo dell&#39;editor di HTML.

Ad esempio:

![Struttura ad albero delle pagine con contenitori Domande per il formato e i contratti di posta elettronica e impostazioni della scheda Generale della pagina.](assets/s_ncs_admin_survey_containers_qu_arbo.png)

Nell’esempio precedente, il rendering sarà il seguente:

![Pagina di sondaggio con rendering con campi, elenco a discesa del formato e-mail e domanda con casella di controllo dei contratti.](assets/s_ncs_admin_survey_containers_qu_ex.png)

>[!NOTE]
>
>Ogni domanda ha un contenitore di tipo **Domanda**.

Puoi abilitare il disegno casuale delle domande in Adobe Campaign. È quindi possibile specificare il numero di domande da visualizzare nella pagina, nel campo che si trova nella parte inferiore della finestra di configurazione.

![Scheda Generale pagina con visualizzazione selezionata in modo casuale e numero di domande da visualizzare impostato su 1.](assets/s_ncs_admin_survey_containers_qu_display.png)

Il rendering sarà simile al seguente:

![Pagina sottoposta a rendering contenente solo due domande selezionate in modo casuale, Domanda 2 e Domanda 3, con pulsante Avanti.](assets/s_ncs_admin_survey_containers_qu_display_rendering.png)

Quando la pagina viene aggiornata, le domande visualizzate non sono le stesse.

>[!CAUTION]
>
>Quando si visualizza una domanda in modo casuale (**[!UICONTROL Display randomly]** opzione selezionata nella pagina), fare attenzione a non utilizzare domande a scelta multipla per le quali una o più selezioni sono obbligatorie.
