---
title: Gestione delle chiavi in Campaign
description: Introduzione alla gestione delle chiavi
feature: Configuration, FFDA
role: Developer
level: Intermediate
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
TQID: https://experienceleague.adobe.com/DfuZXr3sXnip35yNPRvZBDZ1BVb6dJFWYA2j90vc7RE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a658c786-869b-4194-a780-2594d663addaid: b12f6872-9271-4369-85e5-86969a0b99a2id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2: id: cfc95e9b-b035-4403-a6a9-b27a8a053a37id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 576
ht-degree: 3%

---

# Gestione delle chiavi e unicità {#key-management}

Nel contesto di una distribuzione di [Enterprise (FFDA)](enterprise-deployment.md), la chiave primaria è un identificatore ID universalmente univoco (UUID), ovvero una stringa di caratteri. Per creare questo UUID, l&#39;elemento principale dello schema deve contenere gli attributi **autouuid** e **autopk** impostati su **true**.

Adobe Campaign v8 utilizza [!DNL Snowflake] come database di base. L&#39;architettura distribuita del database [!DNL Snowflake] non fornisce un meccanismo per garantire l&#39;unicità di una chiave all&#39;interno di una tabella: gli utenti finali sono responsabili della coerenza delle chiavi all&#39;interno del database Adobe Campaign.

Per preservare la coerenza del database relazionale è obbligatorio evitare duplicati sulle chiavi, in particolare sulle chiavi primarie. I duplicati sulle chiavi primarie causano problemi con le attività del flusso di lavoro di gestione dati come **Query**, **Riconciliazione**, **Aggiorna dati** e altro ancora. Questo è fondamentale per definire i criteri di riconciliazione corretti durante l&#39;aggiornamento di [!DNL Snowflake] tabelle.


>[!CAUTION]
>
>Le chiavi duplicate non sono limitate agli UUID. Ciò può verificarsi in con ID di, incluse le chiavi personalizzate create in tabelle personalizzate.


## Servizio Unicity{#unicity-service}

Il servizio Unicity è un componente di Cloud Database Manager che consente agli utenti di preservare e monitorare l’integrità dei vincoli di chiave univoca all’interno delle tabelle di Cloud Database. Questo consente di ridurre il rischio di inserimento di chiavi duplicate.

Poiché il database cloud non applica vincoli di unicità, il servizio Unicity riduce il rischio di inserimento di duplicati durante la gestione dei dati con Adobe Campaign.

### Flusso di lavoro Unicity{#unicity-wf}

Il servizio Unicity viene fornito con un flusso di lavoro integrato dedicato **[!UICONTROL Unicity alerting]**, per monitorare i vincoli di unicità e avvisare quando vengono rilevati duplicati.

Questo flusso di lavoro tecnico è disponibile dal nodo **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Unicity]** di Campaign Explorer. **Non deve essere modificato**.

Questo flusso di lavoro controlla tutti gli schemi personalizzati e incorporati per rilevare le righe duplicate.

![](assets/unicity-alerting-wf.png)

Se il flusso di lavoro **[!UICONTROL Unicity alerting]** (ffdaUnicity) rileva alcune chiavi duplicate, queste vengono aggiunte a una tabella **Audit Unicity** specifica, che include il nome dello schema, il tipo di chiave, il numero di righe interessate e la data. È possibile accedere alle chiavi duplicate dal nodo **[!UICONTROL Administration > Audit > Key Unicity]**.

![](assets/unicity-table.png)

In qualità di amministratore di database, puoi utilizzare un’attività SQL per rimuovere i duplicati o contattare l’Assistenza clienti di Adobe per ulteriori indicazioni.

### Avvisi{#unicity-wf-alerting}

Una notifica specifica viene inviata al gruppo di operatori **[!UICONTROL Workflow Supervisors]** quando vengono rilevate chiavi duplicate. Il contenuto e il pubblico di questo avviso possono essere modificati nell&#39;attività **Avviso** del flusso di lavoro **[!UICONTROL Unicity alerting]**.

![](assets/wf-alert-activity.png)


## Guardrail aggiuntivi {#duplicates-guardrails}

Campaign viene fornito con un set di nuovi guardrail per impedire l&#39;inserimento di chiavi duplicate nel database [!DNL Snowflake].

>[!NOTE]
>
>Queste protezioni sono disponibili a partire da Campaign v8.3. Per verificare la versione, consulta [questa sezione](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

### Preparazione della consegna {#remove-duplicates-delivery-preparation}

Adobe Campaign rimuove automaticamente qualsiasi UUID duplicato da un pubblico durante la preparazione della consegna. Questo meccanismo impedisce che si verifichino errori durante la preparazione di una consegna. In qualità di utente finale, puoi controllare queste informazioni nei registri di consegna: alcuni destinatari possono essere esclusi dal target principale a causa di una chiave duplicata. In tal caso, verrà visualizzato il seguente avviso: `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/exclusion-duplicates-log.png)

### Aggiornare i dati in un flusso di lavoro {#duplicates-update-data}

Nel contesto di una distribuzione [Enterprise (FFDA)](enterprise-deployment.md), non è possibile selezionare una chiave interna (UUID) come campo per aggiornare i dati in un flusso di lavoro.

![](assets/update-data-no-internal-key.png)

### Eseguire una query su uno schema con duplicati {#query-with-duplicates}

Quando un flusso di lavoro avvia l&#39;esecuzione di una query su uno schema, Adobe Campaign controlla se nella [tabella Controllo unicità](#unicity-wf) sono riportati record duplicati. In tal caso, il flusso di lavoro registra un avviso, poiché l’operazione successiva sui dati duplicati potrebbe influire sui risultati del flusso di lavoro.

![](assets/query-with-duplicates.png)

Questo controllo viene eseguito nelle seguenti attività del flusso di lavoro:

* Query
* Incremental Query
* Lettura di un elenco


>[!NOTE]
>
>Se stai passando da un’altra versione di Campaign, è fondamentale rimuovere i duplicati, risolvere i problemi e bonificare i dati per evitare di influire sulla transizione.
