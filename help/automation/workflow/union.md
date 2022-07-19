---
product: campaign
title: Unione
description: Ulteriori informazioni sull’attività del flusso di lavoro dell’Unione
feature: Workflows, Targeting Activity
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---

# Unione{#union}

A **[!UICONTROL Union]** raggruppa il risultato di diverse attività in entrata in un unico target. Il target viene creato con tutti i risultati ricevuti: tutte le attività precedenti devono pertanto essere portate a termine affinché l&#39;unione sia eseguita.

![](assets/s_user_segmentation_union.png)

>[!NOTE]
>
>Per ulteriori informazioni sulla configurazione e sull’utilizzo di **[!UICONTROL Union]** attività, fai riferimento a [questa pagina](targeting-workflows.md#combining-several-targets--union-).

## Esempio di unione {#union-example}

Nell’esempio seguente, i risultati di due query sono stati combinati per aggiornare l’elenco. Le due query hanno come target i destinatari. I risultati sono quindi basati sulla stessa tabella.

1. Inserisci un **[!UICONTROL Union]** -digita l’attività subito dopo le due query e prima di un’attività di tipo di aggiornamento dell’elenco, quindi aprila.
1. È possibile inserire un’etichetta.
1. Seleziona la **[!UICONTROL Keys only]** metodo di riconciliazione poiché, in questo esempio, la popolazione risultante dalle query contiene dati coerenti.
1. Se hai aggiunto dati aggiuntivi per le query, puoi decidere di conservare solo i dati condivisi.
1. Se desideri limitare la dimensione della popolazione finale, controlla la **[!UICONTROL Limit size of generated population]** opzione .

   Specifica questo numero finale immettendo il numero massimo di destinatari e selezionando la query la cui popolazione avrà priorità.

1. Approva le **[!UICONTROL Union]** quindi configura la [Aggiornamento elenco](list-update.md) attività.
1. Avviare il flusso di lavoro. Viene visualizzato il numero di risultati e viene creato o aggiornato l’elenco definito nell’attività di aggiornamento elenco. Questo elenco contiene l’insieme di destinatari per entrambe le query o, se applicabile, il numero definito nel passaggio precedente.

   ![](assets/union_example.png)

## Parametri di input {#input-parameters}

* tableName
* schema

Ogni evento in entrata deve specificare un target definito da questi parametri.

## Parametri di output {#output-parameters}

* tableName
* schema
* recCount

Questo insieme di tre valori identifica il target risultante dall&#39;unione. **[!UICONTROL tableName]** è il nome della tabella che registra gli identificatori target, **[!UICONTROL schema]** è lo schema della popolazione (in genere nms:recipient) e **[!UICONTROL recCount]** è il numero di elementi nella tabella.
