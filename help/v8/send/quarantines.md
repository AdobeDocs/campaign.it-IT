---
title: Gestione della quarantena in Campaign
description: Gestione della quarantena in Adobe Campaign
feature: Profiles, Monitoring
role: User, Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1317'
ht-degree: 5%

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
>I destinatari non sottoscritti tramite il metodo [&quot;mailto&quot; List-Unsubscribe](https://experienceleague.adobe.com/it/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations#mailto-list-unsubscribe){target="_blank"} non vengono messi in quarantena. È stato annullato l&#39;abbonamento al [servizio](../start/subscriptions.md) associato alla consegna oppure è stato inviato al inserisco nell&#39;elenco Bloccati di (visibile nella sezione **[!UICONTROL No longer contact]** del profilo) se per la consegna non è stato definito alcun servizio.

<!--For the mobile app channel, device tokens are quarantined.-->

## Perché viene messa in quarantena un’e-mail, un telefono o un dispositivo {#quarantine-reason}

Adobe Campaign gestisce la quarantena in base al tipo di consegna non riuscita e al motivo. Questi vengono assegnati durante la qualifica dei messaggi di errore. Ulteriori informazioni sulla gestione degli errori di consegna [in questa pagina](delivery-failures.md).

È possibile acquisire due tipi di errori:

* **Errore rigido**: l&#39;indirizzo e-mail, il numero di telefono o il dispositivo viene messo immediatamente in quarantena.
* **Errore morbido**: gli errori morbidi incrementano un contatore di errori e potrebbero mettere in quarantena un messaggio e-mail, un numero di telefono o un token dispositivo. Campaign esegue [nuovi tentativi](delivery-failures.md#retries): quando il contatore degli errori raggiunge la soglia limite, l&#39;indirizzo, il numero di telefono o il token del dispositivo viene messo in quarantena. [Ulteriori informazioni](delivery-failures.md#retries).

Nell&#39;elenco degli indirizzi messi in quarantena, il campo **[!UICONTROL Error reason]** indica il motivo per cui l&#39;indirizzo selezionato è stato messo in quarantena. [Ulteriori informazioni](#non-deliverable-bounces).


Se un utente qualifica un’e-mail come spam, il messaggio viene automaticamente reindirizzato verso una casella di posta tecnica gestita da Adobe. L’indirizzo e-mail dell’utente viene quindi messo automaticamente in quarantena con lo stato **[!UICONTROL Denylisted]**. Questo stato si riferisce solo all’indirizzo, il profilo non è nel inserisco nell&#39;elenco Bloccati di, in modo che l’utente continui a ricevere messaggi SMS e notifiche push. Ulteriori informazioni sui cicli di feedback sono disponibili nella [Guida alle best practice per le consegne](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=it#feedback-loops){target="_blank"}.

>[!NOTE]
>
>In Adobe Campaign la quarantena distingue tra maiuscole e minuscole. Accertati di importare gli indirizzi e-mail in lettere minuscole, in modo che non vengano reindirizzate in un secondo momento.

## Gestione degli errori morbidi {#soft-error-management}

Al contrario degli errori rigidi, gli errori morbidi non mettono immediatamente un indirizzo in quarantena, ma incrementano un contatore di errori. Quando il contatore di errori raggiunge la soglia limite, l’indirizzo viene messo in quarantena. Ulteriori informazioni sui nuovi tentativi e sui tipi di errore in [Informazioni sugli errori di consegna](delivery-failures.md).

Il contatore degli errori viene reinizializzato se l&#39;ultimo errore significativo si è verificato più di 10 giorni fa. Lo stato dell&#39;indirizzo cambia quindi in **[!UICONTROL Valid]** e viene eliminato dall&#39;elenco di quarantena dal flusso di lavoro **[!UICONTROL Database cleanup]**. [Ulteriori informazioni sui workflow tecnici](../config/workflows.md#technical-workflows).

## Accedere agli indirizzi messi in quarantena {#access-quarantined-addresses}

Gli indirizzi in quarantena possono essere visualizzati per una consegna specifica o per l’intera piattaforma.

### Quarantene per una consegna{#delivery-quarantines}

Gli indirizzi in quarantena vengono elencati durante la fase di preparazione della consegna, nei registri di consegna del dashboard di consegna.

Per ogni consegna, è inoltre possibile controllare il report **[!UICONTROL Delivery summary]**, che mostra il numero di indirizzi in quarantena nel target della consegna e visualizza:

* Il numero di indirizzi messi in quarantena durante l’analisi della consegna,
* Il numero di indirizzi messi in quarantena dopo l’azione di consegna.

Per ulteriori informazioni sui rapporti sulle consegne, consulta [questa sezione](../reporting/gs-reporting.md).

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

Ulteriori informazioni sugli indirizzi non recapitati nella [Guida alle best practice per il recapito messaggi](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html?lang=it){target="_blank"}.

### Indirizzo e-mail in quarantena {#quarantined-recipient}

Puoi cercare lo stato dell’indirizzo e-mail di qualsiasi destinatario.

A tale scopo, selezionare il profilo del destinatario e fare clic sulla scheda **[!UICONTROL Deliveries]**. Per tutte le consegne a quel destinatario, puoi scoprire se l’indirizzo non è riuscito, è stato messo in quarantena durante l’analisi, ecc.

Per ogni cartella, è possibile visualizzare solo i destinatari il cui indirizzo e-mail è in quarantena, con il filtro integrato **[!UICONTROL Quarantined email address]**, come segue:

![](assets/quarantine-filter.png)


## Rimuovere un indirizzo messo in quarantena {#remove-a-quarantined-address}

### Aggiornamenti automatici {#unquarantine-auto}

Gli indirizzi che soddisfano condizioni specifiche vengono eliminati automaticamente dall&#39;elenco di quarantena dal flusso di lavoro integrato **[!UICONTROL Database cleanup]**.

Gli indirizzi vengono rimossi automaticamente dall’elenco di quarantena nei seguenti casi:

* Gli indirizzi con stato **[!UICONTROL With errors]** verranno rimossi dall&#39;elenco di quarantena dopo una consegna riuscita.
* Gli indirizzi con lo stato **[!UICONTROL With errors]** verranno rimossi dall&#39;elenco di quarantena se l&#39;ultimo messaggio non recapitato è stato eseguito più di 10 giorni fa. Per ulteriori informazioni sulla gestione degli errori software, consulta [questa sezione](#soft-error-management).
* Gli indirizzi con stato **[!UICONTROL With errors]** che non hanno superato l&#39;errore **[!UICONTROL Mailbox full]** verranno rimossi dall&#39;elenco di quarantena dopo 30 giorni.

Il loro stato diventa quindi **[!UICONTROL Valid]**.

>[!CAUTION]
>
>I destinatari con un indirizzo nello stato **[!UICONTROL Quarantine]** o **[!UICONTROL Denylisted]** non verranno mai rimossi, anche se ricevono un&#39;e-mail.

### Aggiornamenti manuali {#unquarantine-manual}

È inoltre possibile rimuovere manualmente un indirizzo dall’elenco di quarantena. Per rimuovere manualmente un indirizzo dalla quarantena, è possibile modificarne lo stato in **[!UICONTROL Valid]** dal nodo **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**.

![](assets/tech-quarantine-status.png)

### Aggiornamenti in blocco {#unquarantine-bulk}

Potrebbe essere necessario eseguire aggiornamenti in blocco sull’elenco di quarantena in situazioni specifiche, ad esempio un’interruzione del servizio dell’ISP durante la quale le e-mail vengono erroneamente contrassegnate come non recapitate perché non possono essere consegnate correttamente al destinatario.

Per eseguire un aggiornamento in blocco:

1. Crea un flusso di lavoro e aggiungi una query nella tabella di quarantena (**[!UICONTROL nms:address]**) per filtrare i destinatari interessati
2. Utilizza le condizioni di query per identificare gli indirizzi che non devono essere posti in quarantena, ad esempio:
   * **Dominio e-mail (@domain)** è uguale ai domini ISP interessati
   * **Aggiorna lo stato (@lastModified)** entro l&#39;intervallo di tempo dell&#39;interruzione
   * **Stato (@status)** è uguale allo stato di quarantena
3. Aggiungi un&#39;attività **[!UICONTROL Update data]** per impostare lo stato dell&#39;indirizzo su **[!UICONTROL Valid]**

Gli indirizzi verranno quindi rimossi automaticamente dall&#39;elenco di quarantena dal flusso di lavoro **[!UICONTROL Database cleanup]** e potranno essere inclusi nelle consegne future.

## Argomenti correlati

* [Informazioni sugli errori di consegna](delivery-failures.md) - Scopri i diversi tipi di errori di consegna e come Campaign gestisce i mancati recapiti
* [Monitorare le consegne](delivery-dashboard.md) - Accedere ai registri di consegna e monitorare le prestazioni di consegna
* [Best practice per la consegna](../start/delivery-best-practices.md) - Best practice per mantenere un buon recapito messaggi ed evitare le quarantene

