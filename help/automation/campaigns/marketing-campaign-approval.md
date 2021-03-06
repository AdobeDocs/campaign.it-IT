---
product: campaign
title: Impostare e gestire il processo di approvazione
description: Scopri come gestire le approvazioni delle campagne di marketing
feature: Approvals, Campaigns
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '2272'
ht-degree: 2%

---

# Impostare e gestire il processo di approvazione {#approval-marketing-campaigns}

I metodi e le persone che partecipano alla creazione e all’approvazione di campagne di marketing sono specifici per ciascuna organizzazione. Il processo di approvazione della campagna comporta il coordinamento di più parti interessate: gli addetti al marketing digitale, i responsabili della distribuzione, i responsabili dei contenuti e i proprietari esterni come partner o fornitori.

Con Adobe Campaign puoi impostare un flusso di approvazione per le campagne e avvisare gli operatori quando è necessaria un’azione. Puoi definire approvazioni per ogni fase di una consegna: targeting, contenuto, budget, estrazione e invio di prove. Man mano che le consegne della campagna attraversano i vari passaggi di convalida, in Adobe Campaign viene compilata una cronologia delle modifiche e delle autorizzazioni, tra cui feedback, commenti, richieste di modifica e commenti.

I messaggi di notifica vengono inviati agli operatori Adobe Campaign designati come revisori per informarli di una richiesta di approvazione.


Gli operatori possono approvare in diversi modi:

* Dal messaggio di notifica. Il collegamento presente nell’e-mail porta l’operatore su Campaign tramite un browser web. Dopo la connessione, il revisore può scegliere se approvare o meno il contenuto.
   ![](assets/approval-content-email.png)

* Dal dashboard della campagna.
   ![](assets/approval-from-dashboard.png)

* Dal dashboard di consegna.
   ![](assets/approval-from-delivery-dashboard.png)

Gli operatori possono accedere alla campagna e alla consegna dalla finestra di approvazione. Possono anche inserire un commento.

![](assets/approval-target-confirm.png)

Una volta convalidata l’operatore, le informazioni vengono visualizzate nei dashboard della campagna e della consegna e nei registri.

![](assets/approvals-from-delivery.png)

Le informazioni sono disponibili anche nei registri di approvazione della consegna e nel giornale di registrazione approvazione della campagna. Questi registri sono accessibili tramite il **[!UICONTROL Edit > Audit > Approvals]** schede.

![](assets/approval-logs.png)


## Abilita approvazioni{#enable-approvals}

Le notifiche di approvazione vengono inviate agli operatori interessati a ciascun processo per il quale è stata abilitata l’approvazione.

Possono essere abilitati per il modello di campagna, per ogni campagna singolarmente o per una consegna.

Tutti i processi che richiedono l’approvazione vengono selezionati nel modello della campagna, tramite  **[!UICONTROL Properties]** > **[!UICONTROL Advanced campaign parameters...]** > **[!UICONTROL Approvals]** scheda . Revisori o gruppi di revisori sono selezionati da questa scheda. Essi ricevono notifiche, a meno che questa opzione non sia abilitata. [Ulteriori informazioni](#approving-processes).

Puoi sovrascrivere queste impostazioni per ogni campagna creata utilizzando questo modello e singolarmente per ogni consegna. Sfoglia il **[!UICONTROL Properties]** pulsante della consegna, quindi **[!UICONTROL Approvals]** scheda .

Nell’esempio seguente, il contenuto di consegna non richiederà approvazioni:

![](assets/approval-not-enabled.png)


>[!CAUTION]
>
>Controlla che i revisori abbiano **autorizzazioni appropriate** per l’approvazione e che la relativa zona di sicurezza sia definita correttamente. [Ulteriori informazioni](#selecting-reviewers).

Il processo di approvazione per le consegne è descritto in [questa sezione](#review-and-approve-deliveries).

## Seleziona revisori {#select-reviewers}

Per ciascun tipo di omologazione, gli operatori o i gruppi di operatori incaricati dell’omologazione sono selezionati dall’elenco a discesa nella consegna. È possibile aggiungere altri operatori utilizzando **[!UICONTROL Edit...]** link. Questa finestra consente inoltre di modificare la scadenza dell&#39;approvazione. Per impostazione predefinita, i revisori dispongono di tre giorni a partire dalla data di invio per approvare un processo. Per aggiungere un promemoria automatico, utilizza la **[!UICONTROL Add a reminder]** link.

![](assets/add-reviewers.png)

Se non viene specificato alcun revisore, il proprietario della campagna è responsabile delle approvazioni e riceve le notifiche. Il proprietario della campagna è specificato nel **[!UICONTROL Edit > Properties]** scheda della campagna:

![](assets/campaign-owner.png)

Tutti gli altri operatori Adobe Campaign con **[!UICONTROL Administrator]** I diritti possono anche approvare i lavori, ma non ricevono notifiche.

>[!NOTE]
>
>Per impostazione predefinita, il proprietario della campagna non può eseguire l’approvazione o avviare le consegne se gli operatori di approvazione sono stati definiti. In qualità di amministratore di Adobe Campaign, puoi modificare questo comportamento e consentire ai proprietari delle campagne di approvare/avviare le consegne creando il **NmsCampaign_Activate_OwnerConfirmation** opzione, imposta su **1**.


Se è definito un elenco di revisori, un processo viene approvato quando un revisore lo ha approvato. Il collegamento di approvazione non è più disponibile nei dashboard di campagna e consegna. Quando l’invio di notifiche è abilitato, se un altro revisore fa clic sul collegamento di approvazione nel messaggio di notifica, viene informato che un altro operatore ha già approvato il processo.

![](assets/delivery-target-already-approved.png)


## Revisione e approvazione delle consegne {#review-and-approve-deliveries}

Per ogni campagna puoi approvare il target di consegna, [contenuto di consegna](#approving-content) e i costi. Gli operatori di Adobe Campaign incaricati dell’approvazione possono ricevere una notifica tramite e-mail e accettare o rifiutare l’approvazione dalla console o tramite una connessione web. [Ulteriori informazioni](#approving-processes).

Per le consegne di direct mailing, gli operatori Adobe Campaign possono visualizzare il file di estrazione prima che venga inviato al router e, se necessario, possono modificare il formato e riavviare l’estrazione. [Ulteriori informazioni](#approve-an-extraction-file).

Una volta completate queste fasi di convalida, è possibile avviare la consegna. [Ulteriori informazioni](marketing-campaign-deliveries.md#starting-a-delivery).

>[!NOTE]
>
>I processi che richiedono un’approvazione vengono selezionati nel modello della campagna. [Ulteriori informazioni](marketing-campaign-templates.md).

### Passaggi per approvare una consegna {#approving-processes}

Le fasi che richiedono l’approvazione vengono visualizzate nel dashboard della campagna (tramite la console o l’interfaccia web). Vengono inoltre visualizzati nella tabella di tracciamento della consegna e nel dashboard di consegna.

![](assets/delivery-approval-actions.png)

Per ogni consegna nella campagna, puoi approvare i seguenti processi:

* **Targeting, contenuto e budget**

   Quando il **[!UICONTROL Enable target approval]**, **[!UICONTROL Enable content approval]** o **[!UICONTROL Enable budget approval]** le opzioni sono selezionate nella finestra delle impostazioni di approvazione, i relativi collegamenti sono visualizzati nelle dashboard della campagna e della consegna.

   ![](assets/template-activate-6.png)

   >[!NOTE]
   >
   >L&#39;approvazione del budget è disponibile solo se l&#39;approvazione del target è abilitata nella finestra delle impostazioni di approvazione. Il collegamento per l&#39;approvazione del budget viene visualizzato solo dopo l&#39;analisi del target.

   Se la **[!UICONTROL Assign content editing]** o **[!UICONTROL External content approval]** le opzioni sono selezionate nella finestra delle impostazioni di approvazione, il dashboard mostrerà **[!UICONTROL Available content]** e **[!UICONTROL External content approval]** link.

   L’approvazione del contenuto ti consente di accedere alle bozze inviate.

* **Approvazione estrazione (consegna direct mailing)**

   Quando **[!UICONTROL Enable extraction approval]** è selezionato nella finestra delle impostazioni di approvazione, il file estratto deve essere approvato prima che il router possa essere notificato.

   La **[!UICONTROL Approve file]** nelle dashboard della campagna e della consegna è disponibile l’opzione .

   ![](assets/approve-file-preview.png)

   È possibile visualizzare in anteprima il file di output prima della convalida. L’anteprima del file di estrazione mostra solo un esempio di dati. L&#39;intero file non viene caricato.

* **Approvazione delle consegne associate**

   La **[!UICONTROL Enable individual approval of each associated delivery]** viene utilizzata per una consegna principale associata alle consegne secondarie. Per impostazione predefinita, questa opzione non è selezionata in modo da poter eseguire un&#39;approvazione globale della consegna principale. Se questa opzione è selezionata, ogni consegna deve essere approvata singolarmente.

   ![](assets/enable-ind-approval.png)


>[!NOTE]
>
>In un flusso di lavoro di targeting, se si verifica un errore collegato a un problema di configurazione durante la preparazione dei messaggi, il **[!UICONTROL Restart message preparation]** il collegamento viene visualizzato sul dashboard. Correggi l’errore e utilizza questo collegamento per riavviare la preparazione dei messaggi ignorando la fase di targeting.


### Approvare un contenuto {#approve-content}

>[!CAUTION]
>
>Per approvare un contenuto, è obbligatorio un ciclo di prova. Le bozze consentono di approvare la visualizzazione di informazioni, dati di personalizzazione e verificare che i collegamenti funzionino.
>
>Le funzionalità di approvazione dei contenuti descritte di seguito si riferiscono alla consegna delle prove.

È possibile configurare un ciclo di approvazione dei contenuti. A questo scopo, seleziona la **[!UICONTROL Enable content approval]** nella finestra delle impostazioni di approvazione. Le fasi principali del ciclo di approvazione dei contenuti sono:

1. Dopo aver creato una nuova consegna, il gestore della campagna fa clic su **[!UICONTROL Submit content]** link nel dashboard della campagna per avviare il ciclo di approvazione dei contenuti.

   >[!NOTE]
   >
   >Se la **[!UICONTROL Enable the sending of proofs]** (per le consegne e-mail) o **[!UICONTROL Enable the sending and approval of proofs]** (per le consegne di direct mailing) le opzioni selezionate nella finestra delle impostazioni di approvazione vengono inviate automaticamente le bozze.

1. Viene inviata un’e-mail di notifica alla persona responsabile del contenuto, che può scegliere se approvarla o meno:

   * tramite e-mail di notifica: l’e-mail di notifica contiene un collegamento alle bozze già inviate ed eventualmente a un rendering del messaggio per le varie e-mail web se la **Consegna** add-on è abilitato per questa istanza.

   * tramite la console o l’interfaccia web, il tracciamento della consegna, il dashboard di consegna o il dashboard della campagna. Questo dashboard della campagna consente di visualizzare l’elenco delle bozze inviate, facendo clic sul pulsante **[!UICONTROL Inbox rendering...]** link. Per visualizzarne il contenuto, fai clic sul pulsante **[!UICONTROL Detail]** a destra dell’elenco.

1. Viene inviata un’e-mail di notifica alla persona responsabile della campagna per informarla dell’approvazione o meno del contenuto. Il responsabile della campagna può riavviare il ciclo di approvazione dei contenuti in qualsiasi momento. A questo scopo, fai clic sul collegamento nel **[!UICONTROL Content status]** linea del dashboard della campagna (a livello di consegna), quindi fai clic su **[!UICONTROL Reset content approval to submit it again]**.

#### Assegnare la modifica del contenuto {#assign-content-editing}

Questa opzione ti consente di definire un utente responsabile della modifica dei contenuti, ad esempio un webmaster. Se la **[!UICONTROL Assign content editing]** nella finestra delle impostazioni di approvazione viene selezionata l’opzione , vengono aggiunti diversi passaggi di approvazione tra la creazione della consegna e la consegna dell’e-mail di notifica alla persona responsabile del contenuto:

1. Dopo aver creato una nuova consegna, la persona responsabile della campagna fa clic sul pulsante **[!UICONTROL Submit content editing]** nel dashboard della campagna per avviare il ciclo di modifica dei contenuti.

1. Il responsabile della modifica dei contenuti riceverà un’e-mail in cui informa che il contenuto è disponibile.

1. Possono quindi accedere alla console, aprire la consegna e modificarla utilizzando una procedura guidata semplificata per modificare l’oggetto, HTML e il contenuto del testo e inviare bozze.

   >[!NOTE]
   >
   >Se la **[!UICONTROL Enable the sending of proofs]** (per le consegne e-mail) o **[!UICONTROL Enable the sending and approval of proofs]** (per le consegne di direct mailing) le opzioni selezionate nella finestra delle impostazioni di approvazione vengono inviate automaticamente le bozze.

1. Una volta che il responsabile della modifica dei contenuti ha terminato di apportare modifiche al contenuto della consegna, può rendere disponibile il contenuto.

   A questo scopo, possono utilizzare:

   * la **[!UICONTROL Available content]** nella console Adobe Campaign.
   * il collegamento nel messaggio di notifica.
L’operatore può aggiungere un commento prima di inviare il contenuto alla persona responsabile della campagna.
Il messaggio di notifica consente al revisore di approvare o rifiutare il contenuto.

#### Approvazione dei contenuti esterni {#external-content-approval}

Questa opzione ti consente di definire un operatore esterno incaricato di approvare il rendering della consegna, ad esempio la coerenza della comunicazione del brand, i tassi, ecc. Quando il **[!UICONTROL External content approval]** nella finestra delle impostazioni di approvazione viene selezionata l’opzione , vengono aggiunti diversi passaggi di approvazione tra l’approvazione del contenuto e la consegna della notifica alla persona responsabile della campagna:

1. Il gestore dei contenuti esterni riceve un messaggio e-mail di notifica in cui viene indicato che il contenuto è stato approvato e richiede l’approvazione esterna.
1. L’e-mail di notifica contiene collegamenti alle bozze inviate, che consentono di visualizzare il rendering della consegna, e un pulsante per approvare o rifiutare il contenuto della consegna.

Questi collegamenti sono disponibili solo se sono state inviate una o più bozze. In caso contrario, il rendering della consegna è disponibile solo tramite la console o l’interfaccia web.

### Approvare un file di estrazione {#approve-an-extraction-file}

Per le consegne offline, Adobe Campaign genera un file di estrazione che, a seconda della configurazione, viene inviato al router. Il relativo contenuto dipende dal modello di esportazione utilizzato.

Quando il contenuto, il targeting e il budget sono stati approvati, la consegna cambia in **[!UICONTROL Extraction pending]** fino all’avvio del flusso di lavoro di estrazione per le campagne.

Alla data della richiesta di estrazione, il file di estrazione viene creato e lo stato di consegna cambia in **[!UICONTROL File to approve]**.

Puoi visualizzare il contenuto del file estratto (facendo clic sul suo nome), approvarlo o, se necessario, modificarne il formato e riavviare l’estrazione utilizzando i collegamenti presenti nel dashboard.

Una volta approvato il file, è possibile inviare l&#39;e-mail di notifica al router. [Ulteriori informazioni](marketing-campaign-deliveries.md#start-an-offline-delivery).

## Modalità di approvazione {#approval-modes}

I processi possono essere approvati nel dashboard della campagna, nella scheda di tracciamento della consegna, nel dashboard di consegna o nella notifica e-mail inviata ai revisori.

### Approva nel dashboard {#approval-via-the-dashboard}

Per approvare un processo tramite la console o l’interfaccia Web, fai clic sul collegamento appropriato nel dashboard della campagna.

Ad esempio, una volta eseguita l’analisi della consegna:

1. Seleziona **[!UICONTROL Approve targeting]**.

![](assets/target-validation-from-console.png)

1. Nella finestra a comparsa, controlla le informazioni da approvare.
1. Seleziona **[!UICONTROL Accept]** o **[!UICONTROL Reject]** e, se necessario, inserisci un commento. Questo commento verrà visualizzato nei registri di convalida.
1. Conferma la tua scelta con **[!UICONTROL Target approval]** pulsante .

![](assets/confirm-validation-from-console.png)


Se un processo è già stato approvato da un altro operatore, il collegamento di approvazione non è disponibile.

Se un processo è stato rifiutato, le informazioni vengono visualizzate nel dashboard di consegna come segue:

![](assets/target-approval-rejected.png)


### Approva dai messaggi di notifica {#approval-via-notification-messages}

Per approvare un processo dal [messaggio di notifica](#notifications):

1. Fai clic sul collegamento nella notifica.
1. Accedi ad Adobe Campaign.
1. Controllare le informazioni da approvare
1. Seleziona **[!UICONTROL Accept]** o **[!UICONTROL Reject]** e, se necessario, inserisci un commento.
1. Convalidare. Le scelte e i commenti vengono visualizzati nei registri di convalida.

>[!NOTE]
>
>Se durante il processo sono stati generati avvisi, nella notifica viene visualizzato un avviso.

### Tracciare l’approvazione{#approval-tracking}

I registri di approvazione sono disponibili nell’interfaccia utente:

* Nel registro di approvazione della campagna, **[!UICONTROL Approvals]** sottoscheda della **[!UICONTROL Edit > Audit]** scheda:

   ![](assets/approval-tracking-from-campaign.png)

* Nel registro di consegna della campagna, **[!UICONTROL Deliveries]** sottoscheda della **[!UICONTROL Edit > Audit]** scheda:

   ![](assets/approval-tracking-from-campaign-deliveries.png)

* Lo stato di approvazione per ogni consegna può essere visualizzato facendo clic sul pulsante **[!UICONTROL Hide/display logs]** opzione **[!UICONTROL Summary]** scheda .

   ![](assets/approval-tracking-delivery-dashboard.png)

* Queste informazioni sono accessibili anche tramite il **[!UICONTROL Audit > Approvals]** scheda di ogni consegna:

   ![](assets/approval-tracking-delivery-tab.png)

>[!NOTE]
>
>Una volta che un operatore ha approvato o rifiutato un lavoro, gli altri revisori non possono più modificarlo.

### Approvazioni automatiche/manuali {#automatic-and-manual-approval}

Quando crei un flusso di lavoro di targeting, se l’approvazione è automatica (modalità predefinita), Adobe Campaign visualizza il collegamento di approvazione o invia una notifica non appena è richiesta un’approvazione.

Per scegliere la modalità di approvazione (manuale o automatica), fare clic sul pulsante **[!UICONTROL Edit > Properties]** scheda del modello di campagna o campagna, quindi fai clic su **[!UICONTROL Advanced campaign parameters...]** e infine **[!UICONTROL Approvals]** scheda .
par
![](assets/approval-mode.png)

>[!NOTE]
>
>La modalità di approvazione si applica a tutte le consegne della campagna.

Quando viene generato un flusso di lavoro di targeting, l’approvazione manuale consente di evitare la creazione di collegamenti di approvazione o l’invio automatico di notifiche. Il dashboard della campagna offre quindi un **[!UICONTROL Submit targeting for approval]** per avviare manualmente il processo di approvazione.

Un messaggio di conferma ti consente di autorizzare le approvazioni sui processi selezionati per questa consegna.

I pulsanti di approvazione vengono quindi visualizzati sul dashboard della campagna (per questa consegna), sul dashboard di consegna e nel tracciamento della consegna. Se le notifiche sono abilitate, verranno inviate in parallelo.

Questo metodo di abilitazione delle approvazioni consente di utilizzare il targeting senza inviare notifiche spurie ai revisori.

## Notifiche {#notifications}

Le notifiche sono messaggi e-mail specifici inviati ai revisori per informarli che un processo è in attesa di approvazione. Quando l’operatore fa clic sul collegamento nel messaggio, viene visualizzata una pagina di autenticazione e, dopo l’accesso, l’operatore può visualizzare le informazioni e approvare o rifiutare il processo. È inoltre possibile inserire un commento nella finestra di approvazione.

Il contenuto delle e-mail di notifica può essere personalizzato. Vedi [Contenuto della notifica](#notification-content).

### Attiva/Disattiva notifica {#enabling-disabling-notification}

Per impostazione predefinita, i messaggi di notifica vengono inviati se l’approvazione del processo correlato è abilitata nel modello di campagna, nella campagna o nella consegna. Tuttavia, le notifiche possono essere disattivate per autorizzare solo le approvazioni dalla console.

A questo scopo, modifica la finestra di approvazione della campagna o del modello di campagna ( **[!UICONTROL Edit > Properties]** > **[!UICONTROL Advanced campaign parameters...]** > **[!UICONTROL Approvals]** e seleziona **[!UICONTROL Do not enable notification sending]**.

![](assets/enable-disable-notifications.png)

### Contenuto della notifica {#notification-content}

Il contenuto delle notifiche è definito in un modello specifico: **[!UICONTROL Notification of validations for the marketing campaign]**. Questo modello viene salvato nella **[!UICONTROL Administration > Campaign management > Technical delivery templates]** della struttura Adobe Campaign.
