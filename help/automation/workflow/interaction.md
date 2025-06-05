---
product: campaign
title: Interazione
description: Interazione
feature: Workflows, Interaction
role: User, Admin
version: Campaign v8, Campaign Classic v7
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '131'
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
   <td> Questo flusso di lavoro aggiorna l'aggregazione <strong>Full</strong> per il cubo <strong>Proposta di offerte</strong>. Per impostazione predefinita viene attivato ogni giorno alle 6. Questo aggregato acquisisce le seguenti dimensioni: Canale, Consegna, Offerta di marketing e Data.<br /> Il cubo <strong>Proposta di offerte</strong> viene quindi utilizzato per generare rapporti basati sulle offerte.<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">Calcolo aggregato completo MessageCenter</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> Questo flusso di lavoro aggiorna l'aggregazione <strong>Full</strong> per il cubo <strong>Centro messaggi</strong>. Viene attivato ogni giorno alle 3 per impostazione predefinita. Questo aggregato acquisisce le seguenti dimensioni: Canale, Data, Stato e Tipo evento.<br /> Il cubo <strong>Centro messaggi</strong> viene quindi utilizzato per generare report basati sugli eventi. <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

Ulteriori informazioni su cubi e aggregati sono disponibili in [questa sezione](../../v8/reporting/gs-cubes.md).

