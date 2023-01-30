---
product: campaign
title: Profilo di consegna
description: Ulteriori informazioni sull’attività del flusso di lavoro del profilo di consegna
feature: Workflows, Targeting Activity
exl-id: 3c06b329-b2d8-4ac8-ab9b-3ab3e525d109
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 1%

---

# Profilo di consegna{#delivery-outline}

La **profilo di consegna** consente di utilizzare una struttura in un flusso di lavoro della campagna. La struttura deve essere stata creata in precedenza nella campagna.

Per configurare l’attività, è sufficiente selezionare il profilo desiderato e la data di contatto pianificata. Puoi aggiungere regole di filtro aggiungendo tipologie o regole di tipologia.

## Esempio: Inserimento di un’offerta tramite un profilo di consegna {#example--inserting-an-offer-via-a-delivery-outline}

La **profilo di consegna** L’attività , disponibile nei flussi di lavoro delle campagne, ti consente di presentare offerte a cui si fa riferimento in una struttura di consegna dalla campagna corrente in corso.

>[!NOTE]
>
>La **Interazione** il pacchetto deve essere installato.

1. In un flusso di lavoro, aggiungi un’attività di profilo della consegna prima di aggiungere un’attività di consegna.
1. Nell’attività di struttura della consegna, specifica il profilo da utilizzare.
1. Completa i campi disponibili in base alla consegna.
1. Esistono due casi possibili:

   * Se desideri chiamare il motore di offerta, controlla la **[!UICONTROL Restrict the number of propositions selected]** scatola. Specifica lo spazio di offerta e il numero di proposte da presentare nella consegna.

      Il motore di offerta terrà conto dei fattori di ponderazione e delle regole di idoneità dell’offerta.

   * Se non selezioni la casella , tutte le offerte nel profilo di consegna verranno presentate senza effettuare una chiamata al motore di offerta.

   L’anteprima tiene conto del numero di offerte specificate nella consegna. Quando esegui un flusso di lavoro, viene preso in considerazione il numero specificato nel profilo di consegna.

   ![](assets/int_compo_offre_wf1.png)
