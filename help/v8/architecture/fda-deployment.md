---
title: Introduzione all’implementazione del Snowflake FDA di Campaign
description: Introduzione all’implementazione del Snowflake FDA di Campaign
feature: Overview
role: Admin, Developer, User
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# [!DNL Campaign] FDA [!DNL Snowflake] distribuzione{#gs-fda-snowflake}

In un [!DNL Snowflake] implementazione FDA (predefinita), [!DNL Adobe Campaign] v8 è connesso a [!DNL Snowflake] per accedere ai dati tramite [Federated Data Access](../connect/fda.md) funzionalità: è possibile accedere ed elaborare dati e informazioni esterni archiviati nel [!DNL Snowflake] senza modificare la struttura dei dati di Adobe Campaign.

## Vantaggi{#fda-benefits}

Questo modello di distribuzione offre i seguenti vantaggi:

* **Storage e prestazioni**
Puoi spostare i dati storici in [!DNL Snowflake] quindi riduci le dipendenze al limite degli Adobe Campaign ID. Questa architettura riduce anche la dipendenza dallo storage PostgreSQL e i limiti delle prestazioni. Poiché nel database di Campaign vengono memorizzati meno dati, le prestazioni risultano migliori e le attività di manutenzione vengono eseguite più rapidamente.

* **Estensione del modello dati e gestione dei dati**
È possibile creare tabelle in [!DNL Snowflake] e collegarli ad Adobe Campaign, ad esempio per utilizzare i dati archiviati durante i periodi di conservazione o per eseguire processi di segmentazione con prestazioni eccezionali.

  Questa architettura consente inoltre di utilizzare le funzionalità del flusso di lavoro di gestione dati in [!DNL Snowflake]. Solo gli aggregati e le tabelle temporanee vengono spostati in Campaign a scopo di personalizzazione e consegna.


## Architettura{#fda-archi}

Con questo modello di distribuzione, gli utenti di Adobe Campaign possono estendere i propri dati in [!DNL Snowflake] e sfrutta i vantaggi di una singola piattaforma dati integrata per ottenere informazioni approfondite in tempo reale sui dati delle campagne di marketing. Offre agli utenti la possibilità di sfruttare appieno i propri dati offrendo una piattaforma unica, unificata e di facile utilizzo per l’analisi dei dati. La piattaforma di dati cloud non richiede alcuna gestione, in quanto si adatta all’infinito per supportare qualsiasi volume di dati di marketing da Adobe Campaign.

La comunicazione generale tra server e processi viene eseguita in base allo schema seguente:

![](assets/fda-architecture.png)

PostgreSQL è il database primario e Snowflake è il database secondario. Puoi estendere il modello dati e archiviare i dati sul Snowflake. Successivamente, puoi eseguire ETL, segmentazione e rapporti su un set di dati di grandi dimensioni con prestazioni eccezionali.
