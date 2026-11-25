---
product: campaign
title: 'Casi d’uso: moduli web'
description: 'Casi d’uso: moduli web'
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: 7aa4646d-1325-47c2-b553-6fe375c48973
TQID: 'https://experienceleague.adobe.com/Zw-cfoQrq1PAe-swZ7gvMNyTb4ciCMF2kdT7fN2zLsg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
  - id: e739ee2b-6228-412e-878f-45de0791417d
    internal-label: Use cases
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '1451'
ht-degree: 0%
---
# Casi d’uso: moduli web{#use-cases-web-forms}



## Creare un modulo di abbonamento con doppio consenso {#create-a-subscription--form-with-double-opt-in}

Quando offri servizi di informazione, i destinatari devono iscriversi per ricevere tutte le comunicazioni collegate. Per evitare comunicazioni improprie e assicurarti che il destinatario si sia iscritto intenzionalmente, ti consigliamo di inviare una richiesta di conferma dell’abbonamento per creare un doppio consenso. L’abbonamento sarà effettivo solo dopo che l’utente avrà fatto clic sul collegamento incluso nel messaggio di conferma.

Questo esempio si basa sullo scenario seguente:

1. Creazione di un modulo di abbonamento a una newsletter su un sito Web che contiene una casella di controllo per l’abbonamento a un servizio temporaneo. Questo servizio consente di inviare messaggi di conferma dell&#39;abbonamento.
1. Creazione della consegna di conferma dell’abbonamento con un modello di consegna collegato al modulo web. Contiene il collegamento di conferma che richiama il modulo per l’abbonamento alla newsletter e visualizza un messaggio di approvazione dell’abbonamento.

### Passaggio 1: creazione di servizi informativi {#step-1---creating-information-services}

1. Crea il servizio di abbonamento alla newsletter da offrire ai destinatari. Per ulteriori informazioni su come creare una newsletter, consulta [questa sezione](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/about-services-and-subscriptions){target="_blank"}.

   ![Finestra di dialogo Servizio per il servizio newsletter settimanale con i campi Etichetta, Nome interno, Tipo e-mail e Modalità newsletter.](assets/s_ncs_admin_survey_double-opt-in_sample_1.png)

1. Crea un secondo servizio di informazioni, un servizio temporaneo collegato a un modello di consegna per inviare messaggi di conferma dell’abbonamento.

   ![Dashboard del servizio temporaneo (temp_service) che mostra il tipo e-mail, la newsletter della modalità e la relativa cartella.](assets/s_ncs_admin_survey_double-opt-in_sample_1c.png)

### Passaggio 2: creazione di messaggi di conferma {#step-2---creating-confirmation-messages}

I messaggi di conferma vengono inviati tramite un modello di consegna dedicato a cui si fa riferimento a livello di servizio temporaneo.

1. In **[!UICONTROL Explorer]** , selezionare **[!UICONTROL Resources > Templates > Delivery templates]**.
1. Crea un modello di consegna per l’invio dei messaggi di conferma dell’abbonamento.
1. Fare clic sul pulsante **[!UICONTROL To]** in **[!UICONTROL Email parameters]** per associare il modello di consegna alla mappatura di destinazione Sottoscrizioni anziché Destinatari.

   ![Finestra di dialogo Seleziona destinazione nel modello di consegna con il mapping di destinazione Sottoscrizioni (nms:subscription) selezionato.](assets/s_ncs_admin_survey_double-opt-in_sample_1d.png)

1. Poiché i destinatari di questa consegna non hanno confermato la loro approvazione, si trovano ancora nel database di elenco Bloccati di. Affinché possano ricevere questa comunicazione, devi autorizzare le consegne basate su questo modello per eseguire il targeting dei destinatari sul inserisco nell&#39;elenco Bloccati di.

   A tale scopo, fare clic sulla scheda **[!UICONTROL Exclusions]**.

1. Fare clic sul collegamento **[!UICONTROL Edit...]** e deselezionare l&#39;opzione **[!UICONTROL Exclude recipients who no longer want to be contacted]**.

   <!-- ![](assets/s_ncs_admin_survey_double-opt-in_sample_4d.png)-->

   >[!IMPORTANT]
   >
   >Questa opzione può essere disabilitata solo in questo tipo di contesto.

1. Personalizza la consegna e inserisci il collegamento di conferma nel contenuto del messaggio. Questo collegamento consente di accedere al modulo Web per registrare la conferma dell&#39;abbonamento.

   ![E-mail di conferma nell’editor di consegna con un campo di personalizzazione del nome e un collegamento Fai clic qui.](assets/s_ncs_admin_survey_double-opt-in_sample_1b.png)

1. Con il DCE, collega l’URL al modulo web. Poiché il modulo Web non è ancora stato creato, sostituisci il valore non appena lo crei.

   ![Riquadro collegamento ipertestuale con il campo dell&#39;applicazione Web, ancora vuoto, per il collegamento Fare clic qui nell&#39;e-mail di conferma.](assets/s_ncs_admin_survey_double-opt-in_sample_3.png)

1. Infine, collega questo modello al servizio temporaneo creato in precedenza.

   ![Scheda Modifica servizio temporaneo con la consegna di conferma selezionata nel campo Sottoscrizione.](assets/s_ncs_admin_survey_double-opt-in_sample_3c.png)

### Passaggio 3: creazione del modulo di abbonamento {#step-3---creating-the-subscription-form}

Il modulo Web abilita sia la sottoscrizione del destinatario che la conferma della sottoscrizione.

Il flusso di lavoro del modulo web includerà le seguenti attività:

![Flusso di lavoro per moduli web: precaricamento, test, quindi e-mail vuota porta a Script, Inserisco nell&#39;elenco Bloccati, abbonamento, archiviazione, fine.](assets/s_ncs_admin_survey_double-opt-in_sample_4c.png)

A questo scopo, segui la procedura indicata di seguito:

1. Creare un modulo Web e scegliere il modello **[!UICONTROL Newsletter subscription (subNewsletter)]**.

   ![Finestra di dialogo Nuova applicazione Web con il modello di sottoscrizione newsletter (subNewsletter) selezionato.](assets/s_ncs_admin_survey_double-opt-in_sample_5a.png)

1. Nella scheda **[!UICONTROL Edit]**, è necessario configurare il flusso di lavoro esistente perché si desidera aggiungere un messaggio di conferma ai destinatari che desiderano effettuare la sottoscrizione.

   A tale scopo, fare doppio clic sulla casella **[!UICONTROL Preloading]** e configurarla come segue.

   ![Finestra di dialogo Attività di precaricamento con caricamento automatico dei dati a cui si fa riferimento nel modulo e Ignora precaricamento se non è selezionato alcun ID.](assets/s_ncs_admin_survey_double-opt-in_sample_5b.png)

   Ciò significa che se l’utente accede al modulo tramite il collegamento presente nel messaggio di conferma, le informazioni sul profilo verranno caricate. Se accedono al modulo web tramite una pagina del sito web, non verrà caricata alcuna informazione.

1. Aggiungi un&#39;attività **[!UICONTROL Test]** al flusso di lavoro.

   ![Flusso di lavoro per moduli Web con un&#39;attività di test che si estende su e-mail vuota a Sottoscrizione, Archiviazione ed Fine.](assets/s_ncs_admin_survey_double-opt-in_sample_6e.png)

   L&#39;attività **[!UICONTROL Test]** può riguardare l&#39;e-mail del destinatario. In questo caso, configuralo come segue:

   ![L&#39;editor del ramo attività di test con la condizione @email non è vuoto.](assets/s_ncs_admin_survey_double-opt-in_sample_6d.png)

1. Aggiungi due attività **[!UICONTROL Script]** al flusso di lavoro.

   ![Flusso di lavoro per moduli Web con un&#39;attività Script in ogni ramo dell&#39;attività Test.](assets/s_ncs_admin_survey_double-opt-in_sample_6f.png)

   La prima attività **[!UICONTROL Script]** aggiungerà i destinatari al elenco Bloccati di fino a quando non avranno confermato l&#39;abbonamento alla newsletter. Il suo contenuto deve essere il seguente:

   ```javascript
   ctx.recipient.@blackList=1
   ```

   ![Script per l&#39;attività di Inserisce nell&#39;elenco Bloccati dei contenente lo script ctx.recipient.@blackList=1.](assets/s_ncs_admin_survey_double-opt-in_sample_6bbis.png)

   La seconda attività **[!UICONTROL Script]** autorizza l&#39;invio di consegne agli utenti e li sottoscrive alla newsletter. Le ultime due righe dello script ti consentiranno di trasferire i destinatari dalla cartella temporanea a un’altra cartella e di riconciliarli con i profili esistenti non appena avranno confermato l’abbonamento.

   ```javascript
   ctx.recipient.@blackList=0
   nms.subscription.Subscribe("INTERNAL_NAME_OF_THE_NEWSLETTER", ctx.recipient, false)
   ctx.recipient.folder = <folder name="nmsRootRecipient"/>
   nms.subscription.Unsubscribe("TEMP", ctx.recipient)
   ```

   >[!NOTE]
   >
   >È inoltre possibile eliminare regolarmente la partizione **[!UICONTROL Temp]** tramite un flusso di lavoro.

   ![Seconda attività Script contenente le righe di script Unblocklist, Subscribe, folder e Unsubscribe.](assets/s_ncs_admin_survey_double-opt-in_sample_6b.png)

1. Fare doppio clic sull&#39;attività **[!UICONTROL Subscription]** per personalizzare il modulo di abbonamento e collegare una casella di controllo al servizio temporaneo creato in precedenza.

   ![Editor pagina con la casella di controllo del consenso collegata al servizio temporaneo nel campo Servizio.](assets/s_ncs_admin_survey_double-opt-in_sample_5c.png)

1. Configurare l&#39;attività **[!UICONTROL Storage]** per salvare le informazioni immesse nella pagina del modulo.

   Questa attività ti consente di creare i profili dei destinatari in una cartella temporanea dedicata per distinguerli dai profili nel database a cui possono essere inviate le comunicazioni.

   ![Finestra di dialogo dell&#39;attività di archiviazione con la cartella Temp impostata come cartella di creazione.](assets/s_ncs_admin_survey_double-opt-in_sample_5g.png)

   >[!NOTE]
   >
   >Non è necessario definire opzioni di riconciliazione.

1. Aggiungi due attività **[!UICONTROL End]** per visualizzare un messaggio per l&#39;utente.

   Nella seconda casella **[!UICONTROL End]** verrà visualizzato il messaggio di conferma al termine dell&#39;abbonamento.

   ![Termina la finestra di dialogo dell&#39;attività con il messaggio La sottoscrizione è stata completata. Riceverai presto la nostra newsletter.](assets/s_ncs_admin_survey_double-opt-in_sample_5h.png)

1. Una volta creato e configurato il modulo web, è ora possibile farvi riferimento nel modello di consegna per inviare messaggi di conferma.

   ![Conferma della consegna con il collegamento Fare clic qui che punta all&#39;applicazione Web di doppio consenso per l&#39;abbonamento alla newsletter.](assets/s_ncs_admin_survey_double-opt-in_sample_7b.png)

### Passaggio 4: pubblicazione e verifica del modulo {#step-4---publishing-and-testing-the-form}

È ora possibile pubblicare il modulo per renderlo accessibile agli utenti.

![Dashboard dell&#39;applicazione Web con il pulsante Pubblica e il messaggio che è necessario pubblicare per accedere online.](assets/s_ncs_admin_survey_double-opt-in_sample_8b.png)

L’abbonamento alla newsletter prevede i seguenti passaggi:

1. L’utente del sito web accede alla pagina di abbonamento e approva il modulo.

   ![Modulo di iscrizione newsletter in un browser con nome e indirizzo e-mail compilato, casella di consenso selezionata e pulsante Sottoscrivi.](assets/s_ncs_admin_survey_double-opt-in_sample_8c.png)

   Viene loro notificato tramite un messaggio nel browser che la loro richiesta è stata presa in considerazione.

   ![Pagina finale browser che indica che la richiesta è stata registrata e che verrà visualizzato un messaggio.](assets/s_ncs_admin_survey_double-opt-in_sample_8d.png)

   L&#39;utente viene aggiunto al database di Adobe Campaign nella cartella **[!UICONTROL Temp]** e il suo profilo è in inserita nell&#39;elenco Bloccati di  fino a quando non conferma l&#39;abbonamento con l&#39;e-mail.

   ![Cartella dei destinatari temporanei con il nuovo profilo selezionato e Non contattare più (tramite alcun canale) selezionato.](assets/s_ncs_admin_survey_double-opt-in_sample_8f.png)

1. Viene inviato loro un messaggio di conferma contenente un collegamento per approvare l’abbonamento.

   ![E-mail di conferma dell&#39;abbonamento con un collegamento Fai clic qui per confermare l&#39;abbonamento alla newsletter.](assets/s_ncs_admin_survey_double-opt-in_sample_8e.png)

1. Facendo clic su questo collegamento, la pagina di approvazione viene visualizzata nel browser.

   ![Pagina del browser con titolo Congratulazioni! conferma dell&#39;attivazione della sottoscrizione.](assets/s_ncs_admin_survey_double-opt-in_sample_8.png)

   In Adobe Campaign, il profilo utente viene aggiornato:

   * non sono più sotto inserisce nell&#39;elenco Bloccati di,
   * sono abbonati al servizio di informazione.

     ![Profilo destinatario aggiornato con Non contattare più cancellato e l&#39;abbonamento alla newsletter Movie elencato.](assets/s_ncs_admin_survey_double-opt-in_sample_9.png)

## Visualizzazione di opzioni diverse a seconda dei valori selezionati {#displaying-different-options-depending-on-the-selected-values}

Nell’esempio seguente, viene richiesto all’utente di selezionare un tipo di veicolo. È possibile visualizzare le categorie di veicoli disponibili in base al tipo selezionato. Ciò significa che gli elementi visualizzati nella colonna di destra dipendono dalla selezione dell’utente:

![Pagina di selezione auto con elenco a discesa Tipo di auto impostato su Seleziona.](assets/s_ncs_admin_survey_condition_sample0.png)

* Quando l&#39;utente seleziona &#39;veicolo privato&#39;, viene offerta la scelta tra &quot;Compatto&quot; e &quot;Minivan&quot;.

  ![Pagina di selezione auto con auto personale selezionata, con le opzioni Standard e Compatta.](assets/s_ncs_admin_survey_condition_sample2.png)

* Quando l’utente seleziona &quot;veicolo commerciale&quot;, viene visualizzata una selezione in un elenco a discesa:

  ![Pagina di selezione dell&#39;auto con il carrello mobile selezionato e un elenco a discesa di classi dei tipi di veicolo.](assets/s_ncs_admin_survey_condition_sample1.png)

In questo esempio, il tipo di veicolo non viene memorizzato nel database. L’elenco a discesa è configurato come segue:

![Tipo di proprietà della casella combinata dell&#39;auto con i valori Seleziona, Auto personale e Camion mobile.](assets/s_ncs_admin_survey_condition_config1.png)

Queste informazioni vengono memorizzate in una variabile locale.

La visualizzazione condizionale della colonna di destra è configurata nei contenitori:

![Finestra di dialogo Archiviazione con l&#39;opzione Variabile selezionata per il campo Tipo di auto.](assets/s_ncs_admin_survey_condition_config1bis.png)

* Visibilità condizionata dei campi per un veicolo privato:

  ![Condizione di visibilità sul contenitore Auto personale: tipo di auto uguale a Auto personale.](assets/s_ncs_admin_survey_condition_config2.png)

* Visibilità condizionata dei campi per un veicolo commerciale:

  ![Condizione di visibilità sul contenitore camion/furgone: tipo di auto uguale a camion mobile.](assets/s_ncs_admin_survey_condition_config3.png)
