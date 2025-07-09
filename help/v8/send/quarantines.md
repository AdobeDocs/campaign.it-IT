---
title: Gestione della quarantena in Campaign
description: Gestione della quarantena in Adobe Campaign
feature: Profiles, Monitoring
role: User, Data Engineer
level: Beginner
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: cb4cbc9ba14e953d2b3109e87eece4f310bfe838
workflow-type: tm+mt
source-wordcount: '1213'
ht-degree: 4%

---

# Quarantena {#quarantine-management}

Adobe Campaign gestisce un elenco di indirizzi in quarantena per i canali online (e-mail, SMS, notifiche push). Alcuni provider di accesso a Internet considerano automaticamente le e-mail come spam se la percentuale di indirizzi non validi è troppo elevata. La quarantena consente quindi di evitare che questi provider aggiungano altri elementi al elenco Bloccati del sistema di protezione. Inoltre, le quarantene contribuiscono a ridurre i costi di invio degli SMS escludendo numeri di telefono errati dalle consegne.

Quando l’indirizzo o il numero di telefono vengono messi in quarantena, i destinatari vengono esclusi dal target durante l’analisi della consegna: non potrai inviare messaggi di marketing, incluse e-mail automatizzate del flusso di lavoro, a tali contatti. Se tali indirizzi in quarantena sono presenti anche negli elenchi, verranno esclusi al momento dell’invio a tali elenchi. Un indirizzo e-mail può essere messo in quarantena, ad esempio, quando la cassetta postale è piena, se l’indirizzo non esiste o se il server e-mail non è disponibile.

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

## Quarantena e elenco Bloccati di

**Quarantena** si applica solo a un **indirizzo**, a un **numero di telefono** o a un **token dispositivo**, ma non al profilo stesso. Ad esempio, un profilo con un indirizzo e-mail messo in quarantena può aggiornare il profilo e immettere un nuovo indirizzo, per poi essere nuovamente indirizzato mediante azioni di consegna. Allo stesso modo, se due profili hanno lo stesso numero di telefono, saranno entrambi interessati se il numero viene messo in quarantena. Gli indirizzi o i numeri di telefono messi in quarantena vengono visualizzati nei [registri di esclusione](#delivery-quarantines) (per una consegna) o nell&#39;[elenco di quarantena](#non-deliverable-bounces) (per l&#39;intera piattaforma).

>[!NOTE]
>
>Quando i destinatari segnalano il messaggio come spam o rispondono a un messaggio SMS con una parola chiave come &quot;STOP&quot;, il loro indirizzo o numero di telefono viene messo in quarantena come **[!UICONTROL Denylisted]**. Il loro profilo viene aggiornato di conseguenza.

D&#39;altra parte, **profili** possono trovarsi nel **inserisco nell&#39;elenco Bloccati di** come dopo l&#39;annullamento dell&#39;abbonamento (rinuncia) per un determinato canale: ciò implica che non sono più oggetto di targeting da alcuna consegna. Di conseguenza, se un profilo nel elenco Bloccati di per il canale e-mail ha due indirizzi e-mail, entrambi gli indirizzi verranno esclusi dalla consegna. È possibile verificare se un profilo si trova nel elenco Bloccati di accesso a uno o più canali nella sezione **[!UICONTROL No longer contact]** della scheda **[!UICONTROL General]** del profilo. [Ulteriori informazioni](../audiences/view-profiles.md)

>[!NOTE]
>
>I destinatari non sottoscritti tramite il metodo [&quot;mailto&quot; List-Unsubscribe](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations#mailto-list-unsubscribe){target="_blank"} non vengono messi in quarantena. È stato annullato l&#39;abbonamento al [servizio](../start/subscriptions.md) associato alla consegna oppure è stato inviato al inserisco nell&#39;elenco Bloccati di (visibile nella sezione **[!UICONTROL No longer contact]** del profilo) se per la consegna non è stato definito alcun servizio.

<!--For the mobile app channel, device tokens are quarantined.-->

## Perché viene messa in quarantena un’e-mail, un telefono o un dispositivo {#quarantine-reason}

Adobe Campaign gestisce la quarantena in base al tipo di consegna non riuscita e al motivo. Questi vengono assegnati durante la qualifica dei messaggi di errore. Ulteriori informazioni sulla gestione degli errori di consegna [in questa pagina](delivery-failures.md).

È possibile acquisire due tipi di errori:

* **Errore rigido**: l&#39;indirizzo e-mail, il numero di telefono o il dispositivo viene messo immediatamente in quarantena.
* **Errore morbido**: gli errori morbidi incrementano un contatore di errori e potrebbero mettere in quarantena un messaggio e-mail, un numero di telefono o un token dispositivo. Campaign esegue [nuovi tentativi](delivery-failures.md#retries): quando il contatore degli errori raggiunge la soglia limite, l&#39;indirizzo, il numero di telefono o il token del dispositivo viene messo in quarantena. [Ulteriori informazioni](delivery-failures.md#retries).

Nell&#39;elenco degli indirizzi messi in quarantena, il campo **[!UICONTROL Error reason]** indica il motivo per cui l&#39;indirizzo selezionato è stato messo in quarantena. [Ulteriori informazioni](#identifying-quarantined-addresses-for-the-entire-platform).


Se un utente qualifica un’e-mail come spam, il messaggio viene automaticamente reindirizzato verso una casella di posta tecnica gestita da Adobe. L’indirizzo e-mail dell’utente viene quindi messo automaticamente in quarantena con lo stato **[!UICONTROL Denylisted]**. Questo stato si riferisce solo all’indirizzo, il profilo non è nel inserisco nell&#39;elenco Bloccati di, in modo che l’utente continui a ricevere messaggi SMS e notifiche push. Ulteriori informazioni sui cicli di feedback sono disponibili nella [Guida alle best practice per le consegne](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops){target="_blank"}.

>[!NOTE]
>
>In Adobe Campaign la quarantena distingue tra maiuscole e minuscole. Accertati di importare gli indirizzi e-mail in lettere minuscole, in modo che non vengano reindirizzate in un secondo momento.

## Accedere agli indirizzi messi in quarantena {#access-quarantined-addresses}

Gli indirizzi in quarantena possono essere visualizzati per una consegna specifica o per l’intera piattaforma.

### Quarantene per una consegna{#delivery-quarantines}

Gli indirizzi in quarantena vengono elencati durante la fase di preparazione della consegna, nei registri di consegna del dashboard di consegna.

Per ogni consegna, è inoltre possibile controllare il report **[!UICONTROL Delivery summary]**, che mostra il numero di indirizzi in quarantena nel target della consegna e visualizza:

* Il numero di indirizzi messi in quarantena durante l’analisi della consegna,
* Il numero di indirizzi messi in quarantena dopo l’azione di consegna.

### Indirizzi non consegnabili e non recapitati{#non-deliverable-bounces}

Per visualizzare l&#39;elenco degli indirizzi messi in quarantena **per l&#39;intera piattaforma**, gli amministratori di Campaign possono passare a **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**. In questa sezione sono elencati gli elementi messi in quarantena per i canali **email**, **SMS** e **Push notification**.

![](assets/tech-quarantine.png)

>[!NOTE]
>
>Il numero di quarantene aumenta con il tempo. Ad esempio, se la durata di un indirizzo e-mail è considerata di tre anni e la tabella dei destinatari aumenta del 50% ogni anno, l’aumento delle quarantene può essere calcolato come segue:
>
>Fine anno 1: (1&#42;0,33)/(1+0,5)=22%.
>
>Fine anno 2: ((1,22&#42;0,33)+0,33)/(1,5+0,75)=32,5%.

Inoltre, il report integrato **[!UICONTROL Non-deliverables and bounces]**, disponibile nella sezione **Reports** di questa home page, visualizza informazioni sugli indirizzi messi in quarantena, sui tipi di errore riscontrati e un raggruppamento di errori per dominio. Puoi filtrare i dati per una consegna specifica o personalizzare questo rapporto in base alle esigenze.

Ulteriori informazioni sugli indirizzi non recapitati nella [Guida alle best practice per il recapito messaggi](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html){target="_blank"}.

### Indirizzo e-mail in quarantena {#quarantined-recipient}

Puoi cercare lo stato dell’indirizzo e-mail di qualsiasi destinatario.

A tale scopo, selezionare il profilo del destinatario e fare clic sulla scheda **[!UICONTROL Deliveries]**. Per tutte le consegne a quel destinatario, puoi scoprire se l’indirizzo non è riuscito, è stato messo in quarantena durante l’analisi, ecc.

Per ogni cartella, è possibile visualizzare solo i destinatari il cui indirizzo e-mail è in quarantena, con il filtro integrato **[!UICONTROL Quarantined email address]**, come segue:

![](assets/quarantine-filter.png)


## Rimuovere un indirizzo messo in quarantena {#remove-a-quarantined-address}

Gli indirizzi che soddisfano condizioni specifiche vengono eliminati automaticamente dall&#39;elenco di quarantena dal flusso di lavoro predefinito **Database cleanup**.

Gli indirizzi vengono rimossi automaticamente dall’elenco di quarantena nei seguenti casi:

* Gli indirizzi con stato **[!UICONTROL With errors]** verranno rimossi dall&#39;elenco di quarantena dopo una consegna riuscita.
* Gli indirizzi con lo stato **[!UICONTROL With errors]** verranno rimossi dall&#39;elenco di quarantena se l&#39;ultimo messaggio non recapitato è stato eseguito più di 10 giorni fa. Per ulteriori informazioni sulla gestione degli errori software, consulta [questa sezione](#soft-error-management).
* Gli indirizzi con stato **[!UICONTROL With errors]** che non hanno superato l&#39;errore **[!UICONTROL Mailbox full]** verranno rimossi dall&#39;elenco di quarantena dopo 30 giorni.

Il loro stato diventa quindi **[!UICONTROL Valid]**.

>[!CAUTION]
>
>I destinatari con un indirizzo nello stato **[!UICONTROL Quarantine]** o **[!UICONTROL Denylisted]** non verranno mai rimossi, anche se ricevono un&#39;e-mail.

È inoltre possibile rimuovere manualmente un indirizzo dall’elenco di quarantena. Per rimuovere un indirizzo dalla quarantena, è possibile:

* Cambia lo stato in **[!UICONTROL Valid]** dal nodo **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**.

  ![](assets/tech-quarantine-status.png)

Potrebbe essere necessario eseguire aggiornamenti in blocco sull’elenco di quarantena, ad esempio in caso di un’interruzione del servizio dell’ISP durante la quale le e-mail vengono erroneamente contrassegnate come non recapitate perché non possono essere consegnate correttamente al destinatario.

Per eseguire questa operazione, crea un flusso di lavoro e aggiungi una query sulla tabella di quarantena per filtrare tutti i destinatari interessati in modo che possano essere rimossi dall’elenco di quarantena e inclusi nelle consegne e-mail future di Campaign.

Di seguito sono riportate le linee guida consigliate per questa query:

* **Testo di errore (testo di quarantena)** contiene &quot;Momen_Code10_InvalidRecipient&quot;
* **Dominio e-mail (@domain)** uguale a domain1.com OPPURE **Dominio e-mail (@domain)** uguale a domain2.com OPPURE **Dominio e-mail (@domain)** uguale a domain3.com
* **Aggiorna stato (@lastModified)** in data o dopo `MM/DD/YYYY HH:MM:SS AM`
* **Aggiorna stato (@lastModified)** in data `MM/DD/YYYY HH:MM:SS PM` o prima

Una volta ottenuto l&#39;elenco dei destinatari interessati, aggiungere un&#39;attività **[!UICONTROL Update data]** per impostare il loro stato su **[!UICONTROL Valid]** in modo che vengano rimossi dall&#39;elenco di quarantena dal flusso di lavoro **[!UICONTROL Database cleanup]**,. Puoi anche semplicemente eliminarli dalla tabella di quarantena.

