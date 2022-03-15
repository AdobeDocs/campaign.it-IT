---
product: campaign
title: Presentare un’offerta (interazione in entrata)
description: Scopri come presentare la migliore offerta utilizzando il modulo di interazione di Campaign
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
source-git-commit: c19ac91fe7b4b825f75ec096320efabc3e78328c
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 9%

---

# Presentare l’offerta migliore{#interaction-present-offers}

Le offerte possono essere presentate su vari spazi di offerta utilizzando [un canale in entrata o in uscita](interaction-architecture.md#interaction-types). Questo capitolo descrive alcune funzioni specifiche per i canali in entrata.

![](assets/inbound-interactions.png)

Affinché un’offerta possa essere selezionata dal motore di offerta, deve essere approvata e disponibile in un ambiente live.

![](../assets/do-not-localize/book.png) Per ulteriori informazioni, consulta la [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=en#approving-offer-content)

Nel contesto di un contatto in entrata, l’utente che sta navigando nella pagina può essere identificato dal sito web o meno. Il motore di offerte presenta offerte diverse per i profili identificati e per i profili anonimi.

Prima di poter presentare offerte su un canale in entrata, devi configurare la chiamata del motore di offerta in cui desideri presentare le offerte. Nella maggior parte dei casi, per un’interazione in entrata, si tratta della pagina web.

>[!NOTE]
>
>Per le interazioni in entrata, devi configurare specificatamente il motore di offerta per presentare e aggiornare una o più offerte.
>
>È inoltre necessario attivare la modalità unitaria negli spazi di offerta. Per ulteriori informazioni, consulta [questa pagina](interaction-offer-spaces.md).
