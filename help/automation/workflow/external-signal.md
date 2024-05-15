---
product: campaign
title: Segnale esterno
description: Ulteriori informazioni sull’attività del flusso di lavoro External signal
feature: Workflows
role: User
exl-id: 45cb95ec-77bf-4bab-895f-b94f6ce660fd
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 2%

---

# Segnale esterno{#external-signal}



Il **Segnale esterno** attività consente di attivare l’esecuzione di un set di attività in un flusso di lavoro a una pianificazione.

Quando viene attivata, l&#39;attività &#39;External signal&#39; viene sospesa indefinitamente o fino alla fine del periodo di tempo specificato. La relativa transizione viene attivata dalla chiamata SOAP **PostEvent(sessionToken, workflowId, attività, transizione, parametri, completo).** Il **[!UICONTROL complete]** Il parametro consente di terminare l’attività, pertanto non reagisce alle chiamate successive.

Per ulteriori informazioni sulla funzione PostEvent, consulta la documentazione online relativa alle chiamate SOAP.

Puoi configurare questa attività per definire gli eventi se non viene ricevuto alcun segnale. A questo scopo, modifica l’attività e fai clic su **[!UICONTROL Expiration]** scheda. Fai clic su **[!UICONTROL Insert]** per creare e configurare un evento.

![](assets/edit_signal.png)

La configurazione delle scadenze è descritta in [Scadenze](define-approvals.md).

Il **Ritardo** Questo campo consente di specificare un ritardo di scadenza nelle unità desiderate. Consulta [Wait](wait.md).

Ogni riga rappresenta un tipo di scadenza e coincide con una transizione.

![](assets/external_sign_diag.png)
