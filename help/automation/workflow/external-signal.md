---
product: campaign
title: Segnale esterno
description: Ulteriori informazioni sull’attività del flusso di lavoro External signal
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 45cb95ec-77bf-4bab-895f-b94f6ce660fd
TQID: https://experienceleague.adobe.com/w1Sip-iisntO8WLiUhYCqr-9DeiGY1F2eiU2CUSDF7c
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 168
ht-degree: 2%

---

# Segnale esterno{#external-signal}



L&#39;attività **External signal** consente di attivare l&#39;esecuzione di un set di attività in un flusso di lavoro a una pianificazione.

Quando viene attivata, l&#39;attività &#39;External signal&#39; viene sospesa indefinitamente o fino alla fine del periodo di tempo specificato. La relativa transizione è attivata dalla chiamata SOAP **PostEvent(sessionToken, workflowId, activity, transition, parameters, complete).** Il parametro **[!UICONTROL complete]** consente di completare l&#39;attività, pertanto non reagirà alle chiamate successive.

Per ulteriori informazioni sulla funzione PostEvent, consulta la documentazione online relativa alle chiamate di SOAP.

Puoi configurare questa attività per definire gli eventi se non viene ricevuto alcun segnale. A tale scopo, modificare l&#39;attività e fare clic sulla scheda **[!UICONTROL Expiration]**. Fare clic sul pulsante **[!UICONTROL Insert]** per creare e configurare un evento.

![](assets/edit_signal.png)

La configurazione delle scadenze è descritta in [Scadenze](define-approvals.md).

Il campo **Ritardo** consente di specificare un ritardo di scadenza nelle unità scelte. Vedi [Attendi](wait.md).

Ogni riga rappresenta un tipo di scadenza e coincide con una transizione.

![](assets/external_sign_diag.png)
