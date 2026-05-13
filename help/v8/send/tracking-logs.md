---
title: Registri di tracciamento degli accessi
description: Scopri come accedere e interpretare i registri di tracciamento
feature: Monitoring
role: User
level: Beginner
exl-id: df494786-5950-4646-aa9c-4dde45845057
TQID: https://experienceleague.adobe.com/yiuHvMtsmTULvX9X0ZjlMexNMsXpyGhkosOyMc-VoTs
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2: id: a39dbcf0-89cb-4765-9bcb-cf9dfbe2875f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 340
ht-degree: 0%

---

# Registri di tracciamento degli accessi {#accessing-the-tracking-logs}

Quando la consegna è stata inviata e il tracciamento è attivato, il flusso di lavoro tecnico **[!UICONTROL Tracking]** è responsabile del recupero dei dati di tracciamento. Viene eseguito ogni ora per impostazione predefinita.

## Visualizza tracciamento nei profili dei destinatari {#recipient-tracking}

Queste informazioni vengono visualizzate nella scheda **[!UICONTROL Tracking]** del profilo dei destinatari interessati dalla consegna, come nell’esempio seguente:

![](assets/s_ncs_user_select_tracking_tab_from_recipient.png)

In questa scheda vengono visualizzati tutti gli URL tracciati e su cui il destinatario ha fatto clic, tra cui:

* URL su cui è stato fatto clic
* Data e ora del clic
* La consegna in cui è stato trovato l’URL
* Qualsiasi altra informazione di tracciamento rilevante

Puoi filtrare e ordinare queste informazioni per analizzare il comportamento dei destinatari e identificare i pattern di coinvolgimento.

## Visualizza tracciamento nelle consegne {#delivery-tracking}

Le informazioni di tracciamento sono accessibili anche tramite la scheda **[!UICONTROL Tracking]** della consegna.

![](assets/s_ncs_user_select_tracking_tab_from_del.png)

Da questa scheda puoi visualizzare:

* **[!UICONTROL Tracking statistics]**: fornisce una panoramica di aperture, clic e altri eventi di tracciamento
* **[!UICONTROL URLs and click streams]**: mostra quali collegamenti sono stati selezionati e quante volte
* **[!UICONTROL Hot clicks]**: visualizza una rappresentazione visiva della posizione in cui i destinatari hanno fatto clic nel messaggio
* **[!UICONTROL Tracking logs]**: fornisce record di tracciamento individuali dettagliati

## Risoluzione dei problemi di tracciamento {#troubleshooting}

>[!NOTE]
>
>Se non riesci a visualizzare la scheda **[!UICONTROL Tracking]** di una consegna, significa che il tracciamento non è stato attivato. Consulta [questa sezione](tracked-links.md) per scoprire come configurare il tracciamento.

### Controlla il flusso di lavoro tecnico di tracciamento {#check-tracking-workflow}

Per raccogliere i dati di tracciamento, il flusso di lavoro tecnico di tracciamento deve essere in esecuzione. È possibile individuare il flusso di lavoro tecnico di tracciamento nella cartella **[!UICONTROL Administration > Production > Technical workflows]**.

Per verificare il flusso di lavoro:

1. Apri il flusso di lavoro **[!UICONTROL Tracking]**
1. Controlla la data dell’ultima esecuzione
1. Verifica che non siano presenti errori nei registri del flusso di lavoro

Se il flusso di lavoro non è in esecuzione o presenta errori, contatta l’amministratore di sistema.

## Verificare la raccolta dati di tracciamento

Dopo aver inviato una consegna con il tracciamento abilitato:

1. Attendi l’esecuzione del flusso di lavoro di tracciamento (per impostazione predefinita, ogni ora)
1. Apri la consegna e passa alla scheda **[!UICONTROL Tracking]**
1. Verifica che siano visualizzati i dati di tracciamento
1. Se non vengono visualizzati dati, verificare che:
   * Il tracciamento è stato attivato nelle impostazioni di consegna
   * Il flusso di lavoro tecnico di tracciamento è in esecuzione
   * I destinatari hanno aperto l’e-mail e fatto clic sui collegamenti

## Argomenti correlati {#related-topics}

* [Scopri come configurare i collegamenti tracciati](tracked-links.md)
* [Scopri come verificare il tracciamento](testing-tracking.md)
* [Comprendere i rapporti di tracciamento](../reporting/delivery-reports.md#tracking-indicators)

