---
product: campaign
title: Recapito e-mail
description: Ulteriori informazioni sul pacchetto Recapito e-mail
feature: Workflows, Deliverability
role: User
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 63876777-85c3-57e1-a2da-81f02956c63c
    internal-label: Deliverability
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
source-wordcount: '92'
ht-degree: 3%
---

# Monitoraggio del recapito messaggi (recapito messaggi e-mail){#email-deliverability}

Il flusso di lavoro descritto di seguito viene installato per impostazione predefinita in tutte le istanze e consente di inizializzare l’elenco delle regole di qualifica della posta non recapitata, l’elenco dei domini e l’elenco dei MX. Una volta installato il pacchetto di monitoraggio del recapito messaggi **(recapito messaggi e-mail)**, il flusso di lavoro viene eseguito ogni notte.
<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etichetta</strong><br /> </td> 
   <td> <strong>Nome interno</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Aggiorna per il recapito messaggi</strong><br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td>  Una volta installato il pacchetto <strong>Monitoraggio del recapito messaggi (recapito messaggi e-mail)</strong>, questo flusso di lavoro viene eseguito ogni notte per aggiornare regolarmente l'elenco delle regole e consentire di gestire attivamente il recapito messaggi della piattaforma.<br /> </td> 
  </tr> 
 </tbody> 
</table>

