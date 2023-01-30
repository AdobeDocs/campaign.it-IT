---
product: campaign
title: Gestione delle autorizzazioni del flusso di lavoro
description: Scopri come gestire le autorizzazioni del flusso di lavoro
feature: Workflows
exl-id: 3cb8aeec-e758-4b71-adef-67942cf9ded7
source-git-commit: bff7d1d51b9847c515670e5594eed513fefbe816
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 1%

---

# Gestione delle autorizzazioni del flusso di lavoro{#managing-rights}



Se non sono amministratori, gli operatori Adobe Campaign devono disporre dei diritti di accesso per creare, eseguire o modificare i flussi di lavoro.

In generale, gli operatori che agiscono sui flussi di lavoro devono accedere ai file contenenti i dati utilizzati durante le varie attività (destinatari, elenco destinatari, abbonamenti, consegne, ecc.) ed eventualmente ai relativi sottofile.

Devono anche essere mappati ai diritti denominati che coincidono con le azioni eseguite dai flussi di lavoro che influiranno (importazione dei destinatari, accesso ai file, fusione, esecuzione degli script SQL, ecc.).

Per ulteriori informazioni sulla gestione di operatori e autorizzazioni, consulta [questa sezione](../../v8/start/gs-permissions.md).

## Gruppi di operatori {#operator-groups-wf}

I seguenti gruppi di operatori sono associati al flusso di lavoro:

* La **[!UICONTROL Workflow execution]** consente di controllare l’esecuzione e l’approvazione dei flussi di lavoro di targeting: il WORKFLOW denominato right è mappato sugli operatori di questo gruppo. È richiesto per tutte le azioni sui flussi di lavoro, oltre ad accedere ai diritti ai file di dati. Per impostazione predefinita, la **[!UICONTROL Workflow execution]** gruppo ha accesso in sola lettura ai file di flusso di lavoro di targeting standard e ai modelli di flusso di lavoro. Gli operatori di questo gruppo hanno anche accesso in lettura e scrittura al file di approvazione in sospeso.
* La **[!UICONTROL Workflow supervisors]** consente agli operatori di gestire le approvazioni del flusso di lavoro.
* La **[!UICONTROL Operation Managers]** per accedere ai flussi di lavoro delle campagne.

## Diritti denominati {#named-rights}

Solo il flusso di lavoro denominato a destra è specifico per i flussi di lavoro: consente di creare, avviare e interrompere i flussi di lavoro. I diritti di lettura sul file del flusso di lavoro sono necessari perché sia applicabile il diritto denominato . Per il targeting dei flussi di lavoro, la lettura a destra **[!UICONTROL Profiles and Targets]** file necessario.

## Account di esecuzione del flusso di lavoro {#workflow-execution-account}

Puoi configurare l’account di esecuzione da utilizzare a livello di modello di flusso di lavoro. L’account di esecuzione ti consente di mappare direttamente le autorizzazioni al flusso di lavoro, indipendentemente dall’operatore Adobe Campaign che avvia l’esecuzione. Per impostazione predefinita, ogni flusso di lavoro viene eseguito con i diritti dell’operatore che lo ha avviato.

Per mappare un account di esecuzione a un flusso di lavoro, passa all’elenco dei modelli di flusso di lavoro e fai clic con il pulsante destro del mouse sul modello collegato al flusso di lavoro. Scegli **[!UICONTROL Action > Change execution account...]** quindi seleziona l’account da utilizzare.
