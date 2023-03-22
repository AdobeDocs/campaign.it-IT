---
title: Analisi della consegna
description: Scopri come preparare e controllare la consegna
feature: Personalization
role: User
level: Beginner
source-git-commit: 8f04981e38da79e69afc890311c559f9ffa136f4
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 5%

---

# Analisi della consegna {#analyze-delivery}

L’analisi è la fase di preparazione della consegna. Può essere avviato una volta definito il pubblico di destinazione e il contenuto del messaggio è pronto e testato. Durante l’analisi della consegna, la popolazione target viene calcolata e il contenuto della consegna viene preparato. Una volta completata, la consegna è pronta per essere inviata.

## Avvia l&#39;analisi {#start-the-analysis}

Per preparare la consegna, accertati che il contenuto e il target della consegna siano stati definiti e segui i passaggi seguenti:

1. Dalle finestre di consegna, fai clic sul pulsante **[!UICONTROL Send]** pulsante .
1. Seleziona **[!UICONTROL Deliver as soon as possible]** per eseguire il calcolo del pubblico e la preparazione dei contenuti per un invio immediato. Puoi anche posticipare la consegna a una data successiva, oppure ottenere una stima della popolazione senza preparare il contenuto.

   ![](assets/delivery-analysis-start.png)

1. Fai clic su **[!UICONTROL Analyze]** per avviare l’analisi manualmente. La barra di avanzamento mostra l’avanzamento dell’analisi.

   Durante l’analisi della consegna viene applicata una serie di regole di controllo. Queste regole sono definite in un **tipologia**, che viene selezionato nella **[!UICONTROL Typology]** nelle proprietà di consegna. Ulteriori informazioni sulle tipologie in [questa sezione](../../automation/campaign-opt/campaign-typologies.md).

   Per impostazione predefinita, per le e-mail l’analisi riguarda i seguenti punti:

   * Approvazione dell’oggetto
   * Approvazione di URL e immagini
   * Approvazione delle etichette URL
   * Approvazione del collegamento di annullamento dell’abbonamento
   * Controllo delle dimensioni delle bozze
   * Controllo del periodo di validità
   * Controllo della programmazione delle onde


1. Per interrompere l’analisi in qualsiasi momento, fai clic sul pulsante **[!UICONTROL Stop]** pulsante .

   Non vengono inviati messaggi durante la fase di preparazione. È quindi possibile avviare o annullare l’analisi senza rischi.

   >[!IMPORTANT]
   >
   >Quando viene eseguita, l’analisi blocca la consegna (o bozza). Ogni modifica della consegna (o prova) deve essere seguita da un&#39;altra analisi prima di diventare applicabile.

Al termine dell’analisi, la sezione superiore della finestra indica se la preparazione della consegna è completa o se si sono verificati degli errori. Vengono elencati tutti i passaggi, le avvertenze e gli errori di convalida. Le icone colorate mostrano il tipo di messaggio:

* Un’icona blu indica un messaggio informativo.
* Un’icona gialla indica un errore di elaborazione non critico.
* Un’icona rossa indica un errore critico che impedisce l’invio della consegna.

   ![](assets/delivery-analysis-results.png){width="800" align="left"}

1. Fai clic su **[!UICONTROL Close]** correggere gli eventuali errori. Dopo aver apportato le modifiche, riavvia l&#39;analisi facendo clic su **[!UICONTROL Analyze]**.

   >[!NOTE]
   >
   >Fai clic sul pulsante **[!UICONTROL Change the main delivery target]** se il numero di messaggi da inviare non corrisponde alle tue aspettative. Questa opzione consente di modificare la definizione della popolazione target e di riavviare l’analisi.

1. Dopo aver controllato il risultato dell’analisi, fai clic su **[!UICONTROL Confirm delivery]** per inviare il messaggio al target principale.


## Impostazioni di analisi {#analysis-settings}

Sfoglia il **[!UICONTROL Analysis]** scheda delle proprietà di consegna per definire le impostazioni per la preparazione dei messaggi durante la fase di analisi.

![](assets/delivery-properties-analysis-tab.png){width="800" align="left"}

Questa scheda consente di accedere alle seguenti opzioni:

* **[!UICONTROL Label and code of the delivery]** : le opzioni di questa sezione vengono utilizzate per calcolare i valori di questi campi durante la fase di analisi della consegna. La **[!UICONTROL Compute the execution folder during the delivery analysis]** calcola il nome della cartella che conterrà questa azione di consegna durante la fase di analisi.

* **[!UICONTROL Approval mode]** : questo campo ti consente di definire la consegna manuale o automatica una volta completata l’analisi.

   Se durante l’analisi vengono generati avvisi (ad esempio, se alcuni caratteri vengono accentuati nell’oggetto della consegna, ecc.), puoi configurare la consegna per definire se deve ancora essere eseguita o meno. Per impostazione predefinita, l’utente deve confermare l’invio di messaggi al termine della fase di analisi: si tratta di convalida **manuale**.

   Seleziona un’altra modalità di approvazione dall’elenco a discesa nel campo appropriato.

   Sono disponibili le seguenti modalità di omologazione:

   * **[!UICONTROL Manual]**: Al termine della fase di analisi, l’utente deve confermare la consegna per iniziare l’invio. A questo scopo, fai clic sul pulsante **[!UICONTROL Start]** per avviare la consegna.
   * **[!UICONTROL Semi-automatic]**: L’invio inizia automaticamente se la fase di analisi non genera messaggi di avviso.
   * **[!UICONTROL Automatic]**: L’invio inizia automaticamente al termine della fase di analisi, indipendentemente dal risultato.

* **[!UICONTROL Start job in a detached process]** : questa opzione ti consente di avviare l’analisi della consegna in un processo separato. Per impostazione predefinita, la funzione di analisi utilizza il processo dell’application server (web nlserver) di Adobe Campaign. Selezionando questa opzione, assicurati che l’analisi venga completata anche in caso di errore dell’application server.
* **[!UICONTROL Log SQL queries generated during the analysis in the journal]** : questa opzione aggiunge i registri di query SQL al giornale di registrazione consegne durante la fase di analisi.
* **[!UICONTROL Ignore personalization scripts during sending]** : questa opzione consente di ignorare l’interpretazione delle direttive JavaScript presenti nel contenuto di HTML. Saranno visualizzati così come sono nel contenuto consegnato. Queste direttive sono introdotte con `<%=` tag .


