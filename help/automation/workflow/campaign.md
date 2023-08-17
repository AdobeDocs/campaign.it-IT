---
product: campaign
title: Campaign
description: Campaign
feature: Workflows
topic-tags: technical-workflows
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 15%

---


# Campaign{#campaign}

I flussi di lavoro descritti di seguito vengono installati con **Campagna** per impostazione predefinita.

>[!CAUTION]
>
>Questi flussi di lavoro DEVONO essere avviati affinché i processi della campagna possano essere eseguiti a livello di campagna.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etichetta</strong><br /> </td> 
   <td> <strong>Nome interno</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Calcolo del costo</span> <br /> </td> 
   <td> <span class="uicontrol">budgetManagement</span> <br /> </td> 
   <td> Questo flusso di lavoro avvia il calcolo delle righe spese e costi per budget, piani, programmi, campagne, consegne e attività.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Magazzino: ordini e avvisi</span> <br /> </td> 
   <td> <span class="uicontrol">stockManagement</span> <br /> </td> 
   <td> Questo flusso di lavoro avvia il calcolo delle scorte nelle linee dell'ordine e gestisce le soglie degli avvisi di avvertenza.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Processi sulle consegne nelle campagne</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryManagement</span> <br /> </td> 
   <td> Questo flusso di lavoro attiva le consegne approvate e avvia la post-elaborazione del provider di servizi per una consegna esterna. Invia inoltre notifiche di approvazione e promemoria.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Processi di Campaign</span> <br /> </td> 
   <td> <span class="uicontrol">operationManagement</span> <br /> </td> 
   <td> Questo flusso di lavoro gestisce i processi per le campagne di marketing (avvio, targeting, estrazione file, ecc.). Crea anche flussi di lavoro relativi a campagne ricorrenti e periodiche.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Processi nei fornitori di servizi</span> <br /> </td> 
   <td> <span class="uicontrol">gestioneFornitori</span> <br /> </td> 
   <td> Questo flusso di lavoro avvia l’elaborazione del provider (e-mail al router e post-elaborazione) dopo l’approvazione delle consegne. <br /> </td> 
  </tr> 
 </tbody> 
</table>

