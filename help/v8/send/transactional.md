---
product: Adobe Campaign
title: Messaggistica transazionale di Campaign
description: Guida introduttiva ai messaggi transazionali
feature: Panoramica
role: Data Engineer
level: Beginner
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '1482'
ht-degree: 1%

---

# Guida introduttiva alla messaggistica transazionale{#send-transactional-messages}

La messaggistica transazionale (Message Center, Centro messaggi) è un modulo Campaign progettato per la gestione dei messaggi di attivazione. Questi messaggi sono generati da eventi attivati da sistemi informatici e possono essere: fattura, conferma dell&#39;ordine, conferma della spedizione, modifica della password, notifica di indisponibilità del prodotto, dichiarazione dell&#39;account o creazione dell&#39;account del sito web, ad esempio.

[!DNL :speech_balloon:] In qualità di utente di Cloud Services gestiti,  [contatta ](../start/campaign-faq.md#support) Adobe per installare e configurare i messaggi transazionali di Campaign nel tuo ambiente.

I messaggi transazionali vengono utilizzati per inviare:

* notifiche, ad esempio conferme d&#39;ordine o reimpostazioni di password
* una risposta in tempo reale individuale a un&#39;azione del cliente
* contenuto non promozionale

[!DNL :bulb:] Le impostazioni di messaggistica transazionale sono descritte in  [questa sezione](../config/transactional-msg-settings.md).

[!DNL :bulb:] Comprendere l’architettura dei messaggi transazionali in  [questa pagina](../dev/architecture.md).

>[!CAUTION]
>
>La messaggistica transazionale richiede una licenza specifica. Controlla il tuo contratto di licenza.

## Definire modelli di messaggi transazionali

Ogni evento può attivare un messaggio personalizzato. Affinché ciò accada, devi creare un modello di messaggio per far corrispondere ogni tipo di evento. I modelli contengono le informazioni necessarie per personalizzare il messaggio sulle transazioni. Puoi inoltre utilizzare i modelli per testare l’anteprima del messaggio e inviare bozze utilizzando gli indirizzi di seed prima di consegnarle al target finale.

### Creare il modello

Per creare un modello di messaggio, segui i passaggi seguenti:

1. Vai alla cartella **[!UICONTROL Message Center >Transactional message templates]** nella struttura di Adobe Campaign.
1. Nell’elenco dei modelli di messaggi transazionali, fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL New]** nel menu a discesa oppure fai clic sul pulsante **[!UICONTROL New]** sopra l’elenco dei modelli di messaggi transazionali.

   ![](assets/messagecenter_create_model_001.png)

1. Nella finestra di consegna, seleziona il modello di consegna adatto al canale che desideri utilizzare.

   ![](assets/messagecenter_create_model_002.png)

1. Se necessario, modificarne l’etichetta.
1. Seleziona il tipo di evento che corrisponde al messaggio che desideri inviare.

   ![](assets/messagecenter_create_model_003.png)

   I tipi di evento destinati all’elaborazione da parte di Adobe Campaign devono essere creati nell’istanza di controllo per Adobe.

   >[!NOTE]
   >
   >Un tipo di evento non deve mai essere collegato a più di un modello.

1. Immetti una natura e una descrizione, quindi fai clic su **[!UICONTROL Continue]** per creare il corpo del messaggio. Consulta [Creare il contenuto del messaggio](#create-message-content).

### Crea il contenuto{#create-message-content}

La definizione del contenuto dei messaggi transazionali è la stessa di tutte le consegne in Adobe Campaign. Ad esempio, per una consegna e-mail, puoi creare contenuto in formato HTML o testo, aggiungere allegati o personalizzare l’oggetto di consegna. Per ulteriori informazioni al riguardo, consulta [questa sezione](../start/create-message.md).

>[!CAUTION]
>
>Le immagini incluse nel messaggio devono essere accessibili al pubblico. Adobe Campaign non fornisce alcun meccanismo di caricamento delle immagini per i messaggi transazionali.\
>A differenza di JSSP o webApp, `<%=` non dispone di escape predefinito.
>
>Devi eseguire correttamente l’escape di ogni dato proveniente dall’evento. Questo escape dipende da come viene utilizzato questo campo. Ad esempio, all’interno di un URL, utilizza encodeURIComponent. Per essere visualizzato nell&#39;HTML, è possibile utilizzare escapeXMLString.

Una volta definito il contenuto del messaggio, puoi integrare le informazioni sull’evento nel corpo del messaggio e personalizzarlo. Le informazioni sull’evento vengono inserite nel corpo del testo grazie ai tag di personalizzazione.

![](assets/messagecenter_create_content.png)

* Tutti i campi di personalizzazione provengono dal payload.
* È possibile fare riferimento a uno o più blocchi di personalizzazione in un messaggio transazionale. Il contenuto del blocco verrà aggiunto al contenuto della consegna durante la pubblicazione nell’istanza di esecuzione.

Per inserire tag di personalizzazione nel corpo di un messaggio e-mail, effettua le seguenti operazioni:

1. Nel modello di messaggio, fai clic sulla scheda che corrisponde al formato dell’e-mail (HTML o testo).
1. Inserisci il corpo del messaggio.
1. Nel corpo del testo, inserisci il tag utilizzando i menu **[!UICONTROL Real time events>Event XML]** .

   ![](assets/messagecenter_create_custo_1.png)

1. Compila il tag utilizzando la seguente sintassi: **nome elemento**.@**nome dell&#39;attributo** come mostrato di seguito.

   ![](assets/messagecenter_create_custo_2.png)

### Aggiungere indirizzi seed{#add-seeds}

Un indirizzo di seed ti consente di visualizzare un’anteprima del messaggio, inviare una bozza e testare la personalizzazione dei messaggi prima di inviare il messaggio. Gli indirizzi di seed sono collegati alla consegna e non possono essere utilizzati per altre consegne.

1. Nel modello di messaggio transazionale, fai clic sulla scheda **[!UICONTROL Seed addresses]** , quindi fai clic sul pulsante **[!UICONTROL Add]** .

   ![](assets/messagecenter_create_seed_1.png)

1. Assegna un’etichetta per una selezione semplice in un secondo momento, quindi inserisci l’indirizzo di seed (e-mail o telefono cellulare a seconda del canale di comunicazione).

1. Immetti l’identificatore esterno: questo campo facoltativo consente di inserire una chiave business (ID univoco, nome + e-mail, ecc.) comune a tutte le applicazioni del sito web, utilizzato per identificare i profili. Se questo campo è presente anche nel database di marketing di Adobe Campaign, puoi quindi riconciliare un evento con un profilo nel database.

   ![](assets/messagecenter_create_seed_2.png)

1. Inserire i dati di prova. Fai riferimento a [questa sezione](#personalization-data).

   ![](assets/messagecenter_create_custo_3.png)

1. Fai clic su **[!UICONTROL Ok]** per confermare la creazione dell’indirizzo di seed.

1. Ripeti il processo per creare tutti gli indirizzi necessari.

   ![](assets/messagecenter_create_seed_6.png)

Una volta creati gli indirizzi, puoi accedere alla loro anteprima e personalizzazione.

### Aggiungi dati di personalizzazione{#personalization-data}

Puoi aggiungere dati nel modello di messaggio per testare la personalizzazione dei messaggi transazionali. In questo modo puoi generare un’anteprima o inviare una bozza. Se si installa il modulo **Consegna**, questi dati consentono di visualizzare un rendering dei messaggi per vari client desktop, web o mobili.

Lo scopo di questi dati è quello di testare i messaggi prima della loro consegna finale. Questi messaggi non coincidono con i dati effettivi che devono essere elaborati dal Centro messaggi. Tuttavia, la struttura XML deve essere identica a quella dell&#39;evento memorizzato nell&#39;istanza di esecuzione, come illustrato di seguito.

![](assets/messagecenter_create_custo_4.png)

Queste informazioni consentono di personalizzare il contenuto dei messaggi utilizzando i tag di personalizzazione.

1. Nel modello di messaggio, fai clic sulla scheda **[!UICONTROL Seed addresses]** .
1. Nel contenuto dell&#39;evento, immettere le informazioni di test in formato XML.

   ![](assets/messagecenter_create_custo_3.png)

### Visualizza l&#39;anteprima del messaggio sulle transazioni{#transactional-message-preview}

Dopo aver creato uno o più indirizzi di seed e il corpo del messaggio, puoi visualizzare in anteprima il messaggio e controllarne la personalizzazione.

1. Nel modello di messaggio, fai clic sulla scheda **[!UICONTROL Preview]** , quindi seleziona **[!UICONTROL A seed address]** nell’elenco a discesa.

   ![](assets/messagecenter_preview_1.png)

1. Seleziona l’indirizzo di seed creato in precedenza per visualizzare il messaggio personalizzato.

   ![](assets/messagecenter_create_seed_7.png)

### Inviare una bozza

Puoi verificare la consegna dei messaggi inviando una bozza a un indirizzo di seed creato in precedenza.

L’invio di una bozza comporta la stessa procedura utilizzata per qualsiasi consegna.

[!DNL :arrow_upper_right:] Ulteriori informazioni sulle bozze nella documentazione di  [Campaign Classic v7]((https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html))

Tuttavia, per inviare una prova di un messaggio sulle transazioni, devi eseguire le seguenti operazioni:

* Crea uno o più [indirizzi di seed](#add-seeds) con dati di test di personalizzazione
* Creare il contenuto del messaggio

Per inviare la bozza:

1. Fai clic sul pulsante **[!UICONTROL Send a proof]** nella finestra di consegna.
1. Analizza la consegna.
1. Correggi eventuali errori e conferma la consegna.

   ![](assets/messagecenter_send_proof_001.png)

1. Verifica che il messaggio sia stato recapitato all’indirizzo di seed e che il suo contenuto sia conforme alla tua configurazione.

   ![](assets/messagecenter_send_proof_002.png)

È possibile accedere alle bozze in ciascun modello tramite la scheda **[!UICONTROL Audit]** .

![](assets/messagecenter_send_proof_003.png)

### Pubblicare il modello

Al termine del modello di messaggio creato sull’istanza di controllo, puoi pubblicarlo. Questo processo lo pubblicherà anche su tutte le istanze di esecuzione.

>[!NOTE]
>
>Quando si pubblicano modelli di messaggi transazionali, anche le regole di tipologia vengono pubblicate automaticamente sulle istanze di esecuzione.

La pubblicazione ti consente di creare automaticamente due modelli di messaggio sulle istanze di esecuzione, che ti consentono di inviare messaggi collegati a eventi in tempo reale e batch.

>[!CAUTION]
>
>Ogni volta che apporti modifiche a un modello, accertati di pubblicarlo nuovamente affinché queste modifiche siano effettive durante la consegna dei messaggi transazionali.

1. Nell&#39;istanza di controllo, passare alla cartella **[!UICONTROL Message Center > Transactional message templates]** della struttura ad albero.
1. Seleziona il modello da pubblicare sulle istanze di esecuzione.
1. Fai clic su **[!UICONTROL Publish]**.

   ![](assets/messagecenter_publish_template.png)

Al termine della pubblicazione, nella struttura dell’istanza di produzione nella cartella **[!UICONTROL Administration > Production > Message Center Execution> Default > Transactional message templates]** vengono creati entrambi i modelli di messaggio da applicare agli eventi batch e in tempo reale.

![](assets/messagecenter_deployed_model.png)

Una volta pubblicato un modello, se viene attivato l’evento corrispondente, l’istanza di esecuzione riceverà l’evento, lo collegherà al modello transazionale e invierà il messaggio transazionale corrispondente a ciascun destinatario.

>[!NOTE]
>
>Se sostituisci un campo esistente del modello di messaggio transazionale, ad esempio l’indirizzo del mittente, con un valore vuoto, il campo corrispondente nelle istanze di esecuzione non verrà aggiornato una volta che il messaggio sulle transazioni viene pubblicato nuovamente. Conterrà ancora il valore precedente.
>
>Tuttavia, se aggiungi un valore non vuoto, il campo corrispondente verrà aggiornato come di consueto dopo la pubblicazione successiva.


### Annullare la pubblicazione di un modello

Una volta pubblicato un modello di messaggio sulle istanze di esecuzione, puoi annullarne la pubblicazione.

* In effetti, un modello pubblicato può ancora essere chiamato se viene attivato l’evento corrispondente: se non utilizzi più un modello di messaggio, è consigliabile annullarne la pubblicazione. In questo modo si evita di inviare per errore un messaggio sulle transazioni indesiderato.

   Ad esempio, hai pubblicato un modello di messaggio da utilizzare solo per le campagne di Natale. Puoi annullare la pubblicazione dopo la fine del periodo natalizio e pubblicarlo nuovamente l’anno prossimo.

* Inoltre, non puoi eliminare un modello di messaggio transazionale con lo stato **[!UICONTROL Published]** . Per prima cosa devi annullarla pubblicazione.

Per annullare la pubblicazione di un modello di messaggio sulle transazioni, segui i passaggi riportati di seguito.

1. Nell&#39;istanza di controllo, passare alla cartella **[!UICONTROL Message Center > Transactional message templates]** della struttura ad albero.
1. Seleziona il modello da annullare la pubblicazione.
1. Fai clic su **[!UICONTROL Unpublish]**.
1. Fai clic su **[!UICONTROL Start]**.

![](assets/message-center-unpublish.png)

Lo stato del modello di messaggio transazionale cambia da **[!UICONTROL Published]** a **[!UICONTROL Being edited]**.

Al termine dell’annullamento della pubblicazione:

* Entrambi i modelli di messaggio (applicati a eventi di tipo batch e in tempo reale) vengono eliminati da ogni istanza di esecuzione.

   Non vengono più visualizzate nella cartella **[!UICONTROL Administration > Production > Message Center Execution > Default > Transactional message templates]** .

* Una volta che un modello viene annullato, puoi eliminarlo dall’istanza di controllo.

   A tale scopo, selezionalo dall’elenco e fai clic sul pulsante **[!UICONTROL Delete]** in alto a destra dello schermo.
