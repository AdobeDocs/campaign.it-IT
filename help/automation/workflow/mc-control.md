---
product: campaign
title: Centro messaggi (Controllo)
description: Centro messaggi (Controllo)
feature: Workflows
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 10%

---


# Centro messaggi (Controllo){#message-center-control}

Il flusso di lavoro descritto di seguito è pianificato per l’esecuzione ogni ora. È installato con **Centro messaggi - Controllo** modulo per impostazione predefinita.


<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etichetta</strong><br /> </td> 
   <td> <strong>Nome interno</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Centro messaggi &lt;external_account_name&gt;<br /> </td> 
   <td> mcSynch_&lt;external_account_name&gt;<br /> </td> 
   <td> Questo flusso di lavoro:<br /> 
    <ul> 
     <li> <p>recupera l’elenco degli eventi elaborati dalle operazioni.</p> </li> 
     <li> <p>si sincronizza con la tabella NmsBroadLogMsg per recuperare i requisiti dei messaggi di consegna.</p> </li> 
     <li> <p>recupera i registri di consegna degli eventi non appena la sincronizzazione con la tabella NmsBroadLogMsg è stata completata.</p> </li> 
     <li> <p>si sincronizza con la tabella NmsTrackingUrl al fine di recuperare il tracciamento per gli URL di consegna.</p> </li> 
     <li> <p>recupera gli URL di tracciamento degli eventi non appena la sincronizzazione con la tabella NmsTrackingUrl è stata completata.</p> </li> 
     <li> <p>consente di recuperare tutti gli indirizzi e-mail messi in quarantena ogni tre ore dopo l’invio di una consegna.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

