---
title: Catalogo delle offerte di interazione campagna
description: Scopri come creare un catalogo di offerte
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: 911096e2-0307-46a8-873c-ee2248b8e3e8
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# Creare un catalogo di offerte

Come un **Gestione offerte**, sei responsabile della creazione del catalogo delle offerte.

Un catalogo di offerta è associato a un singolo ambiente preesistente. Le offerte di questo catalogo possono essere associate solo agli spazi specificati nello stesso ambiente.

Prima di creare le offerte, devi specificare un [ambiente](interaction-env.md) che contiene tutte le caratteristiche (idoneità, vincoli sul target, regole di presentazione) di un set di offerte, ordinate in categorie, nonché l’elenco dei relativi spazi.

## Creare categorie di offerta{#creating-offer-categories}

Le offerte sono organizzate in categorie/sottocategorie. Le categorie vengono create in **[!UICONTROL Design]** e viene distribuito automaticamente nel **[!UICONTROL Live]** ambiente (ovvero reso disponibile) quando le offerte in essi contenute vengono approvate. Il **[!UICONTROL Design]** L’ambiente contiene una categoria predefinita per la ricezione di tutte le offerte. È possibile creare sottocategorie per aggiungere una gerarchia alle offerte di catalogo.

Per ogni categoria, puoi definire **date di idoneità**, periodo durante il quale le offerte contenute nella categoria possono essere presentate al target. Puoi anche regolare il peso di una categoria per assegnare la priorità alla presentazione dell’offerta.

Per creare una nuova categoria, effettua le seguenti operazioni:

1. Browser per **[!UICONTROL Offer catalog]** cartella.

   ![](assets/offer_cat_create_001.png)

1. Fai clic con il pulsante destro del mouse e seleziona (Copia negli Appunti) **[!UICONTROL Create a new "Offer category" folder]** dall’elenco a discesa.

   ![](assets/offer_cat_create_002.png)

1. Rinomina la categoria. Puoi modificare l’etichetta in un secondo momento utilizzando **[!UICONTROL General]** scheda.

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >Ripeti questi passaggi per creare tutte le categorie necessarie.

   In seguito, se necessario, è possibile:

   * Assegna date di idoneità da **[!UICONTROL Eligibility]** scheda.

     ![](assets/offer_cat_create_004.png)

   * **[!UICONTROL Edit query]** per applicare filtri al target dell’offerta.

   * Riepilogo delle regole di idoneità.Per visualizzarle, fare clic sul pulsante **[!UICONTROL Schedule and eligibility rules of the offer]** collegamento.

## Aggiungere una categoria di fallback

Al fine di garantire che tutti i destinatari ricevano una proposta di offerta, è possibile aggiungere sistematicamente una o più categorie di offerta nelle raccomandazioni.

Queste offerte di fallback devono avere un peso basso (ma non nullo), in modo che vengano prese in considerazione solo se non sono idonee offerte con un peso maggiore.

Inoltre, a queste offerte non deve essere applicata alcuna regola di presentazione per garantire che vengano sempre incluse nelle raccomandazioni. Ciò significa che, durante una proposta, se non è disponibile un’offerta di peso superiore, il destinatario riceverà almeno un’offerta da questa categoria.

Per includere una categoria di fallback nelle raccomandazioni, effettua le seguenti operazioni:

1. Accedi al catalogo delle offerte.
1. Fai clic su **[!UICONTROL Eligibility]** e seleziona la scheda **[!UICONTROL Always include this category in the recommendations]** opzione.
1. Fai clic su **[!UICONTROL Save]**.

   ![](assets/offer_cat_default_001.png)
