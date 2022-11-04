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

I flussi di lavoro descritti di seguito sono installati con **Motore di offerta (Interazione)** add-on per impostazione predefinita.

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
   <td> Questo flusso di lavoro aggiorna le <strong>Completo</strong> aggregato per <strong>Proposta di offerta</strong> cubo. Viene attivato ogni giorno alle 6 per impostazione predefinita. Questo aggregato acquisisce le seguenti dimensioni: Canale, consegna, offerta di marketing e data.<br /> La <strong>Proposta di offerta</strong> viene quindi utilizzato per generare rapporti basati sulle offerte.<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">Calcolo aggregato completo MessageCenter</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> Questo flusso di lavoro aggiorna le <strong>Completo</strong> aggregato per <strong>Centro messaggi</strong> cubo. Viene attivato ogni giorno alle 3 per impostazione predefinita. Questo aggregato acquisisce le seguenti dimensioni: Canale, data, stato ed evento.<br /> La <strong>Centro messaggi</strong> Il cubo viene quindi utilizzato per generare report basati su eventi. <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

Ulteriori informazioni su cubi e aggregati in [questa sezione](../../v8/reporting/gs-cubes.md).

