---
product: campaign
title: Configurare i sondaggi online
description: Scopri come configurare i sondaggi online
feature: Surveys
version: Campaign v8, Campaign Classic v7
exl-id: 387bc362-4064-4181-9385-8e0c3423ba3e
TQID: 'https://experienceleague.adobe.com/1BTkZ--FyHkp7u0eya-lmuELDu8AMmeC96eGsonYcVM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: 71b1c383-45b9-57e0-b8cd-ea2e98a01a26
    internal-label: Surveys
subfeature_v2:
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
source-git-commit: aa436bfd174075f7ed3e144ea0b16832b6b811ff
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%
---
# Configurare i sondaggi online{#configuring-surveys}

>[!AVAILABILITY]
>
>I sondaggi non sono disponibili per [distribuzioni FFDA di Campaign](../../architecture/enterprise-deployment.md).



## Proprietà sondaggio {#survey-properties}

I sondaggi online sono completamente configurabili e personalizzabili per soddisfare le tue esigenze. I parametri devono essere immessi nella finestra delle proprietà.

I parametri disponibili sono descritti in dettaglio in [questo documento](https://experienceleague.adobe.com/it/docs/campaign-classic/using/designing-content/web-forms/defining-web-forms-properties){target="_blank"}.

![](assets/s_ncs_admin_survey_properties_general.png)

## Archiviazione dei dati del sondaggio {#survey-data-storage}

Per impostazione predefinita, i campi del modulo Web vengono memorizzati nella tabella dei destinatari. Per utilizzare un&#39;altra tabella, selezionarla nel campo **[!UICONTROL Document type]**. L&#39;icona **[!UICONTROL Zoom]** consente di visualizzare il contenuto della tabella selezionata.

Le risposte ai sondaggi forniti dagli utenti che non sono memorizzate nei campi (ma in variabili locali) sono memorizzate nella tabella **Risposte ai sondaggi**. È possibile modificare lo schema utilizzato in base al campo **[!UICONTROL Library]**. Questo campo è disponibile solo per **sondaggi**.
