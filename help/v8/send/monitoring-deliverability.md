---
product: campaign
title: Monitorare il recapito messaggi in Adobe Campaign
description: Scopri gli strumenti e le linee guida per il monitoraggio del recapito messaggi in Adobe Campaign
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 11c8c4c51c7901ba0d119323c564a64b940428b7
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 2%

---

# Monitorare il recapito messaggi{#monitoring-deliverability}

Di seguito trovi i dettagli sui diversi strumenti di monitoraggio forniti da Adobe Campaign, nonché alcune linee guida aggiuntive sull’utilizzo delle funzioni offerte da Adobe Campaign per monitorare il recapito messaggi della piattaforma.

## Strumenti di monitoraggio {#monitoring-tools}

Adobe Campaign ti consente di accedere a tutti gli strumenti di recapito messaggi elencati di seguito.

* Il report di rendering della [Posta in arrivo](inbox-rendering.md) consente di visualizzare l&#39;anteprima dei messaggi sui principali client di posta elettronica per esaminare il contenuto e la reputazione.

* Il report **[!UICONTROL Delivery throughput]** offre una panoramica della velocità effettiva dell&#39;intera piattaforma per un determinato periodo. Per ulteriori informazioni, consulta [questa sezione](../reporting/global-reports.md#delivery-throughput).
* Ogni consegna genera un rapporto sulle statistiche di trasmissione per i diversi provider di servizi Internet (ISP). Mostra alcune metriche relative alla qualità dei dati e alla reputazione che possono influire sul recapito messaggi, tra cui i seguenti numeri:
   * **[!UICONTROL Hard bounces]** indica la qualità dei dati. Questo numero deve essere inferiore al 2%.
   * **[!UICONTROL Soft bounces]** indicare la reputazione. Questo numero non deve essere superiore al 10% per un dato ISP.

  <!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

* Più in generale, il [dashboard di consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#sending-messages){target="_blank"} ti consente di accedere a:
   * il riepilogo della consegna, che mostra i dettagli dell’invio e il numero di messaggi da inviare, elaborare e inviare con esito positivo;
   * i registri di consegna e la cronologia, che indicano quale target è stato escluso e perché;
   * i registri di tracciamento, che mostrano informazioni di tracciamento come aperture e clic.

## Linee guida per il monitoraggio {#monitoring-guidelines}

Di seguito sono riportate alcune linee guida aggiuntive sul monitoraggio della consegna dei messaggi:

* Controlla regolarmente la [velocità effettiva di consegna](../reporting/global-reports.md#delivery-throughput) per l&#39;intera piattaforma per verificare se è coerente con la configurazione originale.
* Verifica che [nuovi tentativi](delivery-failures.md#retries) siano configurati correttamente (30 minuti per il periodo di esecuzione dei nuovi tentativi e più di 20 tentativi) nei modelli di consegna.
* Verificare regolarmente che la cassetta postale [bounce](delivery-failures.md#bounce-mail-qualification) sia accessibile e che l&#39;account non stia per scadere.
* Controlla ogni velocità effettiva di consegna, accessibile dal [dashboard di consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#sending-messages){target="_blank"}, per assicurarti che sia coerente con la validità del contenuto della consegna (ad esempio, le &quot;vendite flash&quot; devono essere consegnate in minuti, non in giorni). è uno strumento chiave per monitorare le consegne e i potenziali problemi durante l’invio dei messaggi.
* Quando utilizzi [scaglioni](configure-and-send.md#sending-using-multiple-waves), verifica che ogni scaglione abbia tempo sufficiente per terminare prima che venga attivato il successivo.
* Verifica che il numero di errori e le nuove [quarantene](quarantines.md) siano coerenti con le altre consegne.
* Consulta attentamente i [registri di consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#delivery-logs-and-history){target="_blank"} per verificare il tipo di errori evidenziati (inserisce nell&#39;elenco Bloccati di, problemi DNS, regole anti-spam, ecc.).
