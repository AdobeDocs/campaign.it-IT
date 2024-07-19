---
title: Messaggistica transazionale di Campaign
description: Introduzione alla messaggistica transazionale
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1491'
ht-degree: 1%

---

# Introduzione alla messaggistica transazionale{#send-transactional-messages}

La messaggistica transazionale (Message Center) è un modulo di Campaign progettato per la gestione dei messaggi di attivazione. Queste notifiche sono generate da eventi attivati dai sistemi informativi e possono essere: fattura, conferma dell’ordine, conferma della spedizione, modifica della password, notifica di indisponibilità del prodotto, estratto conto, creazione di account sul sito web, ecc.

>[!NOTE]
>
>In qualità di utente di Cloud Service gestiti, [contatta l&#39;Adobe](../start/campaign-faq.md#support){target="_blank"} per configurare la messaggistica transazionale di Campaign nel tuo ambiente.

I messaggi transazionali vengono utilizzati per inviare:

* notifiche, ad esempio conferme d’ordine o reimpostazioni della password
* una risposta individuale in tempo reale a un’azione del cliente
* contenuti non promozionali

Le impostazioni dei messaggi transazionali sono descritte in dettaglio in [questa sezione](../config/transactional-msg-settings.md).

Scopri l&#39;architettura della messaggistica transazionale in [questa pagina](../architecture/architecture.md#transac-msg-archi).

## Principio operativo della messaggistica transazionale {#transactional-messaging-operating-principle}

Il modulo di messaggistica transazionale di Adobe Campaign si integra in un sistema di informazioni che restituisce eventi da trasformare in messaggi transazionali personalizzati. Questi messaggi possono essere inviati singolarmente o in batch tramite e-mail, SMS o notifiche push.

Ad esempio, immagina di essere un’azienda con un sito web in cui i clienti possono acquistare prodotti.

Adobe Campaign consente di inviare un’e-mail di notifica ai clienti che hanno aggiunto prodotti al carrello. Quando uno di loro lascia il sito web senza procedere con gli acquisti (evento esterno che attiva un evento Campaign), riceve automaticamente un’e-mail di abbandono del carrello (consegna di messaggi transazionali).

Di seguito sono illustrate le fasi principali per l’attuazione di questa procedura:

1. [Crea un tipo di evento](#create-event-types).
1. [Creare e progettare il modello di messaggio](#create-message-template). Collega un evento al messaggio durante questo passaggio.
1. [Verifica il messaggio](#test-message-template).
1. [Publish il modello di messaggio](#publish-message-template).

Dopo aver progettato e pubblicato il modello di messaggio transazionale, se viene attivato un evento corrispondente, i dati rilevanti vengono inviati a Campaign tramite i metodi [SOAP ](../send/event-description.md) PushEvent e PushEvents e la consegna viene inviata ai destinatari desiderati.

## Creare tipi di evento {#create-event-types}

Per assicurarsi che ogni evento possa essere modificato in un messaggio personalizzato, devi innanzitutto creare **tipi di evento**.

Quando [si crea un modello di messaggio](#create-message-template), verrà selezionato il tipo di evento corrispondente al messaggio che si desidera inviare.

>[!CAUTION]
>
>È necessario creare tipi di evento prima di poterli utilizzare nei modelli di messaggio.

Per creare tipi di evento che verranno elaborati da Adobe Campaign, segui questi passaggi:

1. Individua la cartella **[!UICONTROL Administration > Platform > Enumerations]** di Campaign Explorer.
1. Selezionare l&#39;enumerazione **[!UICONTROL Event type]** dall&#39;elenco.
1. Fare clic su **[!UICONTROL Add]** per creare un valore di enumerazione. Può trattarsi di una conferma d’ordine, di una modifica della password, di una modifica della consegna dell’ordine, ecc.

   ![](assets/messagecenter_eventtype_enum_001.png)

   >[!CAUTION]
   >
   >Ogni tipo di evento deve corrispondere a un valore nell&#39;enumerazione **[!UICONTROL Event type]**.

1. Una volta creati i valori dell’elenco dettagliati, disconnettiti e accedi di nuovo all’istanza per rendere effettiva la creazione.

>[!NOTE]
>
>Ulteriori informazioni sulle enumerazioni in [questa pagina](../../v8/config/ui-settings.md#enumerations).


## Definire un modello per messaggi transazionali {#create-message-template}

Ogni evento può attivare un messaggio personalizzato. Affinché questo accada, devi creare un modello di messaggio corrispondente a ciascun tipo di evento. I modelli contengono le informazioni necessarie per personalizzare il messaggio transazionale. Puoi inoltre utilizzare i modelli per verificare l’anteprima dei messaggi e inviare bozze utilizzando indirizzi di seed prima della consegna al target finale.

### Creare il modello

Per creare un modello di messaggio, effettua le seguenti operazioni:

1. Passare alla cartella **[!UICONTROL Message Center >Transactional message templates]** nella struttura Adobe Campaign.
1. Nell&#39;elenco dei modelli di messaggi transazionali, fare clic con il pulsante destro del mouse e selezionare **[!UICONTROL New]** nel menu a discesa oppure fare clic sul pulsante **[!UICONTROL New]** sopra l&#39;elenco dei modelli di messaggi transazionali.

   ![](assets/messagecenter_create_model_001.png)

1. Nella finestra di dialogo di consegna, seleziona il modello di consegna adatto al canale che desideri utilizzare.

   ![](assets/messagecenter_create_model_002.png)

1. Se necessario, modificane l’etichetta.
1. Seleziona il tipo di evento che corrisponde al messaggio da inviare. I tipi di evento destinati all’elaborazione da parte di Adobe Campaign devono essere creati in precedenza. [Ulteriori informazioni](#create-event-types)

   ![](assets/messagecenter_create_model_003.png)

   >[!CAUTION]
   >
   >Un tipo di evento non deve mai essere collegato a più di un modello.

1. Immettere una natura e una descrizione, quindi fare clic su **[!UICONTROL Continue]** per creare il corpo del messaggio.

### Creare il contenuto{#create-message-content}

La definizione del contenuto dei messaggi transazionali è la stessa di tutte le consegne in Adobe Campaign. Ad esempio, per una consegna e-mail, puoi creare contenuto in formato HTML o testo, aggiungere allegati o personalizzare l’oggetto di consegna. [Ulteriori informazioni](../start/create-message.md).

>[!CAUTION]
>
>Le immagini incluse nel messaggio devono essere accessibili al pubblico. Adobe Campaign non fornisce alcun meccanismo di caricamento di immagini per i messaggi transazionali.\
>A differenza di JSSP o WebApp, `<%=` non ha alcun escape predefinito.
>
>Devi eseguire correttamente l’escape di ogni dato proveniente dall’evento. L’escape dipende da come viene utilizzato questo campo. Ad esempio, all’interno di un URL, utilizza encodeURIComponent. Per essere visualizzato in HTML, è possibile utilizzare escapeXMLString.

Dopo aver definito il contenuto del messaggio, puoi integrare le informazioni sull’evento nel corpo del messaggio e personalizzarlo. Le informazioni sull’evento vengono inserite nel corpo del testo grazie ai tag di personalizzazione.

![](assets/messagecenter_create_content.png)

* Tutti i campi di personalizzazione provengono dal payload.
* È possibile fare riferimento a uno o più blocchi di personalizzazione in un messaggio transazionale. <!--The block content will be added to the delivery content during the publication to the execution instance.-->

Per inserire i tag di personalizzazione nel corpo di un messaggio e-mail, effettua le seguenti operazioni:

1. Nel modello del messaggio, fai clic sulla scheda corrispondente al formato e-mail (HTML o testo).
1. Inserisci il corpo del messaggio.
1. Nel corpo del testo, inserire il tag utilizzando i menu **[!UICONTROL Real time events>Event XML]**.

   ![](assets/messagecenter_create_custo_1.png)

1. Compila il tag utilizzando la seguente sintassi: **nome elemento**.@**nome attributo** come mostrato di seguito.

   ![](assets/messagecenter_create_custo_2.png)

## Testare il modello di messaggio transazionale {#test-message-template}

### Aggiungere indirizzi seed{#add-seeds}

Un indirizzo di seed consente di visualizzare un’anteprima del messaggio, inviarne una bozza e testare la personalizzazione del messaggio prima di inviarlo. Gli indirizzi di seed sono collegati alla consegna e non possono essere utilizzati per altre consegne.

1. Nel modello di messaggio transazionale, fare clic sulla scheda **[!UICONTROL Seed addresses]**, quindi sul pulsante **[!UICONTROL Add]**.

   ![](assets/messagecenter_create_seed_1.png)

1. Assegna un’etichetta a esso per una facile selezione in un secondo momento, quindi inserisci l’indirizzo seed (e-mail o telefono cellulare a seconda del canale di comunicazione).

1. Immetti l’identificatore esterno: questo campo opzionale ti consente di immettere una chiave aziendale (ID univoco, nome + e-mail, ecc.) comune a tutte le applicazioni sul sito web, utilizzato per identificare i profili. Se questo campo è presente anche nel database di marketing di Adobe Campaign, puoi riconciliare un evento con un profilo nel database.

   ![](assets/messagecenter_create_seed_2.png)

1. Inserire i dati di prova. Fai riferimento a [questa sezione](#personalization-data).

   ![](assets/messagecenter_create_custo_3.png)

1. Fare clic su **[!UICONTROL Ok]** per confermare la creazione dell&#39;indirizzo di seed.

1. Ripeti il processo per creare tutti gli indirizzi necessari.

   ![](assets/messagecenter_create_seed_6.png)

Una volta creati gli indirizzi, puoi accedervi all’anteprima e alla personalizzazione.

<!--

### Add personalization data{#personalization-data}

You can add data in the message template to test transactional message personalization. This will allow you to generate a preview or send a proof. If you install the **Deliverability** module, this data allows you to display a rendering of the messages for various desktop, web or mobile clients.

The purpose of this data is to test your messages before their final delivery. These messages do not coincide with actual data to be processed by Message Center.

However, the XML structure must be identical to that of the event stored in the execution instance, as shown below. 

![](assets/messagecenter_create_custo_4.png)

This information enables you to personalize message content using personalization tags.

1. In the message template, click the **[!UICONTROL Seed addresses]** tab.
1. In the event content, enter the test information in XML format.

   ![](assets/messagecenter_create_custo_3.png)
-->

### Anteprima del messaggio sulle transazioni{#transactional-message-preview}

Dopo aver creato uno o più indirizzi di seed e il corpo del messaggio, puoi visualizzare l’anteprima del messaggio e controllarne la personalizzazione.

1. Nel modello del messaggio, fare clic sulla scheda **[!UICONTROL Preview]**, quindi selezionare **[!UICONTROL A seed address]** nell&#39;elenco a discesa.

   ![](assets/messagecenter_preview_1.png)

1. Seleziona l’indirizzo seed creato in precedenza per visualizzare il messaggio personalizzato.

   ![](assets/messagecenter_create_seed_7.png)

### Inviare una bozza

Puoi verificare la consegna dei messaggi inviando una bozza a un indirizzo seed creato in precedenza.

L’invio di una bozza comporta la stessa procedura applicata per qualsiasi consegna. Ulteriori informazioni sulle bozze in [questa sezione](../send/preview-and-proof.md).

Tuttavia, per inviare la bozza di un messaggio sulle transazioni, è necessario effettuare le operazioni seguenti:

* Crea uno o più [indirizzi seed](#add-seeds) con dati di test di personalizzazione
* Creare il contenuto del messaggio

Per inviare la bozza:

1. Fai clic sul pulsante **[!UICONTROL Send a proof]** nella finestra di consegna.
1. Analizza la consegna.
1. Correggi eventuali errori e conferma la consegna.

   ![](assets/messagecenter_send_proof_001.png)

1. Verifica che il messaggio sia stato recapitato all’indirizzo di seed e che il suo contenuto sia conforme alla configurazione.

   ![](assets/messagecenter_send_proof_002.png)

È possibile accedere alle bozze in ogni modello tramite la scheda **[!UICONTROL Audit]**.

![](assets/messagecenter_send_proof_003.png)

## Publish il modello {#publish-message-template}

Quando il modello di messaggio creato<!-- on the control instance--> è completo, è possibile pubblicarlo, in modo da poter inviare messaggi collegati a eventi batch e in tempo reale.

<!--This process will also publish it on all execution instances.

NOTE: When publishing transactional message templates, typology rules are also automatically published on the execution instances.

Publication lets you automatically create two message templates on the execution instances, which will allow you to send messages linked to real-time and batch events.-->

>[!CAUTION]
>
>Ogni volta che apporti modifiche a un modello, assicurati di pubblicarle nuovamente affinché risultino efficaci durante la consegna dei messaggi transazionali.

1. Passare alla cartella **[!UICONTROL Message Center > Transactional message templates]** della struttura.
1. Selezionare il modello da pubblicare<!--on your execution instances-->.
1. Fai clic su **[!UICONTROL Publish]**.

   ![](assets/messagecenter_publish_template.png)

Al termine della pubblicazione, nella cartella **[!UICONTROL Administration > Production > Message Center Execution> Default > Transactional message templates]** vengono creati sia i modelli di messaggio da applicare a eventi batch che gli eventi di tipo in tempo reale.

![](assets/messagecenter_deployed_model.png)

Dopo la pubblicazione di un modello, se viene attivato l&#39;evento corrispondente, Adobe Campaign<!--execution instance--> riceverà l&#39;evento, lo collegherà al modello transazionale e invierà il messaggio transazionale corrispondente a ciascun destinatario.

<!--
>[!NOTE]
>
>If you replace an existing field of the transactional message template, such as the sender address, with an empty value, the corresponding field on the execution instance(s) will not be updated once the transactional message is published again. It will still contain the previous value.
>
>However, if you add a non-empty value, the corresponding field will be updated as usual after the next publication.
-->

## Annullare la pubblicazione di un modello

Dopo la pubblicazione di un modello di messaggio <!--on the execution instances-->, è possibile annullarne la pubblicazione.

* In effetti, un modello pubblicato può ancora essere chiamato se viene attivato l’evento corrispondente: se non utilizzi più un modello di messaggio, si consiglia di annullarne la pubblicazione. In questo modo si evita di inviare per errore un messaggio transazionale indesiderato.

  Ad esempio, hai pubblicato un modello di messaggio da utilizzare solo per le campagne natalizie. Puoi annullarne la pubblicazione al termine del periodo natalizio e pubblicarla nuovamente l’anno prossimo.

* Inoltre, non è possibile eliminare un modello di messaggio transazionale con stato **[!UICONTROL Published]**. Devi prima annullare la pubblicazione.

Per annullare la pubblicazione di un modello di messaggio sulle transazioni, effettua le seguenti operazioni.

1. Selezionare la cartella **[!UICONTROL Message Center > Transactional message templates]**.
1. Seleziona il modello da annullare la pubblicazione.
1. Fai clic su **[!UICONTROL Unpublish]**.
1. Fai clic su **[!UICONTROL Start]**.

![](assets/message-center-unpublish.png)

Lo stato del modello di messaggio transazionale torna da **[!UICONTROL Published]** a **[!UICONTROL Being edited]**.

Una volta completata la pubblicazione:

* Entrambi i modelli di messaggio (applicati a eventi di tipo batch e in tempo reale) sono stati eliminati<!-- from each execution instance-->.

  Non vengono più visualizzati nella cartella **[!UICONTROL Administration > Production > Message Center Execution > Default > Transactional message templates]**.

* Una volta annullata la pubblicazione di un modello, è possibile eliminarlo<!-- from the control instance-->.

  A tale scopo, selezionarlo dall&#39;elenco e fare clic sul pulsante **[!UICONTROL Delete]** in alto a destra dello schermo.
