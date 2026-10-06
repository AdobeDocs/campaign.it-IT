---
product: campaign
title: SMS in entrata
description: Ulteriori informazioni sull’attività del flusso di lavoro SMS in entrata
feature: Workflows, Channels Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 2c12c45b-4429-4e60-bc96-ff70a95d4c9e
TQID: 'https://experienceleague.adobe.com/ZZcWkqyokq5qWLAHGLW7TNJimNc5a9MUEQkSr0fgKgc'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: bce277d1-7efa-48d8-9a1b-b588bb45ba1c
    internal-label: Channels Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 6%
---
# SMS in entrata{#inbound-sms}



L&#39;attività **Inbound SMS** ti consente di scaricare ed elaborare messaggi di testo da un account esterno.

## Proprietà {#properties}

![](assets/sms_rec_edit.png)

La prima scheda dell&#39;attività **SMS in entrata** consente di immettere i parametri di routing per i messaggi SMS e di immettere lo script da eseguire alla ricezione di ogni messaggio. La seconda scheda ti consente di assegnare una pianificazione all’attività e la terza scheda definisce le condizioni di scadenza dell’attività.

1. **[!UICONTROL SMS routing]**: selezionare l&#39;account esterno da utilizzare per il ripristino SMS. Gli account esterni sono configurati tramite il nodo **[!UICONTROL Administration > Platform > External accounts]** della struttura. [Ulteriori informazioni](../../v8/config/external-accounts.md)
1. **[!UICONTROL Script]**
1. **[!UICONTROL Schedule]**

   ![](assets/sms_rec_edit_2.png)

1. **[!UICONTROL Expiration]**

Le schede **[!UICONTROL Script]**, **[!UICONTROL Schedule]** e **[!UICONTROL Expiry]** sono dettagliate in [E-mail in entrata](inbound-emails.md).
