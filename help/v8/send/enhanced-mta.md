---
title: Informazioni sull’MTA avanzato in Adobe Campaign
description: Scopri l’ambito e le specificità dell’invio di e-mail con l’MTA avanzato di Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 0fa0db62f45097755bebcbf434614c4c835d886a
workflow-type: tm+mt
source-wordcount: '972'
ht-degree: 4%

---

# Informazioni sull’MTA avanzato {#sending-with-enhanced-mta}

La **MTA avanzato di Adobe Campaign** (Agente di trasferimento posta) fornisce un&#39;infrastruttura di invio aggiornata che consente di migliorare la consegna, la reputazione, il throughput, il reporting, la gestione dei messaggi non recapitati, l&#39;espansione dell&#39;IP e la gestione delle impostazioni di connessione.

È implementato per tutti i clienti di Campaign v8 per migliorare la scalabilità, aumentare il throughput di consegna e contribuire a inviare più e-mail più rapidamente. Questo si ottiene con nuove tecniche di consegna adattiva che modificano le impostazioni di invio delle e-mail in tempo reale in base al feedback ricevuto dai provider di servizi Internet.

## Utilizzo e vantaggi

**Cos’è l’MTA avanzato?**

Adobe Campaign utilizza un agente di trasferimento della posta (MTA) che esegue l’e-mail commerciale MTA di SparkPost denominata **Momento**.

Momentum rappresenta una tecnologia MTA innovativa e ad alte prestazioni che include una gestione più intelligente dei messaggi non recapitati e una funzionalità di ottimizzazione automatizzata dei messaggi che aiuta i mittenti a raggiungere e mantenere tassi di consegna ottimali nella casella in entrata.

**Quali sono i vantaggi?**

* L&#39;MTA avanzato consente un massiccio aumento della velocità effettiva complessiva e una significativa riduzione dei mancati recapiti.
* Utilizza la tecnologia MTA più recente per fornire le velocità di throughput ottimali per la consegna delle e-mail.
* Adattandosi in modo istantaneo e automatico al feedback ricevuto, assicura anche una consegna e-mail più accurata e intelligente con dati di consegna in tempo reale.

## Specifiche MTA migliorate {#enhanced-mta-impacts}

### Qualificazione non recapitata

Per **sincrono** messaggi di errore di consegna, l’MTA avanzato determina il tipo di mancato recapito e la qualifica e invia tali informazioni a Campaign.

L’MTA avanzato qualifica il messaggio di mancato recapito SMTP e lo invia nuovamente a Campaign sotto forma di codice non recapitato mappato a un motivo e a una qualifica di mancato recapito della campagna.

>[!NOTE]
>
>Attualmente **asincrono** I messaggi non recapitati non sono qualificati dall’MTA avanzato, ma dal processo inMail attraverso il **[!UICONTROL Inbound email]** regole. Per ulteriori informazioni, consulta [Documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}. <!--Refer to [bounce mail qualification](delivery-failures.md#bounce-mail-qualification)-->

Ulteriori informazioni sugli errori di consegna in [questa sezione](delivery-failures.md).

### Periodo di validità

L’impostazione del periodo di validità nelle consegne di Campaign viene utilizzata dall’MTA avanzato solo se è impostata su **3,5 giorni o meno**. Se definisci un valore superiore a 3,5 giorni in Campaign, non verrà preso in considerazione.

Ad esempio, se il periodo di validità è impostato sul valore predefinito di 5 giorni in Campaign, i messaggi di rimbalzo soft entreranno nella coda dei nuovi tentativi dell’MTA avanzato e verranno ritentati per un massimo di 3,5 giorni a partire dal momento in cui il messaggio ha raggiunto l’MTA avanzato. In tal caso, il valore impostato in Campaign non verrà utilizzato.

Una volta che un messaggio è rimasto nella coda dell’MTA avanzato per 3,5 giorni e la consegna non è riuscita, si verificherà un timeout e il suo stato verrà aggiornato da **[!UICONTROL Sent]** a **[!UICONTROL Failed]** nei log di consegna.

Per ulteriori informazioni sul periodo di validità, consulta la sezione [Documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}.

### Nuovi tentativi

I nuovi tentativi di mancato recapito e il periodo di tempo che li separa sono determinati dall’MTA avanzato in base al tipo e alla gravità delle risposte non recapitate provenienti dal dominio e-mail del messaggio.

>[!NOTE]
>
>Le impostazioni relative ai tentativi nelle proprietà di consegna non vengono utilizzate da Campaign.

Ulteriori informazioni sui nuovi tentativi in [questa sezione](delivery-failures.md#retries).

### Regole MX specifiche

Le regole MX (Mail eXchanger) sono regole che gestiscono la comunicazione tra un server di invio e un server di ricezione.

L’MTA avanzato dispone di proprie regole MX che le consentono di personalizzare il throughput in base al dominio in base alla reputazione storica dell’e-mail e al feedback in tempo reale proveniente dai domini in cui invii e-mail.

### Firma DKIM

DKIM (Domain Keys Identified Mail) è un metodo di autenticazione utilizzato per rilevare gli indirizzi del mittente falsificati (comunemente denominato spoofing).

In Adobe Campaign, la firma di autenticazione dell’e-mail DKIM viene eseguita dall’MTA avanzato.

Ulteriori informazioni su DKIM nel [Guida alle best practice per il recapito messaggi di Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target=&quot;_blank&quot;}.

## Servizio di feedback delle e-mail {#email-feedback-service}

Grazie alla funzionalità EFS (Email Feedback Service), lo stato di ogni e-mail viene riportato con precisione, in quanto il feedback viene acquisito direttamente dall’MTA avanzato (Message Transfer Agent).

Una volta avviata la consegna, non vi è alcuna modifica nella **[!UICONTROL Success]** percentuale quando il messaggio viene inviato correttamente da Campaign all’MTA avanzato.

I registri di consegna mostrano le **[!UICONTROL Taken into account by the service provider]** stato per ogni indirizzo di destinazione.

Quando il messaggio viene effettivamente recapitato ai profili target e una volta che tali informazioni vengono segnalate nuovamente in tempo reale dall’MTA avanzato, i registri di consegna mostrano i **[!UICONTROL Sent]** stato per ogni indirizzo che ha ricevuto correttamente il messaggio. La **[!UICONTROL Success]** viene aumentata di conseguenza con ogni consegna riuscita.

Quando i messaggi di rimbalzo rigido vengono segnalati dall’MTA avanzato, lo stato del registro cambia da **[!UICONTROL Taken into account by the service provider]** a **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Quando i messaggi di messaggio non recapitati vengono segnalati nuovamente dall’MTA avanzato, lo stato del registro rimane invariato (**[!UICONTROL Taken into account by the service provider]**): solo il [motivo errore](delivery-failures.md#delivery-failure-reasons) è aggiornato<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. La **[!UICONTROL Success]** La percentuale rimane invariata. I messaggi di rimbalzo temporaneo vengono quindi ritentati durante l’intera consegna [periodo di validità](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}:

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
| Il messaggio viene inviato correttamente da Campaign all’MTA avanzato | **[!UICONTROL Success]** percentuale non visualizzata (inizia a 0%) | Presa in considerazione dal fornitore di servizi |
| I messaggi di rimbalzo rigido vengono segnalati nuovamente dall’MTA avanzato | Nessuna modifica in **[!UICONTROL Success]** percentuale | Non riuscito |
| I messaggi di rimbalzo morbido vengono segnalati nuovamente dall’MTA avanzato | Nessuna modifica in **[!UICONTROL Success]** percentuale | Presa in considerazione dal fornitore di servizi |
| I nuovi tentativi dei messaggi di rimbalzo non sono riusciti | **[!UICONTROL Success]** la percentuale viene aumentata di conseguenza | Inviato |
| Messaggi di rimbalzo morbido non riusciti | Nessuna modifica in **[!UICONTROL Success]** percentuale | Non riuscito |
