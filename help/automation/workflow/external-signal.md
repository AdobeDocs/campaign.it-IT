---
product: campaign
title: Attività External signal
description: Ulteriori informazioni sull’attività del flusso di lavoro del segnale esterno
feature: Workflows
exl-id: 45cb95ec-77bf-4bab-895f-b94f6ce660fd
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 2%

---

# Attività External signal{#external-signal}



La **Segnale esterno** consente di attivare l’esecuzione di un insieme di attività in un flusso di lavoro in base a una pianificazione.

Quando un&#39;attività &quot;External signal&quot; viene attivata, viene messa in pausa indefinitamente o fino alla fine del periodo di tempo specificato. La relativa transizione è attivata dalla chiamata SOAP **PostEvent(sessionToken, workflowId, attività, transizione, parametri, completo).** La **[!UICONTROL complete]** consente di completare l’attività, pertanto non reagisce alle chiamate successive.

Fare riferimento alla documentazione online relativa alle chiamate SOAP per ulteriori informazioni sulla funzione PostEvent.

Puoi configurare questa attività per definire gli eventi se non viene ricevuto alcun segnale. A questo scopo, modifica l’attività e fai clic sul pulsante **[!UICONTROL Expiration]** scheda . Fai clic sul pulsante **[!UICONTROL Insert]** per creare e configurare un evento.

![](assets/edit_signal.png)

La configurazione delle scadenze è descritta in [Scadenza](define-approvals.md).

La **Ritardo** consente di specificare un ritardo di scadenza nelle unità scelte. Vedi [Wait](wait.md).

Ogni riga rappresenta un tipo di scadenza e coincide con una transizione.

![](assets/external_sign_diag.png)
