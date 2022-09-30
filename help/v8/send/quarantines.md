---
title: Gestione della quarantena in Campaign
description: Comprendere la gestione della quarantena in Adobe Campaign
feature: Profiles, Monitoring
role: User, Developer
level: Beginner, Intermediate
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 5%

---

# Quarantena {#quarantine-management}

Adobe Campaign gestisce un elenco di indirizzi messi in quarantena per i canali online (e-mail, SMS, notifiche push). Alcuni provider di accesso a Internet considerano automaticamente le e-mail come spam se il tasso di indirizzi non validi è troppo alto. La quarantena ti consente quindi di evitare di essere aggiunta al elenco Bloccati da questi provider. Inoltre, le quarantene contribuiscono a ridurre i costi di invio degli SMS escludendo numeri di telefono errati dalle consegne.

Quando l’indirizzo o il numero di telefono sono messi in quarantena, i destinatari vengono esclusi dal target durante l’analisi della consegna: non potrai inviare messaggi di marketing, comprese e-mail di flusso di lavoro automatizzate, a tali contatti. Se anche gli indirizzi messi in quarantena sono presenti negli elenchi, saranno esclusi al momento dell’invio a tali elenchi. Un indirizzo e-mail può essere messo in quarantena, ad esempio, quando la cassetta postale è piena, se l’indirizzo non esiste o se il server e-mail non è disponibile.

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

**Quarantena** si applica solo a un **indirizzo**, **numero di telefono** o **token del dispositivo**, ma non al profilo stesso. Ad esempio, un profilo il cui indirizzo e-mail è messo in quarantena può aggiornare il proprio profilo e immettere un nuovo indirizzo e può quindi essere nuovamente oggetto di targeting mediante azioni di consegna. Allo stesso modo, se due profili hanno lo stesso numero di telefono, saranno entrambi interessati se il numero viene messo in quarantena. Gli indirizzi o i numeri di telefono messi in quarantena vengono visualizzati nella [registri di esclusione](#delivery-quarantines) (per una consegna) o [elenco di quarantena](#non-deliverable-bounces) (per l&#39;intera piattaforma).

D’altra parte, i profili possono essere **elenco Bloccati** come dopo un annullamento dell’abbonamento (opt-out), per un dato canale: ciò significa che non sono più presi di mira da nessuno. Di conseguenza, se un profilo nel elenco Bloccati del canale e-mail ha due indirizzi e-mail, entrambi gli indirizzi saranno esclusi dalla consegna. Puoi verificare se un profilo è sul elenco Bloccati di uno o più canali nel **[!UICONTROL No longer contact]** della sezione del profilo **[!UICONTROL General]** scheda . [Ulteriori informazioni](../audiences/view-profiles.md)

>[!NOTE]
>
>Quando i destinatari segnalano il messaggio come spam o rispondono a un messaggio SMS con una parola chiave come &quot;STOP&quot;, l’indirizzo o il numero di telefono vengono messi in quarantena come **[!UICONTROL Denylisted]**. Il loro profilo viene aggiornato di conseguenza.

<!--For the email channel, email addresses are quarantined. For the mobile app channel, device tokens are quarantined. For the SMS channel, phone numbers are quarantined.?-->

## Perché un’e-mail, un telefono o un dispositivo viene messo in quarantena? {#quarantine-reason}

Adobe Campaign gestisce la quarantena in base al tipo di consegna non riuscita e al motivo. Questi vengono assegnati durante la qualifica dei messaggi di errore. Ulteriori informazioni sulla gestione degli errori di consegna [in questa pagina](delivery-failures.md).

È possibile acquisire due tipi o errori:

* **Errore rigido**: l’indirizzo e-mail, il numero di telefono o il dispositivo vengono messi immediatamente in quarantena.
* **Errore morbido**: gli errori soft incrementano un contatore di errori e potrebbero mettere in quarantena un&#39;e-mail, un numero di telefono o un token del dispositivo. Le prestazioni di Campaign [tentativi](delivery-failures.md#retries): quando il contatore degli errori raggiunge la soglia limite, l’indirizzo, il numero di telefono o il token del dispositivo viene messo in quarantena. [Ulteriori informazioni](delivery-failures.md#retries).

Nell’elenco degli indirizzi messi in quarantena, la **[!UICONTROL Error reason]** il campo indica perché l’indirizzo selezionato è stato messo in quarantena. [Ulteriori informazioni](#identifying-quarantined-addresses-for-the-entire-platform).


Se un utente qualifica un’e-mail come spam, il messaggio viene automaticamente reindirizzato verso una casella di posta tecnica gestita da Adobe. L’indirizzo e-mail dell’utente viene quindi messo automaticamente in quarantena con lo stato **[!UICONTROL Denylisted]**. Questo stato si riferisce solo all’indirizzo , il profilo non è nel elenco Bloccati, in modo che l’utente continui a ricevere messaggi SMS e notifiche push. Ulteriori informazioni sui loop di feedback nel [Guida alle best practice per le consegne](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops){target=&quot;_blank&quot;}.

>[!NOTE]
>
>In Adobe Campaign la quarantena distingue tra maiuscole e minuscole. Accertati di importare gli indirizzi e-mail in lettere minuscole, in modo che non vengano reindirizzate in un secondo momento.

## Accedere agli indirizzi messi in quarantena {#access-quarantined-addresses}

Gli indirizzi messi in quarantena possono essere visualizzati per una consegna specifica o per l’intera piattaforma.

### Quarantena per una consegna{#delivery-quarantines}

Gli indirizzi di quarantena sono elencati durante la fase di preparazione della consegna, nei registri di consegna del dashboard di consegna.

Per ogni consegna, puoi anche controllare il **[!UICONTROL Delivery summary]** rapporto: mostra il numero di indirizzi messi in quarantena nel target di consegna e visualizza:

* il numero di indirizzi messi in quarantena durante l’analisi della consegna,
* Il numero di indirizzi messi in quarantena dopo l’azione di consegna.

### Indirizzi non recapitati e non recapitati{#non-deliverable-bounces}

Visualizzazione dell’elenco degli indirizzi messi in quarantena **per l&#39;intera piattaforma**, gli amministratori di Campaign possono sfogliare  **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**. In questa sezione sono elencati gli elementi messi in quarantena per **email**, **SMS** e **Notifica push** canali.

![](assets/tech-quarantine.png)

>[!NOTE]
>
>Il numero di quarantene aumenta con il tempo. Ad esempio, se la durata di un indirizzo e-mail è considerata di tre anni e la tabella dei destinatari aumenta del 50% ogni anno, l’aumento delle quarantene può essere calcolato come segue:
>
>Fine anno 1: 1&#42;0,33)/(1+0,5)=22%.
>
>Fine anno 2: (1.22)&#42;0,33)+0,33)/(1,5+0,75)=32,5%.

Inoltre, il **[!UICONTROL Non-deliverables and bounces]** rapporto incorporato, disponibile dal **Rapporti** in questa sezione della home page vengono visualizzate informazioni sugli indirizzi messi in quarantena, sui tipi di errore riscontrati e su un’interruzione non riuscita per dominio. Puoi filtrare i dati per una consegna specifica o personalizzare il rapporto in base alle tue esigenze.

Ulteriori informazioni sugli indirizzi non recapitati nel [Guida alle best practice per il recapito messaggi](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html){target=&quot;_blank&quot;}.

### Indirizzo e-mail in quarantena {#quarantined-recipient}

Puoi cercare lo stato dell’indirizzo e-mail di qualsiasi destinatario.

A questo scopo, seleziona il profilo del destinatario e fai clic sul pulsante **[!UICONTROL Deliveries]** scheda . Per tutte le consegne a quel destinatario, puoi scoprire se l’indirizzo non è riuscito, se è stato messo in quarantena durante l’analisi, ecc.

Per ogni cartella, puoi visualizzare solo i destinatari il cui indirizzo e-mail è in quarantena, con l’ **[!UICONTROL Quarantined email address]** filtro incorporato, come segue:

![](assets/quarantine-filter.png)


## Rimuovere un indirizzo messo in quarantena {#remove-a-quarantined-address}

Gli indirizzi che corrispondono a condizioni specifiche vengono eliminati automaticamente dall&#39;elenco di quarantena dalla **Pulizia del database** flusso di lavoro integrato.

Gli indirizzi vengono rimossi automaticamente dall’elenco di quarantena nei seguenti casi:

* Indirizzi in un **[!UICONTROL With errors]** lo stato viene rimosso dall’elenco di quarantena dopo la consegna riuscita.
* Indirizzi in un **[!UICONTROL With errors]** lo stato verrà rimosso dall’elenco di quarantena se l’ultimo messaggio non recapitato è stato eseguito più di 10 giorni fa. Per ulteriori informazioni sulla gestione degli errori software, consulta [questa sezione](#soft-error-management).
* Indirizzi in un **[!UICONTROL With errors]** che rimbalzano con il **[!UICONTROL Mailbox full]** L&#39;errore verrà rimosso dall&#39;elenco di quarantena dopo 30 giorni.

Il loro stato cambia in **[!UICONTROL Valid]**.

>[!CAUTION]
>
>Destinatari con un indirizzo in un **[!UICONTROL Quarantine]** o **[!UICONTROL Denylisted]** lo stato non verrà mai rimosso, anche se riceve un’e-mail.

È inoltre possibile rimuovere manualmente un indirizzo dall’elenco di quarantena. Per rimuovere un indirizzo dalla quarantena, puoi:

* Cambia lo stato in **[!UICONTROL Valid]** dal **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]** nodo.

   ![](assets/tech-quarantine-status.png)

* Cambia lo stato in **[!UICONTROL Allowlisted]**: in questo caso, l’indirizzo rimane nell’elenco di quarantena, ma sarà oggetto di targeting sistematico, anche in caso di errore.

>[!CAUTION]
>
>Se si rimuove un indirizzo dall&#39;elenco di quarantena, si riavvia l&#39;invio a questo indirizzo. Questo può avere gravi ripercussioni sul recapito messaggi e sulla reputazione dell’IP, il che potrebbe causare il blocco dell’indirizzo IP o del dominio di invio. Procedi con maggiore attenzione quando consideri di rimuovere qualsiasi indirizzo dalla quarantena. Se hai bisogno di assistenza, contatta il supporto Adobe.
