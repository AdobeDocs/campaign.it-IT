---
title: Gestione delle chiavi in Campaign
description: Guida introduttiva alla gestione delle chiavi
feature: FFDA
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 3%

---

# Gestione delle chiavi e unicità {#key-management}

Nel contesto di un [Distribuzione aziendale (FFDA)](enterprise-deployment.md), la chiave primaria è un identificatore ID universale univoco (UUID), che è una stringa sui caratteri. Per creare questo UUID, l’elemento principale dello schema deve contenere **autouuid** e **autopk** attributi impostati su **true**.

Adobe Campaign v8 utilizza [!DNL Snowflake] come database principale. L&#39;architettura distribuita del [!DNL Snowflake] il database non fornisce un meccanismo per garantire l&#39;unicità di una chiave all&#39;interno di una tabella: gli utenti finali sono responsabili della coerenza delle chiavi all’interno del database Adobe Campaign.

Per preservare la coerenza relazionale del database, è obbligatorio evitare duplicati sulle chiavi e in particolare sulle chiavi primarie. I duplicati sulle chiavi primarie generano problemi con le attività del flusso di lavoro di gestione dei dati, ad esempio **Query**, **Reconciliation**, **Update data** e altro ancora. Questo è fondamentale per definire i criteri di riconciliazione appropriati durante l’aggiornamento [!DNL Snowflake] tabelle.


>[!CAUTION]
>
>Le chiavi duplicate non sono limitate agli UUID. Può accadere con gli ID, incluse le chiavi personalizzate create nelle tabelle personalizzate.


## Servizio Unicity{#unicity-service}

Unicity Service è un componente Cloud Database Manager che consente agli utenti di preservare e monitorare l&#39;integrità dei vincoli di chiave univoci all&#39;interno delle tabelle del database Cloud. Questo consente di ridurre il rischio di inserimento di chiavi duplicate.

Poiché il database cloud non applica vincoli unicity, Unicity Service riduce il rischio di inserimento di duplicati durante la gestione dei dati con Adobe Campaign.

### Flusso di lavoro Unicità{#unicity-wf}

Il servizio Unicity viene fornito con un **[!UICONTROL Unicity alerting]** flusso di lavoro integrato, per monitorare i vincoli unicity e avvisare quando vengono rilevati duplicati.

Questo flusso di lavoro tecnico è disponibile dal **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Unicity]** nodo di Campaign Explorer. **Non deve essere modificato**.

Questo flusso di lavoro controlla tutti gli schemi personalizzati e incorporati per rilevare le righe duplicate.

![](assets/unicity-alerting-wf.png)

Se la **[!UICONTROL Unicity alerting]** Il flusso di lavoro (ffdaUnicity) rileva alcune chiavi duplicate, che vengono aggiunte a uno specifico **Unicità dei controlli** tabella, che include il nome dello schema, il tipo di chiave, il numero di righe interessate e la data. Puoi accedere alle chiavi duplicate dalla **[!UICONTROL Administration > Audit > Key Unicity]** nodo.

![](assets/unicity-table.png)

In qualità di amministratore del database, è possibile utilizzare un&#39;attività SQL per rimuovere i duplicati o contattare l&#39;Assistenza clienti Adobe per ulteriori informazioni.

### Avvisi{#unicity-wf-alerting}

Viene inviata una notifica specifica al **[!UICONTROL Workflow Supervisors]** gruppo di operatori quando vengono rilevate chiavi duplicate. Il contenuto e il pubblico di questo avviso possono essere modificati nella **Avviso** attività del **[!UICONTROL Unicity alerting]** workflow.

![](assets/wf-alert-activity.png)


## Altre protezioni{#duplicates-guardrails}

Campaign viene fornito con un set di nuove protezioni per evitare l’inserimento di chiavi duplicate in [!DNL Snowflake] database.

>[!NOTE]
>
>Queste protezioni sono disponibili a partire da Campaign v8.3. Per verificare la versione, consulta [questa sezione](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

### Preparazione della consegna{#remove-duplicates-delivery-preparation}

Adobe Campaign rimuove automaticamente qualsiasi UUID duplicato da un pubblico durante la preparazione della consegna. Questo meccanismo impedisce che si verifichi un errore durante la preparazione di una consegna. In qualità di utente finale, puoi controllare queste informazioni nei registri di consegna: alcuni destinatari possono essere esclusi dal target principale a causa di una chiave duplicata. In tal caso, viene visualizzato il seguente avviso: `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/exclusion-duplicates-log.png)

### Aggiornare i dati in un flusso di lavoro{#duplicates-update-data}

Nel contesto di un [Distribuzione aziendale (FFDA)](enterprise-deployment.md), non è possibile selezionare un campo di chiave interna (UUID) per aggiornare i dati in un flusso di lavoro.

![](assets/update-data-no-internal-key.png)

Quando utilizzi una chiave di riconciliazione esplicita, la **Update data** l’attività assicura automaticamente l’unicità dello schema di destinazione in base a questa chiave:

1. Deduplicazione dei dati in arrivo (dalla transizione)
1. Deduplicazione di dati con tabella di destinazione (unione)


![](assets/update-data-deduplicate.png)

>[!CAUTION]
>
>Questa protezione si applica solo con opzione **[!UICONTROL Using reconciliation keys]**.


### Eseguire una query di uno schema con duplicati{#query-with-duplicates}

Quando un flusso di lavoro inizia a eseguire una query su uno schema, Adobe Campaign controlla se è presente un record duplicato nel [Tabella Unicità controllo](#unicity-wf). In tal caso, il flusso di lavoro registra un avviso come l’operazione successiva sui dati duplicati dovrebbe potenzialmente influire sul risultato del flusso di lavoro.

![](assets/query-with-duplicates.png)

Questo controllo viene eseguito nelle seguenti attività del flusso di lavoro:

* Query
* Query incrementale
* Lettura di un elenco