---
product: campaign
title: Creare un filtro
description: Scopri come creare un filtro durante l’esecuzione delle query
feature: Query Editor, Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8e6fd9b4-77c4-4af8-921b-c3fe104fa5bc
TQID: 'https://experienceleague.adobe.com/3EkEMTJs1-sdM9wSTYorHWO-emO3Nz5nugrWDU4h5pM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: f5293531-9312-4099-bfa3-9e67df6a8750
    internal-label: Query Editor
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 2%
---
# Creare un filtro {#creating-a-filter}

I filtri disponibili in Adobe Campaign vengono definiti tramite condizioni di filtro create utilizzando la stessa modalità operativa utilizzata per la creazione di query nell&#39;[Editor query](../../v8/start/query-editor.md).

Il nodo **[!UICONTROL Administration > Configuration > Predefined filters]** contiene tutti i filtri predefiniti. Alcuni di questi sono utilizzati negli elenchi e nelle panoramiche. Ulteriori informazioni sui [filtri predefiniti incorporati](../../v8/audiences/create-filters.md).

Ad esempio, l&#39;elenco degli operatori può essere filtrato per **[!UICONTROL Active accounts]**:

![Elenco operatori con il menu Filtri aperto e il filtro Account attivi selezionato](assets/query_editor_filter_sample_1.png)

Il filtro corrispondente contiene la query sul valore **[!UICONTROL Account disabled]** dello schema **[!UICONTROL Operators]**:

![Elenco filtri predefiniti con il filtro Per account di accesso o etichetta selezionato, con etichetta, nome interno e tipo di documento](assets/query_editor_filter_sample_2.png)

Per lo stesso elenco, il filtro **[!UICONTROL By login or label]** consente di filtrare i dati nell&#39;elenco in base al valore immesso nel campo del filtro:

![Elenco di operatori filtrato con agenzia digitata nel campo Contenuto di accesso o etichetta, che restituisce un operatore](assets/query_editor_filter_sample_3.png)

Viene creato come segue:

![Per definizione di filtro di accesso o di etichetta con tre condizioni di filtro per etichetta, nome e descrizione](assets/query_editor_filter_sample_4.png)

Per soddisfare le condizioni di filtro, l’account operatore deve controllare una delle seguenti condizioni:

* L’etichetta contiene i caratteri immessi nel campo di immissione,
* Il nome dell’operatore contiene i caratteri immessi nel campo di immissione,
* Il contenuto dell&#39;area di descrizione contiene i caratteri immessi nel campo di input.

>[!NOTE]
>
>La funzione **[!UICONTROL Upper]** consente di disattivare la funzione con distinzione tra maiuscole e minuscole.

La colonna **[!UICONTROL Taken into account if]** consente di definire i criteri di applicazione per queste condizioni di filtro. Qui i caratteri **$(/tmp/@text)** rappresentano il contenuto del campo di input collegato al filtro:

![Elenco di operatori con agenzia inserito nel campo Login o etichetta contiene, restituzione dell&#39;agenzia di Londra](assets/query_editor_filter_sample_5.png)

In questo caso, **$(/tmp/@text)=&#39;agency&#39;**

L&#39;espressione **$(/tmp/@text)!=&#39;** applica ogni condizione quando il campo di input non è vuoto.
