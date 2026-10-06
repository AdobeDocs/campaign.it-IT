---
product: campaign
title: Gestire i fusi orari
description: Gestire i fusi orari
feature: Workflows, Configuration
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: 04b7638d-55dd-4317-b605-5d618ef014ba
TQID: 'https://experienceleague.adobe.com/M8aAiSm2KJdcKX0VuqX4NCIecbOm6u6B7xCvgs4bW-c'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: a14877cc-63b1-41d9-bf0b-5f97cadd0417
    internal-label: Configuration guidelines
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 4%
---
# Gestire i fusi orari{#managing-time-zones}

Adobe Campaign consente di gestire i ritardi tra i vari paesi interessati dalla stessa istanza. La configurazione applicata viene configurata durante la creazione dell’istanza.

In un flusso di lavoro, puoi adattare i programmi di esecuzione dell’attività e collegare un fuso orario specifico a un’attività o all’intero flusso di lavoro. Questa configurazione può essere utile durante l’importazione del file o nel quadro della pianificazione della consegna.

## Pianificazione dell’esecuzione {#execution-scheduling}

È possibile pianificare l&#39;esecuzione delle attività utilizzando la pianificazione (fare riferimento a [Pianificazione](scheduler.md)). Puoi anche utilizzare le opzioni di pianificazione disponibili nelle attività che offrono questa funzionalità. Queste attività offrono una scheda **[!UICONTROL Schedule]**: **[!UICONTROL File collector]**, **[!UICONTROL File transfer]**, **[!UICONTROL Web download]**, **[!UICONTROL Email reception]** e **[!UICONTROL SMS]**, ecc.

Per tutte le attività pianificate, ovvero tutte le attività con opzioni di pianificazione, è possibile selezionare il fuso orario da applicare. Il fuso orario viene selezionato tramite la scheda **[!UICONTROL Advanced]** dell&#39;attività interessata:

![](assets/wf-timezone-in-a-box.png)

I valori possibili sono:

* Fuso orario server

  Utilizza il fuso orario del server applicazioni Adobe Campaign.

* Fuso orario utente

  Utilizza il fuso orario dell’operatore Adobe Campaign che esegue il flusso di lavoro.

* Fuso orario del database

  Utilizza il fuso orario del server di database utilizzato.

* Fusi orari specifici

  Utilizza il fuso orario selezionato.

Se è selezionato il valore **[!UICONTROL By default]**, viene applicato il fuso orario del flusso di lavoro o, in caso contrario, quello del server applicazioni.

## Collegamento di un fuso orario a un’attività {#linking-a-time-zone-to-an-activity}

La scheda **[!UICONTROL Advanced]** delle attività del flusso di lavoro consente di selezionarne il fuso orario. Anche se nella maggior parte dei casi il fuso orario dei flussi di lavoro è sufficiente, può essere necessario sovraccaricarlo ora e ancora per un’attività specifica, ad esempio l’importazione di dati, per collegare le date al fuso orario corretto.
