---
product: campaign
title: Interazione
description: Interazione
feature: Workflows, Interaction
source-git-commit: 8d9b8d3e31362c2d69ec0fc6f16ab375538d7f10
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 5%

---


# Interazione{#interaction}

I flussi di lavoro descritti di seguito vengono installati con **Motore di offerta (interazione)** componente aggiuntivo per impostazione predefinita.

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
   <td> Questo flusso di lavoro aggiorna <strong>Completo</strong> aggregato per <strong>Proposta di offerta</strong> cubo. Per impostazione predefinita viene attivato ogni giorno alle 6. Questo aggregato acquisisce le seguenti dimensioni: Canale, Consegna, Offerta di marketing e Data.<br /> Il <strong>Proposta di offerta</strong> Il cubo viene quindi utilizzato per generare rapporti basati sulle offerte.<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">Calcolo dell'aggregazione completa MessageCenter</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> Questo flusso di lavoro aggiorna <strong>Completo</strong> aggregato per <strong>Centro messaggi</strong> cubo. Viene attivato ogni giorno alle 3 per impostazione predefinita. Questo aggregato acquisisce le seguenti dimensioni: Canale, Data, Stato e Tipo evento.<br /> Il <strong>Centro messaggi</strong> Il cubo viene quindi utilizzato per generare rapporti basati sugli eventi. <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

Ulteriori informazioni su cubi e aggregati in [questa sezione](../../v8/reporting/gs-cubes.md).

