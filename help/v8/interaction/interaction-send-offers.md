---
title: Inviare un’offerta tramite interazione con Campaign
description: Scopri come inviare un’offerta
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: d39b1768-4c39-4d64-b9b6-d9c9424a2b0d
source-git-commit: 0a55d947a7646aab64ab2f9d0d09a6f930db576e
workflow-type: tm+mt
source-wordcount: '1265'
ht-degree: 7%

---

# Inviare un’offerta{#send}

Affinché un’offerta possa essere selezionata dal motore di offerta, deve essere approvata e disponibile in un **Live** ambiente. [Ulteriori informazioni](interaction-offer.md#approve-offers)

La presentazione dell’offerta tramite un canale di comunicazione in uscita viene eseguita tramite direct mailing, e-mail o consegne su dispositivi mobili. Puoi anche utilizzare la modalità unitaria con la messaggistica transazionale (Centro messaggi).

## Inserire un’offerta in una consegna {#offer-into-a-delivery}

Per inserire le proposte di offerta in una consegna, segui i passaggi seguenti:

1. Nella finestra di dialogo della consegna, fai clic su **Offerte** icona.

   ![](assets/offer_delivery_001.png)

1. Seleziona lo spazio corrispondente all’ambiente delle offerte.

   ![](assets/offer_delivery_002.png)

1. Per perfezionare la scelta delle offerte da parte del motore, seleziona la categoria di cui fanno parte le offerte da presentare oppure uno o più temi. È consigliabile utilizzare solo uno di questi campi alla volta per evitare di sovraccaricare le restrizioni.

   ![](assets/offer_delivery_003.png)

   ![](assets/offer_delivery_004.png)

1. Specifica il numero di offerte che desideri inserire nel corpo della consegna.

   ![](assets/offer_delivery_005.png)

1. Seleziona la **[!UICONTROL Exclude non-eligible recipients]** se necessario. [Ulteriori informazioni](#parameters-for-calling-offer-engine)

   ![](assets/offer_delivery_006.png)

1. Se necessario, selezionare **[!UICONTROL Do not display anything if no offers are selected]** opzione. [Ulteriori informazioni](#parameters-for-calling-offer-engine)

   ![](assets/offer_delivery_007.png)

1. Inserisci le proprietà nel contenuto della consegna utilizzando i campi di unione. Il numero di proposte disponibili dipende dal modo in cui viene configurata la chiamata del motore e il loro ordine dipende dalla priorità delle offerte.

   ![](assets/offer_delivery_008.png)

1. Completa il contenuto, esegui un test e invia la consegna.

   ![](assets/offer_delivery_010.png)


### Parametri del motore di offerta {#parameters-for-calling-offer-engine}

* **[!UICONTROL Space]** : spazio dell’ambiente dell’offerta che deve essere selezionato per attivare il motore delle offerte.
* **[!UICONTROL Category]** : cartella specifica in cui vengono ordinate le offerte. Se non viene specificata alcuna categoria, tutte le offerte contenute nell’ambiente verranno prese in considerazione dal motore di offerta, a meno che non venga selezionato un tema.
* **[!UICONTROL Themes]** : parole chiave definite a monte nelle categorie. Queste fungono da filtro e ti consentono di perfezionare il numero di offerte da presentare selezionandole in un set di categorie.
* **[!UICONTROL Number of propositions]** : numero di offerte restituite dal motore che possono essere inserite nel corpo della consegna. Se non vengono inserite nel messaggio, le offerte verranno comunque generate, ma non presentate.
* **[!UICONTROL Exclude non-eligible recipients]** : Questa opzione consente di attivare o disattivare l’esclusione dei destinatari per i quali non sono disponibili sufficienti offerte idonee. Il numero di proposte idonee può essere inferiore al numero richiesto di proposte. Se questa casella è selezionata, i destinatari che non dispongono di un numero sufficiente di proposte verranno esclusi dalla consegna. Se non selezioni questa opzione, questi destinatari non verranno esclusi ma non avranno il numero richiesto di proposte.
* **[!UICONTROL Do not display anything if no offer is selected]** : questa opzione ti consente di scegliere come verrà elaborato il messaggio nel caso in cui una delle proposte non esista. Quando questa casella è selezionata, la rappresentazione della proposta mancante non viene visualizzata e nel messaggio relativo non verrà visualizzato alcun contenuto. Se la casella non è selezionata, il messaggio viene annullato durante l’invio e i destinatari non riceveranno più messaggi.

## Inviare offerte nei flussi di lavoro{#offer-via-wf}

Diverse attività di flusso di lavoro ti consentono di definire il modo in cui vengono presentate le offerte:

* Arricchimento
* Motore di offerta
* Offerte per cella

### Arricchimento {#enrichment}

Il **Arricchimento** l’attività ti consente di aggiungere offerte o collegamenti alle offerte per i destinatari della consegna.[Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html)

Ad esempio, puoi arricchire i dati di una query del destinatario prima di una consegna.

![](assets/int_enrichment_offer1.png)

Esistono due metodi per specificare le proposte di offerta.

* Specifica di un’offerta o di una chiamata del motore di offerta.
* Riferimento a un collegamento a un’offerta.

#### Specifica un’offerta o una chiamata al motore di offerta {#specifying-an-offer-or-a-call-to-the-offer-engine}

Dopo aver configurato **Query** attività:

1. Aggiungi e apri un **Arricchimento** attività.
1. Nella scheda **[!UICONTROL Enrichment]**, seleziona **[!UICONTROL Add data]**.
1. Seleziona **[!UICONTROL An offer proposition]** nei tipi di dati da aggiungere.

   ![](assets/int_enrichment_offer2.png)

1. Specifica un identificatore e un’etichetta per la proposta che verrà aggiunta.
1. Specifica la selezione dell’offerta. Esistono due opzioni possibili per questo:

   * **[!UICONTROL Search for the best offer in a category]** : seleziona questa opzione e specifica i parametri di chiamata del motore di offerta (spazio dell’offerta, categoria o temi, data di contatto, numero di offerte da mantenere). Il motore calcola automaticamente le offerte da aggiungere in base a questi parametri. È consigliabile completare **[!UICONTROL Category]** o **[!UICONTROL Theme]** e non entrambi contemporaneamente.

     ![](assets/int_enrichment_offer3.png)

   * **[!UICONTROL A pre-defined offer]** : seleziona questa opzione e specifica uno spazio dell’offerta, un’offerta specifica e una data di contatto per configurare direttamente l’offerta da aggiungere, senza chiamare il motore di offerta.

     ![](assets/int_enrichment_offer4.png)

1. Quindi configura un’attività di consegna che corrisponde al canale scelto. [Ulteriori informazioni](#offer-into-a-delivery)

   >[!NOTE]
   >
   >Il numero di proposte disponibili per l’anteprima dipende dalla configurazione eseguita nell’attività di arricchimento anziché da qualsiasi configurazione possibile eseguita direttamente nella consegna.

#### Fare riferimento a un collegamento a un’offerta {#referencing-a-link-to-an-offer}

È inoltre possibile fare riferimento a un collegamento a un’offerta in un **Arricchimento** attività.

A tale scopo, segui la procedura indicata di seguito:

1. Seleziona **[!UICONTROL Add data]** nel file dell’attività **[!UICONTROL Enrichment]** scheda.
1. Nella finestra in cui si sceglie il tipo di dati da aggiungere, selezionare **[!UICONTROL A link]**.
1. Seleziona il tipo di collegamento che desideri stabilire e la relativa destinazione. In questo caso, la destinazione è lo schema dell’offerta.

   ![](assets/int_enrichment_link1.png)

1. Specifica il join tra i dati della tabella in entrata nell’attività di arricchimento (qui la tabella dei destinatari) e la tabella delle offerte. Ad esempio, puoi collegare un codice di offerta a un destinatario.

   ![](assets/int_enrichment_link2.png)

1. Quindi configura un’attività di consegna che corrisponde al canale scelto. [Ulteriori informazioni](#offer-into-a-delivery)

   >[!NOTE]
   >
   >Il numero di proposte disponibili per l’anteprima dipende dalla configurazione eseguita nella consegna.

#### Classificazioni e pesi delle offerte del Negozio {#storing-offer-rankings-and-weights}

Per impostazione predefinita, quando **Arricchimento** L’attività viene utilizzata per fornire le offerte; le loro classificazioni e i loro pesi non vengono memorizzati nella tabella delle proposte.

>[!NOTE]
>
>Il **[!UICONTROL Offer engine]** l’attività memorizza queste informazioni per impostazione predefinita.

Tuttavia, è possibile memorizzare queste informazioni come segue:

1. Crea una chiamata al motore di offerta in un’attività di arricchimento inserita dopo una query e prima di un’attività di consegna. [Ulteriori informazioni](#specifying-an-offer-or-a-call-to-the-offer-engine)
1. Nella finestra principale dell’attività, seleziona **[!UICONTROL Edit additional data...]**.

   ![](assets/ita_enrichment_rankweight_1.png)

1. Aggiungi il **[!UICONTROL @rank]** colonne per la classificazione e **[!UICONTROL @weight]** per il peso dell’offerta.

   ![](assets/ita_enrichment_rankweight_2.png)

1. Conferma l’aggiunta e salva il flusso di lavoro.

La consegna memorizza automaticamente la classificazione e il peso delle offerte. Queste informazioni sono visibili nel **[!UICONTROL Offers]** scheda.

### Motore di offerta {#offer-engine}

Il **[!UICONTROL Offer engine]** L’attività ti consente inoltre di specificare una chiamata al motore di offerta prima della consegna.

Per ulteriori informazioni su **Motore di offerta** attività, fare riferimento a [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/offer-engine.html)

Questa attività funziona in base allo stesso principio **Arricchimento** attività con una chiamata del motore, arricchendo i dati della popolazione in entrata con un’offerta calcolata dal motore, prima di una consegna.

![](assets/int_offerengine_activity2.png)

Dopo aver configurato **Query** attività:

1. Aggiungi e apri un **[!UICONTROL Offer engine]** attività.
1. Completa i vari campi disponibili per specificare i parametri della chiamata al motore di offerta (spazio dell’offerta, categoria o temi, data di contatto, numero di offerte da mantenere). Il motore calcola automaticamente le offerte da aggiungere in base a questi parametri.

   >[!CAUTION]
   >
   >Se utilizzi questa attività, verranno memorizzate solo le proposte di offerta utilizzate nella consegna.

   ![](assets/int_offerengine_activity1.png)

1. Quindi configura un’attività di consegna che corrisponde al canale scelto. [Ulteriori informazioni](#inserting-an-offer-proposition-into-a-delivery)

### Offerte per cella {#offers-by-cell}

Il **[!UICONTROL Offers by cell]** L’attività ti consente di distribuire il gruppo in entrata (ad esempio da una query) in più segmenti e di specificare un’offerta da presentare per ciascuno di questi segmenti.

Per ulteriori informazioni su **Offerta per cella** attività, fare riferimento a [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/offers-by-cell.html)

A questo scopo, utilizza il seguente processo:

1. Aggiungi il **[!UICONTROL Offers by cell]** dopo aver specificato la popolazione target, aprila.
1. In **[!UICONTROL General]** , seleziona lo spazio dell’offerta in cui desideri presentare le offerte.
1. In **[!UICONTROL Cells]** , specificare i diversi sottoinsiemi utilizzando la scheda **[!UICONTROL Add]** pulsante:

   * Specifica la popolazione del sottoinsieme utilizzando le regole di filtro e limitazione disponibili.
   * Quindi seleziona l’offerta da presentare al sottoinsieme. Le offerte disponibili sono quelle idonee nell’ambiente delle offerte selezionato al passaggio precedente.

     ![](assets/int_offer_per_cell1.png)

1. Quindi configura un’attività di consegna che corrisponde al canale scelto.

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
