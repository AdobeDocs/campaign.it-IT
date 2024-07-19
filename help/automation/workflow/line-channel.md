---
product: campaign
title: Canale LINE
description: Canale LINE
feature: Workflows, Line App
role: User
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 2%

---


# Canale LINE{#line-channel}

Per impostazione predefinita, i flussi di lavoro descritti di seguito vengono installati con il modulo **LINE channel**. Per ulteriori informazioni su questo modulo, consulta [questa pagina](../../v8/send/line.md).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etichetta</strong><br /> </td> 
   <td> <strong>Nome interno</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Aggiornamento token di accesso LINE V2</span> <br /> </td> 
   <td> <span class="uicontrol">updateLineV2AccessToken</span> <br /> </td> 
   <td> Questo flusso di lavoro aggiorna il token di accesso a LINE V2.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Elimina utenti LINE bloccati</span> <br /> </td> 
   <td> <span class="uicontrol">deleteBlockedLineUsersV2</span> <br /> </td> 
   <td> Questo flusso di lavoro assicura che i dati degli utenti LINE V2 vengano eliminati dopo che hanno bloccato l'account ufficiale LINE per 180 giorni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Migrazione da <span class="uicontrol">MID a LineUserID</span> <br /> </td> 
   <td> <span class="uicontrol">MIDToUserIDMigration</span> <br /> </td> 
   <td> Questo flusso di lavoro genera l'ID degli utenti LINE V2 per la migrazione da LINE V1 a LINE V2.<br /> </td> 
  </tr> 
 </tbody> 
</table>

