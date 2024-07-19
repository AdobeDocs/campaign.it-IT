---
product: campaign
title: Gestire le autorizzazioni del flusso di lavoro
description: Scopri come gestire le autorizzazioni del flusso di lavoro
feature: Workflows, Permissions
role: Admin
exl-id: 3cb8aeec-e758-4b71-adef-67942cf9ded7
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 1%

---

# Gestire le autorizzazioni del flusso di lavoro{#managing-rights}



Se non sono amministratori, gli operatori Adobe Campaign devono disporre dei diritti di accesso per creare, eseguire o modificare i flussi di lavoro.

In generale, gli operatori che agiscono sui flussi di lavoro devono accedere ai file contenenti i dati utilizzati durante le varie attività (destinatari, elenco destinatari, abbonamenti, consegne, ecc.) ed eventualmente ai loro sottofile.

Devono inoltre essere mappati ai diritti denominati che coincidono con le azioni eseguite dai flussi di lavoro che avranno effetto (importazione dei destinatari, accesso ai file, fusione, esecuzione di script SQL, ecc.).

Per ulteriori informazioni sulla gestione di operatori e autorizzazioni, consulta [questa sezione](../../v8/start/gs-permissions.md).

## Gruppi di operatori {#operator-groups-wf}

Al flusso di lavoro sono associati i seguenti gruppi di operatori:

* Il gruppo **[!UICONTROL Workflow execution]** consente di controllare l&#39;esecuzione e l&#39;approvazione dei flussi di lavoro di targeting: il flusso di lavoro denominato right è mappato agli operatori di questo gruppo. È richiesto per tutte le azioni sui flussi di lavoro, oltre ai diritti di accesso ai file di dati. Per impostazione predefinita, il gruppo **[!UICONTROL Workflow execution]** ha accesso in sola lettura ai file di flusso di lavoro di targeting standard e ai modelli di flusso di lavoro. Gli operatori di questo gruppo dispongono inoltre dell&#39;accesso in lettura e scrittura al file di approvazione in sospeso.
* Il gruppo **[!UICONTROL Workflow supervisors]** consente agli operatori di gestire le approvazioni dei flussi di lavoro.
* Il gruppo **[!UICONTROL Operation Managers]** per accedere ai flussi di lavoro delle campagne.

## Diritti denominati {#named-rights}

Solo il FLUSSO DI LAVORO con nome right è specifico per i flussi di lavoro: consente di creare, avviare e interrompere i flussi di lavoro. Affinché il diritto denominato sia applicabile, è necessario disporre dei diritti di lettura per il file del flusso di lavoro. Per i flussi di lavoro di targeting, è necessario disporre del diritto di lettura sul file **[!UICONTROL Profiles and Targets]**.

## Account di esecuzione del flusso di lavoro {#workflow-execution-account}

Puoi configurare l’account di esecuzione da utilizzare a livello di modello di flusso di lavoro. L’account di esecuzione ti consente di mappare direttamente le autorizzazioni al flusso di lavoro, indipendentemente dall’operatore Adobe Campaign che avvia l’esecuzione. Per impostazione predefinita, ogni flusso di lavoro viene eseguito con i diritti dell’operatore che lo ha avviato.

Per mappare un account di esecuzione a un flusso di lavoro, passa all’elenco dei modelli di flusso di lavoro e fai clic con il pulsante destro del mouse sul modello collegato al flusso di lavoro. Scegliere **[!UICONTROL Action > Change execution account...]**, quindi selezionare l&#39;account da utilizzare.
