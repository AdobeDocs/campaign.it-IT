---
title: Aggiornare la struttura del database
description: Aggiornare la struttura del database
feature: Configuration
role: Developer
level: Intermediate, Experienced
exl-id: fc64f3ca-67f1-47b7-b154-9c9dd044192c
TQID: 'https://experienceleague.adobe.com/1UBvvvkN-05BqOe4aOMpYFtKEMp0Yf-q9ECtbtmHzb0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: a14877cc-63b1-41d9-bf0b-5f97cadd0417
    internal-label: Configuration guidelines
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 0%
---
# Aggiornare la struttura del database {#updating-the-database-structure}

Per applicare le modifiche apportate agli schemi, avviare la procedura guidata di aggiornamento del database. L&#39;assistente è accessibile tramite **[!UICONTROL Tools > Advanced > Update database structure]**. Controlla se la struttura fisica del database corrisponde alla relativa descrizione logica ed esegue gli script di aggiornamento SQL.

![Procedura guidata di aggiornamento del database: pagina Aggiorna parametri con il pulsante Avanti per avviare il processo di individuazione automatica](assets/schema_update.png)

I moduli nel database vengono compilati e attivati automaticamente.

![Procedura guidata di aggiornamento del database: pagina Modifica tabelle con elenco tabelle, con la tabella CusContracts impostata per la sincronizzazione](assets/schema_update_select2.png)

Seguire la procedura riportata di seguito e visualizzare lo script SQL di aggiornamento del database:

![Procedura guidata di aggiornamento del database: pagina Aggiorna script con lo script SQL CREATE TABLE per CusContracts](assets/schema_update2.png)

>[!NOTE]
>
>Si trova in un campo di modifica e può essere modificato per eliminare o aggiungere codice SQL.

Quindi, avviare l&#39;aggiornamento del database:

![Procedura guidata di aggiornamento del database Avvia la pagina di aggiornamento del database con il registro che mostra l&#39;aggiornamento completato al 100%](assets/schema_update3.png)
