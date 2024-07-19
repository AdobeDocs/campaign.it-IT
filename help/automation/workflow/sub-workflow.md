---
product: campaign
title: Flusso di lavoro secondario
description: Ulteriori informazioni sull’attività del flusso di lavoro secondario
feature: Workflows
exl-id: c530fb4e-d21e-4059-88e1-77a8d33a7832
source-git-commit: c3f4ad0b56dd45d19eebaa4d2f06551c8fecac1d
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 1%

---

# Flusso di lavoro secondario{#sub-workflow}



L&#39;attività **[!UICONTROL Sub-workflow]** consente di attivare l&#39;esecuzione di un altro flusso di lavoro e di recuperare il risultato. Questa attività ti consente di utilizzare flussi di lavoro complessi utilizzando un’interfaccia semplificata.

È possibile chiamare più flussi di lavoro secondari in un unico flusso di lavoro. I workflow secondari vengono eseguiti in modo sincrono.

Nell’esempio seguente, un flusso di lavoro primario sta chiamando un flusso di lavoro secondario utilizzando i ponticelli. Per ulteriori informazioni sugli oggetti grafici di tipo Jump, vedere [questa sezione](jump-start-point-and-end-point.md).

1. Crea un flusso di lavoro da utilizzare come flusso di lavoro secondario in un altro flusso di lavoro.
1. Inserire un&#39;attività **[!UICONTROL Jump (end point)]** con priorità 1 all&#39;inizio del flusso di lavoro. Se disponi di più salti di tipo &quot;end point&quot;, Adobe Campaign utilizzerà il salto &quot;end point&quot; con il numero più basso.
1. Inserire un&#39;attività **[!UICONTROL Jump (start point)]** con priorità 2 alla fine del flusso di lavoro. Se disponi di più salti di tipo &quot;punto iniziale&quot;, Adobe Campaign utilizzerà il salto &quot;punto iniziale&quot; con il numero più alto.

   ![](assets/subworkflow_jumps.png)

   >[!NOTE]
   >
   >Se l&#39;attività del flusso di lavoro secondario fa riferimento a un flusso di lavoro con diverse attività **[!UICONTROL Jump]**, il flusso di lavoro secondario viene eseguito tra il salto di tipo &quot;punto finale&quot; con il numero più basso e il salto di tipo &quot;punto iniziale&quot; con il numero più alto.
   >
   >Affinché il flusso di lavoro secondario possa essere eseguito correttamente, è necessario disporre di un solo salto di tipo &quot;punto finale&quot; con il numero più basso e di un solo salto di tipo &quot;punto iniziale&quot; con il numero più alto.

1. Completa e salva questo &quot;flusso di lavoro secondario&quot;.
1. Crea un flusso di lavoro principale.
1. Inserire un&#39;attività **[!UICONTROL Sub-workflow]** e aprirla.
1. Selezionare il flusso di lavoro da utilizzare dall&#39;elenco a discesa **[!UICONTROL Workflow template]**.

   ![](assets/subworkflow_selection.png)

1. Puoi anche aggiungere uno script di configurazione per modificare il flusso di lavoro di riferimento.
1. Fai clic su **[!UICONTROL Ok]**. Verrà automaticamente creata una transizione in uscita con l&#39;etichetta dell&#39;attività **[!UICONTROL Jump (start point)]** dal flusso di lavoro selezionato.

   ![](assets/subworkflow_outbound.png)

1. Esegui il flusso di lavoro.

Dopo l&#39;esecuzione, il flusso di lavoro chiamato come flusso di lavoro secondario rimane nello stato **[!UICONTROL Being edited]**, ovvero:

* Non è possibile fare clic con il pulsante destro del mouse sulle transizioni per visualizzare la destinazione.
* Impossibile visualizzare il conteggio delle popolazioni intermedie.
* I registri del flusso di lavoro secondario vengono visualizzati nel flusso di lavoro principale.

  ![](assets/subworkflow_logs.png)

>[!NOTE]
>
>Se si verifica un errore nel flusso di lavoro secondario, il flusso di lavoro principale viene sospeso e viene creata una copia del flusso di lavoro secondario.

## Parametri di input (facoltativi) {#input-parameters--optional-}

* tableName
* schema

Ogni evento in entrata deve specificare una destinazione definita da questi parametri.

## Parametri di output {#output-parameters}

* tableName
* schema
* recCount

Questo set di tre valori identifica la popolazione target della query. **[!UICONTROL tableName]** è il nome della tabella che registra gli identificatori di destinazione, **[!UICONTROL schema]** è lo schema della popolazione (in genere nms:recipient) e **[!UICONTROL recCount]** è il numero di elementi nella tabella.

* targetSchema: questo valore è lo schema della tabella di lavoro. Questo parametro è valido per tutte le transizioni con **[!UICONTROL tableName]** e **[!UICONTROL schema]**.
