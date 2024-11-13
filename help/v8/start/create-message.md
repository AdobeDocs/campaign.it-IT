---
title: Creare la prima consegna
description: Creare la prima consegna
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 53fab31c21fdfe2f90c4793ccd025af1d5c0e061
workflow-type: tm+mt
source-wordcount: '1523'
ht-degree: 3%

---

# Creare la prima consegna {#create-a-msg}

In questa pagina, scopri come creare una singola consegna. Puoi creare altri tipi di consegne per generare i tuoi casi d’uso. Ulteriori informazioni sui diversi tipi di consegne e su come crearle in [questa pagina](gs-message.md).

I passaggi chiave durante la creazione di una consegna una tantum sono i seguenti:

1. **Crea una nuova consegna**. [Ulteriori informazioni](#create-the-delivery)

1. **Definisci il contenuto della consegna**. [Ulteriori informazioni](#content-of-the-delivery)

1. **Selezionare la popolazione target**. [Ulteriori informazioni](#target-population)

Puoi quindi preparare, testare, inviare e monitorare i messaggi con Adobe Campaign.

>[!NOTE]
>
>I passaggi descritti in questa sezione presuppongono che tutti i destinatari e i loro profili siano memorizzati nel database, tranne nel caso di consegna esterna. Vedere [Selezione di destinatari esterni](#selecting-external-recipients).

## Creare la consegna {#create-the-delivery}

Per creare una consegna, segui questi passaggi:

1. Individuare l&#39;elenco delle consegne e fare clic su **[!UICONTROL Create]**.
1. Seleziona il canale di consegna. A questo scopo, scegli il modello di consegna appropriato dall’elenco a discesa.

   ![](../send/assets/select-the-new-template.png)

   Per ogni canale installato viene fornito un modello incorporato: e-mail, telefono, canali mobili (push/SMS), direct mail, X (Twitter), ecc. I canali disponibili nell’elenco dipendono dal contratto di licenza.

   Puoi creare nuovi modelli di consegna per preconfigurare parametri specifici in base alle tue esigenze.  [Ulteriori informazioni](../send/create-templates.md).

1. Immettere un nome per la consegna nel campo **[!UICONTROL Label]**.

   (facoltativo) Alla consegna può essere assegnato anche un codice di consegna. Il nome della consegna e il relativo codice sono visibili nell’elenco delle consegne ma non esposti ai destinatari.

1. (facoltativo) Aggiungere una descrizione nel campo **[!UICONTROL Description]**.
1. (facoltativo) seleziona la natura della consegna nel campo pertinente. Queste informazioni sono utili per il tracciamento della consegna: puoi filtrare in base a questo criterio nell’elenco di consegna o creare query utilizzando questo criterio di selezione.
1. Fare clic su **[!UICONTROL Continue]** per visualizzare la finestra del contenuto del messaggio.

## Definire il contenuto della consegna {#content-of-the-delivery}

Il contenuto della consegna è pronto per essere configurato. La definizione del contenuto della consegna è specifica per ciascun canale. Per ulteriori informazioni, consulta la sezione dedicata:

* [Definire il contenuto dell’e-mail](../send/email.md)
* [Definire il contenuto dell’SMS](../send/sms/sms-content.md)
* [Definire il contenuto delle direct mail](../send/direct-mail.md)
* [Sgrassare il contenuto delle notifiche push](../send/push.md)


## Definire il pubblico target {#target-population}

Per ogni consegna, puoi definire diversi tipi di pubblico target:

* **Pubblico principale**: profili che ricevono messaggi. [Ulteriori informazioni](#select-the-main-target)
* **Destinazione bozza**: profili che ricevono messaggi di bozza. Una bozza è un messaggio specifico che ti consente di testare un messaggio prima di inviarlo al target principale. [Ulteriori informazioni](#select-the-proof-target)

Inoltre, nel contesto di una campagna di marketing, puoi aggiungere:

* **Indirizzi seed**: destinatari che non rientrano nel target di consegna ma che ricevono la consegna. [Ulteriori informazioni](../audiences/test-profiles.md)
* **Gruppi di controllo**: popolazione che non riceve la consegna, utilizzata per tenere traccia del comportamento e dell&#39;impatto della campagna. [Ulteriori informazioni](../../automation/campaigns/marketing-campaign-target.md#add-a-control-group).

### Selezionare i destinatari principali della consegna {#select-the-main-target}

Nella maggior parte dei casi, il target principale viene estratto dal database di Adobe Campaign (modalità predefinita). Tuttavia, i destinatari possono anche essere archiviati in un [file esterno](#selecting-external-recipients).

Per selezionare i destinatari di una consegna, segui i passaggi seguenti:

1. Nell&#39;editor di consegna, selezionare **[!UICONTROL To]**.
1. Se i destinatari sono memorizzati nel database, scegliere la prima opzione.

   ![](../send/sms/assets/audience_to.png){zoomable="yes"}

1. Selezionare la [mappatura di destinazione](../audiences/target-mappings.md) nell&#39;elenco a discesa **[!UICONTROL Target mapping]**.
1. Fare clic sul pulsante **[!UICONTROL Add]** per definire i filtri di restrizione.

   ![](assets/target-type.png){width="60%" align="left" zoomable="yes"}

   Selezionare un tipo di filtro e fare clic su **[!UICONTROL Next]** per definire le condizioni. È possibile visualizzare i destinatari filtrati dalla scheda **[!UICONTROL Preview]**. A seconda del tipo di destinazione, il pulsante **[!UICONTROL Refine target]** consente di combinare diversi criteri di targeting.

   Sono disponibili i seguenti tipi di destinazione:

   * **[!UICONTROL Filtering conditions]**: utilizzare questa opzione per definire una query e visualizzare il risultato. Scopri come progettare una query in [questa sezione](../../automation/workflow/query.md).
   * **[!UICONTROL A list of recipients]**: utilizzare questa opzione per impostare come destinazione un elenco di profili. Ulteriori informazioni sugli elenchi in [questa sezione](../audiences/create-audiences.md).
   * **[!UICONTROL A recipient]**: utilizzare questa opzione per selezionare un profilo specifico nel database.
   * **[!UICONTROL Recipients included in a folder]**: utilizzare questa opzione per eseguire il targeting di tutti i profili contenuti in una cartella specifica.
   * **[!UICONTROL Recipients of a delivery]**: utilizzare questa opzione per generare la destinazione dai destinatari di una consegna. Seleziona quindi la consegna nell’elenco:

     ![](assets/target-recipient-delivery.png)

   * **[!UICONTROL Delivery recipients belonging to a folder]**: utilizzare questa opzione per generare la destinazione dalle consegne dei destinatari incluse in una cartella specifica.

     ![](assets/target-delivery-folder.png)

     Puoi filtrare il comportamento dei destinatari selezionando dall’elenco a discesa:

     ![](assets/target-filter-behavior.png)

     >[!NOTE]
     >
     >L&#39;opzione **[!UICONTROL Include sub-folders]** consente inoltre di eseguire il targeting delle consegne contenute nelle cartelle presenti nella struttura ad albero sotto il nodo selezionato.

   * **[!UICONTROL Subscribers of an information service]** : questa opzione ti consente di selezionare una newsletter a cui i destinatari devono iscriversi per essere destinatari della consegna creata.

     ![](assets/target-service.png)

   * **[!UICONTROL User filters]**: questa opzione consente di accedere ai filtri preconfigurati per utilizzarli come criteri di filtro per i profili nel database. I filtri preconfigurati sono presentati in [questa sezione](../audiences/create-filters.md#default-filters).
   * L&#39;opzione **[!UICONTROL Exclude recipients from this segment]** consente di eseguire il targeting di destinatari che non soddisfano i criteri di destinazione definiti. Per utilizzare questa opzione, seleziona la casella appropriata e quindi applica il targeting, come definito in precedenza, per escludere i profili risultanti.

1. Immettere un nome per il targeting nel campo **[!UICONTROL Label]**. Per impostazione predefinita, l’etichetta è l’etichetta del primo criterio di targeting. Quando si combinano criteri di filtro, si consiglia di utilizzare un nome esplicito.
1. Fare clic su **[!UICONTROL Finish]** per convalidare le opzioni di targeting.

   I criteri di targeting definiti sono riepilogati nella sezione centrale della scheda di configurazione principale del target. Fai clic su un criterio per visualizzarne il contenuto (configurazione e anteprima). Per eliminare un criterio, fare clic sulla croce che si trova dopo l&#39;etichetta.

   ![](assets/target-remove-criterion.png)

### Seleziona destinatari esterni {#selecting-external-recipients}

Puoi inviare messaggi ai profili che non sono memorizzati nel database, ma in un file esterno. Ad esempio, per inviare una consegna a destinatari importati da un file di testo, effettua le seguenti operazioni:

1. Fai clic sul collegamento **[!UICONTROL To]** per selezionare i destinatari della consegna.
1. Selezionare l&#39;opzione **[!UICONTROL Defined in an external file]**.
1. Seleziona il file contenente i destinatari.
1. Durante l&#39;importazione dei destinatari, fare clic sul collegamento **[!UICONTROL File format definition...]** per selezionare e configurare il file esterno.

   Per ulteriori informazioni sull&#39;importazione dei dati, consulta la [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/en/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs#step-2---source-file-selection){target="_blank"}.

1. Fai clic su **[!UICONTROL Finish]** e configura la consegna come consegna standard.

>[!CAUTION]
>
>Quando definisci il contenuto del messaggio per la consegna e-mail a destinatari esterni, non includere il collegamento alla pagina speculare: non può essere generato in questa modalità di consegna.

### Impostazioni di esclusione {#define-exclusion-settings}

Quando si definisce il pubblico [di una consegna](#target-population), viene utilizzata la scheda **[!UICONTROL Exclusions]** per limitare il numero di messaggi. I parametri predefiniti sono consigliati, ma puoi adattare le impostazioni in base alle tue esigenze. Tuttavia, queste opzioni devono essere modificate solo da un utente esperto per evitare abusi ed errori.

>[!CAUTION]
>
>In qualità di utente esperto, per casi d’uso specifici puoi modificare queste impostazioni, ma Adobe consiglia di mantenere la configurazione predefinita.

Puoi escludere gli indirizzi che hanno raggiunto un certo numero di errori consecutivi o la cui valutazione della qualità è inferiore a una soglia specificata in questa finestra. Puoi anche scegliere se autorizzare o meno gli indirizzi non qualificati per i quali non sono stati restituiti dati.

Per modificare la configurazione predefinita, fare clic sul collegamento **[!UICONTROL Edit...]**.

![](assets/target-exclusion-settings.png)

+++ Visualizza le opzioni disponibili

* **[!UICONTROL Exclude duplicate addresses during delivery]**: questa opzione è attiva per impostazione predefinita e rimuove gli indirizzi e-mail duplicati durante la consegna. La strategia applicata può variare a seconda del modo in cui Adobe Campaign viene utilizzato e del tipo di dati nel database. Il valore dell’opzione può essere configurato per ogni modello di consegna.
* **[!UICONTROL Exclude recipients who no longer want to be contacted]** , ovvero i destinatari i cui indirizzi e-mail si trovano in fase di inserisce nell&#39;elenco Bloccati (opt out) di. Questa opzione deve rimanere selezionata per rispettare l&#39;etica professionale dell&#39;e-marketing.
* **[!UICONTROL Exclude quarantined recipients]**: questa opzione consente di escludere dal target i profili con un indirizzo messo in quarantena. Si consiglia vivamente di mantenere selezionata questa opzione. Ulteriori informazioni sulla gestione della quarantena in [questa sezione](../send/quarantines.md).
* **[!UICONTROL Limit delivery]** a un determinato numero di messaggi. Questa opzione consente di immettere il numero massimo di messaggi da inviare. Se il pubblico di destinazione supera il numero di messaggi indicati, viene applicata una selezione casuale. Per inviare tutti i messaggi, mantieni questo valore su &quot;0&quot;.
* **[!UICONTROL Keep duplicate records (same identifier)]**: questa opzione consente di inviare più consegne a destinatari che soddisfano diversi criteri di targeting.
+++


### Selezionare i destinatari dei messaggi di bozza {#select-the-proof-target}

Per le consegne e-mail, puoi inviare bozze per convalidare il contenuto del messaggio. L’invio di bozze ti consente di controllare il collegamento di rinuncia, la pagina speculare e tutti gli altri collegamenti, convalidare il messaggio, verificare che siano visualizzate le immagini, rilevare eventuali errori, ecc. Puoi anche controllare la progettazione e il rendering su dispositivi diversi.

Una bozza è un messaggio specifico che ti consente di testare un messaggio prima di inviarlo al pubblico principale. I destinatari della bozza hanno il compito di approvare il messaggio: rendering, contenuto, impostazioni di personalizzazione, configurazione.

Per ulteriori informazioni sui destinatari e sull&#39;invio di bozze, consulta [questa sezione](../send/preview-and-proof.md#send-proofs).


#### Video tutorial {#seeds-and-proofs-video}

Questo video illustra come aggiungere seed e bozze a un’e-mail esistente e come inviarla.

>[!VIDEO](https://video.tv.adobe.com/v/333404?quality=12)

Sono disponibili altri video dimostrativi di Campaign Classic [qui](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/overview.html?lang=it).

## Preparare e convalidare la consegna {#validate-the-delivery}

Quando una consegna è stata creata e configurata, devi convalidarla prima di inviarla al target principale.

Per eseguire questa operazione:

1. **Analizza la consegna**: questo passaggio ti consente di preparare i messaggi da consegnare. [Ulteriori informazioni](../send/delivery-analysis.md).

1. **Invia bozze**: questo passaggio ti consente di controllare contenuto, URL, personalizzazione e così via. [Ulteriori informazioni](../send/preview-and-proof.md).

>[!IMPORTANT]
>
>I due passaggi sopra **devono essere** eseguiti dopo ogni modifica al contenuto del messaggio.


## Configurare e inviare la consegna {#configuring-and-sending-the-delivery}

Accedi ai parametri di consegna per configurare altre impostazioni e definire la modalità di invio dei messaggi. Puoi definire la priorità di consegna, impostare l’invio ondate, configurare le impostazioni per i nuovi tentativi e verificare l’invio della consegna. Al termine della configurazione, puoi confermare l’invio. I messaggi vengono quindi inviati immediatamente o in base alla pianificazione della consegna.

Scopri come configurare le impostazioni di consegna in [questa pagina](../send/configure-and-send.md).
