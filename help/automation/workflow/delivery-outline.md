---
product: campaign
title: Profilo di consegna
description: Ulteriori informazioni sull’attività del flusso di lavoro Struttura della consegna
feature: Workflows, Targeting Activity
exl-id: 3c06b329-b2d8-4ac8-ab9b-3ab3e525d109
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 1%

---

# Profilo di consegna{#delivery-outline}

Il **struttura della consegna** consente di utilizzare una struttura in un flusso di lavoro della campagna. La struttura deve essere stata creata in precedenza nella campagna.

Per configurare l’attività, è sufficiente selezionare la struttura desiderata e la data di contatto pianificata. Puoi aggiungere regole di filtro aggiungendo tipologie o regole di tipologia.

## Esempio: inserimento di un’offerta tramite una struttura di consegna {#example--inserting-an-offer-via-a-delivery-outline}

Il **struttura della consegna** l’attività, disponibile nei flussi di lavoro della campagna, ti consente di presentare le offerte a cui si fa riferimento in una struttura di consegna dalla campagna corrente in corso.

>[!NOTE]
>
>Il **Interazione** deve essere installato.

1. In un flusso di lavoro, aggiungi un’attività di struttura della consegna prima di aggiungerla.
1. Nell’attività di struttura della consegna, specifica la struttura da utilizzare.
1. Completa i campi disponibili in base alla consegna.
1. Esistono due casi possibili:

   * Se desideri chiamare il motore di offerta, seleziona la **[!UICONTROL Restrict the number of propositions selected]** casella. Specifica lo spazio dell’offerta e il numero di proposte che verranno presentate nella consegna.

      Il motore di offerta terrà conto dei pesi delle offerte e delle regole di idoneità.

   * Se non selezioni la casella, tutte le offerte nella struttura della consegna verranno presentate senza effettuare una chiamata al motore di offerta.

   L’anteprima prende in considerazione il numero di offerte specificato nella consegna. Durante l’esecuzione di un flusso di lavoro, viene preso in considerazione il numero specificato nella struttura della consegna.

   ![](assets/int_compo_offre_wf1.png)
