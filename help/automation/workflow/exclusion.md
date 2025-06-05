---
product: campaign
title: Esclusione
description: Ulteriori informazioni sull’attività del flusso di lavoro Esclusione
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8ea831e2-8e6e-4ef0-ac05-f27ebf89ccb9
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# Esclusione{#exclusion}



Un&#39;attività di tipo **Exclusion** crea una destinazione basata su una destinazione principale da cui vengono estratte una o più destinazioni.

Per configurare questa attività, immetti la relativa etichetta e seleziona il set di destinatari principale: la popolazione del set principale ti consente di costruire il risultato. Verranno esclusi i profili condivisi dal set principale e almeno una delle attività iniziali.

![](assets/s_user_segmentation_exclu.png)

>[!NOTE]
>
>Per ulteriori informazioni sulla configurazione e sull&#39;utilizzo dell&#39;attività di esclusione, consulta [Esclusione di una popolazione (esclusione)](targeting-workflows.md#excluding-a-population--exclusion-).

Selezionare l&#39;opzione **[!UICONTROL Generate complement]** se si desidera sfruttare il gruppo rimanente. Il complemento conterrà la popolazione entrante principale meno la popolazione uscente. Verrà quindi aggiunta all’attività una transizione di output aggiuntiva, come segue:

![](assets/s_user_segmentation_exclu_compl.png)

## Esempi di esclusione {#exclusion-examples}

L&#39;esempio seguente cerca di compilare un elenco di destinatari di età compresa tra i 18 e i 30 anni, escludendo i residenti di Parigi.

1. Inserire e aprire un&#39;attività di tipo **[!UICONTROL Exclusion]** in seguito a due query. La prima query esegue il targeting dei destinatari che vivono a Parigi. La seconda query esegue il targeting delle persone di età compresa tra i 18 e i 30 anni.
1. Inserisci il set principale. Il set principale è la query **18-30**. Gli elementi relativi al secondo gruppo saranno esclusi dal risultato finale.
1. Se desideri sfruttare i dati che rimangono dopo l&#39;esclusione, seleziona l&#39;opzione **[!UICONTROL Generate complement]**. In questo caso, il complemento è costituito da beneficiari di età compresa tra i 18 e i 30 anni che vivono a Parigi.
1. Approva la configurazione di esclusione, quindi inserisci nel risultato un’attività di aggiornamento elenco. Se necessario, puoi anche inserire un ulteriore aggiornamento dell’elenco del complemento.
1. Esegui il flusso di lavoro. In questo esempio, il risultato è costituito da destinatari di età compresa tra i 18 e i 30 anni, ma quelli che vivono a Parigi sono esclusi e inviati al complemento.

   ![](assets/exclusion_example.png)

## Parametri di input {#input-parameters}

* tableName
* schema

Ogni evento in entrata deve specificare una destinazione definita da questi parametri.

## Parametri di output {#output-parameters}

* tableName
* schema
* recCount

Questo insieme di tre valori identifica il target risultante dall’esclusione. **[!UICONTROL tableName]** è il nome della tabella che registra gli identificatori di destinazione, **[!UICONTROL schema]** è lo schema della popolazione (in genere nms:recipient) e **[!UICONTROL recCount]** è il numero di elementi nella tabella.

La transizione associata al complemento ha gli stessi parametri.
