---
solution: Campaign v8
product: Adobe Campaign
title: Catalogo delle offerte di interazione campagna
description: Scopri come creare un catalogo di offerte
feature: Panoramica
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '1285'
ht-degree: 2%

---

# Inviare un’offerta

Affinché un’offerta possa essere selezionata dal motore di offerta, deve essere approvata e disponibile in un ambiente **Live**. [Ulteriori informazioni](interaction-offer.md#approve-offers)

La presentazione delle offerte tramite un canale di comunicazione in uscita viene eseguita tramite direct mailing, e-mail o consegne su dispositivi mobili. È inoltre possibile utilizzare la modalità unitaria con i messaggi transazionali (Centro messaggi).

## Inserire un&#39;offerta in una consegna {#offer-into-a-delivery}

Per inserire le proposte di offerta in una consegna, effettua le seguenti operazioni:

1. Nella finestra di consegna, fai clic sull&#39;icona **Offerte**.

   ![](assets/offer_delivery_001.png)

1. Seleziona lo spazio che corrisponde all’ambiente delle offerte.

   ![](assets/offer_delivery_002.png)

1. Per perfezionare la scelta delle offerte da parte del motore, seleziona la categoria in cui le offerte da presentare fanno parte o uno o più temi. È consigliabile utilizzare solo uno di questi campi alla volta per evitare di sovraccaricare le restrizioni.

   ![](assets/offer_delivery_003.png)

   ![](assets/offer_delivery_004.png)

1. Specifica il numero di offerte da inserire nel corpo della consegna.

   ![](assets/offer_delivery_005.png)

1. Se necessario, seleziona l’opzione **[!UICONTROL Exclude non-eligible recipients]** . [Ulteriori informazioni](#parameters-for-calling-offer-engine).

   ![](assets/offer_delivery_006.png)

1. Se necessario, seleziona l’opzione **[!UICONTROL Do not display anything if no offers are selected]** . [Ulteriori informazioni](#parameters-for-calling-offer-engine).

   ![](assets/offer_delivery_007.png)

1. Inserire le proprietà nel contenuto della consegna utilizzando i campi di unione. Il numero di proposte disponibili dipende dalla configurazione della chiamata del motore e dal loro ordine dipende dalla priorità delle offerte.

   ![](assets/offer_delivery_008.png)

1. Completare il contenuto, testare e inviare la consegna.

   ![](assets/offer_delivery_010.png)


### Parametri del motore di offerta {#parameters-for-calling-offer-engine}

* **[!UICONTROL Space]** : spazio dell’ambiente dell’offerta che deve essere selezionato per attivare il motore di offerta.
* **[!UICONTROL Category]** : cartella specifica in cui vengono ordinate le offerte. Se non viene specificata alcuna categoria, tutte le offerte contenute nell’ambiente verranno prese in considerazione dal motore di offerta, a meno che non venga selezionato un tema.
* **[!UICONTROL Themes]** : parole chiave definite a monte nelle categorie. Questi fungono da filtro e consentono di perfezionare il numero di offerte da presentare selezionandole in un set di categorie.
* **[!UICONTROL Number of propositions]** : numero di offerte restituite dal motore che possono essere inserite nel corpo della consegna. Se non vengono inserite nel messaggio, le offerte verranno comunque generate ma non presentate.
* **[!UICONTROL Exclude non-eligible recipients]** : Questa opzione ti consente di attivare o disattivare l’esclusione dei destinatari per i quali non sono disponibili sufficienti offerte idonee. Il numero di proposte ammissibili può essere inferiore al numero di proposte richieste. Se questa casella è selezionata, i destinatari che non hanno abbastanza proposte verranno esclusi dalla consegna. Se non selezioni questa opzione, questi destinatari non verranno esclusi ma non avranno il numero di proposte richiesto.
* **[!UICONTROL Do not display anything if no offer is selected]** : questa opzione ti consente di scegliere come verrà elaborato il messaggio nel caso in cui una delle proposte non esista. Quando questa casella è selezionata, la rappresentazione della proposta mancante non viene visualizzata e nel messaggio per la proposta non verrà visualizzato alcun contenuto. Se la casella non è selezionata, il messaggio stesso viene annullato durante l’invio e i destinatari non riceveranno più messaggi.

## Inviare offerte nei flussi di lavoro

Diverse attività del flusso di lavoro ti consentono di definire il modo in cui vengono presentate le offerte:

* Enrichment
* Motore di offerta
* Offerte per cella

### Arricchimento {#enrichment}

L’attività **Arricchimento** ti consente di aggiungere offerte o collegamenti alle offerte per i destinatari della consegna.

:arrow_Upper_right: Per ulteriori informazioni sull&#39;attività Arricchimento, consulta la documentazione [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/enrichment.html)

Ad esempio, puoi arricchire i dati di una query del destinatario prima di una consegna.

![](assets/int_enrichment_offer1.png)

Esistono due metodi per specificare le proposte di offerta.

* Specifica di un&#39;offerta o di una chiamata al motore di offerta.
* Riferimento a un collegamento a un’offerta.

#### Specifica un&#39;offerta o una chiamata al motore di offerta {#specifying-an-offer-or-a-call-to-the-offer-engine}

Dopo aver configurato l&#39;attività **Query**:

1. Aggiungi e apri un&#39;attività **Enrichment** .
1. Nella scheda **[!UICONTROL Enrichment]**, seleziona **[!UICONTROL Add data]**.
1. Seleziona **[!UICONTROL An offer proposition]** nei tipi di dati da aggiungere.

   ![](assets/int_enrichment_offer2.png)

1. Specifica un identificatore e un’etichetta per la proposta che verrà aggiunta.
1. Specifica la selezione dell’offerta. Sono disponibili due opzioni possibili:

   * **[!UICONTROL Search for the best offer in a category]** : seleziona questa opzione e specifica i parametri di chiamata del motore di offerta (spazio di offerta, categoria o tema/i, data di contatto, numero di offerte da mantenere). Il motore calcola automaticamente le offerte da aggiungere in base a questi parametri. È consigliabile completare il campo **[!UICONTROL Category]** o **[!UICONTROL Theme]** anziché entrambi allo stesso tempo.

      ![](assets/int_enrichment_offer3.png)

   * **[!UICONTROL A predefined offer]** : seleziona questa opzione e specifica uno spazio di offerta, un’offerta specifica e una data di contatto per configurare direttamente l’offerta che desideri aggiungere, senza chiamare il motore di offerta.

      ![](assets/int_enrichment_offer4.png)

1. Quindi configura un’attività di consegna corrispondente al canale scelto. [Ulteriori informazioni](#offer-into-a-delivery).

   >[!NOTE]
   >
   >Il numero di proposte disponibili per l’anteprima dipende dalla configurazione effettuata nell’attività di arricchimento, anziché da qualsiasi configurazione possibile eseguita direttamente nella consegna.

#### Fai riferimento a un collegamento a un’offerta {#referencing-a-link-to-an-offer}

Puoi anche fare riferimento a un collegamento a un&#39;offerta in un&#39;attività **Enrichment**.

Per farlo, segui la procedura indicata di seguito:

1. Seleziona **[!UICONTROL Add data]** nella scheda **[!UICONTROL Enrichment]** dell’attività.
1. Nella finestra in cui scegli il tipo di dati da aggiungere, seleziona **[!UICONTROL A link]**.
1. Seleziona il tipo di collegamento che desideri stabilire e la relativa destinazione. In questo caso, la destinazione è lo schema dell&#39;offerta.

   ![](assets/int_enrichment_link1.png)

1. Specifica il join tra i dati della tabella in entrata nell’attività di arricchimento (in questo caso la tabella dei destinatari) e la tabella delle offerte. Ad esempio, puoi collegare un codice di offerta a un destinatario.

   ![](assets/int_enrichment_link2.png)

1. Quindi configura un’attività di consegna corrispondente al canale scelto. [Ulteriori informazioni](#offer-into-a-delivery).

   >[!NOTE]
   >
   >Il numero di proposte disponibili per l’anteprima dipende dalla configurazione eseguita nella consegna.

#### Classificazione e pesi delle offerte store {#storing-offer-rankings-and-weights}

Per impostazione predefinita, quando un&#39;attività **Enrichment** viene utilizzata per fornire offerte, le loro classificazioni e i loro pesi non vengono memorizzati nella tabella delle proposte.

>[!NOTE]
>
>L’attività **[!UICONTROL Offer engine]** memorizza tali informazioni per impostazione predefinita.

Tuttavia, è possibile memorizzare queste informazioni come segue:

1. Crea una chiamata al motore di offerta in un’attività di arricchimento inserita dopo una query e prima di un’attività di consegna. [Ulteriori informazioni](#specifying-an-offer-or-a-call-to-the-offer-engine).
1. Nella finestra principale dell’attività, seleziona **[!UICONTROL Edit additional data...]**.

   ![](assets/ita_enrichment_rankweight_1.png)

1. Aggiungi le colonne **[!UICONTROL @rank]** per la classificazione e **[!UICONTROL @weight]** per il peso dell’offerta.

   ![](assets/ita_enrichment_rankweight_2.png)

1. Conferma l’aggiunta e salva il flusso di lavoro.

La consegna memorizza automaticamente la classificazione e il peso delle offerte. Queste informazioni sono visibili nella scheda **[!UICONTROL Offers]** della consegna.

### Motore di offerta {#offer-engine}

L’attività **[!UICONTROL Offer engine]** ti consente inoltre di specificare una chiamata al motore di offerta prima della consegna.

:arrow_Upper_right: Per ulteriori informazioni sull&#39;attività **Motore di offerta**, consulta la documentazione [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/offer-engine.html)

Questa attività funziona sullo stesso principio dell&#39;attività **Enrichment** con una chiamata al motore, arricchendo i dati della popolazione in entrata con un&#39;offerta calcolata dal motore, prima di una consegna.

![](assets/int_offerengine_activity2.png)

Dopo aver configurato l&#39;attività **Query**:

1. Aggiungi e apri un&#39;attività **[!UICONTROL Offer engine]** .
1. Completa i vari campi disponibili per specificare la chiamata ai parametri del motore di offerta (spazio di offerta, categoria o tema/i, data di contatto, numero di offerte da mantenere). Il motore calcola automaticamente le offerte da aggiungere in base a questi parametri.

   >[!CAUTION]
   >
   >Se utilizzi questa attività, verranno memorizzate solo le proposte di offerta utilizzate nella consegna.

   ![](assets/int_offerengine_activity1.png)

1. Quindi configura un’attività di consegna corrispondente al canale scelto. [Ulteriori informazioni](#inserting-an-offer-proposition-into-a-delivery).

### Offerte per cella {#offers-by-cell}

L’attività **[!UICONTROL Offers by cell]** ti consente di distribuire il gruppo in entrata (da una query, ad esempio) in diversi segmenti e di specificare un’offerta da presentare per ciascuno di questi segmenti.

:arrow_Upper_right: Per ulteriori informazioni sull&#39;attività **Offerta per cella**, consulta la documentazione [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/offers-by-cell.html)

A questo scopo, utilizza il seguente processo:

1. Aggiungi l’attività **[!UICONTROL Offers by cell]** una volta specificata la popolazione target, quindi aprila.
1. Nella scheda **[!UICONTROL General]** , seleziona lo spazio di offerta in cui desideri presentare le offerte.
1. Nella scheda **[!UICONTROL Cells]** , specifica i diversi sottoinsiemi utilizzando il pulsante **[!UICONTROL Add]** :

   * Specifica il gruppo di sottoinsiemi utilizzando le regole di filtraggio e limitazione disponibili.
   * Quindi seleziona l’offerta da presentare al set secondario. Le offerte disponibili sono quelle idonee nell’ambiente delle offerte selezionato al passaggio precedente.

      ![](assets/int_offer_per_cell1.png)

1. Quindi configura un’attività di consegna corrispondente al canale scelto.

<!--

## Delivering with delivery outlines {#delivering-with-delivery-outlines}

You can also present offers in a delivery using delivery outlines.

For more information on delivery outlines, refer to the Campaign - MRM guide.

1. Create a new campaign or access an existing campaign.
1. Access the delivery outlines via the campaign's **[!UICONTROL Edit]** > **[!UICONTROL Documents]** tab.
1. Add an outline then insert as many offers as you like into it by right-clicking on the outline and selecting **[!UICONTROL New]** > **[!UICONTROL Offer]**, then save the campaign.


1. Create a delivery whose delivery outlines you have access to (for example, a direct mail delivery).
1. When editing the delivery, click **[!UICONTROL Select a delivery outline]**.

   >[!NOTE]
   >
   >Depending on the type of delivery, this option can be found in the **[!UICONTROL Properties]** > **[!UICONTROL Advanced]** menu (for email deliveries for example).


1. Using the **[!UICONTROL Offers]** button, you can then configure the offer space as well as the number of offers to present in the delivery.


1. Add the propositions into the delivery body using the personalization fields (for more on this, refer to the [Inserting an offer proposition into a delivery](#inserting-an-offer-proposition-into-a-delivery) section), or in the case of a direct mail delivery, by editing the extraction file format.

   Propositions will be selected from the offers referenced in the delivery outline.

   >[!NOTE]
   >
   >Information regarding the offer rankings and weights is only saved in the proposition table if the offers are generated directly in the delivery.
-->
