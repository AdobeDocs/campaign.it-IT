---
title: Esecuzione della consegna dei messaggi transazionali
description: Ulteriori informazioni sull’esecuzione e il monitoraggio della consegna dei messaggi transazionali
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 1%

---


# Esecuzione della consegna {#delivery-execution}

Una volta completato l’arricchimento e collegato un modello di consegna all’evento, la consegna viene inviata dall’istanza di esecuzione.

>[!NOTE]
>
>I messaggi transazionali hanno priorità rispetto a qualsiasi altra consegna.

Tutte le consegne sono raggruppate nel **[!UICONTROL Administration > Production > Message Center > Default > Deliveries]** cartella.

Per impostazione predefinita, sono ordinate in sottocartelle per mese di consegna. Questo ordinamento può essere modificato nelle proprietà del modello di messaggio.

## Monitoraggio dei messaggi transazionali {#transactional-message-monitoring}

Per monitorare i messaggi transazionali, controlla il [registri di consegna](send.md).

Le consegne transazionali inviate dall’istanza di esecuzione vengono sincronizzate nuovamente nell’istanza di controllo tramite un flusso di lavoro tecnico (**[!UICONTROL Message Center execution instance]**) che viene eseguito ogni ora.

>[!NOTE]
>
>Le consegne accumulano settimanalmente gli eventi in base all’ultimo aggiornamento dell’evento e non alla data di creazione dell’evento. Pertanto, quando si estraggono i registri di consegna dei messaggi transazionali dall’istanza di controllo, l’ID di consegna associato a ciascun ID di registro di consegna può cambiare nel tempo mentre il registro viene aggiornato (ad esempio, quando viene ricevuto un messaggio non recapitato in entrata per l’evento).

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->
