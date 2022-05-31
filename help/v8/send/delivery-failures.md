---
title: Errori di consegna in Campaign
description: Comprendere i possibili errori durante l’invio di messaggi con Adobe Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 9c83ebeb-e923-4d09-9d95-0e86e0b80dcc
source-git-commit: 9fa6666532a6943c438268d7ea832f0908588208
workflow-type: tm+mt
source-wordcount: '3009'
ht-degree: 6%

---

# Errori di consegna {#delivery-failures}

I rimbalzi sono il risultato di un tentativo di consegna e di un errore in cui l&#39;ISP fornisce avvisi di errore di back. La lavorazione dei rifiuti è una parte fondamentale dell&#39;igiene degli elenchi. Dopo che una data e-mail è stata rimbalzata diverse volte di fila, questo processo la contrassegna per la soppressione.

Questo processo impedisce ai sistemi di continuare a inviare indirizzi e-mail non validi. I rimbalzi sono uno dei dati chiave utilizzati dagli ISP per determinare la reputazione IP. È importante tenere d’occhio questa metrica. &quot;Consegnato&quot; rispetto a &quot;rimbalzato&quot; è probabilmente il modo più comune per misurare la consegna dei messaggi di marketing: più alta è la percentuale consegnata, meglio è.

Se un messaggio non può essere inviato a un profilo, il server remoto invia automaticamente un messaggio di errore ad Adobe Campaign. Questo errore è qualificato per determinare se l’indirizzo e-mail, il numero di telefono o il dispositivo devono essere messi in quarantena. Vedi [Gestione della posta non recapitata](#bounce-mail-qualification).

Una volta inviato un messaggio, puoi visualizzare lo stato di consegna per ciascun profilo e il tipo e il motivo dell’errore associati nei registri di consegna.

Quando un indirizzo e-mail viene messo in quarantena o se un profilo è in elenco Bloccati, il destinatario viene escluso al passaggio di preparazione della consegna. I messaggi esclusi sono elencati nel dashboard di consegna.

## Perché la consegna del messaggio non è riuscita {#delivery-failure-reasons}

Esistono due tipi di errori quando un messaggio non riesce. Ogni tipo di errore di consegna determina se un indirizzo viene inviato a [quarantena](quarantines.md#quarantine-reason) o no.

* **Rimbalzi netti**
I mancati recapiti rigidi sono errori permanenti generati dopo che un ISP determina un tentativo di invio di posta a un indirizzo utente iscritto come non recapitato. All’interno di Adobe Campaign, i messaggi non recapitati rigidi classificati come non recapitati vengono aggiunti all’elenco di quarantena, il che significa che non verranno tentati nuovamente. Ci sono alcuni casi in cui un rimbalzo duro verrebbe ignorato se la causa del fallimento è sconosciuta.

   Di seguito sono riportati alcuni esempi comuni di rimbalzi duri: L&#39;indirizzo non esiste, Account disabilitato, Sintassi non valida, Dominio non valido

* **Rimbalzi morbidi**
I messaggi non recapitati morbidi sono errori temporanei generati dagli ISP in caso di difficoltà nella consegna della posta. Gli errori soft [riprovare](#retries) più volte (con varianza a seconda dell’utilizzo delle impostazioni di consegna personalizzate o predefinite) per tentare di eseguire una consegna corretta. Gli indirizzi che rimbalzano continuamente morbido non verranno aggiunti alla quarantena fino a quando non viene tentato il numero massimo di tentativi (che variano di nuovo a seconda delle impostazioni).

   Alcune cause comuni di non recapiti morbidi includono: Cassetta postale piena, ricezione server e-mail inattivo, problemi di reputazione del mittente

La  **Ignorato** È noto che il tipo di errore è temporaneo, ad esempio &quot;Fuori sede&quot;, o un errore tecnico, ad esempio se il tipo di mittente è &quot;postmaster&quot;.

Il ciclo di feedback funziona come e-mail non recapitate: quando un utente qualifica un’e-mail come posta indesiderata, puoi configurare le regole e-mail in Adobe Campaign per bloccare tutte le consegne a questo utente. Gli indirizzi di questi utenti vengono inserita nell&#39;elenco Bloccati anche se non hanno fatto clic sul collegamento di annullamento dell’abbonamento. Gli indirizzi vengono aggiunti al (**NmsAddress**) tabella di quarantena e non al (**NmsRecipient**) tabella dei destinatari con **[!UICONTROL Denylisted]** stato. Ulteriori informazioni sul meccanismo del ciclo di feedback nel [Guida alle best practice per il recapito messaggi di Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops).

## Errori sincroni e asincroni {#synchronous-and-asynchronous-errors}

La consegna di un messaggio può non riuscire immediatamente. In tal caso, viene definito un errore sincrono. Se l’invio del messaggio non riesce o in un secondo momento, dopo che è stato inviato, l’errore è asincrono.

Questi tipi di errori vengono gestiti come segue:

* **Errore sincrono**: il server remoto contattato dal server di consegna Adobe Campaign restituisce immediatamente un messaggio di errore. La consegna non può essere inviata al server del profilo. L’agente di trasferimento della posta (MTA) determina il tipo di messaggio non recapitato e qualifica l’errore e invia tali informazioni a Campaign per determinare se gli indirizzi e-mail in questione devono essere messi in quarantena. Consulta [Qualificazione di mail non recapitate](#bounce-mail-qualification).

* **Errore asincrono**: una mail non recapitata o un SR viene inviato successivamente dal server ricevente. Questo errore è qualificato con un&#39;etichetta relativa all&#39;errore. Gli errori asincroni possono verificarsi fino a una settimana dopo l’invio di una consegna.

>[!NOTE]
>
>In qualità di utente Managed Services, la configurazione della cassetta postale di rimbalzo viene eseguita per Adobe.

## Qualificazione di mail non recapitate {#bounce-mail-qualification}

<!--NO LONGER WITH MOMENTUM - Rules used by Campaign to qualify delivery failures are listed in the **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]** node. It is non-exhaustive, and is regularly updated by Adobe Campaign and can also be managed by the user.

![](assets/delivery-log-qualification.png)-->

Attualmente, il modo in cui la qualifica della posta non recapitata viene gestita in Adobe Campaign dipende dal tipo di errore:

* **Errori sincroni**: L’MTA determina il tipo di messaggio non recapitato e la relativa qualifica e invia nuovamente tali informazioni a Campaign. Le qualifiche non recapitate nel **[!UICONTROL Delivery log qualification]** tabella non utilizzata per **sincrono** messaggi di errore di consegna.

* **Errori asincroni**: Le regole utilizzate da Campaign per qualificare gli errori di consegna asincroni sono elencate in **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]** nodo. I messaggi non recapitati asincroni sono qualificati dal processo inMail attraverso **[!UICONTROL Inbound email]** regole. Per ulteriori informazioni, consulta [Documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}.

<!--NO LONGER WITH MOMENTUM - The message returned by the remote server on the first occurrence of this error type is displayed in the **[!UICONTROL First text]** column of the **[!UICONTROL Audit]** tab.

![](assets/delivery-log-first-txt.png)

Adobe Campaign filters this message to delete the variable content (such as IDs, dates, email addresses, phone numbers, etc.) and displays the filtered result in the **[!UICONTROL Text]** column. The variables are replaced with **`#xxx#`**, except addresses that are replaced with **`*`**.

This process allows to bring together all failures of the same type and avoid multiple entries for similar errors in the Delivery log qualification table.
  
>[!NOTE]
>
>The **[!UICONTROL Number of occurrences]** field displays the number of occurrences of the message in the list. It is limited to 100 000 occurrences. You can edit the field, if you want, for example, to reset it.

Bounce mails can have the following qualification status:

* **[!UICONTROL To qualify]** : the bounce mail could not be qualified. Qualification must be assigned to the Deliverability team to guarantee efficient platform deliverability. As long as it is not qualified, the bounce mail is not used to enrich the list of email management rules.
* **[!UICONTROL Keep]** : the bounce mail was qualified and will be used by the **Refresh for deliverability** workflow to be compared to existing email management rules and enrich the list.
* **[!UICONTROL Ignore]** : the bounce mail is ignored, meaning that this bounce will never cause the recipient's address to be quarantined. It will not be used by the **Refresh for deliverability** workflow and it will not be sent to client instances.

![](assets/delivery-log-status.png)

>[!NOTE]
>
>In case of an outage of an ISP, emails sent through Campaign will be wrongly marked as bounces. To correct this, you need to update bounce qualification.-->


## Gestione dei tentativi {#retries}

Se la consegna del messaggio non riesce a seguito di un errore temporaneo (**Morbido** o **Ignorato**), Campaign tenta nuovamente di inviare. Questi tentativi possono essere eseguiti fino alla fine della durata della consegna.

I nuovi tentativi di mancato recapito e il periodo di tempo che li separa sono determinati dall’MTA in base al tipo e alla gravità delle risposte non recapitate provenienti dal dominio e-mail del messaggio.

>[!NOTE]
>
>Le impostazioni relative ai tentativi nelle proprietà di consegna non vengono utilizzate da Campaign.

## Periodo di validità

L’impostazione del periodo di validità nelle consegne di Campaign è limitata a **3,5 giorni o meno**. Per una consegna, se definisci un valore superiore a 3,5 giorni in Campaign, non verrà preso in considerazione.

Ad esempio, se il periodo di validità è impostato sul valore predefinito di 5 giorni in Campaign, i messaggi di rimbalzo soft verranno inseriti nella coda dei nuovi tentativi MTA e verranno ritentati per un massimo di 3,5 giorni a partire dal momento in cui il messaggio ha raggiunto l’MTA. In tal caso, il valore impostato in Campaign non verrà utilizzato.

Una volta che un messaggio è rimasto nella coda dell’MTA per 3,5 giorni e la consegna non è riuscita, si verificherà un timeout e il suo stato verrà aggiornato da **[!UICONTROL Sent]** a **[!UICONTROL Failed]** nei registri di consegna.

Per ulteriori informazioni sul periodo di validità, consulta la sezione [Documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}.


## Tipi di errore e-mail {#email-error-types}

Per il canale e-mail, i possibili motivi di un errore di consegna sono elencati di seguito.

<table> 
 <tbody> 
  <tr> 
   <td> Etichetta errore </td> 
   <td> Tipo di errore </td> 
   <td> Valore tecnico </td> 
   <td> Descrizione </td> 
  </tr> 
  <tr> 
   <td> Account disabilitato </td> 
   <td> Morbido/Duro </td> 
   <td> 4 </td> 
   <td> L'account collegato all'indirizzo non è più attivo. Quando il provider di accesso a Internet (IAP) rileva un periodo prolungato di inattività, può chiudere l'account dell'utente. Le consegne all’indirizzo dell’utente saranno quindi impossibili. Se l’account è temporaneamente disattivato a causa di sei mesi di inattività e può ancora essere attivato, verrà assegnato lo stato Con errori e l’account verrà ritentato finché il contatore degli errori non raggiunge 5. Se l’errore segnala che l’account è disattivato in modo permanente, viene impostato direttamente su Quarantena.<br /> </td> 
  </tr> 
  <tr> 
   <td> Indirizzo in quarantena </td> 
   <td> Duro </td> 
   <td> 9 </td> 
   <td> L'indirizzo è stato messo in quarantena.<br /> </td> 
  </tr> 
  <tr> 
   <td> Indirizzo non specificato </td> 
   <td> Duro </td> 
   <td> 7 </td> 
   <td> Il destinatario non riceve alcun indirizzo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Indirizzo di cattiva qualità </td> 
   <td> Ignorato </td> 
   <td> 14 </td> 
   <td> Il punteggio di qualità per questo indirizzo è troppo basso.<br /> </td> 
  </tr> 
  <tr> 
   <td> Indirizzo Inserita nell'elenco Bloccati </td> 
   <td> Duro </td> 
   <td> 8 </td> 
   <td> L’indirizzo è stato aggiunto al elenco Bloccati al momento dell’invio. Questo stato viene utilizzato per importare dati da elenchi esterni e sistemi esterni nell’elenco quarantena di Adobe Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Indirizzo di controllo </td> 
   <td> Ignorato </td> 
   <td> 127 </td> 
   <td> L'indirizzo del destinatario fa parte del gruppo di controllo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Doppio </td> 
   <td> Ignorato </td> 
   <td> 10 </td> 
   <td> L'indirizzo del destinatario era già in questa consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Errore ignorato </td> 
   <td> Ignorato </td> 
   <td> 25 </td> 
   <td> L'indirizzo è sull'inserire nell'elenco Consentiti. L’errore viene quindi ignorato e viene inviato un messaggio e-mail.<br /> </td> 
  </tr> 
  <tr> 
   <td> Escluso dopo arbitrato </td> 
   <td> Ignorato </td> 
   <td> 12 </td> 
   <td> Il destinatario è stato escluso da una regola di tipologia della campagna di tipo "arbitrale".<br /> </td> 
  </tr> 
  <tr> 
   <td> Escluso da una regola SQL </td> 
   <td> Ignorato </td> 
   <td> 11 </td> 
   <td> Il destinatario è stato escluso da una regola di tipologia della campagna di tipo SQL.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dominio non valido </td> 
   <td> Morbido </td> 
   <td> 2 </td> 
   <td> Il dominio dell'indirizzo e-mail non è corretto o non esiste più. Questo profilo sarà nuovamente oggetto di targeting fino a raggiungere 5 errori. Successivamente, il record verrà impostato sullo stato di quarantena e non verrà eseguito alcun nuovo tentativo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cassetta postale piena </td> 
   <td> Morbido </td> 
   <td> 5 </td> 
   <td> La cassetta postale di questo utente è piena e non può accettare altri messaggi. Questo profilo sarà nuovamente oggetto di targeting fino a raggiungere 5 errori. Successivamente, il record verrà impostato sullo stato di quarantena e non verrà eseguito alcun nuovo tentativo.<br /> Questo tipo di errore viene gestito da un processo di pulizia, l’indirizzo viene impostato su uno stato valido dopo 30 giorni.<br /> Avviso: per rimuovere automaticamente l’indirizzo dall’elenco degli indirizzi in quarantena, è necessario avviare il flusso di lavoro tecnico Database cleanup .<br /> </td> 
  </tr> 
  <tr> 
   <td> Non connesso </td> 
   <td> Ignorato </td> 
   <td> 6 </td> 
   <td> Il telefono cellulare del destinatario è spento o non è connesso alla rete quando il messaggio viene inviato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Non definito </td> 
   <td> Non definito </td> 
   <td> 0 </td> 
   <td> L’indirizzo è in qualificazione perché l’errore non è ancora stato incrementato. Questo tipo di errore si verifica quando un nuovo messaggio di errore viene inviato dal server: può essere un errore isolato, ma se si verifica di nuovo, il contatore degli errori aumenta, avvisando i team tecnici. Possono quindi eseguire un'analisi dei messaggi e qualificare questo errore tramite il <span class="uicontrol">Amministrazione</span> / <span class="uicontrol">Campaign Management</span> / <span class="uicontrol">Gestione non consegnabili</span> nella struttura ad albero.<br /> </td> 
  </tr> 
  <tr> 
   <td> Non ammissibile alle offerte </td> 
   <td> Ignorato </td> 
   <td> 16 </td> 
   <td> Il destinatario non era idoneo per le offerte nella consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rifiutato </td> 
   <td> Morbido/Duro </td> 
   <td> 20 </td> 
   <td> L’indirizzo è stato messo in quarantena a causa di un feedback di sicurezza come un rapporto spam. In base all’errore, l’indirizzo verrà ritentato finché il contatore degli errori non raggiunge 5, o verrà inviato direttamente alle quarantene.<br /> </td> 
  </tr> 
  <tr> 
   <td> Target con dimensioni limitate </td> 
   <td> Ignorato </td> 
   <td> 17 </td> 
   <td> La dimensione massima di consegna è stata raggiunta per il destinatario.<br /> </td> 
  </tr> 
  <tr> 
   <td> Indirizzo non qualificato </td> 
   <td> Ignorato </td> 
   <td> 15 </td> 
   <td> L'indirizzo postale non è stato qualificato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Non raggiungibile </td> 
   <td> Morbido/Duro </td> 
   <td> 3 </td> 
   <td> Errore nella catena di consegna dei messaggi. Potrebbe essere un problema sul relay SMTP, un dominio temporaneamente irraggiungibile, ecc. In base all’errore, l’indirizzo verrà ritentato finché il contatore degli errori non raggiunge 5, o verrà inviato direttamente alle quarantene.<br /> </td> 
  </tr> 
  <tr> 
   <td> Utente sconosciuto </td> 
   <td> Duro </td> 
   <td> 1 </td> 
   <td> L'indirizzo non esiste. Per questo profilo non verranno tentate ulteriori consegne.<br /> </td> 
  </tr> 
 </tbody> 
</table>



## Tipi di errore notifiche push {#push-error-types}

Per il canale dell’app mobile, i possibili motivi di un errore di consegna sono elencati di seguito.

### quarantena iOS {#ios-quarantine}

Il protocollo HTTP/V2 consente un feedback e uno stato diretti per ogni consegna push. Se si utilizza il connettore del protocollo HTTP/V2, il servizio di feedback non viene più chiamato dal **[!UICONTROL mobileAppOptOutMgt]** workflow. Un token viene considerato non registrato quando un’app mobile viene disinstallata o reinstallata.

In modo sincrono, se le APN restituiscono uno stato &quot;non registrato&quot; per un messaggio, il token di destinazione viene messo immediatamente in quarantena.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Scenario</strong><br /> </td> 
   <td> <strong>Stato</strong><br /> </td> 
   <td> <strong>Messaggio di errore</strong><br /> </td> 
   <td> <strong>Tipo di errore</strong><br /> </td> 
   <td> <strong>Motivo dell'errore</strong><br /> </td> 
   <td> <strong>Riprova</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Dispositivo di destinazione alimentato su<br /> </td> 
   <td> OK<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Dispositivo di destinazione spento<br /> </td> 
   <td> OK<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> L'utente disabilita le notifiche per l'applicazione<br /> </td> 
   <td> OK<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Fase di creazione/analisi dei messaggi: payload troppo grande<br /> </td> 
   <td> Errore<br /> </td> 
   <td> Payload troppo lungo<br /> </td> 
   <td> Morbido<br /> </td> 
   <td> Rifiutato<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Fase di creazione/analisi dei messaggi - problema di formato di contenuto imprevisto<br /> </td> 
   <td> Errore<br /> </td> 
   <td> Vari messaggi di errore in base all’errore<br /> </td> 
   <td> Morbido<br /> </td> 
   <td> Non definito<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Problema del certificato (password, corruzione, ecc.) e verifica la connessione al problema APN<br /> </td> 
   <td> Errore<br /> </td> 
   <td> Vari messaggi di errore in base all’errore<br /> </td> 
   <td> Morbido<br /> </td> 
   <td> Rifiutato<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Connessione di rete persa durante l'invio<br /> </td> 
   <td> Errore<br /> </td> 
   <td> Errore di connessione<br /> </td> 
   <td> Non definito<br /> </td> 
   <td> Non raggiungibile<br /> </td> 
   <td> Sì<br /> </td> 
  </tr> 
  <tr> 
   <td> Rifiuto del messaggio APN: Annulla registrazione<br /> l'utente ha rimosso l'applicazione o il token è scaduto<br /> </td> 
   <td> Errore<br /> </td> 
   <td> Non registrato<br /> </td> 
   <td> Duro<br /> </td> 
   <td> Utente sconosciuto<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Rifiuto del messaggio APN: tutti gli altri errori<br /> </td> 
   <td> Errore<br /> </td> 
   <td> La causa del rifiuto dell’errore sarà presente nel messaggio di errore<br /> </td> 
   <td> Morbido<br /> </td> 
   <td> Rifiutato<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
 </tbody> 
</table>

### quarantena Android {#android-quarantine}

**Per Android V1**

Per ogni notifica, Adobe Campaign riceve gli errori sincroni direttamente dal server FCM. Adobe Campaign li gestisce al volo e genera errori rigidi o morbidi in base alla gravità dell’errore e può essere eseguito un nuovo tentativo:

* Lunghezza del payload superata, problema di connessione, problema di disponibilità del servizio: esecuzione di un nuovo tentativo, errore morbido, motivo dell&#39;errore **[!UICONTROL Refused]**.
* Quota del dispositivo superata: nessun nuovo tentativo, errore soft, motivo di errore **[!UICONTROL Refused]**.
* Token non valido o non registrato, errore imprevisto, problema dell&#39;account del mittente: nessun nuovo tentativo, errore rigido, motivo errore **[!UICONTROL Refused]**.

La **[!UICONTROL mobileAppOptOutMgt]** il flusso di lavoro viene eseguito ogni 6 ore per aggiornare **AppSubscriptionRcp** tabella. Per i token dichiarati non registrati o non più validi, il campo **Disabilitato** è impostato su **True** e la sottoscrizione collegata a tale token dispositivo verrà automaticamente esclusa dalle consegne future.

Durante l’analisi della consegna, tutti i dispositivi esclusi dal target vengono aggiunti automaticamente al **excludeLogAppSubRcp** tabella.

>[!NOTE]
>
>Per i clienti che utilizzano il connettore Baidu, di seguito sono riportati i diversi tipi di errori:
>
>* Problema di connessione all’inizio della consegna: tipo di errore **[!UICONTROL Undefined]**, motivo dell&#39;errore **[!UICONTROL Unreachable]**, viene eseguito un nuovo tentativo.
>* Connessione persa durante una consegna: errore morbido, motivo errore **[!UICONTROL Refused]**, viene eseguito un nuovo tentativo.
>* Errore sincrono restituito da Baidu durante l&#39;invio: errore grave, motivo errore **[!UICONTROL Refused]**, non viene eseguito alcun nuovo tentativo.
>
>Adobe Campaign contatta il server Baidu ogni 10 minuti per recuperare lo stato del messaggio inviato e aggiorna i registri di trasmissione. Se un messaggio viene dichiarato come inviato, lo stato del messaggio nei registri di trasmissione è impostato su **[!UICONTROL Received]**. Se Baidu dichiara un errore, lo stato è impostato su **[!UICONTROL Failed]**.

**Per Android V2**

Il meccanismo di quarantena Android V2 utilizza lo stesso processo di Android V1, lo stesso vale per l’aggiornamento degli abbonamenti e delle esclusioni. Per ulteriori informazioni, consulta la sezione [Android V1](#android-quarantine) sezione .

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Scenario</strong><br /> </td> 
   <td> <strong>Stato</strong><br /> </td> 
   <td> <strong>Messaggio di errore</strong><br /> </td> 
   <td> <strong>Tipo di errore</strong><br /> </td> 
   <td> <strong>Motivo dell'errore</strong><br /> </td> 
   <td> <strong>Riprova</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Fase di creazione/analisi dei messaggi: parole chiave non valide utilizzate nei campi personalizzati<br /> </td> 
   <td> Errore<br /> </td> 
   <td> Non è possibile utilizzare le seguenti parole chiave: {1}<br /> </td> 
   <td> Morbido<br /> </td> 
   <td> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Fase di creazione/analisi dei messaggi: carico utile troppo grande<br /> </td> 
   <td> Errore<br /> </td> 
   <td> La notifica è troppo pesante: {1} bit, mentre sono autorizzati solo {2}<br /> </td> 
   <td> Morbido<br /> </td> 
   <td> Rifiutato<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Connessione di rete persa durante l'invio<br /> </td> 
   <td> Errore<br /> </td> 
   <td> Nessuna risposta dal servizio Firebase Cloud Messaging sull'indirizzo: {1}<br /> </td> 
   <td> Morbido<br /> </td> 
   <td> Non raggiungibile<br /> </td> 
   <td> Sì<br /> </td> 
  </tr> 
  <tr> 
   <td> Rifiuto del messaggio FCM: Il server FCM non è temporaneamente disponibile (ad esempio con timeout). <br /> </td> 
   <td> Errore<br /> </td> 
   <td> Servizio Firebase Cloud Messaging temporaneamente non disponibile<br /> </td> 
   <td> Morbido<br /> </td> 
   <td> Non raggiungibile<br /> </td> 
   <td> Sì<br /> </td> 
  </tr> 
  <tr> 
   <td> Rifiuto del messaggio FCM: Errore durante l'autenticazione dell'account del mittente<br /> </td> 
   <td> Errore<br /> </td> 
   <td> Impossibile identificare l'account sviluppatore. Controllare l'ID e la password<br /> </td> 
   <td> Morbido<br /> </td> 
   <td> Rifiutato<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Rifiuto del messaggio FCM: Quota del dispositivo superata<br /> </td> 
   <td> Errore<br /> </td> 
   <td> </td> 
   <td> Morbido<br /> </td> 
   <td> Rifiutato<br /> </td> 
   <td> Sì<br /> </td> 
  </tr> 
  <tr> 
   <td> Rifiuto del messaggio FCM: Registrazione non valida / non registrata<br /> </td> 
   <td> Errore<br /> </td> 
   <td> </td> 
   <td> Duro<br /> </td> 
   <td> Utente sconosciuto<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Rifiuto del messaggio FCM: Tutti gli altri errori<br /> </td> 
   <td> Errore<br /> </td> 
   <td> Il server Firebase Cloud Messaging ha restituito un codice di errore imprevisto: {1} </td> 
   <td> </td> 
   <td> Rifiutato<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
    <tr> 
   <td> Rifiuto del messaggio FCM: Argomento non valido<br /> </td> 
   <td> Errore<br /> </td> 
   <td> INVALID_ARGUMENT </td> 
   <td> Ignorato</td> 
   <td> Non definito<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Rifiuto del messaggio FCM: Errore di autenticazione di terze parti<br /> </td> 
   <td> Errore<br /> </td> 
   <td> THIRD_PARTY_AUTH_ERROR </td> 
   <td> Ignorato</td>
   <td> Rifiutato<br /> </td> 
   <td> Sì<br /> </td> 
  </tr>
    <tr> 
   <td> Rifiuto del messaggio FCM: ID mittente non corrispondente<br /> </td> 
   <td> Errore<br /> </td> 
   <td> SENDER_ID_MISMATCH </td> 
   <td> Morbido</td>
   <td> Utente sconosciuto<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Rifiuto del messaggio FCM: Non registrato<br /> </td> 
   <td> Errore<br /> </td>
   <td> NON REGISTRATO </td> 
   <td> Duro</td> 
   <td> Utente sconosciuto<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Rifiuto del messaggio FCM: Interno<br /> </td> 
   <td> Errore<br /> </td> 
   <td> INTERNO </td> 
   <td> Ignorato</td> 
   <td> Rifiutato<br /> </td> 
   <td> Sì<br /> </td> 
  </tr>
    <tr> 
   <td> Rifiuto del messaggio FCM: Non disponibile<br /> </td> 
   <td> Errore<br /> </td> 
   <td> NON DISPONIBILE</td> 
   <td> Ignorato</td> 
   <td> Rifiutato<br /> </td> 
   <td> Sì<br /> </td> 
  </tr>
    <tr> 
   <td> Rifiuto del messaggio FCM: codice di errore imprevisto<br /> </td> 
   <td> Errore<br /> </td> 
   <td> codice di errore imprevisto</td> 
   <td> Ignorato</td> 
   <td> Rifiutato<br /> </td> 
   <td> No<br /> </td> 
  </tr>
  <tr> 
   <td> Autenticazione: Problema di connessione<br /> </td> 
   <td> Errore<br /> </td> 
   <td> Impossibile connettersi al server di autenticazione </td> 
   <td> Ignorato</td>
   <td> Rifiutato<br /> </td> 
   <td> Sì<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticazione: Client o ambito non autorizzato nella richiesta.<br /> </td> 
   <td> Errore<br /> </td> 
   <td> unauthorized_client </td> 
   <td> Ignorato</td>
   <td> Rifiutato<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticazione: Client non autorizzato a recuperare token di accesso utilizzando questo metodo o client non autorizzato per nessuno degli ambiti richiesti.<br /> </td> 
   <td> Errore<br /> </td> 
   <td> unauthorized_client </td> 
   <td> Ignorato</td>
   <td> Rifiutato<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticazione: Accesso negato<br /> </td> 
   <td> Errore<br /> </td>
   <td> access_negato</td> 
   <td> Ignorato</td>
   <td> Rifiutato<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticazione: E-mail non valida<br /> </td> 
   <td> Errore<br /> </td> 
   <td> valid_Grant </td> 
   <td> Ignorato</td> 
   <td> Rifiutato<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticazione: JWT non valido<br /> </td> 
   <td> Errore<br /> </td> 
   <td> valid_Grant </td> 
   <td> Ignorato</td> 
   <td> Rifiutato<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticazione: Firma JWT non valida<br /> </td> 
   <td> Errore<br /> </td> 
   <td> valid_Grant </td> 
   <td> Ignorato</td> 
   <td> Rifiutato<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticazione: Pubblico del token ID o dell’ambito OAuth non valido<br /> </td> 
   <td> Errore<br /> </td> 
   <td> unauthorized_client</td> 
   <td> Ignorato</td> 
   <td> Rifiutato<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticazione: Client OAuth disabilitato<br /> </td> 
   <td> Errore<br /> </td> 
   <td> disabled_client</td> 
   <td> Ignorato</td> 
   <td> Rifiutato<br /> </td> 
   <td> No<br /> </td> 
  </tr>
 </tbody> 
</table>

## quarantena SMS {#sms-quarantines}

**Per connettori standard**

Le specificità del canale SMS sono elencate di seguito.

>[!NOTE]
>
>La **[!UICONTROL Delivery log qualification]** la tabella non si applica al **SMPP generico esteso** connettore.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Scenario</strong><br /> </td> 
   <td> <strong>Stato</strong><br /> </td> 
   <td> <strong>Messaggio di errore</strong><br /> </td> 
   <td> <strong>Tipo di errore</strong><br /> </td> 
   <td> <strong>Motivo dell'errore</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Inviato al provider<br /> </td> 
   <td> Inviato<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Ricevuto sul cellulare<br /> </td> 
   <td> Ricevuto<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Errore restituito dal provider<br /> </td> 
   <td> Errore<br /> </td> 
   <td> Errore durante la ricezione dei dati (SR o MO)<br /> </td> 
   <td> Morbido<br /> </td> 
   <td> Non raggiungibile<br /> </td> 
  </tr> 
  <tr> 
   <td> Conferma MT non valida<br /> </td> 
   <td> Errore<br /> </td> 
   <td> Errore '{1}' durante l'elaborazione del frame di conferma per la query di invio<br /> </td> 
   <td> Morbido<br /> </td> 
   <td> Non raggiungibile<br /> </td> 
  </tr> 
  <tr> 
   <td> Errore durante l'invio dell'MT<br /> </td> 
   <td> Errore<br /> </td> 
   <td> Errore durante l'invio dei messaggi<br /> </td> 
   <td> Morbido<br /> </td> 
   <td> Non raggiungibile<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Per il connettore SMPP generico esteso**

Quando si utilizza il protocollo SMPP per inviare messaggi SMS, la gestione degli errori viene gestita in modo diverso.

Il connettore SMPP recupera i dati dal messaggio SR (Status Report) restituito utilizzando espressioni regolari (regexes) per filtrare il contenuto. Questi dati vengono quindi confrontati con le informazioni presenti in **[!UICONTROL Delivery log qualification]** (disponibile tramite **[!UICONTROL Administration]** > **[!UICONTROL Campaign Management]** > **[!UICONTROL Non deliverables Management]** menu).

Prima che un nuovo tipo di errore sia qualificato, il motivo dell’errore è sempre impostato su **Rifiutato** per impostazione predefinita.

>[!NOTE]
>
>I tipi di errore e i motivi dell’errore sono gli stessi utilizzati per le e-mail.
>
>Chiedi al tuo provider di un elenco di stati e codici di errore per impostare i tipi di errori e i motivi corretti per un errore nella tabella di qualificazione del registro di consegna.

Esempio di messaggio generato:

```
SR Generic DELIVRD 000|#MESSAGE#
```

* Tutti i messaggi di errore iniziano con **SR** per distinguere i codici di errore SMS dai codici di errore e-mail.
* seconda parte (**Generico** in questo esempio) del messaggio di errore si riferisce al nome dell&#39;implementazione SMSC, come definito in **[!UICONTROL SMSC implementation name]** campo dell’account esterno SMS.

   Poiché lo stesso codice di errore può avere un significato diverso per ogni provider, questo campo ti consente di sapere quale provider ha generato il codice di errore. Puoi quindi trovare l’errore nella documentazione del provider pertinente.

* terza parte (**DELIVRD** in questo esempio) del messaggio di errore corrisponde al codice di stato recuperato dall’SR utilizzando il regex di estrazione dello stato definito nell’account esterno SMS.

   Questo regex è specificato nel **[!UICONTROL SMSC specificities]** scheda dell’account esterno.
Per impostazione predefinita, il regex estrae il **stat:** come definito dal **Appendice B** della sezione **Specifiche di SMPP 3.4**.

* quarta parte (**000** in questo esempio) del messaggio di errore corrisponde al codice di errore estratto dall’SR utilizzando il regex di estrazione del codice di errore definito nell’account esterno SMS.

   Questo regex è specificato nel **[!UICONTROL SMSC specificities]** scheda dell’account esterno.

   Per impostazione predefinita, il regex estrae il **errore:** come definito dal **Appendice B** della sezione **Specifiche di SMPP 3.4**.

* Tutto ciò che viene dopo il simbolo di tubo (|) viene visualizzato solo nel **[!UICONTROL First text]** della colonna **[!UICONTROL Delivery log qualification]** tabella. Questo contenuto viene sempre sostituito da **#MESSAGE#** dopo la normalizzazione del messaggio. Questo processo evita di avere più voci per errori simili ed è lo stesso delle e-mail.

Il connettore SMPP generico esteso applica un euristico per trovare valori predefiniti ragionevoli: se lo stato inizia con **DELIV**, viene considerato un successo perché corrisponde agli stati comuni **DELIVRD** o **CONSEGNATO** utilizzato dalla maggior parte dei fornitori. Qualsiasi altro stato causa un errore grave.
