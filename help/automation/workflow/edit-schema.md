---
product: campaign
title: Modifica di uno schema
description: Ulteriori informazioni sull’attività Modifica flusso di lavoro dello schema
feature: Workflows, Targeting Activity
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 16fb1aa5-cf99-4461-a1a4-7a68d97e2a74
TQID: https://experienceleague.adobe.com/uHsIfXEPlhLjwbGdRaUagbAhFhZb5JFxGurpSH4c0fI
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 115
ht-degree: 3%

---

# Modifica di uno schema{#edit-schema}



I dati possono essere trasformati, normalizzati e, se necessario, arricchiti nel flusso di lavoro utilizzando l&#39;attività **[!UICONTROL Edit schema]**. Viene generalmente utilizzato per normalizzare la struttura dei dati: è possibile rinominare le colonne di output o modificarne il contenuto, ad esempio calcolando i valori medi di un campo o di un aggregato.

Questa attività non modifica i dati nella tabella di lavoro, ma solo il relativo schema, ovvero la vista logica dei dati.

![](assets/wf_manipulation_box.png)

È inoltre possibile creare join con altre tabelle di lavoro tramite la scheda **[!UICONTROL Links]**.

![](assets/wf_manipulation_box_link_tab.png)

La sezione inferiore consente di configurare l’elenco delle condizioni di join, ovvero i criteri utilizzati per riconciliare i dati delle due tabelle.
