---
product: campaign
title: Presentare un’offerta (interazione in entrata)
description: Scopri come presentare l’offerta migliore utilizzando il modulo di interazione di Campaign
feature: Interaction, Offers
role: User, Admin
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 4%

---

# Presenta l’offerta migliore{#interaction-present-offers}

Le offerte possono essere presentate in vari spazi dell’offerta utilizzando [un canale in entrata o in uscita](interaction-architecture.md#interaction-types). Questo capitolo descrive alcune funzioni specifiche per i canali in entrata.

![](assets/inbound-interactions.png)

Per poter essere selezionata dal motore di offerta, un’offerta deve essere approvata e disponibile in un ambiente live.

Per ulteriori informazioni, consulta [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html#approving-offer-content)

Nel contesto di un contatto in entrata, l’utente che sta navigando nella pagina può essere identificato dal sito web o meno. Il motore di offerta presenta diverse offerte per profili identificati e per profili anonimi.

Prima di poter presentare le offerte su un canale in entrata, devi configurare la chiamata del motore di offerta in cui desideri che vengano presentate le offerte. Nella maggior parte dei casi per un’interazione in entrata, questa è la pagina web.

>[!NOTE]
>
>Per le interazioni in entrata, devi configurare in modo specifico il motore delle offerte per presentare e aggiornare una o più offerte.
>
>Devi anche abilitare la modalità unitaria negli spazi dell’offerta. Per ulteriori informazioni, consulta [questa pagina](interaction-offer-spaces.md).
