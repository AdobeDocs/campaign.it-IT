---
product: campaign
title: Interazione
description: Interazione
feature: Workflows, Interaction
role: User, Admin
version: Campaign v8, Campaign Classic v7
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 3%
---

# Interazione{#interaction}

I flussi di lavoro descritti di seguito vengono installati con il componente aggiuntivo **Offer Engine (Interaction)** per impostazione predefinita.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etichetta</strong><br /> </td> 
   <td> <strong>Nome interno</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Calcolo aggregato completo (cubo propositionrcp)</span> <br /> </td> 
   <td> <span class="uicontrol">agg_nmspropositionrcp_full</span> <br /> </td> 
   <td> Questo flusso di lavoro aggiorna l'aggregazione <strong>Full</strong> per il cubo <strong>Proposta di offerte</strong>. Per impostazione predefinita viene attivato ogni giorno alle 6. Questo aggregato acquisisce le dimensioni seguenti: Canale, Consegna, Offerta di marketing e Data.<br /> Il cubo <strong>Proposta di offerte</strong> viene quindi utilizzato per generare rapporti basati sulle offerte.<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">Calcolo aggregato completo MessageCenter</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> Questo flusso di lavoro aggiorna l'aggregazione <strong>Full</strong> per il cubo <strong>Centro messaggi</strong>. Viene attivato ogni giorno alle 3 per impostazione predefinita. Questo aggregato acquisisce le dimensioni seguenti: Canale, Data, Stato e Tipo evento.<br /> Il cubo <strong>Centro messaggi</strong> viene quindi utilizzato per generare report basati sugli eventi. <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

Ulteriori informazioni su cubi e aggregati sono disponibili in [questa sezione](../../v8/reporting/gs-cubes.md).

