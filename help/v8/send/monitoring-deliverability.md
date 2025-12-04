---
product: campaign
title: Monitorare il recapito messaggi in Adobe Campaign
description: Scopri gli strumenti e le linee guida per il monitoraggio del recapito messaggi in Adobe Campaign
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 3dd4f6041ef193a0d7ea74a0b2c06183861c2797
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 3%

---

# Monitorare il recapito messaggi{#monitoring-deliverability}

Di seguito trovi i dettagli sui diversi strumenti di monitoraggio forniti da Adobe Campaign, nonché alcune linee guida aggiuntive sull’utilizzo delle funzioni offerte da Adobe Campaign per monitorare il recapito messaggi della piattaforma.

## Strumenti di monitoraggio {#monitoring-tools}

Adobe Campaign consente di accedere agli strumenti di consegna dei messaggi elencati di seguito.

### Rendering della casella in entrata {#inbox-rendering-tool}

Il report di rendering della [Posta in arrivo](inbox-rendering.md) consente di visualizzare l&#39;anteprima dei messaggi sui principali client di posta elettronica per esaminare il contenuto e la reputazione.

### Velocità di consegna {#throughput-reports}

Il report **[!UICONTROL Delivery throughput]** offre una panoramica della velocità effettiva dell&#39;intera piattaforma per un determinato periodo. Per ulteriori informazioni, consulta [questa sezione](../reporting/global-reports.md#delivery-throughput).

### Statistiche di trasmissione {#broadcast-statistics}

Ogni consegna genera un rapporto sulle statistiche di trasmissione per i diversi provider di servizi Internet (ISP). Mostra alcune metriche relative alla qualità dei dati e alla reputazione che possono influire sul recapito messaggi, tra cui i seguenti numeri:

**[!UICONTROL Hard bounces]** indica la qualità dei dati. Questo numero deve essere inferiore al 2%.

**[!UICONTROL Soft bounces]** indicare la reputazione. Questo numero non deve essere superiore al 10% per un dato ISP.

<!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

### Dashboard delle consegne {#delivery-dashboard-monitoring}

Più in generale, il [dashboard di consegna](delivery-dashboard.md) ti consente di accedere a:

Il riepilogo della consegna, che mostra i dettagli dell’invio e il numero di messaggi da inviare, elaborati e inviati con successo.

I registri di consegna e la cronologia, che mostrano quale target è stato escluso e perché.

I registri di tracciamento, che mostrano informazioni di tracciamento come aperture e clic.

### Test di SpamAssassin {#spam-testing}

Utilizza [SpamAssassin](spamassassin.md) per testare il contenuto delle e-mail e assegnargli un punteggio per determinare se un messaggio corre il rischio di essere considerato come spam dagli strumenti anti-spam utilizzati al momento della ricezione.

### Pannello di controllo {#control-panel-monitoring}

>[!NOTE]
>
>Il Pannello di controllo Campaign è disponibile per gli utenti di Campaign v8 Managed Cloud Services. Ulteriori informazioni su [Pannello di controllo Campaign](../config/self-service.md).

Il [Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it){target="_blank"} di Campaign fornisce funzionalità di monitoraggio per il recapito messaggi, tra cui la gestione dei sottodomini e dei certificati, il monitoraggio dei profili attivi e le metriche della velocità effettiva e della latenza di consegna.

## Linee guida per il monitoraggio {#monitoring-guidelines}

Di seguito sono riportate alcune linee guida aggiuntive sul monitoraggio della consegna dei messaggi:

### Monitoraggio della velocità effettiva della piattaforma

Controlla regolarmente la [velocità effettiva di consegna](../reporting/global-reports.md#delivery-throughput) per l&#39;intera piattaforma per verificare se è coerente con la configurazione originale.

### Ritenta configurazione

Verifica che [nuovi tentativi](delivery-failures.md#retries) siano configurati correttamente (30 minuti per il periodo di esecuzione dei nuovi tentativi e più di 20 tentativi) nei modelli di consegna.

### Verifica cassetta postale di mancato recapito

Verificare regolarmente che la cassetta postale [bounce](delivery-failures.md#bounce-mail-qualification) sia accessibile e che l&#39;account non stia per scadere.

### Controlli delle prestazioni della consegna

Controlla ogni velocità effettiva di consegna, accessibile dal [dashboard di consegna](delivery-dashboard.md), per assicurarti che sia coerente con la validità del contenuto della consegna (ad esempio, le &quot;vendite flash&quot; devono essere consegnate in minuti, non in giorni).

### Convalida intervalli ondate

Quando utilizzi [scaglioni](configure-and-send.md#sending-using-multiple-waves), verifica che ogni scaglione abbia tempo sufficiente per terminare prima che venga attivato il successivo.

### Monitoraggio della quarantena

Verifica che il numero di errori e le nuove [quarantene](quarantines.md) siano coerenti con le altre consegne.

### Analisi del registro di consegna

Consulta attentamente i [registri di consegna](delivery-dashboard.md#delivery-logs-and-history) per verificare il tipo di errori evidenziati (inserisce nell&#39;elenco Bloccati di, problemi DNS, regole anti-spam, ecc.).

## Argomenti correlati

La [Guida alle procedure consigliate per il recapito messaggi di Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=it){target="_blank"} fornisce indicazioni complete su strategia, definizione, metriche e best practice per il recapito messaggi.

[Che cos&#39;è il recapito messaggi](about-deliverability.md) introduce i concetti chiave per il recapito messaggi e come migliorare il tasso di recapito messaggi in Campaign.

[Errori di consegna e mancati recapiti](delivery-failures.md) descrive i diversi tipi di errori di consegna e il modo in cui Campaign li gestisce; include indicazioni per la risoluzione dei problemi comuni.

[Gestione della quarantena](quarantines.md) spiega come Campaign gestisce gli indirizzi messi in quarantena per proteggere la reputazione di invio.

[Controlla il contenuto del messaggio](control-message-content.md) fornisce indicazioni su come garantire che il contenuto sia ottimizzato per il recapito messaggi.
