---
title: Modificare l’origine dati
description: Ulteriori informazioni sull’attività Cambia origine dati
feature: Workflows, Data Management, Federated Data Access
exl-id: ca7eca9d-9112-4ea1-9a0c-a24cf6a978e6
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%

---

# Modificare l’origine dati {#change-data-source}

Utilizza la **[!UICONTROL Change data source]** attività per modificare l’origine dati di un [tabella di lavoro del flusso di lavoro](use-workflow-data.md#workflow-temporary-work-table). Questa attività offre una maggiore flessibilità per gestire i dati tra diverse origini dati, come Federated Data Access (FDA), il database di Campaign Cloud (FFDA) e il database locale di Campaign.

Il flusso di lavoro **[!UICONTROL Working table]** viene utilizzato per gestire e condividere i dati con le attività del flusso di lavoro.

Per impostazione predefinita, la **[!UICONTROL Working table]** viene creato nello stesso database dell&#39;origine dei dati su cui eseguire la query.
Ad esempio, quando si esegue una query sul **[!UICONTROL Recipients]** memorizzato nel database Cloud, il flusso di lavoro crea un **[!UICONTROL Working table]** sullo stesso database Cloud.

Utilizza un **[!UICONTROL Change Data Source]** per utilizzare un’origine dati diversa per la **[!UICONTROL Working table]**.

Tieni presente che quando utilizzi **[!UICONTROL Change Data Source]** per continuare l’esecuzione del flusso di lavoro, devi tornare al database Cloud .

Per utilizzare **[!UICONTROL Change Data Source]** attività, devi:

1. Creare un flusso di lavoro.

1. Invia una query ai destinatari con un **[!UICONTROL Query]** attività.

   Per ulteriori informazioni sulla **[!UICONTROL Query]** attività, fai riferimento a [page](query.md#create-a-query).

1. Aggiungi un **[!UICONTROL Change data source]** attività.

   ![](assets/change-data-source.png)

1. Modifica il **[!UICONTROL Change data source]** attività da selezionare **[!UICONTROL Default data source]**.

   La tabella di lavoro, che contiene il risultato della query, viene quindi spostata nel database locale di Campaign predefinito.

   ![](assets/change-data-source_2.png)

1. Aggiungi un **[!UICONTROL JavaScript code]** attività per eseguire operazioni unitarie sul tavolo di lavoro.

   Per ulteriori informazioni sulla **[!UICONTROL JavaScript code]** attività, fai riferimento alla [questa pagina](sql-code-and-javascript-code.md#javascript-code).

1. Aggiungi un altro **[!UICONTROL Change data source]** attività per tornare al database Cloud.

1. Modifica questa attività e seleziona **[!UICONTROL Active FDA external account]** e il corrispondente **[!UICONTROL External database]** conto esterno.

   ![](assets/change-data-source_3.png)

1. Ora puoi avviare il flusso di lavoro.
