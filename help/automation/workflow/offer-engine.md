---
product: campaign
title: Motore di offerta
description: Motore di offerta
feature: Workflows, Interaction
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 4%

---

# Motore di offerta{#offer-engine}

La **[!UICONTROL Offer engine]** l’attività ti consente di definire una chiamata al motore di offerta prima di una consegna.

Questa attività funziona sullo stesso principio dell’attività di arricchimento con una chiamata al motore, arricchendo i dati della popolazione in entrata con un’offerta calcolata dal motore, prima di una consegna.

![](assets/int_offerengine_activity2.png)

Dopo aver configurato la query (consulta questo [sezione](query.md)):

1. Aggiungi e apri un **[!UICONTROL Offer engine]** attività.
1. Completa i vari campi disponibili per specificare la chiamata ai parametri del motore di offerta (spazio di offerta, categoria o tema/i, data di contatto, numero di offerte da mantenere). Il motore calcola automaticamente le offerte da aggiungere in base a questi parametri.

   >[!CAUTION]
   >
   >Se utilizzi questa attività, verranno memorizzate solo le proposte di offerta utilizzate nella consegna.

   ![](assets/int_offerengine_activity1.png)

1. Quindi configura un’attività di consegna corrispondente al canale scelto. Fai riferimento a [Consegne cross-channel](cross-channel-deliveries.md).
