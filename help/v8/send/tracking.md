---
title: Introduzione al tracciamento dei messaggi
description: Ulteriori informazioni sulle funzionalità di tracciamento in Adobe Campaign
feature: Monitoring, Email
role: User
level: Beginner
exl-id: f3de901f-519f-42ae-846c-f20c7cb560df
source-git-commit: 57e177dc6c30502f2ed3bb08b18586fa5399e89c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# Introduzione al tracciamento dei messaggi {#get-started-tracking}

Grazie alle sue funzionalità di tracciamento, Adobe Campaign ti consente di tenere traccia dei messaggi inviati e di controllare il comportamento dei destinatari: apertura, clic sui collegamenti, annullamento dell’abbonamento e altro ancora.

Queste informazioni vengono recuperate nella scheda **[!UICONTROL Tracking]** del profilo di ciascun destinatario della consegna. Questa scheda presenta tutti i collegamenti URL tracciati e cliccati dal destinatario selezionato dall’elenco. Si tratta dell’accumulo di tutti gli URL tracciati nelle consegne ancora presenti nella schermata di consegna. L’elenco può essere configurato e in genere contiene: l’URL su cui è stato fatto clic, la data e l’ora del clic e il documento in cui è stato trovato l’URL.

Il **dashboard di consegna** è anche uno strumento chiave per monitorare le consegne e i potenziali problemi durante l&#39;invio dei messaggi.

Il diagramma seguente mostra le fasi della finestra di dialogo tra l’utente e i vari server.

<img src="assets/tracking-diagram.png" width="70%">

>[!NOTE]
>
>La configurazione del tracciamento viene eseguita da Adobe per le distribuzioni di Managed Cloud Services.

## Tracciamento dei messaggi {#message-tracking}

**Collegamenti tracciati**

Puoi tenere traccia della ricezione dei messaggi e dell’attivazione dei collegamenti inseriti nel contenuto del messaggio per comprendere meglio il comportamento dei destinatari.

[Ulteriori informazioni sui collegamenti tracciati](tracked-links.md)

**Tracciamento URL**

Le opzioni di tracciamento possono essere configurate attivando o disattivando gli URL tracciati.

[Ulteriori informazioni sulle opzioni di tracciamento URL](url-tracking.md)

**Personalizzazione collegamento tracciato**

Le funzionalità di tracciamento delle campagne consentono di aggiungere alle e-mail collegamenti che possono essere personalizzati e che supportano il tracciamento.

[Ulteriori informazioni sul tracciamento dei collegamenti personalizzati](personalized-links.md)

**Registri di tracciamento**

Il flusso di lavoro tecnico **Tracciamento** recupera i dati di tracciamento una volta inviata la consegna e attivato il tracciamento. Questi dati si trovano nella scheda Tracciamento della consegna.

[Ulteriori informazioni sui registri di tracciamento](tracking-logs.md)

**Test del tracking**

Prima di inviare i messaggi con il tracciamento, puoi testarlo sulla pagina speculare, sui registri e collegamenti e-mail.

[Ulteriori informazioni sul tracciamento dei test](testing-tracking.md)

## Tracciamento dei rapporti {#tracking-reports}

**Statistiche di tracciamento**

Questo rapporto fornisce statistiche su aperture, clic e transazioni e consente di tenere traccia dell’impatto di marketing della consegna.

[Ulteriori informazioni sui rapporti di tracciamento](../reporting/delivery-reports.md#tracking-indicators)

**URL e flussi di clic**

Questo rapporto mostra l’elenco delle pagine visitate dopo una consegna.

[Ulteriori informazioni su URL e flussi di clic](../reporting/delivery-reports.md#urls-and-click-streams)

**Persona/persone e destinatari**

Con questo esempio, puoi comprendere meglio la differenza di tracciamento tra una persona/persone e un destinatario in Adobe Campaign.

[Ulteriori informazioni su persone e destinatari mirati](../reporting/metrics-calculation.md#targeted-persons---recipients)

**Indicatori di tracciamento**

Questo rapporto combina gli indicatori chiave per monitorare il comportamento dei destinatari al momento della ricezione della consegna, ad esempio i tassi di apertura e click-through e i flussi di clic.

[Ulteriori informazioni sugli indicatori di tracciamento](../reporting/delivery-reports.md#tracking-indicators)

**Calcolo indicatore**

Le diverse tabelle forniscono l’elenco degli indicatori utilizzati nei diversi rapporti e la relativa formula di calcolo a seconda del tipo di consegna.

[Ulteriori informazioni sul calcolo degli indicatori](../reporting/metrics-calculation.md)


