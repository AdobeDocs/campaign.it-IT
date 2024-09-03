---
title: Analisi della consegna
description: Scopri come preparare e controllare la consegna
feature: Personalization
role: User
level: Beginner
exl-id: 1526048d-9f02-4853-948f-8fb618670dbd
source-git-commit: 69ff08567f3a0ab827a118a089495fc75bb550c5
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 5%

---

# Analisi della consegna {#analyze-delivery}

L’analisi è il passaggio di preparazione della consegna. Può essere avviato una volta definito il pubblico target e testato il contenuto del messaggio. Durante l’analisi della consegna, viene calcolata la popolazione target e viene preparato il contenuto della consegna. Una volta completata, la consegna è pronta per essere inviata.

## Avviare l’analisi {#start-the-analysis}

Per preparare la consegna, assicurati che il contenuto e il target della consegna siano stati definiti e segui i passaggi seguenti:

1. Dalle finestre di consegna, fare clic sul pulsante **[!UICONTROL Send]**.
1. Selezionare **[!UICONTROL Deliver as soon as possible]** per eseguire il calcolo del pubblico e la preparazione del contenuto per un invio immediato. Puoi anche posticipare la consegna a una data successiva, oppure ottenere una stima della popolazione senza preparare il contenuto.

   ![](assets/delivery-analysis-start.png)

1. Fare clic su **[!UICONTROL Analyze]** per avviare l&#39;analisi manualmente. La barra di avanzamento mostra lo stato di avanzamento dell’analisi.

   Durante l’analisi della consegna viene applicata una serie di regole di controllo. Queste regole sono definite in una **tipologia**, selezionata nella scheda **[!UICONTROL Typology]** nelle proprietà di consegna. Ulteriori informazioni sulle tipologie in [questa sezione](../../automation/campaign-opt/campaign-typologies.md).

   Per impostazione predefinita, per le e-mail, l’analisi tratta i seguenti punti:

   * Approvazione dell&#39;oggetto
   * Approvazione di URL e immagini
   * Approvazione delle etichette URL
   * Approvazione del collegamento di annullamento dell’abbonamento
   * Controllo della dimensione delle bozze
   * Verifica del periodo di validità
   * Controllo della programmazione delle ondate


1. È possibile interrompere l&#39;analisi in qualsiasi momento facendo clic sul pulsante **[!UICONTROL Stop]**.

   Durante la fase di preparazione non vengono inviati messaggi. È quindi possibile avviare o annullare l’analisi senza rischi.

   >[!IMPORTANT]
   >
   >Durante l’esecuzione, l’analisi blocca la consegna (o la bozza). Eventuali modifiche alla consegna (o alla prova) devono essere seguite da un’altra analisi prima di diventare applicabili.

   Al termine dell’analisi, la sezione superiore della finestra indica se la preparazione della consegna è completa o se si sono verificati errori. Vengono elencati tutti i passaggi, le avvertenze e gli errori di convalida. Le icone colorate mostrano il tipo di messaggio:

   * Un’icona blu indica un messaggio informativo.
   * Un&#39;icona gialla indica un errore di elaborazione non critico.
   * Un’icona rossa indica un errore critico che impedisce l’invio della consegna.

   ![](assets/delivery-analysis-results.png){width="800" align="left"}

1. Fare clic su **[!UICONTROL Close]** per correggere gli eventuali errori. Dopo aver apportato le modifiche, riavviare l&#39;analisi facendo clic su **[!UICONTROL Analyze]**.

   >[!NOTE]
   >
   >Fare clic sul collegamento **[!UICONTROL Change the main delivery target]** se il numero di messaggi da inviare non corrisponde alle aspettative. Questa opzione consente di modificare la definizione della popolazione target e riavviare l’analisi.
   >

1. Dopo aver verificato il risultato dell&#39;analisi, fare clic su **[!UICONTROL Confirm delivery]** per inviare il messaggio alla destinazione principale.


## Impostazioni analisi {#analysis-settings}

Passa alla scheda **[!UICONTROL Analysis]** delle proprietà di consegna per definire le impostazioni per la preparazione dei messaggi durante la fase di analisi.

![](assets/delivery-properties-analysis-tab.png){width="800" align="left"}

Questa scheda consente di accedere alle seguenti opzioni:

* **[!UICONTROL Label and code of the delivery]**: le opzioni di questa sezione vengono utilizzate per calcolare i valori di questi campi durante la fase di analisi della consegna. Il campo **[!UICONTROL Compute the execution folder during the delivery analysis]** calcola il nome della cartella che conterrà questa azione di consegna durante la fase di analisi.

* **[!UICONTROL Approval mode]**: questo campo consente di definire la consegna manuale o automatica una volta completata l&#39;analisi.

  Se durante l’analisi vengono generati avvisi (ad esempio, se determinati caratteri sono accentuati nell’oggetto della consegna, ecc.), puoi configurare la consegna per definire se deve ancora essere eseguita. Per impostazione predefinita, l’utente deve confermare l’invio di messaggi al termine della fase di analisi: si tratta di convalida **manuale**.

  Seleziona un’altra modalità di approvazione dall’elenco a discesa nel campo appropriato.

  Sono disponibili le seguenti modalità di approvazione:

   * **[!UICONTROL Manual]**: al termine della fase di analisi, l&#39;utente deve confermare la consegna per iniziare l&#39;invio. A tale scopo, fare clic sul pulsante **[!UICONTROL Start]** per avviare la consegna.
   * **[!UICONTROL Semi-automatic]**: l&#39;invio inizia automaticamente se la fase di analisi non genera messaggi di avviso.
   * **[!UICONTROL Automatic]**: l&#39;invio inizia automaticamente alla fine della fase di analisi indipendentemente dal risultato.

* **[!UICONTROL Start job in a detached process]**: questa opzione consente di avviare l&#39;analisi della consegna in un processo separato. Per impostazione predefinita, la funzione di analisi utilizza il processo del server applicazioni di Adobe Campaign (web nlserver). Selezionando questa opzione, l&#39;analisi verrà completata anche in caso di errore del server applicazioni.
* **[!UICONTROL Log SQL queries generated during the analysis in the journal]**: questa opzione aggiunge i registri di query SQL al giornale di registrazione di consegna durante la fase di analisi.
* **[!UICONTROL Ignore personalization scripts during sending]**: questa opzione consente di ignorare l&#39;interpretazione delle direttive di JavaScript presenti nel contenuto di HTML. Vengono visualizzati così come sono nel contenuto consegnato. Queste direttive sono state introdotte con il tag `<%=`.
