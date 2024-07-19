---
title: Inviare e monitorare i messaggi transazionali
description: Scopri come inviare e monitorare i messaggi transazionali
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 084607f6-47d8-40c0-89ba-bfbb88fc2e53
source-git-commit: c044b391c900e8ff82147f2682e2e4f91845780c
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 1%

---

# Inviare e monitorare i messaggi transazionali {#delivery-execution}

## Inviare messaggi{#send-transactional-msg}

Una volta completato l’arricchimento e collegato un modello di consegna all’evento, la consegna viene inviata dall’istanza di esecuzione.

>[!NOTE]
>
>I messaggi transazionali hanno priorità rispetto a qualsiasi altra consegna.

Tutte le consegne sono raggruppate nella cartella **[!UICONTROL Administration > Production > Message Center > Default > Deliveries]**.

Per impostazione predefinita, sono ordinate in sottocartelle per mese di consegna. Questo può essere modificato nelle proprietà del modello del messaggio.

## Monitorare i messaggi {#monitor-transactional-msg}

Per monitorare i messaggi transazionali, controlla i [registri di consegna](send.md).

Le consegne transazionali inviate dall&#39;istanza di esecuzione vengono sincronizzate con l&#39;istanza di controllo tramite un flusso di lavoro tecnico (**[!UICONTROL Message Center execution instance]**) che viene eseguito ogni ora.

>[!NOTE]
>
>Le consegne settimanali accumulano gli eventi in base all’ultimo aggiornamento dell’evento e non alla data di creazione dell’evento. Pertanto, durante l’estrazione dei registri di consegna della messaggistica transazionale dall’istanza di controllo, l’ID di consegna associato a ciascun ID del registro di consegna può cambiare nel tempo man mano che il registro viene aggiornato (ad esempio, quando viene ricevuto un mancato recapito in entrata per l’evento).

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->

## Reportistica{#reporting-transactional-msg}

Adobe Campaign offre diversi rapporti che ti consentono di controllare l’attività e l’esecuzione fluida delle istanze di esecuzione.

È possibile accedere a questi report del Centro messaggi dalla scheda **[!UICONTROL Reports]** dell&#39;**istanza di controllo**.

![](assets/mc-reports.png)

### Cronologia eventi del Centro messaggi {#history-events}

Il report **[!UICONTROL Message Center event history]** visualizza una panoramica dell&#39;attività del modulo Centro messaggi, ovvero il numero di eventi elaborati e consegnati come messaggi transazionali.

Quando il rapporto viene aperto, le informazioni visualizzate per impostazione predefinita coincidono con la frequenza dei messaggi transazionali inviati correttamente. Per visualizzare più livelli, è possibile aprire i vari nodi e posizionare il cursore sul livello appropriato per selezionarlo.

Puoi visualizzare i dati specifici di ciascun tipo di evento, per periodo di tempo. La colonna **[!UICONTROL Events]** corrisponde al numero di eventi ricevuti per istanza di controllo. Il numero di eventi trasformati in messaggi transazionali personalizzati è descritto nella colonna **[!UICONTROL Sent]**.


### Tempo di elaborazione del Centro messaggi {#processing-time}

Il report **[!UICONTROL Message Center processing time]** visualizza gli indicatori principali relativi alla coda in tempo reale. È inoltre possibile accedere al report tramite la scheda **[!UICONTROL Monitoring]** nell&#39;istanza di controllo.

![](assets/mc-processing-time-report.png)

È possibile scegliere di visualizzare le statistiche globali o quelle relative a una particolare istanza di esecuzione. Puoi anche filtrare i dati per canale e in un periodo specifico.

Gli indicatori visualizzati nella sezione **[!UICONTROL Indicators over the period]** vengono calcolati per il periodo selezionato:

* **[!UICONTROL Average queuing time]**: tempo medio trascorso nel Centro messaggi durante l&#39;elaborazione degli eventi. Viene preso in considerazione solo il tempo di elaborazione.
* **[!UICONTROL Average message sending time (s)]**: tempo medio trascorso nel Centro messaggi durante l&#39;elaborazione degli eventi. Viene preso in considerazione solo il tempo di consegna dell’MTA.
* **[!UICONTROL Average processing time (s)]**: tempo medio trascorso nel Centro messaggi durante l&#39;elaborazione degli eventi. Il calcolo tiene conto del tempo di elaborazione e del tempo di invio dell’MTA.
* **[!UICONTROL Maximum number of queued events]**: numero massimo di eventi presenti nella coda del Centro messaggi in un determinato momento.
* **[!UICONTROL Minimum number of queued events]**: numero minimo di eventi presenti nella coda del Centro messaggi in un determinato momento.
* **[!UICONTROL Average number of queued events]**: numero medio di eventi presenti nella coda del Centro messaggi in un determinato momento.

>[!NOTE]
>
>Le soglie degli indicatori di avviso (arancione) e di avviso (rosso) possono essere configurate nella procedura guidata di distribuzione di Adobe Campaign. Consulta [Monitorare le soglie](#thresholds).



### Livello di servizio del Centro messaggi {#service-level}

Il report **[!UICONTROL Message Center service level]** visualizza le statistiche di consegna relative ai messaggi transazionali e il raggruppamento degli errori. Puoi fare clic su un tipo di errore per visualizzarne i dettagli.

È inoltre possibile accedere al report tramite la scheda **[!UICONTROL Monitoring]** nell&#39;istanza di controllo.

È possibile scegliere di visualizzare le statistiche globali o quelle relative a una particolare istanza di esecuzione. Puoi anche filtrare i dati per canale e in un periodo specifico.

Gli indicatori visualizzati nella sezione **[!UICONTROL Indicators over the period]** vengono calcolati per il periodo selezionato:

* **[!UICONTROL Incoming (throughput event/h)]**: numero medio orario di eventi immessi nella coda del Centro messaggi.
* **[!UICONTROL Incoming (event vol)]**: numero di eventi immessi nella coda del Centro messaggi.
* **[!UICONTROL Outgoing (throughput msg/h)]**: numero medio orario di eventi del Centro messaggi in uscita completati (inviati da una consegna).
* **[!UICONTROL Outgoing (msg vol)]**: numero di eventi del Centro messaggi in uscita completati (inviati da una consegna).
* **[!UICONTROL Average sending time (seconds)]**: tempo medio trascorso nel Centro messaggi per gli eventi elaborati correttamente. Il calcolo tiene conto del tempo di elaborazione e del tempo di invio dell’MTA.
* **[!UICONTROL Error rate]**: numero di eventi con errori rispetto al numero di eventi che sono entrati nella coda del Centro messaggi. Vengono presi in considerazione i seguenti errori: errore di routing, evento scaduto (evento che è stato nella coda troppo lungo), errore di consegna, ignorato dalla consegna (quarantena, ecc.).

>[!NOTE]
>
>Le soglie degli indicatori di avviso (arancione) e di avviso (rosso) possono essere configurate nella procedura guidata di distribuzione di Adobe Campaign. Consulta [Monitorare le soglie](#thresholds).

### Monitorare le soglie {#thresholds}

È possibile configurare le soglie di avviso (arancione) e di avviso (rosso) degli indicatori visualizzati nei report **Livello di servizio del Centro messaggi** e **Tempo di elaborazione del Centro messaggi**.

A questo scopo, segui la procedura indicata di seguito:

1. Aprire la procedura guidata di distribuzione nell&#39;**istanza di esecuzione** e passare alla pagina **[!UICONTROL Message Center]**.
1. Utilizzare le frecce per modificare le soglie.

   ![](assets/mc-thresholds.png)
