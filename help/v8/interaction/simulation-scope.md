---
product: campaign
title: Ambito della simulazione
description: Ambito della simulazione
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: simulating-offers
exl-id: 4f6b3de2-3fdf-441d-925d-476e20e75c6f
TQID: 'https://experienceleague.adobe.com/mZ618bV3lzbXS09MXBXJxM5RizvMWl6lEgw0Bwb2bGI'
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
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 936b7519d13ab54d94df9305ef05d4ceb6d6742d
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 2%
---
# Ambito della simulazione{#simulation-scope}



## Definizione del campo di applicazione {#definition-of-the-scope}

Apri la scheda **[!UICONTROL Scope]** per scegliere le impostazioni.

I seguenti elementi sono obbligatori:

* Ambiente o categoria di offerta.
* Spazio dell’offerta.
* Data di contatto. Le offerte non idonee alla data di contatto non vengono prese in considerazione.
* Popolazione target.

  Se non configuri un filtro sulla destinazione, verrà presa in considerazione l’intera tabella dei destinatari.

* Numero di proposte da simulare per target.

  Il destinatario riceverà un numero così elevato di proposte. Ad esempio, se immetti 5, ogni destinatario riceverà un massimo di 5 proposte di offerta.

  ![](assets/offer_simulation_009.png)

Per perfezionare le offerte da prendere in considerazione per la simulazione, puoi aggiungere uno o più temi (precedentemente specificati nelle categorie).

Puoi anche scegliere di eseguire la simulazione su tutte le offerte o solo su quelle online. Alcuni filtri ti consentono di modificare la selezione, se lo desideri.

>[!NOTE]
>
>Specificare una data di contatto. In questo modo il motore di interazione può ordinare le offerte nell’ambiente o nella categoria selezionati. Se non è configurata alcuna data, la simulazione genera un errore.

## Aggiunta di assi di reporting {#adding-reporting-axes}

È possibile migliorare l&#39;analisi di simulazione aggiungendo assi di reporting sul target o sulle offerte stesse tramite la scheda **[!UICONTROL Calculations]**.

A tale scopo, fare clic sul pulsante **[!UICONTROL Add]** e scegliere i campi appropriati. Gli assi vengono utilizzati per il calcolo della simulazione e vengono visualizzati nel rapporto di analisi. Per ulteriori informazioni, consulta [Tracciamento della simulazione](simulation-tracking.md).

![](assets/offer_simulation_011.png)
