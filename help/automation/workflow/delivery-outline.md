---
product: campaign
title: Profilo di consegna
description: Ulteriori informazioni sull’attività del flusso di lavoro Struttura della consegna
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 3c06b329-b2d8-4ac8-ab9b-3ab3e525d109
TQID: 'https://experienceleague.adobe.com/-uyRqPAXzP-l05tmEfq4ZcJizCiGpTfY0qu-6tQ8cU0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: ff84ab2f-a7c2-4ced-a3c8-5113f4348d99
    internal-label: Targeting Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 1%
---
# Profilo di consegna{#delivery-outline}

La **struttura di consegna** ti consente di utilizzare una struttura in un flusso di lavoro della campagna. La struttura deve essere stata creata in precedenza nella campagna.

Per configurare l’attività, è sufficiente selezionare la struttura desiderata e la data di contatto pianificata. Puoi aggiungere regole di filtro aggiungendo tipologie o regole di tipologia.

## Esempio: inserimento di un’offerta tramite una struttura di consegna {#example--inserting-an-offer-via-a-delivery-outline}

L&#39;attività **struttura consegna**, disponibile nei flussi di lavoro della campagna, consente di presentare le offerte a cui si fa riferimento in una struttura di consegna della campagna corrente in corso.

>[!NOTE]
>
>È necessario installare il pacchetto **Interaction**.

1. In un flusso di lavoro, aggiungi un’attività di struttura della consegna prima di aggiungerla.
1. Nell’attività di struttura della consegna, specifica la struttura da utilizzare.
1. Completa i campi disponibili in base alla consegna.
1. Esistono due casi possibili:

   * Se desideri chiamare il motore di offerta, seleziona la casella **[!UICONTROL Restrict the number of propositions selected]**. Specifica lo spazio dell’offerta e il numero di proposte che verranno presentate nella consegna.

     Il motore di offerta terrà conto dei pesi delle offerte e delle regole di idoneità.

   * Se non selezioni la casella, tutte le offerte nella struttura della consegna verranno presentate senza effettuare una chiamata al motore di offerta.

   L’anteprima prende in considerazione il numero di offerte specificato nella consegna. Durante l’esecuzione di un flusso di lavoro, viene preso in considerazione il numero specificato nella struttura della consegna.

   ![](assets/int_compo_offre_wf1.png)
