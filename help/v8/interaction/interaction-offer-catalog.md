---
title: Catalogo delle offerte di interazione campagna
description: Scopri come creare un catalogo di offerte
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 911096e2-0307-46a8-873c-ee2248b8e3e8
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# Creare un catalogo di offerte

Come **Gestione delle offerte**, l’utente è responsabile della creazione del catalogo delle offerte.

Un catalogo di offerte è associato a un singolo ambiente preesistente. Le offerte in questo catalogo possono essere associate solo agli spazi specificati nello stesso ambiente.

Prima di creare le offerte, devi innanzitutto specificare un [ambiente](interaction-env.md) che contiene tutte le caratteristiche (idoneità, vincoli sul target, regole di presentazione) di un insieme di offerte, suddivise in categorie, nonché l’elenco dei relativi spazi.

## Creare categorie di offerta{#creating-offer-categories}

L’offerta è organizzata in categorie/sottocategorie. Le categorie vengono create nel **[!UICONTROL Design]** e implementato automaticamente in **[!UICONTROL Live]** ambiente (cioè reso disponibile) quando le offerte che contengono sono approvate. La **[!UICONTROL Design]** l’ambiente contiene una categoria predefinita per la ricezione di tutte le offerte. È possibile creare sottocategorie per aggiungere una gerarchia alle offerte del catalogo.

Per ogni categoria, puoi definire **date di ammissibilità**, ossia il periodo durante il quale le offerte contenute nella categoria possono essere presentate al loro target. Puoi anche regolare il peso di una categoria per assegnare una priorità alla presentazione dell’offerta.

Per creare una nuova categoria, segui i passaggi seguenti:

1. Browser to the **[!UICONTROL Offer catalog]** cartella.

   ![](assets/offer_cat_create_001.png)

1. Fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Create a new "Offer category" folder]** dall’elenco a discesa.

   ![](assets/offer_cat_create_002.png)

1. Rinomina la categoria. Puoi modificare l’etichetta in un secondo momento utilizzando la **[!UICONTROL General]** scheda .

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >Ripeti questi passaggi per creare tutte le categorie necessarie.

   Quindi, in base alle esigenze, puoi:

   * Assegnare le date di idoneità dal **[!UICONTROL Eligibility]** scheda .

      ![](assets/offer_cat_create_004.png)

   * **[!UICONTROL Edit query]** per applicare filtri al target dell’offerta.

   * Un riepilogo delle regole di idoneità.Per visualizzarle, fare clic sul pulsante **[!UICONTROL Schedule and eligibility rules of the offer]** link.

## Aggiungi una categoria di fallback

Per garantire che tutti i destinatari ricevano una proposta di offerta, è possibile aggiungere sistematicamente una o più categorie di offerta nelle raccomandazioni.

Queste offerte di fallback devono avere un peso basso (ma non nullo), in modo che vengano prese in considerazione solo se non sono idonee offerte con peso maggiore.

Inoltre, non deve essere applicata alcuna regola di presentazione a queste offerte per garantire che siano sempre incluse nelle raccomandazioni. Ciò significa che, durante una proposta, se non è disponibile un’offerta di peso più elevato, il destinatario riceverà almeno un’offerta da questa categoria.

Per includere una categoria di fallback nei consigli, segui i passaggi seguenti:

1. Sfoglia il catalogo delle offerte.
1. Fai clic sul pulsante **[!UICONTROL Eligibility]** e seleziona la **[!UICONTROL Always include this category in the recommendations]** opzione .
1. Fai clic su **[!UICONTROL Save]**.

   ![](assets/offer_cat_default_001.png)
