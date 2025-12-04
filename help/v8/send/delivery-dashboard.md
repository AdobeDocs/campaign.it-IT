---
title: Monitorare le consegne nell’interfaccia utente di Campaign
description: Scopri come accedere all’elenco delle consegne e utilizzare il dashboard di consegna per monitorare le consegne
feature: Monitoring
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 3%

---

# Monitorare le consegne nell’interfaccia utente di Campaign {#delivery-dashboard}

Il monitoraggio delle consegne è essenziale per garantire l’efficienza delle campagne e raggiungere i clienti. Adobe Campaign fornisce gli strumenti per accedere alle consegne e monitorarne le prestazioni tramite l’elenco delle consegne e il dashboard di consegna.

## Accedere all’elenco delle consegne {#list-of-deliveries}

Puoi accedere alle consegne dall’elenco di consegna tramite il nodo **[!UICONTROL Campaign Management > Deliveries]** della struttura.

![](assets/deliveries-list.png)

Per impostazione predefinita, l’elenco delle consegne contiene i nomi e gli stati delle consegne create nel nodo selezionato. Mostra anche il numero di messaggi da inviare, elaborati e inviati con successo.

* Il numero di **[!UICONTROL Messages to send]** corrisponde al numero di destinatari interessati dopo l&#39;analisi e prima della consegna.
* Il numero di messaggi nella colonna **[!UICONTROL Success]** corrisponde al numero di messaggi inviati dal server e ricevuti dai destinatari.
* Il numero di **[!UICONTROL Processed]** messaggi corrisponde al numero di messaggi ricevuti più il numero di messaggi con errori.

>[!NOTE]
>
>Per consegne di grandi dimensioni, potrebbe essere utile aggiornare questi valori. A questo scopo, seleziona la consegna in questione e fai clic con il pulsante destro del mouse su di essa. Selezionare **[!UICONTROL Action > Recompute delivery and tracking indicators...]**, quindi utilizzare l&#39;assistente per aggiornare queste informazioni.

## Panoramica del dashboard di consegna {#delivery-dashboard-overview}

Il **dashboard di consegna** è fondamentale per monitorare le consegne e gli eventuali problemi rilevati durante l&#39;invio dei messaggi.

Ti consente di recuperare informazioni su una consegna e modificarle, se necessario. Tieni presente che il contenuto delle schede non può più essere modificato una volta inviata la consegna.

Di seguito sono riportate le informazioni che è possibile monitorare utilizzando le diverse schede disponibili nel dashboard:

* [Riepilogo della consegna](#delivery-summary)
* [Rapporti sulle consegne](#delivery-reports)
* [Registri di consegna, pagine mirror, esclusioni](#delivery-logs-and-history)
* [Registri e cronologia di tracciamento delle consegne](#tracking-logs)
* [Rendering consegna](#delivery-rendering)
* [Audit della consegna](#delivery-audit-)

![](assets/s_ncs_user_del_details.png)

**Argomenti correlati:**

* [Errori di consegna](delivery-failures.md)
* [Gestione della quarantena](quarantines.md)
* [Best practice per la consegna](../start/delivery-best-practices.md)
* [Gestione del recapito messaggi](about-deliverability.md)

## Riepilogo della consegna {#delivery-summary}

La scheda **[!UICONTROL Summary]** contiene le caratteristiche della consegna: stato della consegna, canale utilizzato, informazioni sul mittente, oggetto e informazioni sull&#39;esecuzione.

## Rapporti sulle consegne {#delivery-reports}

Il collegamento **[!UICONTROL Reports]**, accessibile dalla scheda **[!UICONTROL Summary]**, consente di esaminare una serie di rapporti relativi all&#39;azione di consegna: report di consegna generale, report dettagliato, report di consegna, distribuzione dei messaggi non riusciti, tasso di apertura, clic e transazioni, ecc.

Il contenuto di questa scheda può essere configurato in base alle tue esigenze. Per ulteriori informazioni sui report di consegna, consulta [questa sezione](../reporting/delivery-reports.md).

![](assets/delivery-report.png)

## Registri di consegna, cronologia ed esclusioni {#delivery-logs-and-history}

La scheda **[!UICONTROL Delivery]** fornisce una cronologia delle occorrenze in questa consegna. Contiene i registri di consegna, ovvero l’elenco dei messaggi inviati e il loro stato e i messaggi associati.

Per una consegna, puoi visualizzare (ad esempio) solo i destinatari con una consegna non riuscita o un indirizzo in quarantena. A tale scopo, fare clic sul pulsante **[!UICONTROL Filters]** e selezionare **[!UICONTROL By state]**. Quindi seleziona lo stato nell’elenco a discesa. Nella pagina [stati di consegna](delivery-statuses.md) sono elencati diversi stati.

>[!NOTE]
>
>L’elenco che mostra i registri di consegna può essere personalizzato, come qualsiasi altro elenco in Campaign. Ad esempio, puoi aggiungere una colonna per individuare l’indirizzo IP che ha inviato ogni e-mail di una consegna. Per ulteriori informazioni sulla configurazione della visualizzazione degli elenchi, consulta [questa sezione](../config/ui-settings.md#customize-lists).

![](assets/s_ncs_user_delivery_delivery_tab.png)

Il collegamento **[!UICONTROL Display the mirror page for this message...]** ti consente di visualizzare in una nuova finestra la pagina speculare per il contenuto della consegna selezionata dall&#39;elenco.

La pagina speculare è disponibile solo per le consegne per le quali è stato definito il contenuto di HTML. Per ulteriori informazioni, consulta [Collegamento alla pagina mirror](mirror-page.md).

![](assets/s_ncs_user_wizard_miror_page_link.png)

## Registri e cronologia di tracciamento delle consegne {#tracking-logs}

La scheda **[!UICONTROL Tracking]** elenca la cronologia di tracciamento per questa consegna. In questa scheda vengono visualizzati i dati di tracciamento per i messaggi inviati, ovvero tutti gli URL soggetti a tracciamento da parte di Adobe Campaign. I dati di tracciamento vengono aggiornati ogni ora.

>[!NOTE]
>
>Se il tracciamento non è abilitato per una consegna, questa scheda non viene visualizzata.

La configurazione del tracciamento viene eseguita nella fase appropriata nell’assistente alla consegna. Consulta [Come configurare i collegamenti tracciati](tracking.md).

I dati di **[!UICONTROL Tracking]** vengono interpretati nei report di consegna. Consulta [questa sezione](../reporting/delivery-reports.md).

![](assets/s_ncs_user_delivery_tracking_tab.png)

## Rendering della casella in entrata {#delivery-rendering}

La scheda **[!UICONTROL Inbox rendering]** consente di visualizzare in anteprima il messaggio nei diversi contesti in cui può essere ricevuto e di verificare la compatibilità nei desktop e nelle applicazioni principali.

In questo modo, puoi assicurarti che il messaggio venga visualizzato ai destinatari in modo ottimale su diversi client web, servizi di posta sul web e dispositivi.

Per ulteriori informazioni sul rendering della casella in entrata, consulta [questa pagina](inbox-rendering.md)


## Audit della consegna {#delivery-audit-}

La scheda **[!UICONTROL Audit]** contiene il registro di consegna e tutti i messaggi relativi alle bozze.

Il pulsante **[!UICONTROL Refresh]** consente di aggiornare i dati. Utilizzare il pulsante **[!UICONTROL Filters]** per definire un filtro per i dati.

Icone speciali consentono di identificare errori o avvisi. Consulta [Analisi della consegna](delivery-analysis.md).

La scheda secondaria **[!UICONTROL Proofs]** ti consente di visualizzare l&#39;elenco delle bozze che sono state inviate.

![](assets/s_ncs_user_delivery_log_tab.png)

È possibile modificare le informazioni visualizzate in questa finestra (e quelle delle schede **[!UICONTROL Delivery]** e **[!UICONTROL Tracking]**) selezionando le colonne da visualizzare. A tale scopo, fare clic sull&#39;icona **[!UICONTROL Configure list]** situata nell&#39;angolo inferiore destro. Per ulteriori informazioni sulla configurazione della visualizzazione degli elenchi, consulta [questa sezione](../config/ui-settings.md#customize-lists).

## Sincronizzazione del dashboard di consegna {#delivery-dashboard-synchronization}

Dal dashboard di consegna, controlla i messaggi elaborati e i registri di consegna per assicurarti che la consegna sia stata inviata correttamente.

Alcuni indicatori o stato possono essere errati o non aggiornati, e questo problema può essere risolto con le seguenti soluzioni:

* Se lo stato della consegna non è corretto, verificare che tutte le approvazioni necessarie siano state completate per la consegna o che i flussi di lavoro tecnici **[!UICONTROL operationMgt]** e **[!UICONTROL deliveryMgt]** siano in esecuzione senza errori.

* Se il contatore di consegna non corrisponde alla consegna, prova a ricalcolare gli indicatori facendo clic con il pulsante destro del mouse sulla consegna pertinente in Adobe Campaign Explorer e selezionando **[!UICONTROL Actions]** > **[!UICONTROL Recompute delivery and tracking indicators]** per la risincronizzazione. Per ulteriori informazioni sugli indicatori di tracciamento, consulta questa [sezione](../reporting/delivery-reports.md#tracking-indicators).

Puoi anche tenere traccia delle consegne con diversi rapporti tramite il dashboard di consegna. Per ulteriori informazioni, consulta questa [sezione](../reporting/delivery-reports.md).

>[!NOTE]
>
>In qualità di utente di Campaign v8 Managed Cloud Services, l’infrastruttura è monitorata e gestita da Adobe. Se riscontri problemi persistenti con gli indicatori di consegna o la sincronizzazione della dashboard, contatta l’Assistenza clienti di Adobe.

## Risoluzione dei problemi di consegne lente {#troubleshooting-slow-deliveries}

Se la consegna sembra richiedere più tempo del solito dopo aver fatto clic sul pulsante **[!UICONTROL Send]**, verifica le seguenti possibili cause:

### Problemi di reputazione dell’indirizzo IP

Alcuni provider di posta elettronica potrebbero aver aggiunto i tuoi indirizzi IP a un inserisco nell&#39;elenco Bloccati di. Controlla i registri di consegna (broadLog) nella scheda **[!UICONTROL Delivery]** per i messaggi di mancato recapito che indicano problemi di reputazione. Consulta la sezione [monitoraggio del recapito messaggi](monitoring-deliverability.md) per informazioni sulla gestione della reputazione.

### Dimensioni e complessità della consegna

La consegna potrebbe essere troppo grande per essere elaborata rapidamente. Ciò può verificarsi con:

Personalizzazione JavaScript intensa che richiede un’elaborazione significativa dei dati per ogni destinatario.

Consegna con peso superiore a 60 kilobyte a causa di contenuti HTML di grandi dimensioni, immagini incorporate o ampia personalizzazione.

Per informazioni sulle linee guida per i contenuti e sulle best practice per la personalizzazione, consulta [Best practice per la consegna](../start/delivery-best-practices.md). La dimensione massima consigliata è di circa 35 KB per prestazioni ottimali.

### Prestazioni del sistema

I problemi di sistema possono impedire ai server di elaborare le consegne in modo efficiente. Se sospetti problemi di prestazioni, controlla i registri di consegna per individuare eventuali errori di timeout o problemi di comunicazione.

>[!NOTE]
>
>In qualità di utente di Campaign v8 Managed Cloud Services, il monitoraggio dell’infrastruttura server è gestito da Adobe. Se riscontri problemi persistenti di prestazioni con l’invio della consegna, contatta l’Assistenza clienti Adobe con i registri di consegna.

