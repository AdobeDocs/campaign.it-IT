---
product: campaign
title: Inviare un rapporto a un elenco
description: Scopri come inviare un rapporto a un elenco con un flusso di lavoro
feature: Workflows
exl-id: 5bc576d0-cab7-4d26-a3a5-91982a00e356
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 3%

---

# Inviare un rapporto a un elenco{#send-a-report-to-a-list}

Questo caso d’uso descrive come generare una versione preconfigurata mensile **[!UICONTROL Tracking indicators]** rapporto in formato PDF e come inviarlo a un elenco di destinatari.

![](assets/use_case_report_intro.png)

I passaggi principali di implementazione per questo caso d’uso sono:

* Crea un elenco di destinatari per questo report. [Ulteriori informazioni](#step-1--create-the-recipient-list).
* Crea un modello di consegna che crea una nuova consegna ogni volta che viene eseguito il flusso di lavoro. [Ulteriori informazioni](#step-2--create-the-delivery-template).
* Crea un flusso di lavoro che genera il rapporto in formato PDF e lo invia all’elenco dei destinatari. [Ulteriori informazioni](#step-3--create-the-workflow)).

## Passaggio 1: creare l’elenco dei destinatari {#step-1--create-the-recipient-list}

Per creare l’elenco dei destinatari target, effettua le seguenti operazioni:

1. Accedi a **[!UICONTROL Profiles and targets]** , fare clic sulla scheda **[!UICONTROL Lists]** collegamento.
1. Fai clic sul pulsante **[!UICONTROL Create]**.
1. Seleziona **[!UICONTROL New list]** e crea un nuovo elenco di destinatari al quale inviare il rapporto.

Per ulteriori informazioni sulla creazione di elenchi, consulta [questa sezione](../../v8/audiences/create-audiences.md).

## Passaggio 2: creare il modello di consegna {#step-2--create-the-delivery-template}

Per creare il modello di consegna, segui i passaggi seguenti:

1. Accedi a **[!UICONTROL Resources > Templates > Delivery templates]** dell&#39;Adobe Campaign explorer e duplicare il **[!UICONTROL Email delivery]** modello incorporato.

   Per ulteriori informazioni sulla creazione di un modello di consegna, consulta [questa sezione](../../v8/send/create-templates.md).

1. Immetti i parametri del modello: etichetta, destinazione (l’elenco dei destinatari creati in precedenza), oggetto e contenuto.

   Ogni volta che il flusso di lavoro viene eseguito, il **[!UICONTROL Tracking indicators]** il rapporto viene aggiornato come spiegato in [Passaggio 3: creare il flusso di lavoro](#step-3--creating-the-workflow)).

1. Per includere nella consegna la versione più recente del rapporto, è necessario aggiungere una **[!UICONTROL Calculated attachment]**:

   * Fai clic su **[!UICONTROL Attachments]** e fai clic sulla freccia accanto al **[!UICONTROL Add]** pulsante. Seleziona **[!UICONTROL Calculated attachment...]**.

     ![](assets/use_case_report_4.png)

   * In **[!UICONTROL Type]** , seleziona l’opzione più recente: **[!UICONTROL File name is computed during delivery of each message (it may then depend on the recipient profile)]**.

     ![](assets/use_case_report_5.png)

     Il valore immesso nel **[!UICONTROL Label]** non verrà visualizzato nella consegna finale.

   * Nell&#39;area di testo immettere il percorso di accesso e il nome del file.

     ![](assets/use_case_report_6.png)

     >[!CAUTION]
     >
     >Il percorso e il nome devono essere identici a quelli immessi nella **[!UICONTROL JavaScript code]** tipo di attività del flusso di lavoro, come spiegato in [Passaggio 3: creare il flusso di lavoro](#step-3--creating-the-workflow).

   * Seleziona la **[!UICONTROL Advanced]** Tab e check **[!UICONTROL Script the name of the file name displayed in the mails sent]**. Nell’area di testo, immetti il nome dell’allegato nella consegna finale.

     ![](assets/use_case_report_6b.png)

## Passaggio 3: creare il flusso di lavoro {#step-3--creating-the-workflow}

Crea il seguente flusso di lavoro per questo caso d’uso.

![](assets/use_case_report_8.png)

Utilizza tre attività:

* A **[!UICONTROL Scheduler]** attività che esegue il flusso di lavoro una volta al mese,
* A **[!UICONTROL JavaScript code]** attività che genera il rapporto in formato PDF,
* A **[!UICONTROL Delivery]** attività che fa riferimento al modello di consegna creato in precedenza.

Per creare questo flusso di lavoro, effettua le seguenti operazioni:

1. Accedi a **[!UICONTROL Administration > Production > Technical workflows]** esplora il nodo di Campaign e crea una nuova cartella in cui archiviare i flussi di lavoro.
1. Crea un nuovo flusso di lavoro.

   ![](assets/use_case_report_7.png)

1. Per iniziare, aggiungi un **[!UICONTROL Scheduler]** digita l’attività e configurala in modo che il flusso di lavoro venga eseguito il primo lunedì del mese.

   ![](assets/use_case_report_9.png)

   Per ulteriori informazioni sulla configurazione della pianificazione, consulta [Scheduler](scheduler.md).

1. Quindi aggiungi **[!UICONTROL JavaScript code]** attività di tipo.

   ![](assets/use_case_report_10.png)

   Immetti il seguente codice nella zona di modifica:

   ```sql
   var reportName = "indicators";
   var path = "/tmp/indicators.pdf";
   var exportFormat = "PDF";
   var reportURL = "<PUT THE URL OF THE REPORT HERE>";
   var _ctx = <ctx _context="global" _reportContext="deliveryFeedback" />
   var isAdhoc = 0;
   
   xtk.report.export(reportName, _ctx, exportFormat, path, isAdhoc);
   ```


   con le seguenti variabili:

   * **var reportName**: inserisci il nome interno del rapporto tra virgolette. In questo caso, il nome interno del **Indicatore di tracciamento** report è &quot;deliveryFeedback&quot;.
   * **percorso var**: immetti il percorso di salvataggio del file (&quot;tmp&quot;), il nome che desideri assegnare al file (&quot;deliveryFeedback&quot;) e l’estensione (&quot;.pdf&quot;). In questo caso, abbiamo utilizzato il nome interno come nome del file. I valori devono essere compresi tra virgolette doppie e separati dal carattere &quot;+&quot;.

     >[!CAUTION]
     >
     >Il file deve essere salvato sul server. È necessario immettere lo stesso percorso e lo stesso nome del file **[!UICONTROL General]** scheda della finestra di modifica per l&#39;allegato calcolato, come descritto [qui](#step-2--create-the-delivery-template)).

   * **var exportFormat**: inserisci il formato di esportazione del file (&quot;PDF&quot;).
   * **var_ctx** (contesto): in questo caso utilizziamo il **[!UICONTROL Tracking indicators]** nel suo contesto globale.

1. Termina aggiungendo un **[!UICONTROL Delivery]** attività con le seguenti opzioni:

   ![](assets/use_case_report_11.png)

   * **[!UICONTROL Delivery]**: seleziona **[!UICONTROL New, created from a template]** e seleziona il modello di consegna creato in precedenza.
   * Per **[!UICONTROL Recipients]** e **[!UICONTROL Content]** campi, seleziona **[!UICONTROL Specified in the delivery]**.
   * **[!UICONTROL Action to perform]**: seleziona **[!UICONTROL Prepare and start]**.
   * Deseleziona la **[!UICONTROL Generate an outbound transition]** e **[!UICONTROL Process errors]** opzioni.

1. Salva le modifiche e avvia il workflow. Il messaggio viene inviato all’elenco dei destinatari ogni primo lunedì del mese, con il rapporto allegato.
