---
product: campaign
title: Presentare un’offerta (interazione in entrata)
description: Scopri come presentare l’offerta migliore utilizzando il modulo di interazione di Campaign
feature: Interaction, Offers
role: User, Admin
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
TQID: https://experienceleague.adobe.com/aC-hN1JwwFkuGc6ZNV0M3uHpM7LcXTHpyC9wCbxKziQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 8%

---

# Presenta l’offerta migliore{#interaction-present-offers}

Le offerte possono essere presentate in vari spazi di offerta utilizzando [un canale in entrata o in uscita](interaction-architecture.md#interaction-types). Questo capitolo descrive alcune funzioni specifiche per i canali in entrata.

![](assets/inbound-interactions.png)

Per poter essere selezionata dal motore di offerta, un’offerta deve essere approvata e disponibile in un ambiente live.

Per ulteriori informazioni, consulta la [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html#approving-offer-content){target="_blank"}.

Nel contesto di un contatto in entrata, l’utente che sta navigando nella pagina può essere identificato dal sito web o meno. Il motore di offerta presenta diverse offerte per profili identificati e per profili anonimi.

Prima di poter presentare le offerte su un canale in entrata, devi configurare la chiamata del motore di offerta in cui desideri che vengano presentate le offerte. Nella maggior parte dei casi per un’interazione in entrata, questa è la pagina web.

>[!NOTE]
>
>Per le interazioni in entrata, devi configurare in modo specifico il motore delle offerte per presentare e aggiornare una o più offerte.
>
>Devi anche abilitare la modalità unitaria negli spazi dell’offerta. Per ulteriori informazioni, consulta [questa pagina](interaction-offer-spaces.md).
