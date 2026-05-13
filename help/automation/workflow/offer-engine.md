---
product: campaign
title: Motore di offerta
description: Motore di offerta
feature: Workflows, Interaction
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: d77858e1-3cd5-4372-b1bc-ea4b518c958d
TQID: https://experienceleague.adobe.com/1ZdqlgFBd-cmAQ-B--443wvLhmUXZ9YD4l-A9enANhY
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 137
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
