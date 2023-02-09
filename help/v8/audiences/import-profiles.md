---
title: Importare profili in Campaign
description: Scopri come importare i contatti in Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 11%

---

# Importare i profili da un file{#create-profiles}

Per compilare il database di Campaign, puoi [aggiungere profili manualmente](create-profiles.md) o importa profili come descritto di seguito. È inoltre possibile utilizzare i file importati per aggiornare i dati di contatto.

## Importare profili con un flusso di lavoro {#import-profiles-with-a-wf}

I flussi di lavoro possono essere un modo utile per automatizzare alcuni dei processi di importazione. Sia che importi dati da un file locale o da un SFTP, puoi utilizzare i flussi di lavoro per standardizzare le procedure di gestione dei dati.

### Utilizzare i dati di un elenco: Leggi elenco {#data-from-read-list}

Prepara e struttura i dati in un file per importarli con un flusso di lavoro. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html).

### Caricare dati da un file {#data-from-a-file}

I dati elaborati in un flusso di lavoro possono essere estratti da un file strutturato in modo che possano essere importati in Adobe Campaign. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html).

Una volta raccolti i dati, puoi utilizzarli nei flussi di lavoro, ad esempio per arricchire una consegna o aggiornare il database. Per ulteriori informazioni al riguardo, consulta [questa sezione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html).

## Importazioni una tantum{#import-jobs}

Adobe Campaign fornisce una funzionalità di importazione generica che consente, ad esempio, di estrarre un elenco di clienti o potenziali clienti che diventeranno parte di una popolazione target, o di fornire al database dati provenienti da file esterni.

Le importazioni generiche vengono gestite dal **[!UICONTROL Profiles and Targets > Jobs]** menu della home page di Adobe Campaign.

![](assets/new-import-job.png)

I passaggi per eseguire un’importazione generica sono descritti in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=it){target="_blank"}.
