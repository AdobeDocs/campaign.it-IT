---
product: campaign
title: Creare un filtro
description: Scopri come creare un filtro durante l’esecuzione delle query
feature: Query Editor, Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8e6fd9b4-77c4-4af8-921b-c3fe104fa5bc
TQID: https://experienceleague.adobe.com/3EkEMTJs1-sdM9wSTYorHWO-emO3Nz5nugrWDU4h5pM
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 219
ht-degree: 2%

---

# Creare un filtro {#creating-a-filter}

I filtri disponibili in Adobe Campaign vengono definiti tramite condizioni di filtro create utilizzando la stessa modalità operativa utilizzata per la creazione di query nell&#39;[Editor query](../../v8/start/query-editor.md).

Il nodo **[!UICONTROL Administration > Configuration > Predefined filters]** contiene tutti i filtri predefiniti. Alcuni di questi sono utilizzati negli elenchi e nelle panoramiche. Ulteriori informazioni sui [filtri predefiniti incorporati](../../v8/audiences/create-filters.md).

Ad esempio, l&#39;elenco degli operatori può essere filtrato per **[!UICONTROL Active accounts]**:

![](assets/query_editor_filter_sample_1.png)

Il filtro corrispondente contiene la query sul valore **[!UICONTROL Account disabled]** dello schema **[!UICONTROL Operators]**:

![](assets/query_editor_filter_sample_2.png)

Per lo stesso elenco, il filtro **[!UICONTROL By login or label]** consente di filtrare i dati nell&#39;elenco in base al valore immesso nel campo del filtro:

![](assets/query_editor_filter_sample_3.png)

Viene creato come segue:

![](assets/query_editor_filter_sample_4.png)

Per soddisfare le condizioni di filtro, l’account operatore deve controllare una delle seguenti condizioni:

* L’etichetta contiene i caratteri immessi nel campo di immissione,
* Il nome dell’operatore contiene i caratteri immessi nel campo di immissione,
* Il contenuto dell&#39;area di descrizione contiene i caratteri immessi nel campo di input.

>[!NOTE]
>
>La funzione **[!UICONTROL Upper]** consente di disattivare la funzione con distinzione tra maiuscole e minuscole.

La colonna **[!UICONTROL Taken into account if]** consente di definire i criteri di applicazione per queste condizioni di filtro. Qui i caratteri **$(/tmp/@text)** rappresentano il contenuto del campo di input collegato al filtro:

![](assets/query_editor_filter_sample_5.png)

In questo caso, **$(/tmp/@text)=&#39;agency&#39;**

L&#39;espressione **$(/tmp/@text)!=&#39;** applica ogni condizione quando il campo di input non è vuoto.
