---
product: campaign
title: Approvazione e attivazione di un’offerta
description: Approvazione e attivazione di un’offerta
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: managing-an-offer-catalog
exl-id: cf7649fe-f62a-4dfa-a19e-9c1ca545e3e3
TQID: 'https://experienceleague.adobe.com/f0zYxpc5-71Ci-4Q485v4rRdD1xHs6tKLkl7vrITMP0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 0%
---
# Approvazione e attivazione di un’offerta{#approving-and-activating-an-offer}



Una volta completato il contenuto dell’offerta, devi approvarlo affinché possa essere duplicato nell’ambiente live e consegnato. L’approvazione riguarda il contenuto dell’offerta e la sua idoneità.

Il banner sul dashboard delle offerte indica se l’offerta deve o meno superare il ciclo di approvazione.

![Banner del dashboard delle offerte che indica che l&#39;offerta è in attesa di approvazione, con il pulsante Approvazione.](assets/offer_validate_001.png)

## Approvazione del contenuto delle offerte {#approving-offer-content}

Approvando il contenuto dell’offerta si selezionano le rappresentazioni da rendere disponibili nell’ambiente live.

Il contenuto di un’offerta ha una rappresentazione per spazio. Poiché ogni spazio dell’offerta ha la propria struttura e le proprie funzioni di rendering, la rappresentazione dell’offerta può variare.

Puoi scegliere di approvare il contenuto dell’offerta in alcuni spazi disponibili e rifiutarlo in altri.

>[!IMPORTANT]
>
>Una volta approvati il contenuto e l’idoneità di un’offerta, il flusso di lavoro di pubblicazione (notifica di offerta) viene eseguito automaticamente e l’offerta viene resa live e disponibile su tutti gli spazi attivati.

Per approvare il contenuto dell’offerta, effettua le seguenti operazioni:

1. Fare clic sul pulsante **[!UICONTROL Approval]** e selezionare **[!UICONTROL Approve content]** nel popup.

   ![Menu Approvazione con contenuto approvato selezionato, apertura dell&#39;azione nella finestra di dialogo dell&#39;offerta.](assets/offer_validate_002.png)

1. Utilizzando l&#39;elenco a discesa, selezionare le rappresentazioni che si desidera continuare a modificare o quelle che si desidera pubblicare nell&#39;ambiente live, quindi fare clic su **[!UICONTROL Content approval]**.

   ![Azione nella finestra di dialogo dell&#39;offerta: scegliere Continua a modificare o Abilita, aggiungere un commento, fare clic su Approvazione contenuto.](assets/offer_validate_003.png)

   Una volta approvato il contenuto dell’offerta, le informazioni vengono aggiornate nella tabella del dashboard delle offerte.

   ![Dashboard offerte dopo l&#39;approvazione: la rappresentazione è Abilitata e la sezione Approvazioni mostra Contenuto approvato.](assets/offer_validate_004.png)

   >[!NOTE]
   >
   >La menzione **[!UICONTROL Content approved]** non significa che tutte le rappresentazioni dell&#39;offerta sono state abilitate e approvate. Indica che il processo di approvazione del contenuto è stato completato, indipendentemente dal fatto che tutte le offerte siano state abilitate/approvate o meno.

## Approvazione idoneità offerta {#approving-offer-eligibility}

L’approvazione dell’idoneità per l’offerta comporta l’accettazione o il rifiuto dei pesi dell’offerta e delle regole di idoneità configurate anche nell’offerta o ereditate dalle regole create nella categoria principale.

>[!IMPORTANT]
>
>Una volta approvati il contenuto e l’idoneità di un’offerta, il flusso di lavoro di pubblicazione (notifica di offerta) viene eseguito automaticamente e l’offerta viene resa live e disponibile su tutti gli spazi attivati.

* Per visualizzare l&#39;elenco completo delle regole, fare clic su **[!UICONTROL Schedule and eligibility rules]**.

  ![Elenco delle regole di pianificazione e idoneità con pesi e intervalli di date, aperto dalla finestra di dialogo di approvazione.](assets/offer_validate_005.png)

* Per modificare le regole di idoneità, fare clic su **[!UICONTROL Reject]**, quindi su **[!UICONTROL Eligibility approval]**.

  ![Finestra di dialogo di approvazione dell&#39;idoneità con Rifiuta selezionato, un commento e il pulsante di approvazione dell&#39;idoneità.](assets/offer_validate_007.png)

  I vari stati vengono aggiornati nel dashboard delle offerte.

  ![Dashboard dopo il rifiuto: l&#39;approvazione dell&#39;idoneità è stata rifiutata banner, pulsante Invia idoneità, idoneità rifiutata.](assets/offer_validate_006.png)

* Per accettare l&#39;idoneità dell&#39;offerta, fare clic su **[!UICONTROL Approve eligibility]**.

  ![Pulsante Invia idoneità che apre l&#39;azione nella finestra di dialogo dell&#39;offerta con le opzioni Approva e Rifiuta.](assets/offer_validate_008.png)

  Approva l&#39;idoneità, aggiungi un commento se necessario, quindi fai clic su **[!UICONTROL Eligibility approval]**.

  ![Finestra di dialogo di approvazione dell&#39;idoneità con l&#39;opzione Approva selezionata, un commento immesso e il pulsante di approvazione dell&#39;idoneità.](assets/offer_validate_009.png)

  I vari stati vengono aggiornati nel dashboard delle offerte.

  ![Dashboard che mostra la distribuzione dell&#39;offerta in sospeso nell&#39;ambiente live, con idoneità approvata e contenuto approvato.](assets/offer_validate_010.png)

## Tracciamento approvazione {#approval-tracking}

Il tracciamento delle approvazioni è disponibile nel dashboard delle offerte. Fare clic su **[!UICONTROL Hide/display logs]** per accedervi.

![Dashboard delle offerte con i registri di approvazione visualizzati dopo aver fatto clic su Nascondi/visualizza registri, azione elenco, tipo e approvatore.](assets/offer_validate_012.png)

>[!NOTE]
>
>Il tracciamento è disponibile anche nella scheda **[!UICONTROL Audit]** dell&#39;offerta, con i dettagli dei commenti dei revisori.

## Riavvia l’approvazione {#restart-the-approval}

Una volta avviata, l’approvazione può essere riavviata. A questo scopo, segui queste istruzioni:

1. Fare clic su **[!UICONTROL Content approved]** nel dashboard delle offerte.
1. Nella finestra **[!UICONTROL Edit]** visualizzata, selezionare l&#39;approvazione da riavviare, quindi fare clic su **[!UICONTROL Re-initialize approval to submit it again]**.
1. Confermare facendo clic su **[!UICONTROL Ok]**.

![Approvals journal nella finestra Modifica con il collegamento Reinizializza l&#39;approvazione per inviarla nuovamente.](assets/offer_validate_013.png)

## Pubblicazione dell’offerta {#publishing-the-offer}

Dopo aver approvato sia il contenuto che l’idoneità di un’offerta, l’offerta viene pubblicata da un flusso di lavoro che viene eseguito automaticamente per ogni offerta il cui ciclo di approvazione è stato completato. Il flusso di lavoro **[!UICONTROL Offer notification]** viene inoltre eseguito ogni ora per sincronizzare (se necessario) gli spazi e le categorie contenuti nel catalogo delle offerte dall&#39;ambiente di progettazione all&#39;ambiente live.

Il dashboard dell’offerta disponibile nell’ambiente di progettazione contiene informazioni relative alla pubblicazione, tra cui il nome dell’offerta corrispondente nell’ambiente live.

![Dashboard delle offerte di progettazione: banner della data di distribuzione, collegamento in linea delle offerte con stato Pubblicato, rappresentazione in linea in tempo reale.](assets/offer_golive_001.png)

Per visualizzare l’offerta disponibile nell’ambiente live, fai clic sull’etichetta dell’offerta: l’offerta live presenta una dashboard contenente tutte le informazioni rilevanti.

![Collegamento al dashboard delle offerte live, che mostra lo stato Online, l&#39;ambiente e le regole di pianificazione e idoneità.](assets/offer_golive_002.png)

## Disabilitazione di un’offerta {#disabling-an-offer}

Una volta approvata l’offerta, puoi disattivarla.

A questo scopo, vai al dashboard per un&#39;offerta online o un&#39;offerta in attesa di passare online, quindi fai clic su **[!UICONTROL Disable offer]**.

È inoltre possibile disabilitare direttamente una categoria accedendo alla scheda **[!UICONTROL Eligibility]** e selezionando la casella **[!UICONTROL Enabled]**.

>[!NOTE]
>
>Quando un’offerta viene eliminata in un ambiente di progettazione, viene disattivata automaticamente nell’ambiente online collegato. Dopo un periodo di conservazione della proposta, le offerte disattivate vengono eliminate dall’ambiente online.

![Dashboard delle offerte in attesa di distribuzione, con il pulsante Disattiva offerta utilizzato per disattivare l&#39;offerta.](assets/offer_preview_deactivate.png)
