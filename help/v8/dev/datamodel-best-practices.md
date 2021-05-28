---
solution: Campaign v8
product: Adobe Campaign
title: Best practice per i modelli di dati
description: Scopri le best practice per l’estensione del modello dati di Campaign
source-git-commit: 583a8f6a03b00e1eafa6d408c9949e60a6f8158d
workflow-type: tm+mt
source-wordcount: '2681'
ht-degree: 4%

---

# Best practice per i modelli di dati{#data-model-best-practices}

Questo documento delinea i consigli chiave durante la progettazione del modello dati Adobe Campaign.

Il sistema Adobe Campaign è molto flessibile e può essere esteso oltre l&#39;implementazione iniziale. Tuttavia, mentre le possibilità sono infinite, è fondamentale prendere decisioni sagge e creare solide basi per iniziare a progettare il modello dati.

Per una migliore comprensione delle tabelle integrate di Campaign e del modo in cui si relazionano tra loro, consulta [questa sezione](datamodel.md) .

[!DNL :bulb:] Consulta  [questa ](schemas.md) sezione per iniziare a utilizzare gli schemi di Campaign.

[!DNL :bulb:] Scopri come configurare gli schemi di estensione per estendere il modello dati concettuale del database Adobe Campaign in  [questa pagina](extend-schema.md).

## Architettura del modello dati {#data-model-architecture}

Adobe Campaign è un potente sistema di gestione delle campagne cross-channel che consente di allineare le strategie online e offline per creare esperienze cliente personalizzate.

### Approccio incentrato sul cliente {#customer-centric-approach}

Mentre la maggior parte dei provider di servizi e-mail comunica ai clienti con un approccio incentrato sull’elenco, Adobe Campaign si basa su un database relazionale per sfruttare una visione più ampia dei clienti e dei loro attributi.

Per accedere alla descrizione di ciascuna tabella, vai a **[!UICONTROL Admin > Configuration > Data schemas]**, seleziona una risorsa dall’elenco e fai clic sulla scheda **[!UICONTROL Documentation]** .


>[!NOTE]
>
>Adobe Campaign consente di creare una [tabella dei destinatari personalizzata](custom-recipient.md). Tuttavia, nella maggior parte dei casi, si consiglia di sfruttare la tabella [Destinatario incorporata](datamodel.md#ootb-profiles) che dispone già di tabelle e funzionalità aggiuntive predefinite.

### Dati per Adobe Campaign {#data-for-campaign}

Quali dati devono essere inviati ad Adobe Campaign? È fondamentale determinare i dati necessari per le attività di marketing.

>[!NOTE]
>
>Adobe Campaign non è né un data warehouse né uno strumento di reporting. Pertanto, non cercare di importare in Adobe Campaign tutti i possibili clienti e le relative informazioni associate, né di importare dati che verranno utilizzati solo per generare rapporti.

Per decidere se un attributo sarebbe necessario o meno in Adobe Campaign, chiedi se rientra in una di queste categorie:

* Attributo utilizzato per **segmentazione**
* Attributo utilizzato per **processi di gestione dei dati** (ad esempio, calcolo aggregato)
* Attributo utilizzato per **personalizzazione**

Se non rientra in nessuno di questi, è molto probabile che questo attributo non sarà necessario in Adobe Campaign.

### Scelta dei tipi di dati {#data-types}

Per garantire una buona architettura e prestazioni del sistema, segui le best practice riportate di seguito per configurare i dati in Adobe Campaign.

* All’interno di una tabella di grandi dimensioni, è possibile inserire campi stringa o numerici e aggiungere collegamenti alle tabelle di riferimento (quando si lavora con un elenco di valori).
* L&#39;attributo **expr** consente di definire un attributo di schema come campo calcolato anziché come valore di set fisico in una tabella. In questo modo è possibile accedere alle informazioni in un formato diverso (ad esempio per l’età e la data di nascita) senza dover memorizzare entrambi i valori. Questo è un buon modo per evitare la duplicazione dei campi. Ad esempio, la tabella Destinatario utilizza un’espressione per il dominio, già presente nel campo e-mail.
* Tuttavia, quando il calcolo dell&#39;espressione è complesso, si sconsiglia di utilizzare l&#39;attributo **expr** come calcolo on-the-fly può influire sulle prestazioni delle query.
* Il tipo **XML** è un buon modo per evitare di creare troppi campi. Ma occupa anche spazio su disco in quanto utilizza una colonna CLOB nel database. Può anche portare a query SQL complesse e può influire sulle prestazioni.
* La lunghezza di un campo **string** deve sempre essere definita con la colonna . Per impostazione predefinita, la lunghezza massima in Adobe Campaign è di 16 K, ma l’Adobe consiglia di mantenere il campo più breve se sai già che la dimensione non supererà una lunghezza più breve.
* È accettabile avere un campo più breve in Adobe Campaign rispetto al sistema di origine se si è certi che la dimensione nel sistema di origine è stata sopravvalutata e non verrà raggiunta. Ciò potrebbe significare una stringa più breve o un numero intero più piccolo in Adobe Campaign.

### Scelta dei campi {#choice-of-fields}

Un campo deve essere memorizzato in una tabella se ha uno scopo di targeting o personalizzazione. In altre parole, se un campo non viene utilizzato per inviare un’e-mail personalizzata o come criterio in una query, occuperà inutilmente spazio su disco.


### Scelta dei tasti {#choice-of-keys}

Oltre alle **autouuid** e **autopk** definite per impostazione predefinita nella maggior parte delle tabelle, è consigliabile aggiungere alcune chiavi logiche o aziendali (numero di account, numero di client e così via). Può essere utilizzato successivamente per le importazioni/riconciliazione o i pacchetti di dati. Per ulteriori informazioni, consulta [Identificatori](#identifiers).

Le chiavi efficienti sono essenziali per le prestazioni. Con Snowflake, è possibile inserire tipi di dati numerici o basati su stringhe come chiavi per le tabelle.

<!-- ### Dedicated tablespaces {#dedicated-tablespaces}

The tablespace attribute in the schema allows you to specify a dedicated tablespace for a table.

The installation wizard allows you to store objects by type (data, temporary).

Dedicated tablespaces are better for partitioning, security rules, and allow fluid and flexible administration, better optimization, and performance. -->

## Identificatori {#identifiers}

Le risorse Adobe Campaign hanno tre identificatori ed è possibile aggiungere un identificatore aggiuntivo.

Nella tabella seguente sono descritti questi identificatori e il loro scopo.

| Identificatore | Descrizione | Best practice |
|--- |--- |--- |
| Id | <ul><li>L’id è la chiave primaria fisica di una tabella Adobe Campaign. Per le tabelle incorporate, si tratta di un ID universale univoco (UUID)</li><li>Questo identificatore deve essere univoco. </li><li>Un UUID può essere visibile in una definizione dello schema.</li></ul> | <ul><li>Gli identificatori generati automaticamente non devono essere utilizzati come riferimento in un flusso di lavoro o nella definizione di un pacchetto.</li><li>L’ID in una tabella è un UUID e questo tipo non deve essere modificato.</li></ul> |
| Nome (o nome interno) | <ul><li>Queste informazioni sono un identificatore univoco di un record in una tabella. Questo valore può essere aggiornato manualmente, in genere con un nome generato.</li><li>Questo identificatore mantiene il suo valore quando viene distribuito in un’istanza diversa di Adobe Campaign e non deve essere vuoto.</li></ul> | <ul><li>Rinomina il nome del record generato da Adobe Campaign se l’oggetto deve essere distribuito da un ambiente a un altro.</li><li>Quando un oggetto dispone di un attributo namespace (*schema* ad esempio), questo spazio dei nomi comune verrà utilizzato in tutti gli oggetti personalizzati creati. Alcuni spazi dei nomi riservati non devono essere utilizzati: *nms*, *xtk*, ecc.  Alcuni namespace sono interni solo. [Ulteriori informazioni](schemas.md#reserved-namespaces).</li><li>Quando un oggetto non dispone di uno spazio dei nomi (*workflow* o *delivery* ad esempio), questa nozione di spazio dei nomi viene aggiunta come prefisso di un oggetto nome interno: *namespaceMyObjectName*.</li><li>Non utilizzare caratteri speciali come lo spazio &quot;&quot;, la semicolonna &quot;:&quot; o il trattino &quot;-&quot;. Tutti questi caratteri verranno sostituiti da un carattere di sottolineatura &quot;_&quot; (carattere consentito). Ad esempio, &quot;abc-def&quot; e &quot;abc:def&quot; vengono memorizzati come &quot;abc_def&quot; e si sovrascrivono a vicenda.</li></ul> |
| Etichetta | <ul><li>L’etichetta è l’identificatore aziendale di un oggetto o record in Adobe Campaign.</li><li>Questo oggetto consente spazi e caratteri speciali.</li><li>Non garantisce l&#39;unicità di un documento.</li></ul> | <ul><li>È consigliabile determinare una struttura per le etichette degli oggetti.</li><li>Questa è la soluzione più semplice da usare per identificare un record o un oggetto per un utente Adobe Campaign.</li></ul> |

La chiave primaria di Adobe Campaign è un UUID generato automaticamente per tutte le tabelle integrate. Un UUID può essere utilizzato anche per le tabelle personalizzate.

Anche se il numero di ID è infinito, ti devi occupare delle dimensioni del database per garantire prestazioni ottimali. Per evitare qualsiasi problema, assicurati di regolare le impostazioni di eliminazione dell’istanza. Per ulteriori informazioni, consulta [questa sezione](#data-retention).


## Tasti interni personalizzati {#custom-internal-keys}

Le chiavi primarie sono necessarie per ogni tabella creata in Adobe Campaign.

La maggior parte delle organizzazioni importa record da sistemi esterni. Anche se la chiave fisica della tabella Destinatario è l’attributo &quot;id&quot;, è possibile determinare anche una chiave personalizzata.

Questa chiave personalizzata è la chiave primaria del record effettiva nel sistema esterno che alimenta Adobe Campaign.

Durante la creazione di una tabella personalizzata sono disponibili due opzioni:
* Combinazione di chiave generata automaticamente (id) e chiave interna (personalizzata). Questa opzione è interessante se la chiave di sistema è una chiave composita o non un numero intero. Con il Snowflake, i numeri interi o le chiavi basate su stringhe forniscono prestazioni più elevate nelle tabelle grandi e si uniscono ad altre tabelle.
* Utilizzo della chiave primaria come chiave primaria del sistema esterno. Questa soluzione è solitamente preferita in quanto semplifica l&#39;approccio all&#39;importazione e all&#39;esportazione di dati, con una chiave coerente tra i diversi sistemi. **** Se la chiave si chiama &quot;id&quot; e deve essere compilata con valori esterni (non generata automaticamente), l’opzione Autouuidid deve essere disabilitata.

>[!CAUTION]
>
>Un autouuid non deve essere utilizzato come riferimento nei flussi di lavoro.


## Collegamenti e cardinalità {#links-and-cardinality}

### Collegamenti {#links}

Attenzione all&#39;integrità &quot;propria&quot; su grandi tavoli. L&#39;eliminazione di record con tabelle di grandi dimensioni con integrità &quot;propria&quot; può potenzialmente arrestare l&#39;istanza. La tabella è bloccata e le eliminazioni vengono effettuate una per una. Quindi è meglio utilizzare l&#39;integrità &quot;neutrale&quot; sui tavoli figli che hanno grandi volumi.

La dichiarazione di un collegamento come join esterno non è valida per le prestazioni. Il record zero-id emula la funzionalità di join esterno. Non è necessario dichiarare join esterni se il collegamento utilizza l&#39; **autouuid**.

Sebbene sia possibile unire qualsiasi tabella in un flusso di lavoro, Adobe consiglia di definire collegamenti comuni tra le risorse direttamente nella definizione della struttura dati.

Il collegamento deve essere definito in allineamento con i dati effettivi nelle tabelle. Una definizione errata potrebbe influire sui dati recuperati tramite i collegamenti, ad esempio duplicando inaspettatamente i record.

Assegna al collegamento un nome coerente con il nome della tabella: il nome del collegamento dovrebbe aiutare a comprendere cosa sia la tabella lontana.

Non denominare un collegamento con &quot;id&quot; come suffisso. Ad esempio, denominalo &quot;transaction&quot; anziché &quot;transactionId&quot;.

Per impostazione predefinita, Adobe Campaign crea un collegamento utilizzando la chiave primaria della tabella esterna. Per una maggiore chiarezza, è preferibile definire esplicitamente il join nella definizione del collegamento.

### Cardinalità {#cardinality}

Quando progetti un collegamento, assicurati che il record di destinazione sia univoco quando è stata dichiarata una relazione 1-1. In caso contrario, il join potrebbe restituire più record quando è previsto un solo record. Questo si traduce in errori durante la preparazione della consegna quando &quot;la query restituisce più righe del previsto&quot;. Imposta il nome del collegamento sullo stesso nome dello schema di destinazione.

Definisci un collegamento con una cardinalità (1-N) nello schema sul lato (1). Ad esempio, la transazione Destinatario relazione (1) - (N) deve essere definita nello schema della transazione.

Per impostazione predefinita, una cardinalità inversa di un collegamento è (N). È possibile definire un collegamento (1-1) aggiungendo l&#39;attributo revCardinality=&#39;single&#39; alla definizione del collegamento.

Se il link inverso non deve essere visibile all&#39;utente, puoi nasconderlo con la definizione del link revLink=&#39;_NONE_&#39;. Un buon caso d’uso è quello di definire un collegamento tra il destinatario e l’ultima transazione completata, ad esempio. Devi solo visualizzare il collegamento dal destinatario all’ultima transazione e non è necessario alcun link di storno per essere visibile dalla tabella delle transazioni.

I collegamenti che eseguono un join esterno (1-0.1) devono essere utilizzati con attenzione in quanto influiranno sulle prestazioni del sistema.

## Conservazione dei dati {#data-retention}

Adobe Campaign non è né un data warehouse né uno strumento di reporting. Pertanto, per garantire buone prestazioni della soluzione Adobe Campaign, la crescita del database dovrebbe rimanere sotto controllo. A questo scopo, segui alcune delle best practice riportate di seguito.

Per quanto riguarda la conservazione, le tabelle di registro integrate in Campaign dispongono di periodi di conservazione preimpostati che in genere limitano l’archiviazione dei dati a un massimo di sei mesi.

Di seguito sono riportati i valori di conservazione predefiniti per le tabelle integrate. Ricorda che la configurazione della conservazione è impostata dagli amministratori tecnici di Adobe durante l’implementazione e che i valori possono variare per ciascuna implementazione, in base ai requisiti dei clienti.

* **Tracciamento consolidato**: 1 anno
* **Registri di consegna**: 6 mesi
* **Registri di tracciamento**: 1 anno
* **Consegne eliminate**: 1 settimana
* **Rifiuti di importazione**: 6 mesi
* **Profili dei visitatori**: 1 mese
* **Proposte di offerta**: 1 anno
* **Eventi**: 1 mese
* **Statistiche sull’elaborazione degli eventi**: 1 anno
* **Eventi archiviati**: 1 anno
* **Eventi di pipeline ignorati**: 1 mese

>[!CAUTION]
>
>Le tabelle personalizzate non vengono eliminate con il processo di pulizia standard. Anche se questo potrebbe non essere necessario il primo giorno, non dimenticare di creare un processo di eliminazione per le tabelle personalizzate in quanto ciò potrebbe portare a problemi di prestazioni.

Sono disponibili alcune soluzioni per ridurre al minimo la necessità di record in Adobe Campaign:
* Esporta i dati in un data warehouse esterno ad Adobe Campaign.
* Genera valori aggregati che utilizzeranno meno spazio pur essendo sufficienti per le tue pratiche di marketing. Ad esempio, non è necessaria l’intera cronologia delle transazioni cliente in Adobe Campaign per tenere traccia degli ultimi acquisti.

È possibile dichiarare l&#39;attributo &quot;deleteStatus&quot; in uno schema. È più efficiente contrassegnare il record come eliminato, quindi rimandare l&#39;eliminazione nell&#39;attività di pulizia.

[!DNL :speech_balloon:] In qualità di utente di Cloud Services gestiti, rivolgiti ai consulenti o agli amministratori tecnici di Adobe per ulteriori informazioni sulla fidelizzazione o per impostare la fidelizzazione per le tabelle personalizzate.

## Prestazioni {#performance}

Per garantire prestazioni migliori in qualsiasi momento, segui le best practice riportate di seguito.

### Raccomandazioni generali {#general-recommendations}

* Evitare di utilizzare operazioni come &quot;CONTAINS&quot; nelle query. Se sai cosa ci si aspetta e vuoi filtrare, applica la stessa condizione con un operatore di filtro &quot;EQUAL TO&quot; o con altri operatori di filtro specifici.
* Cerca di assicurarsi che i processi come l&#39;importazione e l&#39;esportazione avvengano al di fuori dell&#39;orario di lavoro.
* Assicurati che ci sia una pianificazione per tutte le attività quotidiane e attieniti alla pianificazione.
* Se uno o pochi dei processi giornalieri non riescono e se è obbligatorio eseguirlo lo stesso giorno, assicurati che non vi siano processi in conflitto in esecuzione quando il processo manuale viene avviato in quanto ciò potrebbe influire sulle prestazioni del sistema.
* Assicurati che nessuna delle campagne giornaliere venga eseguita durante il processo di importazione o quando viene eseguito un processo manuale.
* Utilizzare una o più tabelle di riferimento anziché duplicare un campo in ogni riga. Quando si utilizzano coppie chiave/valore, è preferibile scegliere una chiave numerica.
* Una stringa breve rimane accettabile. Nel caso in cui le tabelle di riferimento siano già presenti in un sistema esterno, il riutilizzo dello stesso agevolerà l’integrazione dei dati con Adobe Campaign.

### Relazioni uno-a-molti {#one-to-many-relationships}

* La progettazione dei dati influisce su usabilità e funzionalità. Se si progetta il modello dati con molte relazioni uno-a-molti, risulta più difficile per gli utenti creare una logica significativa nell’applicazione. La logica di filtro uno-a-molti può essere difficile per gli addetti al marketing non tecnici creare e comprendere correttamente.
* È opportuno disporre di tutti i campi essenziali in una tabella, in quanto semplifica la creazione delle query da parte degli utenti. A volte è anche utile che le prestazioni duplichino alcuni campi tra le tabelle, se è possibile evitare un join.
* Alcune funzionalità integrate non saranno in grado di fare riferimento a relazioni uno-a-molti, ad esempio, formula di ponderazione delle offerte e consegne.

## Tabelle grandi {#large-tables}

Adobe Campaign si basa su motori di database di terze parti. A seconda del provider, l’ottimizzazione delle prestazioni per le tabelle più grandi può richiedere una progettazione specifica.

Di seguito sono riportate alcune best practice comuni da seguire per progettare il modello dati utilizzando tabelle di grandi dimensioni e join complessi.

* Quando utilizzi tabelle dei destinatari personalizzate aggiuntive, assicurati di disporre di una tabella di registro dedicata per ogni mappatura della consegna.
* Ridurre il numero di colonne, in particolare identificando quelle inutilizzate.
* Ottimizza le relazioni del modello dati evitando join complessi, ad esempio join su più condizioni e/o più colonne.
* Per le chiavi di join, è possibile utilizzare valori numerici o basati su stringhe.
* Riduci quanto più possibile la profondità di conservazione del registro. Se hai bisogno di una cronologia più approfondita, puoi aggregare il calcolo e/o gestire tabelle di log personalizzate per memorizzare una cronologia più grande.

### Dimensioni delle tabelle {#size-of-tables}

La dimensione della tabella è una combinazione del numero di record e del numero di colonne per record. Entrambi possono influire sulle prestazioni delle query.

* Una tabella **di piccole dimensioni** è simile alla tabella Consegna.
* Una tabella **di medie dimensioni** ha le stesse dimensioni della tabella Destinatario. Ha un record per cliente.
* Una tabella **di grandi dimensioni** è simile alla tabella di registro Ampio. Ha molti documenti per cliente.
Ad esempio, se il database contiene 10 milioni di destinatari, la tabella di registro Ampio contiene da 100 a 200 milioni di messaggi e la tabella Consegna contiene alcune migliaia di record.

Anche il numero di righe influisce sulle prestazioni. Il database Adobe Campaign non è progettato per memorizzare dati storici non utilizzati attivamente per il targeting o la personalizzazione, si tratta di un database operativo.

Per evitare problemi di prestazioni relativi al numero elevato di righe, conservare solo i record necessari nel database. Qualsiasi altro record deve essere esportato in un data warehouse di terze parti e rimosso dal database operativo Adobe Campaign.

Di seguito sono riportate alcune best practice relative alle dimensioni delle tabelle:

* Progettazione di tabelle di grandi dimensioni con meno campi e più dati numerici.
* Non utilizzare un tipo di colonna con un numero elevato per memorizzare numeri di piccole dimensioni come i valori booleani.
* Rimuovere le colonne non utilizzate dalla definizione della tabella.
* Non conservare i dati storici o inattivi nel database Adobe Campaign (esportazione e pulizia).
