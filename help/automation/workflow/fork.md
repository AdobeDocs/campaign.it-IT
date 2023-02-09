---
product: campaign
title: Attività Fork
description: Ulteriori informazioni sull’attività del flusso di lavoro Fork
feature: Workflows
exl-id: 7b94776c-2478-4e12-82a6-c94be12e7e22
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# Attività Fork{#fork}



È possibile utilizzare **[!UICONTROL Fork]** per creare più transizioni in uscita ed eseguire diverse attività in modo indipendente all’interno dello stesso flusso di lavoro.

>[!IMPORTANT]
>
>Le transizioni in uscita aggiunte dopo un **[!UICONTROL Fork]** l’attività non viene eseguita simultaneamente. Questo comportamento può influire sulle prestazioni del flusso di lavoro. Utilizza la **[!UICONTROL Fork]** se devi eseguire diverse attività in modo indipendente. Facoltativamente, puoi unire le attività in uscita prima della parte successiva del flusso di lavoro.

Per configurare un **[!UICONTROL Fork]** attività e relative attività, segui questi passaggi:

1. Apri **[!UICONTROL Fork]** e definisci il nome e l’etichetta delle transizioni in uscita.

   ![](assets/s_user_segmentation_fork.png)

1. Apri ogni transizione in uscita e configurala.
1. Facoltativamente, per unire transizioni in uscita, aggiungi un’attività AND-join . [Ulteriori informazioni](and-join.md).

   La parte successiva del flusso di lavoro viene eseguita solo al completamento delle transizioni in uscita unite.

## Esempio: segmentazione

In questo esempio, vengono inviate e-mail diverse a diversi gruppi di popolazione. A **[!UICONTROL Fork]** l’attività viene utilizzata dopo una query per eseguire due azioni in parallelo:

* Salva il risultato della query
* Segmenta il risultato per inviare più consegne

   ![L’attività Fork segue l’intersezione di due query e precede un’attività di aggiornamento elenco e un’attività divisa.](assets/wkf_fork_example.png)

Il flusso di lavoro comprende le seguenti attività:

1. **[!UICONTROL Query]** attività

   Sono selezionati due gruppi di popolazione: donne e parigini.

1. **[!UICONTROL Intersection]** attività

   Viene selezionata l&#39;intersezione dei risultati della query, ovvero donne parigine.

1. **[!UICONTROL Fork]** attività

   La popolazione calcolata viene salvata e, in parallelo, segmentata in due gruppi:

   1. Parigine di età compresa tra i 18 e i 40 anni
   1. donne parigine sopra i 40 anni

1. **[!UICONTROL Delivery]** attività

   Viene inviata un’e-mail diversa a ogni gruppo di popolazione.

## Caso di utilizzo: invia un’e-mail di compleanno

Un’e-mail ricorrente viene inviata a un elenco di destinatari al momento del loro compleanno. A **[!UICONTROL Fork]** L’attività viene utilizzata per includere i destinatari nati il 29 febbraio in un anno bisestile. [Ulteriori informazioni](send-a-birthday-email.md) informazioni su questo caso d’uso.

![L’attività fork segue un’attività di test e precede due attività di query.](assets/birthday-workflow_usecase_1.png)

## Caso di utilizzo: automatizzare il contenuto con un flusso di lavoro


Puoi quindi configurare ogni transizione in uscita e unirle utilizzando un’ [AND-join](and-join.md) , se necessario. In questo modo, il resto del flusso di lavoro viene eseguito solo una volta che il **[!UICONTROL Fork]** le transizioni in uscita dell’attività sono completate.

## Argomenti correlati

* [Attività AND-join](and-join.md)
* [Caso di utilizzo: mail di compleanno](send-a-birthday-email.md)
