---
product: campaign
title: Caricamento dati (RDBMS)
description: Ulteriori informazioni sull’attività del flusso di lavoro Caricamento dati (RDBMS)
feature: Workflows, Data Management Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 2d650573-f630-4aba-bd40-2db88ef1c346
TQID: 'https://experienceleague.adobe.com/3FkutZSFu-yv9yuqmqQoxVrGaEVJrVuErmEC95JbVTM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: 97f7b899-98c8-5133-9446-bfaf99a51b9f
    internal-label: Data Management Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%
---
# Caricamento dati (RDBMS){#data-loading-rdbms}



L&#39;attività **[!UICONTROL Data loading (RDBMS)]** ti consente di accedere direttamente a questo database esterno e di raccogliere solo i dati necessari per il targeting.

Per migliorare le prestazioni, è consigliabile utilizzare l’attività di query, in cui è possibile utilizzare i dati di un database esterno. Per ulteriori informazioni, vedere [Accesso a un database esterno (FDA)](accessing-an-external-database-fda.md).

Il funzionamento è il seguente:

1. Selezionare l&#39;origine dati dall&#39;elenco e immettere il nome della tabella contenente i dati da estrarre.

   ![](assets/s_advuser_wf_sgbd_sample_1.png)

   Il nome della tabella immesso nel campo corrispondente viene utilizzato come modello per la raccolta dei dati nel database esterno. Il nome della tabella elaborata dal flusso di lavoro può essere calcolato o trasmesso dalla transizione in entrata dell’attività di caricamento dei dati. Per selezionare la tabella da utilizzare, fare clic su **[!UICONTROL Advanced..]**. collegare e selezionare l&#39;opzione **[!UICONTROL Specified in the transition]** o **[!UICONTROL Explicit]**.

   ![](assets/s_advuser_wf_sgbd_sample_5.png)

1. Fare clic sul collegamento **[!UICONTROL Select the columns to extract...]** per scegliere i dati da raccogliere nel database.

   ![](assets/s_advuser_wf_sgbd_sample_2.png)

1. Puoi definire un filtro per questi dati. A tale scopo, fare clic sul collegamento **[!UICONTROL Edit query....]**.

   I dati raccolti in questo modo possono essere utilizzati in tutto il ciclo di vita del flusso di lavoro.
