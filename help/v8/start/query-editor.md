---
title: Utilizzare l’editor delle query
description: Scopri come utilizzare l’editor delle query
feature: Query Editor, Data Management
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: 56d5628312ea3dedf9335dd0933811e4bf66eb97
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 5%

---

# Query database Campaign

Lo strumento di query è disponibile a vari livelli dell’applicazione e può essere utilizzato per definire popolazioni target, segmentare i clienti, estrarre e filtrare i registri di tracciamento, creare filtri e altro ancora.

Fornisce un assistente dedicato, l&#39;editor di query generico, accessibile dal menu **[!UICONTROL Tools > Generic query editor...]**. Questo editor consente alle query di database di estrarre, organizzare, raggruppare e ordinare le informazioni. Ad esempio, può recuperare i destinatari che hanno fatto clic più di n volte su un collegamento a una newsletter durante un determinato periodo di tempo.

L’editor di query generico centralizza tutte le funzionalità di query. Consente la creazione e l’archiviazione di filtri di restrizione, che possono quindi essere riutilizzati in altri contesti, ad esempio la casella Query di un flusso di lavoro di targeting.

![Accedere all&#39;editor delle query e selezionare una tabella](assets/query_editor_nveau_21.png)


I passaggi per creare una query sono descritti in dettaglio [in questa pagina](design-queries.md).

<!--
Contexts to use the query editor iin Campaign are listed below:

|Usage|Example|
|  ---  |  ---  |
|**Define a Query activity in a workflow**: Define the criteria to query Campaign database in a workflow. [Learn how to configure the Query activity](../../automation/workflow/query.md)|![Image showing how to configure a query activity in a workflow](../../automation/workflow/assets/query-activity.png){width="200" align="center" zoomable="yes"}|
|**Define audiences**: Specify the population you want to target in your messages, and effortlessly create new audiences tailored to your needs. [Learn how to build audiences](../start/create-message.md#define-the-target-audience)|![Image showing how to access the audience creation interface](../send/sms/assets/audience_to.png){width="200" align="center" zoomable="yes"}|
|**Define audiences**: Specify the population you want to target in your messages or workflows, and effortlessly create new audiences tailored to your needs. [Learn how to build audiences](../audiences/create-audiences.md)|![Image showing how to access the audience creation interface](../audiences/assets/targeting-wf-age-filter.png){width="200" align="center" zoomable="yes"}|
|**Customize workflow activities**: Apply rules within workflow activities, such as **Split** and **Reconciliation**, to align with your specific requirements. [Learn more about workflow activities](../../automation/workflow/activities.md)|![Image showing how to access workflow customization options](assets/access-workflow.png){width="200" align="center" zoomable="yes"}|
|**Predefined filters**: Create predefined filters that serve as shortcuts during various filtering operations, whether you're working with data lists or forming the audience for a delivery. [Learn how to work with predefined filters](../get-started/predefined-filters.md)|![Image showing how to access predefined filters](assets/access-predefined-filter.png){width="200" align="center" zoomable="yes"}|
|**Filter reports data**: Add rules to filter the data displayed in reports. [Learn how to work with reports](../reporting/gs-reports.md)|![Image showing how to filter data in reports](assets/access-reports.png){width="200" align="center" zoomable="yes"}|
|**Customize lists**: Create custom rules to filter the data displayed in lists such as recipients or deliveries lists. [Learn how to filter lists](../get-started/list-filters.md#list-built-in-filters)|![Image showing how to customize list filters](assets/access-lists.png){width="200" align="center" zoomable="yes"}|
|**Build conditional content**: Make email content dynamic by creating conditions that define which content should be displayed to different recipients, ensuring personalized and relevant messaging. [Learn how to build conditional content](../personalization/conditions.md)|![Image showing how to create conditional content](assets/conditional-content.png){width="200" align="center" zoomable="yes"}|
-->

**Argomenti correlati**

* [Attività query flusso di lavoro](../../automation/workflow/query.md)
* [Eseguire una query sulla tabella dei destinatari](../../automation/workflow/querying-recipient-table.md)
* [Condizioni di filtro](filter-conditions.md)