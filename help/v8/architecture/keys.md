---
title: Gestione delle chiavi in Campaign
description: Introduzione alla gestione delle chiavi
feature: Configuration, FFDA
role: Developer
level: Intermediate
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 3%

---

# Gestione delle chiavi e unicità {#key-management}

Nell&#39;ambito di una [Distribuzione aziendale (FFDA)](enterprise-deployment.md), la chiave primaria è un identificatore ID universalmente univoco (UUID), che è una stringa di caratteri. Per creare questo UUID, l’elemento principale dello schema deve contenere **autouuid** e **autopk** attributi impostati su **true**.

Adobe Campaign v8 utilizza [!DNL Snowflake] come database di base. Architettura distribuita del [!DNL Snowflake] Il database di non fornisce un meccanismo per garantire l’unicità di una chiave all’interno di una tabella: gli utenti finali sono responsabili della coerenza delle chiavi all’interno del database di Adobe Campaign.

Per preservare la coerenza del database relazionale è obbligatorio evitare duplicati sulle chiavi, in particolare sulle chiavi primarie. I duplicati sulle chiavi primarie causano problemi con le attività del flusso di lavoro di gestione dati come **Query**, **Reconciliation**, **Aggiorna dati**, e altro ancora. Questo è fondamentale per definire i criteri di riconciliazione corretti durante l’aggiornamento [!DNL Snowflake] tabelle.


>[!CAUTION]
>
>Le chiavi duplicate non sono limitate agli UUID. Ciò può verificarsi in con ID di, incluse le chiavi personalizzate create in tabelle personalizzate.


## Servizio Unicity{#unicity-service}

Il servizio Unicity è un componente di Cloud Database Manager che consente agli utenti di preservare e monitorare l’integrità dei vincoli di chiave univoca all’interno delle tabelle di Cloud Database. Questo consente di ridurre il rischio di inserimento di chiavi duplicate.

Poiché il database cloud non applica vincoli di unicità, il servizio Unicity riduce il rischio di inserimento di duplicati durante la gestione dei dati con Adobe Campaign.

### Flusso di lavoro Unicity{#unicity-wf}

Il servizio Unicity viene fornito con un **[!UICONTROL Unicity alerting]** flusso di lavoro integrato, per monitorare i vincoli di unicità e avvisare quando vengono rilevati duplicati.

Questo flusso di lavoro tecnico è disponibile nella **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Unicity]** di Campaign Explorer. **Non deve essere modificato**.

Questo flusso di lavoro controlla tutti gli schemi personalizzati e incorporati per rilevare le righe duplicate.

![](assets/unicity-alerting-wf.png)

Se il **[!UICONTROL Unicity alerting]** (ffdaUnicity) Il flusso di lavoro rileva alcune chiavi duplicate, che vengono aggiunte a un **Unicità audit** , che include il nome dello schema, il tipo di chiave, il numero di righe interessate e la data. Puoi accedere alle chiavi duplicate dalla **[!UICONTROL Administration > Audit > Key Unicity]** nodo.

![](assets/unicity-table.png)

In qualità di amministratore di database, puoi utilizzare un’attività SQL per rimuovere i duplicati o contattare l’Adobe Customer Care per ulteriori indicazioni.

### Avvisi{#unicity-wf-alerting}

Viene inviata una notifica specifica al **[!UICONTROL Workflow Supervisors]** gruppo di operatori quando vengono rilevate chiavi duplicate. Il contenuto e il pubblico di questo avviso possono essere modificati in **Avviso** attività del **[!UICONTROL Unicity alerting]** flusso di lavoro.

![](assets/wf-alert-activity.png)


## Guardrail aggiuntivi{#duplicates-guardrails}

Campaign viene fornito con un set di nuove protezioni per impedire l’inserimento di chiavi duplicate in [!DNL Snowflake] database.

>[!NOTE]
>
>Queste protezioni sono disponibili a partire da Campaign v8.3. Per verificare la versione, consulta [questa sezione](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

### Preparazione della consegna{#remove-duplicates-delivery-preparation}

Adobe Campaign rimuove automaticamente qualsiasi UUID duplicato da un pubblico durante la preparazione della consegna. Questo meccanismo impedisce che si verifichino errori durante la preparazione di una consegna. In qualità di utente finale, puoi controllare queste informazioni nei registri di consegna: alcuni destinatari possono essere esclusi dal target principale a causa di una chiave duplicata. In tal caso, viene visualizzata la seguente avvertenza: `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/exclusion-duplicates-log.png)

### Aggiornare i dati in un flusso di lavoro{#duplicates-update-data}

Nell&#39;ambito di una [Distribuzione aziendale (FFDA)](enterprise-deployment.md), non è possibile selezionare una chiave interna (UUID) come campo per aggiornare i dati in un flusso di lavoro.

![](assets/update-data-no-internal-key.png)

### Eseguire una query su uno schema con duplicati{#query-with-duplicates}

Quando un flusso di lavoro avvia l’esecuzione di una query su uno schema, Adobe Campaign controlla se eventuali record duplicati sono segnalati in [Tabella Unicity controllo](#unicity-wf). In tal caso, il flusso di lavoro registra un avviso, poiché l’operazione successiva sui dati duplicati potrebbe influire sui risultati del flusso di lavoro.

![](assets/query-with-duplicates.png)

Questo controllo viene eseguito nelle seguenti attività del flusso di lavoro:

* Query
* Incremental Query
* Lettura di un elenco