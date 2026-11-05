---
product: campaign
title: Piattaforma di mid-sourcing
description: Piattaforma di mid-sourcing
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
source-git-commit: 8a7bf8408d15e0bd9e1c3e72f7846bf9a79c6885
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 1%
---

# Piattaforma di mid-sourcing{#mid-sourcing-platform}



Per impostazione predefinita, il flusso di lavoro descritto di seguito viene installato con il modulo **Piattaforma Mid-Sourcing**.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etichetta</strong><br /> </td> 
   <td> <strong>Nome interno</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Indicatori di consegna</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryIndicators</span> <br /> </td> 
   <td> Questo flusso di lavoro aggiorna gli indicatori di tracciamento della consegna per una consegna. Questo flusso di lavoro viene attivato ogni ora per impostazione predefinita.<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Il periodo di conservazione del registro nel server di mid-sourcing deve essere più lungo del periodo di validità della consegna più il valore **indicatorsDuration**. In caso contrario, gli indicatori di consegna diminuiscono quando i registri precedenti vengono eliminati e i valori inferiori vengono sincronizzati con l’istanza di marketing. Ad esempio, con un periodo di validità di 5 giorni e una **indicatorsDuration** di 30 giorni, imposta il periodo di conservazione su almeno 36 giorni.
