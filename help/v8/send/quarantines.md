---
title: Gestione della quarantena in Campaign
description: Gestione della quarantena in Adobe Campaign
feature: Profiles, Monitoring
role: User, Developer
level: Beginner, Intermediate
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: b783b1444457b3204fea35b613582642499acf65
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 4%

---

# Quarantena {#quarantine-management}

Adobe Campaign gestisce un elenco di indirizzi in quarantena per i canali online (e-mail, SMS, notifiche push). Alcuni provider di accesso a Internet considerano automaticamente le e-mail come spam se la percentuale di indirizzi non validi è troppo elevata. La quarantena consente quindi di evitare di essere aggiunti al elenco Bloccati da parte di questi provider. Inoltre, le quarantene contribuiscono a ridurre i costi di invio degli SMS escludendo numeri di telefono errati dalle consegne.

Quando l’indirizzo o il numero di telefono vengono messi in quarantena, i destinatari vengono esclusi dal target durante l’analisi della consegna: non potrai inviare messaggi di marketing, incluse e-mail automatizzate del flusso di lavoro, a tali contatti. Se tali indirizzi in quarantena sono presenti anche negli elenchi, verranno esclusi al momento dell’invio a tali elenchi. Un indirizzo e-mail può essere messo in quarantena, ad esempio, quando la cassetta postale è piena, se l’indirizzo non esiste o se il server e-mail non è disponibile.

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

**Quarantena** si applica solo a un **indirizzo**, a **numero di telefono** o un **token dispositivo**, ma non al profilo stesso. Ad esempio, un profilo con un indirizzo e-mail messo in quarantena può aggiornare il profilo e immettere un nuovo indirizzo, per poi essere nuovamente indirizzato mediante azioni di consegna. Allo stesso modo, se due profili hanno lo stesso numero di telefono, saranno entrambi interessati se il numero viene messo in quarantena. Gli indirizzi o i numeri di telefono in quarantena vengono visualizzati nel [registri di esclusione](#delivery-quarantines) (per una consegna) o nella [elenco di quarantena](#non-deliverable-bounces) (per l’intera piattaforma).

D’altra parte, i profili possono trovarsi nel **inserisco nell&#39;elenco Bloccati** come dopo l’annullamento dell’abbonamento (rinuncia), per un determinato canale: questo significa che non sono più oggetto di targeting da parte di alcun. Di conseguenza, se un profilo nel inserisco nell&#39;elenco Bloccati di per il canale e-mail ha due indirizzi e-mail, entrambi gli indirizzi verranno esclusi dalla consegna. Puoi verificare se un profilo si trova nel inserisco nell&#39;elenco Bloccati di per uno o più canali nel **[!UICONTROL No longer contact]** sezione del profilo **[!UICONTROL General]** scheda. [Ulteriori informazioni](../audiences/view-profiles.md)

>[!NOTE]
>
>Quando i destinatari segnalano il messaggio come spam o rispondono a un messaggio SMS con una parola chiave come &quot;STOP&quot;, il loro indirizzo o numero di telefono vengono messi in quarantena come **[!UICONTROL Denylisted]**. Il loro profilo viene aggiornato di conseguenza.

<!--For the email channel, email addresses are quarantined. For the mobile app channel, device tokens are quarantined. For the SMS channel, phone numbers are quarantined.?-->

## Perché viene messa in quarantena un’e-mail, un telefono o un dispositivo {#quarantine-reason}

Adobe Campaign gestisce la quarantena in base al tipo di consegna non riuscita e al motivo. Questi vengono assegnati durante la qualifica dei messaggi di errore. Ulteriori informazioni sulla gestione degli errori di consegna [in questa pagina](delivery-failures.md).

È possibile acquisire due tipi di errori:

* **Errore rigido**: l’indirizzo e-mail, il numero di telefono o il dispositivo viene messo immediatamente in quarantena.
* **Errore morbido**: gli errori soft incrementano un contatore di errori e potrebbero mettere in quarantena un messaggio e-mail, un numero di telefono o un token del dispositivo. Prestazioni della campagna [nuovi tentativi](delivery-failures.md#retries): quando il contatore di errori raggiunge la soglia limite, l’indirizzo, il numero di telefono o il token del dispositivo viene messo in quarantena. [Ulteriori informazioni](delivery-failures.md#retries).

Nell’elenco degli indirizzi messi in quarantena, il **[!UICONTROL Error reason]** indica il motivo per cui l’indirizzo selezionato è stato messo in quarantena. [Ulteriori informazioni](#identifying-quarantined-addresses-for-the-entire-platform).


Se un utente qualifica un’e-mail come spam, il messaggio viene automaticamente reindirizzato verso una casella di posta tecnica gestita da Adobe. L’indirizzo e-mail dell’utente viene quindi messo automaticamente in quarantena con lo stato **[!UICONTROL Denylisted]**. Questo stato si riferisce solo all’indirizzo, il profilo non è nel inserisco nell&#39;elenco Bloccati di, in modo che l’utente continui a ricevere messaggi SMS e notifiche push. Ulteriori informazioni sui cicli di feedback in [Guida alle best practice di consegna](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops){target="_blank"}.

>[!NOTE]
>
>In Adobe Campaign la quarantena distingue tra maiuscole e minuscole. Accertati di importare gli indirizzi e-mail in lettere minuscole, in modo che non vengano reindirizzate in un secondo momento.

## Accedere agli indirizzi messi in quarantena {#access-quarantined-addresses}

Gli indirizzi in quarantena possono essere visualizzati per una consegna specifica o per l’intera piattaforma.

### Quarantene per una consegna{#delivery-quarantines}

Gli indirizzi in quarantena vengono elencati durante la fase di preparazione della consegna, nei registri di consegna del dashboard di consegna.

Per ogni consegna, puoi anche controllare il **[!UICONTROL Delivery summary]** rapporto: mostra il numero di indirizzi in quarantena nel target di consegna e visualizza:

* Il numero di indirizzi messi in quarantena durante l’analisi della consegna,
* Il numero di indirizzi messi in quarantena dopo l’azione di consegna.

### Indirizzi non consegnabili e non recapitati{#non-deliverable-bounces}

Per visualizzare l’elenco degli indirizzi messi in quarantena **per l&#39;intera piattaforma**, gli amministratori di Campaign possono navigare su  **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**. In questa sezione sono elencati gli elementi messi in quarantena per **email**, **SMS** e **Notifica push** canali.

![](assets/tech-quarantine.png)

>[!NOTE]
>
>Il numero di quarantene aumenta con il tempo. Ad esempio, se la durata di un indirizzo e-mail è considerata di tre anni e la tabella dei destinatari aumenta del 50% ogni anno, l’aumento delle quarantene può essere calcolato come segue:
>
>Fine anno 1: (1&#42;0,33)/(1+0,5)=22%.
>
>Fine anno 2: ((1,22&#42;0,33)+0,33)/(1,5+0,75)=32,5%.

Inoltre, la **[!UICONTROL Non-deliverables and bounces]** rapporto incorporato, disponibile dal **Rapporti** sezione di questa home page, visualizza informazioni sugli indirizzi in quarantena, i tipi di errore riscontrati e un raggruppamento degli errori per dominio. Puoi filtrare i dati per una consegna specifica o personalizzare questo rapporto in base alle esigenze.

Ulteriori informazioni sugli indirizzi non recapitati in [Guida alle best practice per la consegna](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html){target="_blank"}.

### Indirizzo e-mail in quarantena {#quarantined-recipient}

Puoi cercare lo stato dell’indirizzo e-mail di qualsiasi destinatario.

A questo scopo, seleziona il profilo del destinatario e fai clic sul pulsante **[!UICONTROL Deliveries]** scheda. Per tutte le consegne a quel destinatario, puoi scoprire se l’indirizzo non è riuscito, è stato messo in quarantena durante l’analisi, ecc.

Per ogni cartella, puoi visualizzare solo i destinatari il cui indirizzo e-mail è in quarantena, con **[!UICONTROL Quarantined email address]** filtro incorporato, come segue:

![](assets/quarantine-filter.png)


## Rimuovere un indirizzo messo in quarantena {#remove-a-quarantined-address}

Gli indirizzi che soddisfano condizioni specifiche vengono automaticamente eliminati dall’elenco di quarantena da **Database cleanup** flusso di lavoro integrato.

Gli indirizzi vengono rimossi automaticamente dall’elenco di quarantena nei seguenti casi:

* Indirizzi in una **[!UICONTROL With errors]** Lo stato verrà rimosso dall’elenco di quarantena dopo una consegna riuscita.
* Indirizzi in una **[!UICONTROL With errors]** Lo stato verrà rimosso dall’elenco di quarantena se l’ultimo messaggio non recapitato si è verificato più di 10 giorni fa. Per ulteriori informazioni sulla gestione degli errori soft, consulta [questa sezione](#soft-error-management).
* Indirizzi in una **[!UICONTROL With errors]** stato non restituito con **[!UICONTROL Mailbox full]** L’errore verrà rimosso dall’elenco di quarantena dopo 30 giorni.

Il loro stato diventa quindi **[!UICONTROL Valid]**.

>[!CAUTION]
>
>Destinatari con un indirizzo in una **[!UICONTROL Quarantine]** o **[!UICONTROL Denylisted]** Lo stato non verrà mai rimosso, anche se si riceve un’e-mail.

È inoltre possibile rimuovere manualmente un indirizzo dall’elenco di quarantena. Per rimuovere un indirizzo dalla quarantena, è possibile:

* Modifica il suo stato in **[!UICONTROL Valid]** dal **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]** nodo.

  ![](assets/tech-quarantine-status.png)

Potrebbe essere necessario eseguire aggiornamenti in blocco sull’elenco di quarantena, ad esempio in caso di un’interruzione del servizio dell’ISP durante la quale le e-mail vengono erroneamente contrassegnate come non recapitate perché non possono essere consegnate correttamente al destinatario.

Per eseguire questa operazione, crea un flusso di lavoro e aggiungi una query sulla tabella di quarantena per filtrare tutti i destinatari interessati in modo che possano essere rimossi dall’elenco di quarantena e inclusi nelle consegne e-mail future di Campaign.

Di seguito sono riportate le linee guida consigliate per questa query:

* **Testo di errore (testo di quarantena)** contiene &quot;Momen_Code10_InvalidRecipient&quot;
* **Dominio e-mail (@domain)** uguale a domain1.com OR **Dominio e-mail (@domain)** uguale a domain2.com OR **Dominio e-mail (@domain)** uguale a domain3.com
* **Stato aggiornamento (@lastModified)** il o dopo il GG/MM/AAAA HH:MM:SS AM
* **Stato aggiornamento (@lastModified)** entro il GG/MM/AAAA HH:MM:SS PM

Dopo aver visualizzato l’elenco dei destinatari interessati, aggiungi un **[!UICONTROL Update data]** per impostare il loro stato su **[!UICONTROL Valid]** in modo che vengano rimossi dall’elenco di quarantena dal **[!UICONTROL Database cleanup]** workflow,. Puoi anche semplicemente eliminarli dalla tabella di quarantena.

