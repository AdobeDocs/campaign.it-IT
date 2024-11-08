---
title: Best practice per la consegna
description: Scopri le best practice per la progettazione e l’invio di consegne con Adobe Campaign
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
source-git-commit: b4fad76b43a77909a4ea2c0877527af80027681a
workflow-type: tm+mt
source-wordcount: '2869'
ht-degree: 3%

---

# Best practice per la consegna {#delivery-best-practices}

Consulta le best practice con le funzionalità di consegna di Campaign.

## Ottimizzare la consegna {#optimize-delivery}

Prima ancora di iniziare a creare le consegne, puoi intraprendere diverse azioni per proteggere e ottimizzare il processo di invio a monte. La sezione seguente illustra le best practice e le procedure consigliate per la configurazione ottimale di Adobe Campaign.

### Prestazioni della piattaforma

Diversi fattori possono influire direttamente sulle prestazioni del server e rallentare la piattaforma Campaign:

* Il numero e il tipo di [elementi di personalizzazione](../send/personalize.md): la personalizzazione nelle e-mail estrae dati dal database per ogni destinatario. nel caso di molti elementi di personalizzazione, la quantità di dati necessari per preparare la consegna è maggiore. Questo può rallentare la piattaforma. Ulteriori informazioni sui guardrail di personalizzazione in [questa sezione](../send/personalize.md#perso-guardrails).

* Caricamento del server: quando il server di marketing gestisce più attività diverse contemporaneamente, può rallentare le prestazioni. Il server di marketing deve coordinare tutti i dati in entrata e in uscita per tutte le consegne per garantire che i dati siano corretti e puntuali.
Per evitare questo problema, coordina la pianificazione delle consegne con gli altri membri del team per garantire le migliori prestazioni.

* Esecuzione del flusso di lavoro: il monitoraggio dei flussi di lavoro è essenziale per evitare problemi di prestazioni della piattaforma. Segui le linee guida elencate [in questo documento](../../automation/workflow/workflow-best-practices.md#execution-and-performance).

* Connettiti a [Funzionalità di Pannello di controllo Campaign di Campaign](https://experienceleague.adobe.com/en/docs/control-panel/using/discover-control-panel/key-features){target="_blank"} per monitorare la tua piattaforma, utilizzando [funzionalità di monitoraggio delle prestazioni](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/about-performance-monitoring){target="_blank"}.

#### Gestione della quarantena {#quarantine-management}

È nel tuo interesse mantenere processi di gestione della quarantena efficaci.

Quando inizi a inviare e-mail su una nuova piattaforma, puoi utilizzare un elenco di indirizzi non completamente qualificati. Se invii a indirizzi non validi o a indirizzi honeypot (cassette postali create solo per ingannare gli spammer), questo comincerà a ridurre la reputazione della tua piattaforma. Una buona gestione della quarantena aiuta a: mantenere la qualità dell’indirizzo, evitare l’inserisco nell&#39;elenco Bloccati da parte dei provider di accesso a Internet e ridurre il tasso di errore, velocizzando le consegne e la velocità effettiva.


Per ulteriori informazioni su come avviare una nuova piattaforma, consulta la [Guida alle best practice per il recapito messaggi di Adobe](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/ac-starting-new-platform){target="_blank"}.

I consigli tecnici sono elencati in [questa sezione](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations){target="_blank"}.


**Suggerimenti**

* Se disponi di un elenco di indirizzi non validi, Adobe consiglia di importarlo nella tabella di quarantena tramite **[!UICONTROL Administration]** > **[!UICONTROL Campaign Management]** > **[!UICONTROL Non deliverables Management]** > **[!UICONTROL Non deliverables and addresses]**.

* I destinatari i cui indirizzi sono in quarantena sono esclusi per impostazione predefinita durante l’analisi della consegna: non sono oggetto di targeting. In questo modo le consegne sono più rapide, in quanto il tasso di errore ha un effetto significativo sulla velocità di consegna. Un indirizzo e-mail può essere messo in quarantena, ad esempio quando la casella in entrata è piena o se l’indirizzo non esiste.
Adobe Campaign gestisce gli indirizzi errati in base al tipo di errore restituito. [Ulteriori informazioni sulle quarantene](../send/quarantines.md)

* Alcuni provider di accesso a Internet considerano automaticamente le e-mail come spam se la percentuale di indirizzi non validi è troppo elevata. La quarantena consente quindi di evitare che questi provider aggiungano altri elementi al elenco Bloccati del sistema di protezione.


### Doppio meccanismo di consenso {#double-opt-in}

Per evitare l’invio di messaggi a indirizzi non validi, limitare le comunicazioni improprie e migliorare la reputazione del mittente, Adobe consiglia di implementare un doppio meccanismo di consenso per la conferma dopo l’abbonamento. Questo aiuta a garantire che un destinatario si sia iscritto intenzionalmente.

## Utilizzare i modelli {#use-templates}

I modelli di consegna consentono una maggiore efficienza, fornendo scenari pronti per i tipi più comuni di attività. Con i modelli, gli esperti di marketing possono distribuire nuove campagne con una personalizzazione minima in un periodo di tempo più breve. [Ulteriori informazioni sui modelli di consegna](../send/create-templates.md).

### Branding

Quando gestisci più marchi in Adobe Campaign, Adobe consiglia di avere un sottodominio per marchio. Ad esempio, una banca può avere diversi sottodomini corrispondenti a ciascuna delle sue agenzie regionali. Se una banca è proprietaria del dominio bluebank.com, i sottodomini possono essere @ny.bluebank.com, @ma.bluebank.com, @ca.bluebank.com, ecc. Disporre di un modello di consegna per sottodominio consente di utilizzare sempre i giusti parametri preconfigurati per ciascun marchio, evitando errori e risparmiando tempo. Ulteriori informazioni sul branding dei sottodomini nella [documentazione del Pannello di controllo Campaign Campaign](https://experienceleague.adobe.com/en/docs/control-panel/using/subdomains-and-certificates/subdomains-branding){target="_blank"}.

### Configurare gli indirizzi

Assicurati di applicare le seguenti linee guida:

* L’indirizzo del mittente è obbligatorio per consentire l’invio di un’e-mail. Alcuni ISP (provider di servizi Internet) verificano la validità dell’indirizzo del mittente prima di accettare i messaggi.
* Un indirizzo con formato non corretto può comportare il rifiuto da parte del server ricevente. Devi accertarti che sia stato fornito un indirizzo corretto.
* L’indirizzo deve identificare esplicitamente il mittente. Il dominio deve essere di proprietà del mittente e deve essere registrato nel mittente.
* Adobe consiglia di creare account e-mail corrispondenti agli indirizzi specificati per le consegne e le risposte. Rivolgiti all’amministratore del sistema di messaggistica.

Per configurare gli indirizzi nell’interfaccia di Campaign, effettua le seguenti operazioni:

1. Nel [modello di consegna](../send/create-templates.md), fai clic sul collegamento **[!UICONTROL From]**. Nella finestra **[!UICONTROL Email header parameters]**, immettere le impostazioni.

1. Nel campo **[!UICONTROL Sender address]**, assicurati che il dominio dell&#39;indirizzo sia lo stesso del sottodominio che hai delegato ad Adobe. È possibile modificare la parte che precede &#39;@&#39; ma non l&#39;indirizzo di dominio.

1. Nel campo **[!UICONTROL From]**, utilizza un nome facilmente identificabile dai destinatari, ad esempio il nome del tuo marchio, per aumentare il tasso di apertura delle consegne. Per migliorare ulteriormente l’esperienza del destinatario, puoi aggiungere il nome di una persona, ad esempio &quot;Emma from Megastore&quot;.

1. Nei campi **[!UICONTROL Reply address text]**, l&#39;indirizzo del mittente viene utilizzato per impostazione predefinita per le risposte. Tuttavia, Adobe consiglia di utilizzare un indirizzo reale esistente, ad esempio l’assistenza clienti del tuo marchio. In questo caso, se un destinatario invia una risposta, l’assistenza clienti sarà in grado di gestirla.

### Configurare un gruppo di controllo

Una volta inviata la consegna, puoi confrontare il comportamento dei destinatari esclusi con quello dei destinatari che l’hanno ricevuta. Puoi quindi misurare l’efficienza delle campagne. Ulteriori informazioni sui gruppi di controllo [in questa sezione](../../automation/campaigns/marketing-campaign-target.md#add-a-control-group).

### Utilizzare le tipologie per applicare filtri o regole di controllo

Una tipologia contiene regole di controllo applicate durante la fase di analisi, prima di inviare qualsiasi messaggio.

Nella scheda **[!UICONTROL Typology]** delle proprietà del modello, modifica la tipologia predefinita in base alle tue esigenze.

Ad esempio, per controllare meglio il traffico in uscita, puoi definire quali indirizzi IP possono essere utilizzati definendo un’affinità per sottodominio e creando una tipologia per affinità. Le affinità sono definite nel file di configurazione dell’istanza. Contatta il tuo amministratore Adobe Campaign.

Per ulteriori informazioni sulle tipologie, consulta [questa sezione](../../automation/campaign-opt/campaign-typologies.md).

## Ottimizzare i contenuti {#optimize-content}

### Creare contenuti personalizzati {#perso-content}

Per personalizzare i messaggi, puoi utilizzare i dati dei destinatari memorizzati nel database o raccolti tramite tracciamento, pagine di destinazione, abbonamenti e così via. Le nozioni di base su Personalization sono presentate in [questa sezione](../send/personalize.md).

Assicurati che il contenuto del messaggio sia progettato correttamente per evitare errori che possono essere correlati alla personalizzazione. Un tag di personalizzazione Adobe Campaign ha sempre il seguente formato: `<%=table.field%>`. L’utilizzo errato dei parametri nei blocchi di personalizzazione può rappresentare un problema. Ad esempio, le variabili in JavaScript devono essere utilizzate come segue:

``
<%
var brand = "xxx"
%>
``

Per ulteriori informazioni sui blocchi di personalizzazione, consulta [questa sezione](../send/personalization-blocks.md).

Puoi preparare i dati di personalizzazione in un flusso di lavoro per migliorare l’analisi della preparazione della consegna. Questa deve essere utilizzata in modo particolare se i dati di personalizzazione provengono da una tabella esterna tramite Federated Data Access (FDA). Questa opzione è descritta in [questa sezione](../send/personalization-data.md#optimize-personalization)

### Creare contenuti ottimizzati {#build-optimized-content}

Durante la creazione delle e-mail, tieni presenti le best practice generali riportate di seguito:

* Design semplice

* Tieni presente gli utenti mobili

* Evita e-mail interamente basate su immagini

* Utilizza font sicuri per le e-mail

* Codifica caratteri speciali

### Oggetto

Lavora sulla [riga dell&#39;oggetto](../send/personalization-fields.md#personalization-fields-uc) per migliorare i tassi di apertura:

* Evitare soggetti troppo lunghi. Usa massimo 50 caratteri

* Evita di usare parole ripetitive come &quot;gratuito&quot; o &quot;offerta&quot;, che potrebbero essere considerate spam

* Evita lettere maiuscole e caratteri speciali come &quot;!&quot;, &quot;£&quot;, &quot;€&quot;, &quot;$&quot;

### Pagina mirror

Includi sempre un collegamento a una pagina speculare. La posizione preferita è nella parte superiore dell’e-mail. Ulteriori informazioni sulla pagina mirror in [questa pagina](../send/mirror-page.md)

### Collegamento annullamento dell’abbonamento

Il collegamento di annullamento dell’abbonamento è essenziale. Deve essere visibile e valido e il modulo deve essere funzionale. Per impostazione predefinita, quando il messaggio viene analizzato, una regola di tipologia [ **[!UICONTROL Unsubscription link approval]** integrata](../../automation/campaign-opt/control-rules.md) controlla se è stato incluso un collegamento di rinuncia e, in caso contrario, genera un avviso.

**Suggerimento**: poiché l&#39;errore umano è sempre possibile, verificare che il collegamento di rinuncia funzioni correttamente prima di ogni invio. Ad esempio, quando invii la bozza, accertati che il collegamento sia valido, che il modulo sia in linea e che il campo `No longer contact this recipient ` sia modificato in `Yes`.

Scopri come inserire un collegamento di rinuncia [in questa sezione](personalization-blocks.md#personalization-blocks-example).

### Dimensione e-mail

Per evitare problemi di prestazioni o recapito messaggi, la dimensione massima consigliata per un&#39;e-mail è di circa **35KB**. Per verificare la dimensione del messaggio, sfogliare la scheda **[!UICONTROL Preview]** e scegliere un profilo di test. Una volta generata, la dimensione del messaggio viene visualizzata nell’angolo in alto a destra.

Per mantenere l’e-mail entro il limite, considera quanto segue:

* Rimuovi stili ridondanti o inutilizzati

* Spostare parte del contenuto dell’e-mail in una pagina di destinazione

* Minimizzare il codice

Assicurati di verificare eventuali modifiche prima dell’invio finale.

### Lunghezza SMS

Per impostazione predefinita, il numero di caratteri in un SMS soddisfa gli standard GSM (Global System for Mobile Communications). I messaggi SMS che utilizzano la codifica GSM sono limitati a 160 caratteri o 153 caratteri per SMS per messaggi inviati in più parti.

La traslitterazione consiste nel sostituire un carattere di un SMS con un altro quando tale carattere non è preso in considerazione dallo standard GSM. L’inserimento di campi di personalizzazione nel contenuto del messaggio SMS potrebbe introdurre caratteri che non vengono presi in considerazione dalla codifica GSM. Puoi autorizzare la traslitterazione di caratteri selezionando la casella corrispondente nella scheda Impostazioni canale SMPP del **[!UICONTROL External account]** corrispondente.

**Suggerimenti**

* Per mantenere invariati tutti i caratteri nei messaggi SMS, ad esempio per non modificare i nomi propri, non abilitare la traslitterazione.

* Tuttavia, se i messaggi SMS contengono molti caratteri che non sono presi in considerazione dallo standard GSM, abilita la traslitterazione per limitare i costi di invio dei messaggi.

Per ulteriori informazioni, consulta [questa sezione](../send/sms/smpp-external-account.md#smpp-transliteration).

### Evita allegati

Gli allegati rimangono uno dei vettori più comuni per la proliferazione di malware, soprattutto quando vengono inviati in massa. Includere un collegamento sicuro al documento invece di allegarlo. Questo garantisce un ulteriore livello di sicurezza per evitare la ridistribuzione involontaria e riduce notevolmente le possibilità che il messaggio venga rifiutato nei gateway e-mail in entrata per motivi di dimensioni o sicurezza.

<!--
## Work on formatting {#formatting}

To avoid common formatting errors, check the following elements:

* Correct **date formatting**: Adobe Campaign provides date formatting functions for the JavaScript templates and XSL stylesheets. [Learn more](formatting.md#date-display)

* Usage of **authorized characters** in emails: the list of valid characters for email addresses is defined in the "XtkEmail_Characters" option. Learn how to access Campaign options [in this section](../../installation/using/configuring-campaign-options.md). To correctly handle special characters, Adobe Campaign needs to be installed in Unicode. 

* Configuration of **Email Authentication**: make sure that the email headers contain the DKIM signature. DKIM (Domain Keys Identified Mail) authentication allows the receiving email server to verify that a message was indeed sent by the person or entity it claims it was sent by, and whether the message content was altered in between the time it was originally sent (and DKIM "signed") and the time it was received. This standard typically uses the domain in the From or Sender header. For more on this, refer to the [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).-->


## Gestione immagini {#manage-images}

Di seguito sono riportate alcune linee guida specifiche per l’ottimizzazione delle immagini per la campagna di e-mail marketing.

### Impedisci il blocco delle immagini

Per impostazione predefinita, alcuni client di posta elettronica bloccano le immagini e alcuni utenti modificano le proprie impostazioni in modo da bloccare le immagini per il salvataggio nell’utilizzo dei dati. Pertanto, se le immagini non vengono scaricate, l’intero messaggio può andare perso. Per evitare questo problema:

* Bilancia il contenuto con immagine e testo. Evita di inviare e-mail interamente basate su immagini.

* Se il testo deve essere contenuto in un’immagine, utilizza il testo alt e il testo del titolo per assicurarti che il messaggio venga trasmesso. Personalizzate lo stile del testo alt/titolo per migliorarne l&#39;aspetto.

* Evita l’uso di immagini di sfondo, in quanto non sono supportate da alcuni client e-mail.

### Rendi le immagini dinamiche

Prova a rendere le immagini dinamiche e ridimensionabili. Tieni presente che questo può avere un impatto sui costi, poiché la generazione richiede più tempo.

### Usa riferimenti immagine assoluti

Per essere accessibili dall’esterno, le immagini utilizzate nelle e-mail e nelle risorse pubbliche collegate alle campagne devono essere presenti su un server accessibile dall’esterno.

* Dall&#39;assistente alla consegna, puoi importare una pagina di HTML contenente immagini o inserire immagini direttamente utilizzando l&#39;editor di HTML tramite l&#39;icona **[!UICONTROL Image]**.

* Se le immagini non vengono visualizzate, verificare che siano disponibili sul server. A questo scopo, passa alla scheda **Source** della consegna. Trova le tue immagini e copia-incolla l’URL di ogni immagine in un browser web. Se le immagini non vengono visualizzate, contatta l’amministratore IT o il fornitore di terze parti che fornisce i contenuti di consegna.

### Anteprima e verifica del messaggio {#preview-msg}

Adobe consiglia di visualizzare l’anteprima del messaggio per controllarne la personalizzazione e per vedere come i destinatari visualizzeranno la consegna.

Nell&#39;assistente alla consegna, la scheda secondaria **[!UICONTROL Preview]** ti consente di visualizzare il rendering di ciascun contenuto per un destinatario. I campi di personalizzazione e gli elementi condizionali del contenuto vengono sostituiti con le informazioni corrispondenti per il profilo selezionato. [Ulteriori informazioni](../send/preview-and-proof.md).


<!--
*  An automatic anti-spam checking is performed during each preview. In the **[!UICONTROL Preview]** sub-tab, check [SpamAssassin](spamassassin.md) spam scoring.  Click **[!UICONTROL More...]** to find out more about the warning.  Before doing so, make sure SpamAssassin is correctly installed and configured on the Adobe Campaign application server. [Learn more](../../installation/using/configuring-spamassassin.md)
-->

## Definire il pubblico adatto {#define-the-right-audience}

La popolazione target è fondamentale: crea i tuoi elenchi con attenzione, testa le e-mail sui client e-mail e sui dispositivi mobili più diffusi e assicurati che i tuoi elenchi e-mail siano aggiornati (senza indirizzi sconosciuti o obsoleti). Puoi anche inviare bozze utili per impostare un ciclo di convalida completo. Per ulteriori informazioni sui tipi di pubblico, consulta [questa sezione](../audiences/gs-audiences.md).

### Rivolgersi al pubblico giusto {#target-the-right-audience}

Quando il contenuto è pronto, è necessario definire con attenzione chi riceverà il messaggio.

Per garantire la corretta consegna, desideri inviare i contenuti personalizzati più rilevanti ai destinatari giusti. Adobe Campaign ti consente di creare il target più preciso: puoi selezionare i destinatari in base all’età, alla localizzazione, a cosa hanno acquistato, se hanno fatto clic su un collegamento in una consegna precedente, ecc. Con Adobe Campaign, puoi anche definire profili di test, gruppi di controllo e indirizzi di seed per assicurarti che il target sia corretto.

### Mappature di destinazione {#target-mappings}

In Campaign, per impostazione predefinita, i modelli di consegna sono destinati a **Destinatari**. Adobe Campaign offre altre mappature di destinazione per le consegne, che puoi modificare in base alle tue esigenze. Ad esempio, puoi distribuire ai visitatori i cui profili sono stati raccolti tramite social network o ai visitatori abbonati a un servizio di informazioni.

Queste mappature sono presentate [in questa sezione](../audiences/target-mappings.md).

### Destinatari esterni {#external-recipients}

Puoi consegnare a destinatari memorizzati in un file esterno anziché salvati nel database. Per ulteriori informazioni, consulta [questa sezione](create-message.md#select-external-recipients-selecting-external-recipients).

<!--
### Send to your subscribers {#send-to-subscribers}

To send messages to the subscribers of a newsletter, you can directly target the subscribers to the corresponding information service. Learn more [in this section](../audiences/).-->

### Destinatari di prova {#test-recipients-seed-addresses}

Per verificare la consegna, utilizza le bozze prima di inviare al target principale.

Accertati di selezionare i destinatari della bozza appropriati, in quanto convalidano il modulo e il contenuto del messaggio. I passaggi per definire i destinatari della bozza sono descritti in [questa sezione](create-message.md#select-the-recipients-of-proof-messages-select-the-proof-target).


### Deduplica indirizzi {#deduplicate-addresses}

È importante evitare di avere indirizzi e-mail duplicati, perché questo può avere un impatto sul target:

* Lo stesso messaggio può essere inviato più di una volta quando una destinazione viene divisa.

* Se un destinatario annulla l’iscrizione dopo aver ricevuto un messaggio, il suo profilo duplicato riceverà comunque messaggi futuri.

La deduplicazione degli indirizzi protegge la reputazione del mittente e garantisce una buona gestione della quarantena.

**Argomenti correlati:**

* [Attività di deduplicazione](../../automation/workflow/deduplication.md).
* [Caso d&#39;uso: utilizzo della funzionalità di unione dell&#39;attività Deduplicazione](../../automation/workflow/deduplication-merge.md).


## Esegui tutti i controlli prima dell’invio {#perform-all-checks}

Quando il messaggio è pronto, accertati che il suo contenuto sia visualizzato correttamente, su tutti i dispositivi, e non contenga errori quali personalizzazione errata o collegamenti interrotti. Prima di inviare il messaggio, assicurati anche che i parametri e la configurazione siano coerenti con la consegna.

I passaggi per la convalida di una consegna sono descritti [in questa sezione](../send/preview-and-proof.md).

<!--
### Inbox rendering {#inbox-and-email-rendering}

Inbox rendering enables you to preview your messages on major email clients, scan content and reputation, discover how recipients are reading messages.

**Tips**:

* You can view the sent message in the different contexts in which it may be received: webmail, message service, mobile, etc.

* Inbox rendering capabilities are crucial to identifying whether your email campaigns successfully make it past the filters of major ISPs (Internet Service Providers) and webmail services. Such tools send a pre-flight copy of an email to a network of test inboxes, so you can see how the message will display, or render, across these services. They may also include reports and code correction options that help you quickly identify and make fixes that improve deliverability.

Learn more [in this section](inbox-rendering.md).-->

### Messaggi di bozza {#proof-messages}

L’invio di bozze ti consente di controllare il collegamento di rinuncia, la pagina speculare e tutti gli altri collegamenti, convalidare il messaggio, verificare che siano visualizzate le immagini, rilevare eventuali errori, ecc. Puoi anche controllare la progettazione e il rendering su dispositivi diversi.

<!--
### Set up A/B testing deliveries {#a-b-testing-deliveries}

If you have several contents for an email delivery, you can use A/B testing to find out which version will have the biggest impact on the targeted population.

**Tips**:

* Send the different versions to some of your recipients

* Select the one with the highest success rate and send it to the rest of your target

Learn more [in this section](get-started-a-b-testing.md).-->

### Assicurati che il messaggio sia consegnato {#make-sure-your-message-is-delivered}

Come ultimo passo, massimizza le opportunità e sfrutta la potenza di Adobe Campaign per garantire che il messaggio venga effettivamente consegnato ai destinatari pertinenti.

#### Seguire un processo di convalida

Puoi definire un processo di convalida completo, che coinvolga operatori e gruppi di Adobe Campaign, per convalidare sia il contenuto di destinazione che quello del messaggio. Ciò garantirà il monitoraggio e il controllo completo dei vari processi della campagna: targeting, contenuto, budget, estrazione e invio di una bozza. A seconda delle autorizzazioni, gli utenti riceveranno una notifica, riceveranno delle bozze e saranno in grado di convalidare o rifiutare il messaggio. Per ulteriori informazioni, consulta [questa sezione](../../automation/campaigns/marketing-campaign-approval.md).

#### Usa ondate

È possibile aumentare progressivamente il volume inviato mediante scaglioni. In questo modo i messaggi non verranno contrassegnati come spam o quando desideri limitare il numero di messaggi al giorno. Utilizzando le scaglioni è possibile suddividere le consegne in più batch anziché inviare contemporaneamente volumi elevati di messaggi. Per ulteriori informazioni, consulta [questa sezione](../send/configure-and-send.mdsending-using-multiple-waves).

#### Assegnare priorità ai messaggi

Puoi impostare l’ordine di invio per le consegne indicando il livello di priorità. Per eseguire questa operazione:

1. Modificare le proprietà di consegna e selezionare la scheda **[!UICONTROL Delivery]**.

1. Definisci il livello di priorità per la consegna su una scala da **[!UICONTROL Very low]** a **[!UICONTROL Very high]**.

>[!NOTE]
>
>Non è possibile definire l’ordine di invio dei messaggi da una consegna.

<!--
#### Setup IP Affinities

To better control the outbound SMTP traffic, you can manage affinities by defining which specific IP addresses can be used for each affinity. This lets you restrict the number of emails for specific deliveries towards machines or output addresses. For example, you can use one affinity per country or sub-domain. You can then create one typology per country and link each affinity to the corresponding typology.

You can:

* Define the IP affinities in the serverConf.xml configuration file. [Learn more](../../installation/using/configuring-campaign-server.md#managing-outbound-smtp-traffic-with-affinities)

* For each IPAffinity element, declare the IP addresses that can be used. [Learn more](../../installation/using/email-deliverability.md#list-of-ip-addresses-to-use)

* In the [typology](../../campaign-opt/using/about-campaign-typologies.md) of your choice, use the **[!UICONTROL Managing affinities with IP addresses]** field to link deliveries to the delivery server (MTA) which manages the said affinity. [Learn more](../../campaign-opt/using/applying-rules.md#control-outgoing-smtp-traffic).

* Once the email is sent, check the header to verify which IP address the delivery was sent from. Your email administrator should help you obtain the header information.

* For SMS deliveries, make sure that the SMS channel has a dedicated affinity limited to **one** application server container. [Learn more](../../installation/using/configure-delivery-settings.md#managing-outbound-smtp-traffic-with-affinities)

>[!NOTE]
>
>Most of these steps can only be performed by an expert user.-->

#### Utilizzare le tipologie

Puoi utilizzare le regole di tipologia per escludere parte del target in base a criteri specifici. Ciò garantisce che i messaggi inviati soddisfino al meglio le esigenze e le aspettative dei clienti, in linea con le politiche di comunicazione aziendali. Ad esempio, puoi filtrare i destinatari minorenni dal target della newsletter. Ulteriori informazioni [in questo esempio](../../automation/campaign-opt/filtering-rules.md).


## Tracciamento e monitoraggio {#track-and-monitor}

Hai fatto clic sul pulsante **Invia**? Vediamo cosa succede. Una volta inviata la consegna, Adobe Campaign ti consente di tenere traccia dei messaggi inviati e scoprire come i destinatari reagiscono alla consegna. Questo ti aiuterà a migliorare l’invio futuro e a ottimizzare le campagne successive.

## Monitorare le consegne {#monitoring-deliveries}

Per controllare le campagne, devi assicurarti che il messaggio sia stato effettivamente recapitato ai destinatari.

Dal dashboard di consegna di Campaign, puoi controllare i messaggi elaborati e i registri di controllo della consegna. Puoi anche controllare lo stato dei messaggi nei registri di consegna.

[Ulteriori informazioni sul monitoraggio della consegna nella documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target="_blank"}


## Tracciare il comportamento {#track-behaviour}

Per conoscere meglio il comportamento dei destinatari, puoi tenere traccia della loro reazione a una consegna: ricezione, apertura, clic su collegamenti, annullamenti di abbonamenti, ecc. In Campaign, queste informazioni vengono visualizzate nella scheda **Tracciamento** dei destinatari interessati dalla consegna e nella scheda Tracciamento della consegna.

**Suggerimento**: il monitoraggio dei messaggi è abilitato per impostazione predefinita. Per configurare gli URL, seleziona l’opzione Visualizza URL nella sezione inferiore dell’assistente alla consegna. Per ogni URL del messaggio, puoi scegliere se attivare il tracciamento.


[Ulteriori informazioni sulle funzionalità di tracciamento sono disponibili nella documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html#sending-messages){target="_blank"}

