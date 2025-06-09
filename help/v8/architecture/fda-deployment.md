---
title: Introduzione all’implementazione FDA di Campaign
description: Introduzione all’implementazione FDA di Campaign
feature: Architecture, Federated Data Access, Deployment
role: Admin, Developer
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
source-git-commit: 561e4b6d2c99e98e068132c80c2bebb756b60a44
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# Distribuzione FDA [!DNL Campaign]{#gs-fda}

Nella distribuzione FDA di Campaign (predefinita), [!DNL Adobe Campaign] v8 può essere connesso a [!DNL Snowflake] per accedere ai dati tramite la funzionalità [Federated Data Access](../connect/fda.md): è quindi possibile accedere ed elaborare i dati e le informazioni esterni archiviati nel database [!DNL Snowflake] senza modificare la struttura dei dati di Adobe Campaign.

>[!NOTE]
>
>In questo modello di distribuzione, il database secondario [!DNL Snowflake] è disponibile solo su richiesta. Per aggiornare la distribuzione con [!DNL Snowflake], contatta il tuo Adobe Transition Manager.
>

## Vantaggi{#fda-benefits}

Questo modello di distribuzione offre i seguenti vantaggi:

* **Archiviazione e prestazioni**
Puoi spostare i dati storici in [!DNL Snowflake] e quindi ridurre le dipendenze al limite degli Adobe Campaign ID. Questa architettura riduce anche la dipendenza dallo storage PostgreSQL e i limiti delle prestazioni. Poiché nel database di Campaign vengono memorizzati meno dati, le prestazioni risultano migliori e le attività di manutenzione vengono eseguite più rapidamente.

* **Estensione del modello dati e gestione dati**
È possibile creare tabelle in [!DNL Snowflake] e collegarle ad Adobe Campaign, ad esempio per utilizzare i dati archiviati durante i periodi di conservazione, oppure eseguire processi di segmentazione con prestazioni eccezionali.

  Questa architettura consente inoltre di utilizzare le funzionalità del flusso di lavoro di gestione dati in [!DNL Snowflake]. Solo gli aggregati e le tabelle temporanee vengono spostati in Campaign a scopo di personalizzazione e consegna.


## Architettura{#fda-archi}

Con questo modello di distribuzione, gli utenti di Adobe Campaign possono estendere i propri dati in [!DNL Snowflake] e sfruttare i vantaggi di un&#39;unica piattaforma di dati integrata per potenti informazioni approfondite sui dati delle campagne di marketing in tempo reale. Offre agli utenti la possibilità di sfruttare appieno i propri dati offrendo una piattaforma unica, unificata e di facile utilizzo per l’analisi dei dati. La piattaforma di dati cloud non richiede alcuna gestione, in quanto si adatta all’infinito per supportare qualsiasi volume di dati di marketing da Adobe Campaign.

La comunicazione generale tra server e processi viene eseguita in base allo schema seguente:

![](assets/fda-architecture.png)

PostgreSQL è il database primario e Snowflake può essere utilizzato come database secondario. Puoi estendere il modello dati e archiviare i dati su Snowflake. Successivamente, puoi eseguire ETL, segmentazione e rapporti su un set di dati di grandi dimensioni con prestazioni eccezionali.
