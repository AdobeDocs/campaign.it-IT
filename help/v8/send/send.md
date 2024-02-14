---
title: Inviare e monitorare le e-mail
description: Scopri l’ambito e le specificità dell’invio di e-mail con Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 84b90cbd150c81edc81f5cc653db6fbe96af80aa
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 2%

---


# Inviare e monitorare le e-mail  {#send-and-monitor-emails}

Quando la consegna è configurata e pronta per essere inviata, assicurati di aver eseguito l’analisi della consegna. [Ulteriori informazioni](delivery-analysis.md)

Al termine, conferma la consegna per avviare la consegna dei messaggi.

Monitora l’esecuzione della consegna da **Consegna** accessibile tramite i dettagli di questa consegna o tramite l’elenco delle consegne.

## Monitorare le e-mail {#email-monitoring}

Una volta inviato, controlla lo stato della consegna in **Dashboard di consegna** e accedere ai registri di consegna e ai rapporti per confermare che i messaggi sono stati inviati correttamente.

Dal dashboard di consegna, puoi controllare i messaggi elaborati e i registri di controllo della consegna. Puoi anche controllare lo stato dei messaggi nei registri di consegna.

>[!NOTE]
>
>Gli stati di consegna non vengono visualizzati in tempo reale. Ulteriori informazioni su Email Feedback Service [in questa sezione](#email-feedback-service).


![](../assets/do-not-localize/book.png) [Ulteriori informazioni sul monitoraggio della consegna nella documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target="_blank"}

## MTA della campagna {#mta}

Campaign v8 Mail Transfer Agent (MTA) fornisce un’infrastruttura di invio all’avanguardia che consente di migliorare il recapito messaggi, la reputazione, il throughput, il reporting, la gestione dei messaggi non recapitati, l’incremento graduale dell’IP e la gestione delle impostazioni di connessione.

Disponibile per tutti i clienti di Campaign v8, garantisce scalabilità, un elevato throughput di consegna e consente di inviare più e-mail più rapidamente. Ciò si ottiene con nuove tecniche di consegna adattiva che modificano le impostazioni di invio delle e-mail in tempo reale in base al feedback ricevuto dai provider di servizi Internet.

### Vantaggi

Adobe Campaign utilizza un Mail Transfer Agent (MTA) che esegue l’MTA dell’e-mail commerciale di SparkPost denominato **Momentum**.

Momentum rappresenta una tecnologia MTA innovativa e ad alte prestazioni che include una gestione dei messaggi non recapitati più intelligente e una funzionalità di ottimizzazione automatizzata della consegna dei messaggi che consente ai mittenti di raggiungere e mantenere tassi di consegna della casella in entrata ottimali.

* L’MTA consente un aumento massiccio della velocità di trasmissione complessiva e una riduzione significativa dei mancati recapiti non permanenti.
* Utilizza la tecnologia MTA più recente per fornire le velocità effettive ottimali per la consegna delle e-mail.
* Adattandosi istantaneamente e automaticamente al feedback ricevuto, garantisce inoltre una consegna delle e-mail più precisa e intelligente con dati in tempo reale.

### Qualificazione di mancato recapito

Per **sincrono** messaggi di errore di consegna, l’MTA determina il tipo di mancato recapito e la qualifica e invia nuovamente tali informazioni a Campaign.

L’MTA qualifica il mancato recapito SMTP e invia nuovamente tale qualifica a Campaign sotto forma di un codice di mancato recapito mappato su un motivo e una qualifica di mancato recapito della campagna.

>[!NOTE]
>
>Attualmente **asincrono** i mancati recapiti sono qualificati dal processo inMail attraverso **[!UICONTROL Inbound email]** regole.

Ulteriori informazioni sugli errori di consegna in [questa sezione](delivery-failures.md).


### Regole MX specifiche

Le regole MX (Mail eXchanger) sono le regole che gestiscono la comunicazione tra un server di invio e un server ricevente.

L’MTA dispone di proprie regole MX che gli consentono di personalizzare la velocità effettiva per dominio in base alla reputazione cronologica dell’e-mail e al feedback in tempo reale proveniente dai domini in cui stai inviando le e-mail.

### Firma DKIM

Domain Keys Identified Mail (DKIM) è un metodo di autenticazione utilizzato per rilevare indirizzi di mittente contraffatti (comunemente chiamato spoofing).

In Adobe Campaign, la firma di autenticazione dell’e-mail DKIM viene eseguita dall’MTA.

Ulteriori informazioni su DKIM in [Guida alle procedure consigliate per la consegna dei messaggi di Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target="_blank"}.

## Servizio di feedback delle e-mail {#email-feedback-service}

Il servizio di feedback delle e-mail di Campaign (EFS) segnala lo stato di ogni consegna e-mail inviata con Adobe Campaign.

Una volta iniziata la consegna, non vi è alcuna modifica nel **[!UICONTROL Success]** percentuale di inoltro del messaggio da Campaign all’MTA. I registri di consegna mostrano **[!UICONTROL Taken into account by the service provider]** stato per ogni indirizzo di destinazione.

Quando il messaggio viene effettivamente recapitato ai profili target e una volta che queste informazioni vengono segnalate in tempo reale dall’MTA, i registri di consegna mostrano **[!UICONTROL Sent]** stato di ogni indirizzo che ha ricevuto correttamente il messaggio. Il **[!UICONTROL Success]** la percentuale viene aumentata di conseguenza con ogni consegna riuscita.

Quando i messaggi non recapitabili vengono segnalati dall’MTA, lo stato del registro cambia da **[!UICONTROL Taken into account by the service provider]** a **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Quando i messaggi in soft-bouncing vengono segnalati dall’MTA, il loro stato di registro rimane invariato (**[!UICONTROL Taken into account by the service provider]**): solo il [motivo errore](delivery-failures.md#delivery-failure-reasons) è aggiornato<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. Il **[!UICONTROL Success]** La percentuale rimane invariata. I messaggi in mancati recapiti non permanenti vengono quindi ritentati durante la consegna [periodo di validità](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"}:

* Se un nuovo tentativo ha esito positivo prima della fine del periodo di validità, lo stato del messaggio cambia in **[!UICONTROL Sent]** e **[!UICONTROL Success]** la percentuale viene aumentata di conseguenza.

* In caso contrario, lo stato cambia in **[!UICONTROL Failed]**. Il **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->La percentuale rimane invariata.

>[!NOTE]
>
>Per ulteriori informazioni sui mancati recapiti non permanenti, consulta [questa sezione](delivery-failures.md#delivery-failure-reasons).
>
>Per ulteriori informazioni sui nuovi tentativi dopo un errore temporaneo di consegna, consulta [questa sezione](delivery-failures.md#retries).

La tabella seguente mostra come vengono aggiornati gli stati dei KPI e dei registri di invio in ogni fase del processo di invio.

| Passaggio nel processo di invio | Riepilogo KPI | Stato dei registri di invio |
|--- |--- |--- |
| Il messaggio è stato inoltrato correttamente da Campaign all’MTA | **[!UICONTROL Success]** percentuale non visualizzata (inizia da 0%) | Considerato dal fornitore di servizi |
| I messaggi non recapitabili vengono segnalati dall’MTA | Nessuna modifica in **[!UICONTROL Success]** percentuale | Non riuscito |
| I messaggi in soft-bouncing vengono segnalati dall’MTA | Nessuna modifica in **[!UICONTROL Success]** percentuale | Considerato dal fornitore di servizi |
| Nuovi tentativi di messaggi con mancati recapiti non permanenti riusciti | **[!UICONTROL Success]** la percentuale viene aumentata di conseguenza | Inviato |
| Nuovi tentativi di messaggi con mancati recapiti non riusciti | Nessuna modifica in **[!UICONTROL Success]** percentuale | Non riuscito |
