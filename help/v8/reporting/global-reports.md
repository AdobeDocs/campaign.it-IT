---
title: Rapporti globali di Adobe Campaign
description: Scopri come accedere e utilizzare i rapporti globali
feature: Reporting, Monitoring
exl-id: 6e3409d8-86bd-44ba-a40d-10287f53a960
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '1763'
ht-degree: 10%

---

# Rapporti globali {#global-reports}

Tali relazioni riguardano l&#39;attività dei dati nell&#39;intero database. Per visualizzare il dashboard dei rapporti, vai al **[!UICONTROL Reports]** scheda.

![](assets/reports-tab.png)

Per visualizzare i rapporti, fai clic sui relativi nomi. Per impostazione predefinita sono disponibili i seguenti rapporti:

![](assets/report-global-list.png)

>[!NOTE]
>
>Questa sezione mostra solo i rapporti collegati alle consegne.

* **[!UICONTROL Delivery throughput]** : fai riferimento a [Velocità effettiva di consegna](#delivery-throughput).
* **[!UICONTROL Browsers]** : fai riferimento a [Browser](#browsers).
* **[!UICONTROL Sharing to social networks]** : fai riferimento a [Condivisione sui social network](#sharing-to-social-networks).
* **[!UICONTROL Statistics on sharing activities]** : fai riferimento a [Statistiche sulla condivisione delle attività](#statistics-on-sharing-activities).
* **[!UICONTROL Operating systems]** : fai riferimento a [Sistemi operativi](#operating-systems).
* **[!UICONTROL URLs and click streams]** : fai riferimento a [URL e flussi di clic](delivery-reports.md#urls-and-click-streams).
* **[!UICONTROL Tracking indicators]** : fai riferimento a [Indicatori di tracciamento](delivery-reports.md#tracking-indicators).
* **[!UICONTROL Non-deliverables and bounces]** : fai riferimento a [Non consegnabili e mancati recapiti](#non-deliverables-and-bounces).
* **[!UICONTROL User activities]** : fai riferimento a [Attività degli utenti](#user-activities).
* **[!UICONTROL Subscription tracking]** : fai riferimento a [Tracciamento abbonamento](#subscription-tracking).
* **[!UICONTROL Delivery summary]** : fai riferimento a [Riepilogo delle consegne](delivery-reports.md#delivery-summary).
* **[!UICONTROL Delivery statistics]** : fai riferimento a [Statistiche consegna](#delivery-statistics).
* **[!UICONTROL Breakdown of opens]** : fai riferimento a [Raggruppamento delle aperture](#breakdown-of-opens).

## Velocità effettiva di consegna {#delivery-throughput}

Questo rapporto contiene informazioni sulla velocità effettiva di consegna dell’intera piattaforma per un determinato periodo. I criteri utilizzati per misurare la velocità con cui vengono consegnati i messaggi comprendono il numero di messaggi inviati all’ora e le dimensioni dei messaggi (in bit al secondo). Nell’esempio seguente, il primo grafico mostra le consegne riuscite in blu e il numero di consegne con errori in arancione.

![](assets/report-toolbar.png)

Puoi configurare i valori visualizzati modificando la scala cronologica: visualizzazione a 1 ora, visualizzazione a 3 ore, visualizzazione a 24 ore, ecc. Fai clic su **[!UICONTROL Refresh]** per confermare la selezione.

>[!NOTE]
>
>Puoi anche monitorare il numero di consegne inviate all’ora utilizzando [Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/sftp-storage-management.html).
>
>Il Pannello di controllo è accessibile a tutti gli utenti amministratori. I passaggi per concedere a un utente l’accesso come amministratore sono descritti in[questa pagina](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=it#discover-control-panel).
>

## Attività degli utenti {#user-activities}

Questo rapporto mostra il raggruppamento di aperture, clic e transazioni per mezz’ora, ora o giorno, sotto forma di un grafico.

Sono disponibili le seguenti opzioni:

* **[!UICONTROL Opens]** : numero totale di messaggi aperti. Le e-mail in formato testo non vengono prese in considerazione. [Ulteriori informazioni](metrics-calculation.md#tracking-opens-).
* **[!UICONTROL Clicks]** : numero totale di clic sui collegamenti nelle consegne. I clic sui collegamenti di annullamento dell’abbonamento e sulle pagine mirror non vengono presi in considerazione.
<!--
* **[!UICONTROL Transactions]** : Total number of transactions after a message is received. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
-->

## Messaggi non recapitabili e mancati recapiti {#non-deliverables-and-bounces}

Questo rapporto mostra il raggruppamento dei messaggi non recapitati e dei messaggi non recapitati per dominio Internet.

Il **[!UICONTROL Number of messages processed]** rappresenta il numero totale di messaggi elaborati dal server di consegna. Questo valore è inferiore al numero di messaggi da consegnare quando alcune consegne sono state interrotte o sospese (prima di essere elaborate dal server).

**[!UICONTROL Breakdown of errors by type]**

>[!NOTE]
>
>Gli errori inclusi in questo rapporto attivano il processo di quarantena. Per ulteriori informazioni sulla gestione della quarantena, consulta [Gestione della quarantena](../send/quarantines.md).

La prima sezione di questo rapporto mostra la suddivisione dei messaggi non recapitati sotto forma di tabella di valori e di grafico.

Per ogni tipo di errore, sono disponibili:

* il numero di messaggi di errore di questo tipo,
* la percentuale di messaggi con errori di questo tipo rispetto al numero totale di messaggi con errori,
* percentuale di messaggi di errore di questo tipo rispetto al numero totale di messaggi elaborati.

Sono utilizzati i seguenti indicatori:

* **[!UICONTROL User unknown]** : tipo di errore generato durante la consegna per indicare che l’indirizzo e-mail non è valido.
* **[!UICONTROL Invalid domain]** : tipo di errore generato durante l’invio di una consegna per indicare che il dominio dell’indirizzo e-mail è errato o non esiste.
* **[!UICONTROL Inbox full]** : tipo di errore generato dopo cinque tentativi di consegna per indicare che la casella in entrata dei destinatari contiene troppi messaggi.
* **[!UICONTROL Account disabled]** : tipo di errore generato durante l’invio di una consegna per indicare che l’indirizzo non esiste più.
* **[!UICONTROL Rejected]** : tipo di errore generato quando un indirizzo viene rifiutato da IAP (Internet Access Provider), ad esempio in seguito all’applicazione di una regola di sicurezza (software anti-spam).
* **[!UICONTROL Unreachable]** : tipo di errore che si verifica nella stringa di distribuzione del messaggio: incidente sull’inoltro SMTP, dominio temporaneamente non raggiungibile, ecc.
* **[!UICONTROL Not connected]** : tipo di errore per indicare che il telefono cellulare del destinatario è spento o disconnesso dalla rete al momento dell’invio.

  >[!NOTE]
  >
  >Questo indicatore si riferisce alle consegne il [canali mobili](../send/send.md) solo.

  È possibile aprire ogni riga della tabella dei valori facendo clic sul pulsante `[+]` simbolo. Per ogni tipo di errore, puoi visualizzare la suddivisione dei messaggi di errore per dominio.

**[!UICONTROL Breakdown of errors per domain]**

La seconda sezione di questo rapporto mostra la suddivisione degli errori per dominio Internet sotto forma di tabella di valori e grafico.

Per ogni nome di dominio, abbiamo:

* il numero di messaggi con errori per questo dominio,
* la percentuale di messaggi con errori per questo dominio rispetto al numero totale di messaggi elaborati per questo dominio,
* la percentuale di messaggi di errore per questo dominio rispetto al numero totale di messaggi di errore.

È possibile aprire ogni riga della tabella dei valori facendo clic sul pulsante [+] simbolo. Per ogni tipo di dominio, puoi visualizzare la suddivisione dei messaggi di errore per tipo.

![](assets/errors-report-details.png)

>[!NOTE]
>
>I nomi di dominio visualizzati in questo report sono definiti a livello di cubo. Per modificare questi valori, modificare il **[!UICONTROL Delivery logs (broadlogrcp)]** cubo. Per ulteriori informazioni al riguardo, consulta [questa sezione](gs-cubes.md). Il **[!UICONTROL Others]** categoria include i nomi di dominio che non appartengono a una classe specifica.

## Browser {#browsers}

Questo rapporto mostra il raggruppamento dei browser Internet utilizzati dai destinatari della consegna per il periodo in questione.

>[!NOTE]
>
>I valori mostrati in questo rapporto sono stime: verranno presi in considerazione solo i destinatari che hanno fatto clic in una consegna.

**Statistiche globali**

Le statistiche globali sull’utilizzo del browser sono presentate sotto forma di tabella di valori e di grafico.

![](assets/browser-report.png)

Sono utilizzati i seguenti indicatori:

* **[!UICONTROL Visitors]** : numero totale di destinatari target (per browser Internet) che hanno fatto clic almeno una volta su una consegna.
* **[!UICONTROL Pages viewed]** : numero totale di clic sui collegamenti in una consegna (per browser Internet) per tutte le consegne.
* **[!UICONTROL Usage rate]** : questo tasso rappresenta la suddivisione dei visitatori (per browser Internet) in relazione al numero totale di visitatori.

**Statistiche per browser**

Nella tabella dei valori delle statistiche globali, puoi fare clic sul nome di ogni browser per visualizzarne le statistiche di utilizzo.

![](assets/browser-report-info.png)

Le statistiche sono presentate sotto forma di curva, grafico e tabella di valori.

Il **[!UICONTROL History]** rappresenta la frequenza giornaliera di questo browser. Il tasso è il rapporto tra il numero di visitatori al giorno (in questo browser) e il numero di visitatori misurato nel giorno con il tasso di partecipazione più elevato.

Il **[!UICONTROL Breakdown per version]** il grafico rappresenta il raggruppamento dei visitatori per versione rispetto al numero totale di visitatori (in questo browser).

La tabella dei valori utilizza i seguenti indicatori:

* **[!UICONTROL Global rate]** : questo tasso rappresenta il raggruppamento dei visitatori per versione rispetto al numero totale di visitatori (su tutti i browser).
* **[!UICONTROL Relative rate]** : questo tasso rappresenta il raggruppamento dei visitatori per versione rispetto al numero totale di visitatori (in questo browser).


<!--
### Sharing to social networks {#sharing-to-social-networks}

Viral marketing lets delivery recipients share information with their contact network: they can add a link to their profile (Facebook, Twitter, etc.) or send a message to a friend. Each share and each access to shared information is tracked within the delivery. For more information on viral marketing, refer to [this section](../../delivery/using/viral-and-social-marketing.md).

This report shows the breakdown of shared and opened messages per social network (Facebook, Twitter, etc.) and/or per email.

![](assets/s_ncs_user_social_report.png)

**[!UICONTROL Email delivery statistics]**

In the email delivery statistics, two values are displayed:

* **[!UICONTROL Number of messages to be delivered]** : Total number of messages processed during delivery analysis.
* **[!UICONTROL Number of successful deliveries]** : Number of messages processed successfully.

**[!UICONTROL Sharing activities and mail open statistics]**

The central table shows the statistics on email shares and opens.

In the **[!UICONTROL Shares]** column, we have the following indicators:

* **[!UICONTROL No. of sharing activities]** : Total number of messages shared on each social network. This value equals the total number of clicks on the icon of the matching **[!UICONTROL Links for sharing to social networks]** personalization block.
* **[!UICONTROL Breakdown]** : This rate represents the breakdown of shares per social network, in relation to the total number of shares.
* **[!UICONTROL Sharing rate]** : This rate represents the breakdown of shares per social network, in relation to the number of messages to be delivered.

In the **[!UICONTROL Opens]** column, we have the following indicators:

* **[!UICONTROL No. of opens]** : Total number of messages opened by people whom the message was forwarded to (via the **[!UICONTROL Links for sharing to social networks]** personalization block). This value equals the number of times the mirror page was displayed. Opens by delivery recipients are not taken into account.
* **[!UICONTROL Breakdown]** : This rate represents the breakdown of opens per social network, in relation to the total number of opens.
* **[!UICONTROL Rate of opens]** : This rate represents the breakdown of opens per social network, in relation to the total number of shares.

**[!UICONTROL Breakdown of sharing activities and opens]**

This section includes two charts which represent the breakdown of sharing activities and opens per social network.


## Statistics on sharing activities {#statistics-on-sharing-activities}

This report shows the evolution of shares to social media in time.

For more information on viral marketing, refer to [this section](../../delivery/using/viral-and-social-marketing.md).

Statistics are presented in the form of a table of values and a chart.

The following indicators are used:

* **[!UICONTROL New contacts]** : Number of new subscriptions following the reception of a message shared via email. This value matches the number of people who received a message shared via email, clicked the **[!UICONTROL Subscription link]** and filled in the subscription form. 
* **[!UICONTROL Opens]** : Total number of messages opened by people whom the message was transferred to (via the **[!UICONTROL Link for sharing to social networks]** personalization block). This value equals the number of times the mirror page was displayed. Opens by delivery recipients are not taken into account.
* **[!UICONTROL Sharing activities]** : Total number of messages shared via social networks. This value matches the total number of clicks on the icon of the **[!UICONTROL Links for sharing to social networks]** personalization block.
-->

## Sistemi operativi {#operating-systems}

Questo rapporto mostra la suddivisione dei sistemi operativi utilizzati dai destinatari delle consegne per il periodo in questione.

>[!NOTE]
>
>I valori mostrati in questo rapporto sono stime: verranno presi in considerazione solo i destinatari che hanno fatto clic in una consegna.

**Statistiche globali**

Le statistiche di utilizzo globali dei sistemi operativi vengono presentate sotto forma di tabella di valori e di grafico.

![](assets/os-report.png)

Sono utilizzati i seguenti indicatori:

* **[!UICONTROL Visitors]** : media giornaliera del numero totale di destinatari target (per sistema operativo) che hanno fatto clic almeno una volta in una consegna.
* **[!UICONTROL Pages viewed]** : media giornaliera del numero totale di clic sui collegamenti di consegna (per sistema operativo) per tutte le consegne.
* **[!UICONTROL Rate of use]** : questo tasso rappresenta la suddivisione dei visitatori (per sistema operativo) in relazione al numero totale di visitatori.

**Statistiche per sistema operativo**

Nella tabella dei valori delle statistiche globali fare clic sul nome di ogni sistema operativo per visualizzare le statistiche per sistema operativo.

![](assets/os-report-details.png)

Le statistiche sono presentate sotto forma di curva, grafico e tabella di valori.

Il **[!UICONTROL History]** La curva rappresenta il tasso di utilizzo giornaliero del sistema operativo. Questo tasso è il rapporto tra il numero di visitatori al giorno (in questo sistema operativo) e il numero di visitatori misurato nel giorno con la partecipazione più elevata.

Il **[!UICONTROL Breakdown by version]** il grafico rappresenta il raggruppamento dei visitatori per versione in relazione al numero totale di visitatori su questo sistema operativo.

La tabella dei valori utilizza i seguenti indicatori:

* **[!UICONTROL Global rate]** : questo tasso rappresenta la suddivisione dei visitatori (per versione) in relazione al numero totale di visitatori in tutti i sistemi operativi.
* **[!UICONTROL Relative rate]** : questo tasso rappresenta la suddivisione dei visitatori (per versione) in relazione al numero totale di visitatori per questo sistema operativo.

## Tracciamento abbonamento {#subscription-tracking}

Questo report consente di monitorare gli abbonamenti ai servizi di informazione. Mostra gli abbonamenti e il loro annullamento.

![](assets/service-report.png)

Per visualizzarlo per un abbonamento, fai clic sul pulsante **[!UICONTROL Profiles and targets > Services and subscriptions]** della home page o dell&#39;explorer. Selezionare l&#39;abbonamento desiderato, quindi fare clic su **[!UICONTROL Reports]** scheda. Il **[!UICONTROL Subscriptions tracking]** è disponibile per impostazione predefinita. Ti consente di visualizzare le tendenze di abbonamento e annullamento dell’abbonamento e il tasso di fedeltà in un periodo. Puoi configurare la rappresentazione di questi dati tramite l’elenco a discesa. Clic **[!UICONTROL Refresh]** per convalidare la configurazione selezionata.

Per ulteriori informazioni, fare riferimento a [questa pagina](../start/subscriptions.md).

Il **[!UICONTROL Number subscribed to date]** rappresenta il numero totale di persone attualmente abbonate.

**[!UICONTROL Overall evolution of subscriptions]**

La tabella dei valori utilizza i seguenti indicatori:

* **[!UICONTROL Subscribers]** : numero totale di abbonati per il periodo in questione.
* **[!UICONTROL Subscriptions]** : numero di abbonamenti per il periodo in questione.
* **[!UICONTROL Unsubscriptions]** : numero di annullamenti di abbonamenti per il periodo in questione.
* **[!UICONTROL Evolution]** : numero di annullamenti di abbonamenti meno il numero di abbonamenti. La tariffa viene calcolata in base al numero totale di abbonati.
* **[!UICONTROL Loyalty]** : tasso di fedeltà degli abbonati per il periodo in questione.

**[!UICONTROL Subscription evolution curves]**

Questo grafico mostra l’evoluzione degli abbonamenti e dei loro annullamenti per il periodo in questione.

## Statistiche consegna {#delivery-statistics}

Questo rapporto mostra la suddivisione per dominio Internet di tutti i messaggi elaborati e inviati, di mancati recapiti permanenti e non permanenti, aperture, clic e annullamenti di abbonamenti.

![](assets/broadcast-report.png)

Sono utilizzati i seguenti indicatori:

* **[!UICONTROL Emails processed]** : numero totale di messaggi elaborati dal server di consegna.
* **[!UICONTROL Delivered]** : percentuale del numero di messaggi elaborati correttamente rispetto al numero totale di messaggi elaborati.
* **[!UICONTROL Hard bounces]** : percentuale del numero di mancati recapiti &quot;permanenti&quot; rispetto al numero totale di messaggi elaborati.
* **[!UICONTROL Soft bounces]** : percentuale del numero di mancati recapiti &quot;non permanenti&quot; rispetto al numero totale di messaggi elaborati.

  >[!NOTE]
  >
  >Per ulteriori informazioni sui mancati recapiti permanenti e non permanenti, consulta [questa pagina](../send/quarantines.md).

* **[!UICONTROL Opens]** : percentuale del numero di destinatari che hanno aperto un messaggio almeno una volta rispetto al numero di messaggi elaborati correttamente.
* **[!UICONTROL Clicks]** : percentuale del numero di persone che hanno fatto clic su una consegna almeno una volta rispetto al numero di messaggi elaborati correttamente.
* **[!UICONTROL Unsubscription]** : percentuale del numero di clic su un collegamento di annullamento dell’abbonamento rispetto al numero di messaggi elaborati correttamente.

## Raggruppamenti delle aperture {#breakdown-of-opens}

Raggruppamenti delle aperture: questo rapporto mostra le aperture raggruppate per sistema operativo, dispositivo e browser per il periodo in questione. Per ogni categoria vengono utilizzati due grafici. Il primo visualizza le statistiche relative all’apertura su un computer e dispositivi mobili. Il secondo visualizza le statistiche relative solo all’apertura su dispositivi mobili.

Il numero di aperture corrisponde al numero totale di messaggi aperti. Le e-mail in formato testo non vengono conteggiate. Per ulteriori informazioni sulle aperture di tracciamento, consulta [questa sezione](metrics-calculation.md#tracking-opens-).

![](assets/user-agent-report.png)

>[!NOTE]
>
>I nomi del browser e del sistema operativo costituiscono parte delle informazioni inviate dall’agente utente del browser a cui è stato aperto il messaggio. Adobe Campaign deduce il tipo di dispositivo utilizzando le relative informazioni sul dispositivo.
