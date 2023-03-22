---
title: Inviare e-mail e monitorarle
description: Scopri l’ambito e le specificità dell’invio di e-mail con Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 4c79078e32c77499f15906fc81f31ce2b26559d7
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 3%

---


# Inviare e-mail e monitorarle

Una volta configurata la consegna e pronta per l’invio, assicurati di aver eseguito l’analisi della consegna. [Ulteriori informazioni](delivery-analysis.md)

Al termine, conferma la consegna per avviare la consegna dei messaggi.

Monitora l’esecuzione della consegna dal **Consegna** , accessibile tramite i dettagli di questa consegna o tramite l’elenco delle consegne.

## Monitorare le e-mail

Una volta inviata, controlla lo stato di consegna nel Dashboard di consegna e accedi ai registri di consegna e ai rapporti per confermare che i messaggi sono stati inviati correttamente.

![](../assets/do-not-localize/book.png) [Ulteriori informazioni sono disponibili nella documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target="_blank"}


## MTA campagna {#mta}

Campaign v8 Mail Transfer Agent (MTA) fornisce un’infrastruttura di invio all’avanguardia che consente un recapito ottimale, reputazione, velocità effettiva, reporting, gestione dei messaggi non recapitati, configurazione dell’IP e gestione delle impostazioni di connessione.

Disponibile per tutti i clienti di Campaign v8, garantisce scalabilità, un throughput di consegna elevato e consente di inviare più e-mail più rapidamente. Questo si ottiene con nuove tecniche di consegna adattiva che modificano le impostazioni di invio delle e-mail in tempo reale in base al feedback ricevuto dai provider di servizi Internet.

### Vantaggi

Adobe Campaign utilizza un agente di trasferimento della posta (MTA) che esegue l’e-mail commerciale MTA di SparkPost denominata **Momento**.

Momentum rappresenta una tecnologia MTA innovativa e ad alte prestazioni che include una gestione più intelligente dei messaggi non recapitati e una funzionalità di ottimizzazione automatizzata dei messaggi che aiuta i mittenti a raggiungere e mantenere tassi di consegna ottimali nella casella in entrata.

* L&#39;MTA consente un massiccio aumento della velocità effettiva complessiva e una significativa riduzione dei mancati rimbalzi morbidi.
* Utilizza la tecnologia MTA più recente per fornire le velocità di throughput ottimali per la consegna delle e-mail.
* Adattandosi in modo istantaneo e automatico al feedback ricevuto, assicura anche una consegna e-mail più accurata e intelligente con dati di consegna in tempo reale.

### Qualificazione non recapitata

Per **sincrono** messaggi di errore di consegna, l’MTA determina il tipo di mancato recapito e la qualifica e invia tali informazioni a Campaign.

L’MTA qualifica il messaggio di mancato recapito SMTP e lo invia nuovamente a Campaign sotto forma di codice non recapitato mappato a un motivo e a una qualifica di mancato recapito della campagna.

>[!NOTE]
>
>Attualmente **asincrono** i messaggi non recapitati sono qualificati dal processo inMail attraverso **[!UICONTROL Inbound email]** regole.

Ulteriori informazioni sugli errori di consegna in [questa sezione](delivery-failures.md).


### Regole MX specifiche

Le regole MX (Mail eXchanger) sono regole che gestiscono la comunicazione tra un server di invio e un server di ricezione.

L’MTA dispone di proprie regole MX che le consentono di personalizzare il throughput in base al dominio in base alla reputazione storica dell’e-mail e al feedback in tempo reale proveniente dai domini in cui invii e-mail.

### Firma DKIM

DKIM (Domain Keys Identified Mail) è un metodo di autenticazione utilizzato per rilevare gli indirizzi del mittente falsificati (comunemente denominato spoofing).

In Adobe Campaign, la firma di autenticazione dell’e-mail DKIM viene eseguita dall’MTA.

Ulteriori informazioni su DKIM nel [Guida alle best practice per il recapito messaggi di Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target="_blank"}.

## Servizio di feedback delle e-mail {#email-feedback-service}

Con la funzionalità EFS (Email Feedback Service), lo stato di ogni e-mail viene riportato con precisione, perché il feedback viene acquisito direttamente dall’MTA.

Una volta avviata la consegna, non vi è alcuna modifica nella **[!UICONTROL Success]** percentuale quando il messaggio viene inviato correttamente da Campaign all’MTA.

I registri di consegna mostrano le **[!UICONTROL Taken into account by the service provider]** stato per ogni indirizzo di destinazione.

Quando il messaggio viene effettivamente recapitato ai profili target e una volta che tali informazioni vengono segnalate nuovamente in tempo reale dall’MTA, i registri di consegna mostrano i **[!UICONTROL Sent]** stato per ogni indirizzo che ha ricevuto correttamente il messaggio. La **[!UICONTROL Success]** viene aumentata di conseguenza con ogni consegna riuscita.

Quando i messaggi di rimbalzo rigido vengono segnalati dall’MTA, lo stato del registro cambia da **[!UICONTROL Taken into account by the service provider]** a **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Quando i messaggi di messaggio non recapitati vengono segnalati nuovamente dall’MTA, lo stato del registro rimane invariato (**[!UICONTROL Taken into account by the service provider]**): solo il [motivo errore](delivery-failures.md#delivery-failure-reasons) è aggiornato<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. La **[!UICONTROL Success]** La percentuale rimane invariata. I messaggi di rimbalzo temporaneo vengono quindi ritentati durante l’intera consegna [periodo di validità](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"}:

* Se un nuovo tentativo ha esito positivo prima della fine del periodo di validità, lo stato del messaggio cambia in **[!UICONTROL Sent]** e **[!UICONTROL Success]** la percentuale viene aumentata di conseguenza.

* In caso contrario, lo stato viene modificato in **[!UICONTROL Failed]**. La **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->La percentuale rimane invariata.

>[!NOTE]
>
>Per ulteriori informazioni sui rimbalzi rigidi e morbidi, vedi [questa sezione](delivery-failures.md#delivery-failure-reasons).
>
>Per ulteriori informazioni sui nuovi tentativi dopo un errore temporaneo di consegna, consulta [questa sezione](delivery-failures.md#retries).

La tabella seguente mostra come gli stati dei KPI e dei log di invio vengono aggiornati in ogni fase del processo di invio con la funzionalità EFS.

| Passaggio nel processo di invio | Riepilogo KPI | Stato dei registri di invio |
|--- |--- |--- |
| Il messaggio viene inviato correttamente da Campaign all’MTA | **[!UICONTROL Success]** percentuale non visualizzata (inizia a 0%) | Considerato dal fornitore di servizi |
| I messaggi di rimbalzo rigido vengono segnalati nuovamente dall’MTA | Nessuna modifica in **[!UICONTROL Success]** percentuale | Operazione non riuscita |
| I messaggi di rimbalzo morbido vengono segnalati nuovamente dall’MTA | Nessuna modifica in **[!UICONTROL Success]** percentuale | Considerato dal fornitore di servizi |
| I nuovi tentativi dei messaggi di rimbalzo non sono riusciti | **[!UICONTROL Success]** la percentuale viene aumentata di conseguenza | Inviato |
| Messaggi di rimbalzo morbido non riusciti | Nessuna modifica in **[!UICONTROL Success]** percentuale | Operazione non riuscita |
