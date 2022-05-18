---
title: Importare profili in Campaign
description: Scopri come importare i contatti in Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 6%

---

# Importare i profili da un file{#create-profiles}

Per compilare il database di Campaign, puoi [aggiungere profili manualmente](create-profiles.md) o importa profili come descritto di seguito. È inoltre possibile utilizzare i file importati per aggiornare i dati di contatto.

## Importare profili con un flusso di lavoro {#import-profiles-with-a-wf}

I flussi di lavoro possono essere un modo utile per automatizzare alcuni dei processi di importazione. Sia che importi dati da un file locale o da un SFTP, puoi utilizzare i flussi di lavoro per standardizzare le procedure di gestione dei dati.

### Utilizzare i dati di un elenco: Leggi elenco {#data-from-read-list}

Prepara e struttura i dati in un file per importarli con un flusso di lavoro.

Per ulteriori informazioni sull’utilizzo dell’attività di lettura dell’elenco in un flusso di lavoro, consulta [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/read-list.html){target=&quot;_blank&quot;}.

### Caricare dati da un file {#data-from-a-file}

I dati elaborati in un flusso di lavoro possono essere estratti da un file strutturato in modo che possano essere importati in Adobe Campaign.

Una descrizione dell’attività di caricamento dei dati si trova nella sezione [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/data-loading--file-.html){target=&quot;_blank&quot;}.

Una volta raccolti i dati, puoi utilizzarli nei flussi di lavoro, ad esempio per arricchire una consegna o aggiornare il database. Per ulteriori informazioni, consulta [Documentazione di Campaign Classic v7]https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/how-to-use-workflow-data.htmll){target=&quot;_blank&quot;}.

## Importazioni una tantum{#import-jobs}

Adobe Campaign fornisce una funzionalità di importazione generica che consente, ad esempio, di estrarre un elenco di clienti o potenziali clienti che diventeranno parte di una popolazione target, o di fornire al database dati provenienti da file esterni.

Le importazioni generiche vengono gestite dal **[!UICONTROL Profiles and Targets > Jobs]** menu della home page di Adobe Campaign.

![](assets/new-import-job.png)

I passaggi per eseguire un’importazione generica sono descritti in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=it){target=&quot;_blank&quot;}.
