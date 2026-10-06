---
product: campaign
title: Centro messaggi (esecuzione)
description: Centro messaggi (esecuzione)
feature: Workflows
role: User
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
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 2%
---

# Centro messaggi (esecuzione){#message-center-execution}

Per impostazione predefinita, i flussi di lavoro descritti di seguito vengono installati con il componente aggiuntivo **Centro messaggi - Esecuzione**.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etichetta</strong><br /> </td> 
   <td> <strong>Nome interno</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Update event status</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> Questo flusso di lavoro ti consente di assegnare uno stato a un evento. Gli stati degli eventi sono i seguenti:<br /> 
    <ul> 
     <li> <p><strong>In sospeso</strong>: l'evento è in coda. Non è ancora stato associato alcun modello di messaggio.</p> </li> 
     <li> <p><strong>Consegna in sospeso</strong>: l'evento si trova in una coda, a cui è stato associato un modello di messaggio ed è attualmente in fase di elaborazione da parte della consegna.</p> </li> 
     <li> <p><strong>Inviato</strong>: questo stato viene copiato dai registri di consegna. Significa che la consegna è stata inviata.</p> </li> 
     <li> <p><strong>Ignorato dalla consegna</strong>: questo stato viene copiato dai log di consegna. Significa che la consegna è stata ignorata.</p> </li> 
     <li> <p><strong>Errore di consegna</strong>: questo stato viene copiato dai registri di consegna. Significa che la consegna non è riuscita.</p> </li> 
     <li> <p><strong>Evento non coperto</strong>: l'evento non è stato associato a un modello di messaggio. L’evento non verrà rielaborato.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Elaborazione eventi batch</span> <br /> </td> 
   <td> <span class="uicontrol">batchEventsProcessing</span> <br /> </td> 
   <td> Questo flusso di lavoro ti consente di mettere in coda gli eventi batch prima di associarli a un modello di messaggio. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Elaborazione eventi in tempo reale</span> <br /> </td> 
   <td> <span class="uicontrol">rtEventsProcessing</span> <br /> </td> 
   <td> Questo flusso di lavoro consente di mettere in coda eventi in tempo reale prima di associarli a un modello di messaggio. <br /> </td> 
  </tr> 
 </tbody> 
</table>

