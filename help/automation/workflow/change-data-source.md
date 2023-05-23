---
title: Modificare l’origine dati
description: Ulteriori informazioni sull’attività Modifica origine dati
feature: Workflows, Data Management, Federated Data Access
exl-id: ca7eca9d-9112-4ea1-9a0c-a24cf6a978e6
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%

---

# Modificare l’origine dati {#change-data-source}

Utilizza il **[!UICONTROL Change data source]** attività per modificare l’origine dati di un [tabella di lavoro del flusso di lavoro](use-workflow-data.md#workflow-temporary-work-table). Questa attività offre maggiore flessibilità per gestire i dati tra diverse origini dati, come Federated Data Access (FDA), Campaign Cloud database (FFDA) e Campaign Local database.

Il flusso di lavoro **[!UICONTROL Working table]** viene utilizzato per gestire e condividere i dati con le attività del flusso di lavoro.

Per impostazione predefinita, il **[!UICONTROL Working table]** viene creato nello stesso database dell’origine dei dati su cui è necessario eseguire la query.
Ad esempio, quando si esegue una query su **[!UICONTROL Recipients]** memorizzata nel database Cloud, il flusso di lavoro crea un **[!UICONTROL Working table]** sullo stesso database cloud.

Utilizza un **[!UICONTROL Change Data Source]** per utilizzare un’origine dati diversa per il tuo **[!UICONTROL Working table]**.

Tieni presente che quando utilizzi **[!UICONTROL Change Data Source]** attività, devi tornare al database Cloud per continuare l’esecuzione del flusso di lavoro.

Per utilizzare **[!UICONTROL Change Data Source]** attività, devi:

1. Creare un flusso di lavoro.

1. Effettua query sui destinatari target con una **[!UICONTROL Query]** attività.

   Per ulteriori informazioni su **[!UICONTROL Query]** attività, fai riferimento a questo [pagina](query.md#create-a-query).

1. Aggiungi un **[!UICONTROL Change data source]** attività.

   ![](assets/change-data-source.png)

1. Modifica il **[!UICONTROL Change data source]** attività da selezionare **[!UICONTROL Default data source]**.

   La tabella di lavoro, che contiene il risultato della query, viene quindi spostata nel database locale di Campaign predefinito.

   ![](assets/change-data-source_2.png)

1. Aggiungi un **[!UICONTROL JavaScript code]** attività per eseguire operazioni unitarie sulla tabella di lavoro.

   Per ulteriori informazioni su **[!UICONTROL JavaScript code]** attività, fai riferimento alla [questa pagina](sql-code-and-javascript-code.md#javascript-code).

1. Aggiungi un altro **[!UICONTROL Change data source]** per tornare al database Cloud.

1. Modifica questa attività e seleziona **[!UICONTROL Active FDA external account]**, e la corrispondente **[!UICONTROL External database]** account esterno.

   ![](assets/change-data-source_3.png)

1. Ora puoi avviare il flusso di lavoro.
