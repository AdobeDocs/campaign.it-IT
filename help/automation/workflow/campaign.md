---
product: campaign
title: Campaign
description: Campaign
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
topic-tags: technical-workflows
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 3%

---


# Campaign{#campaign}

Per impostazione predefinita, i flussi di lavoro descritti di seguito sono installati con il modulo **Campaign**.

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
   <td> <span class="uicontrol">Calcolo costi</span> <br /> </td> 
   <td> <span class="uicontrol">budgetMgt</span> <br /> </td> 
   <td> Questo flusso di lavoro avvia il calcolo delle righe spese e costi per budget, piani, programmi, campagne, consegne e attività.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Magazzino: Ordini e avvisi</span> <br /> </td> 
   <td> <span class="uicontrol">stockMgt</span> <br /> </td> 
   <td> Questo flusso di lavoro avvia il calcolo delle scorte nelle linee dell'ordine e gestisce le soglie degli avvisi di avvertenza.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Processi su consegne nelle campagne</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryMgt</span> <br /> </td> 
   <td> Questo flusso di lavoro attiva le consegne approvate e avvia la post-elaborazione del provider di servizi per una consegna esterna. Invia inoltre notifiche di approvazione e promemoria.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Processi campagna</span> <br /> </td> 
   <td> <span class="uicontrol">operationMgt</span> <br /> </td> 
   <td> Questo flusso di lavoro gestisce i processi per le campagne di marketing (avvio, targeting, estrazione file, ecc.). Vengono inoltre creati flussi di lavoro relativi a campagne ricorrenti e periodiche.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Processi nei provider di servizi</span> <br /> </td> 
   <td> <span class="uicontrol">gestione fornitori</span> <br /> </td> 
   <td> Questo flusso di lavoro avvia l’elaborazione del provider (e-mail al router e post-elaborazione) dopo l’approvazione delle consegne. <br /> </td> 
  </tr> 
 </tbody> 
</table>

