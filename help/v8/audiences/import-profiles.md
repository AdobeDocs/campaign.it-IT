---
title: Importare profili in Campaign
description: Scopri come importare i contatti in Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
TQID: https://experienceleague.adobe.com/qoVtBCkTTk2DKaR605exVaJvjQ7kjKRoRg-9fJqdoo4
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2: id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 287
ht-degree: 14%

---

# Importare i profili da un file{#create-profiles}

Per popolare il database di Campaign, puoi [aggiungere profili manualmente](create-profiles.md) o importare i profili come descritto di seguito. È inoltre possibile utilizzare i file importati per aggiornare i dati dei contatti.

## Importare profili con un flusso di lavoro {#import-profiles-with-a-wf}

I flussi di lavoro possono essere utili per automatizzare alcuni dei processi di importazione. Che tu importi dati da un file locale o da un SFTP, puoi utilizzare i flussi di lavoro per standardizzare le procedure di gestione dei dati.

### Utilizza dati da un elenco: Leggi elenco {#data-from-read-list}

Prepara e struttura i dati in un file per importarlo con un flusso di lavoro. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html){target="_blank"}.

### Caricare dati da un file {#data-from-a-file}

I dati elaborati in un flusso di lavoro possono essere estratti da un file strutturato in modo che possa essere importato in Adobe Campaign. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html){target="_blank"}.

Una volta raccolti i dati, puoi utilizzarli nei flussi di lavoro, ad esempio per arricchire una consegna o aggiornare il database. Per ulteriori informazioni al riguardo, consulta [questa sezione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html){target="_blank"}.

## Importazioni una tantum{#import-jobs}

Adobe Campaign fornisce funzionalità di importazione generiche che consentono, ad esempio, di estrarre un elenco di clienti o potenziali che entreranno a far parte di una popolazione target o di fornire al database dati provenienti da file esterni.

Le importazioni generiche vengono gestite dal menu **[!UICONTROL Profiles and Targets > Jobs]** della home page di Adobe Campaign.

![](assets/new-import-job.png)

I passaggi per eseguire un&#39;importazione generica sono descritti nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=it){target="_blank"}.
