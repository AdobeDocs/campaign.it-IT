---
product: campaign
title: Motore di offerta
description: Motore di offerta
feature: Workflows, Interaction
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: d77858e1-3cd5-4372-b1bc-ea4b518c958d
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 4%

---

# Motore di offerta{#offer-engine}

L&#39;attività **[!UICONTROL Offer engine]** ti consente di definire una chiamata al motore di offerta prima di una consegna.

Questa attività funziona sullo stesso principio dell’attività di arricchimento con una chiamata al motore, arricchendo i dati della popolazione in entrata con un’offerta calcolata dal motore, prima di una consegna.

![](assets/int_offerengine_activity2.png)

Dopo aver configurato la query (consulta questa [sezione](query.md)):

1. Aggiungi e apri un&#39;attività **[!UICONTROL Offer engine]**.
1. Completa i vari campi disponibili per specificare i parametri del motore di offerta della chiamata (spazio dell’offerta, categoria o temi, data di contatto, numero di offerte da mantenere). Il motore calcola automaticamente le offerte da aggiungere in base a questi parametri.

   >[!CAUTION]
   >
   >Se utilizzi questa attività, verranno memorizzate solo le proposte di offerta utilizzate nella consegna.

   ![](assets/int_offerengine_activity1.png)

1. Quindi configura un’attività di consegna che corrisponde al canale scelto. Consulta [Consegne cross-channel](cross-channel-deliveries.md).
