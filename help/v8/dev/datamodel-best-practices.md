---
title: Best practice per i modelli di dati
description: Scopri le best practice per l’estensione Campaign Data Model
feature: Data Model
role: User, Developer
level: Beginner, Intermediate
exl-id: bdd5e993-0ce9-49a8-a618-ab0ff3796d49
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '2718'
ht-degree: 4%

---

# Best practice per i modelli di dati {#data-model-best-practices}

Questo documento illustra i consigli chiave durante la progettazione del modello dati di Adobe Campaign.

Il sistema Adobe Campaign è molto flessibile e può essere esteso oltre l’implementazione iniziale. Tuttavia, anche se le possibilità sono infinite, è fondamentale prendere decisioni sagge e creare solide basi per iniziare a progettare il modello di dati.

Per comprendere meglio le tabelle integrate di Campaign e le rispettive relazioni, consulta [questa sezione](datamodel.md).

![](../assets/do-not-localize/glass.png) Leggete [questa sezione](schemas.md) per iniziare a utilizzare gli schemi di Campaign.

![](../assets/do-not-localize/glass.png) Scopri come configurare gli schemi di estensione per estendere il modello dati concettuale del database di Adobe Campaign in [questa pagina](extend-schema.md).

## Architettura del modello dati {#data-model-architecture}

Adobe Campaign è un potente sistema di gestione delle campagne cross-channel che consente di allineare le strategie online e offline per creare esperienze cliente personalizzate.

### Approccio incentrato sul cliente {#customer-centric-approach}

Mentre la maggior parte dei provider di servizi e-mail comunica con i clienti tramite un approccio incentrato sugli elenchi, Adobe Campaign si basa su un database relazionale per sfruttare una visione più ampia dei clienti e dei loro attributi.

Per accedere alla descrizione di ogni tabella, vai a **[!UICONTROL Admin > Configuration > Data schemas]**, seleziona una risorsa dall’elenco e fai clic su **[!UICONTROL Documentation]** scheda.


>[!NOTE]
>
>Adobe Campaign consente di creare un [tabella dei destinatari personalizzata](custom-recipient.md). Tuttavia, nella maggior parte dei casi, si consiglia di sfruttare il [Tabella destinatari](datamodel.md#ootb-profiles) che dispone già di tabelle e funzionalità aggiuntive predefinite.

### Dati per Adobe Campaign {#data-for-campaign}

Quali dati devono essere inviati ad Adobe Campaign? È fondamentale determinare i dati necessari per le attività di marketing.

>[!NOTE]
>
>Adobe Campaign non è né un data warehouse né uno strumento di reporting. Pertanto, non cercare di importare in Adobe Campaign tutti i possibili clienti e le relative informazioni associate, né importare dati che verranno utilizzati solo per creare rapporti.

Per decidere se un attributo sia necessario o meno in Adobe Campaign, chiediti se rientra in una di queste categorie:

* Attributo utilizzato per **segmentazione**
* Attributo utilizzato per **processi di gestione dei dati** (ad esempio, calcolo aggregato).
* Attributo utilizzato per **personalizzazione**

Se non rientra in nessuno di questi, molto probabilmente non avrai bisogno di questo attributo in Adobe Campaign.

### Scelta dei tipi di dati {#data-types}

Per garantire una buona architettura e prestazioni del sistema, segui le best practice riportate di seguito per configurare i dati in Adobe Campaign.

* All’interno di tabelle di grandi dimensioni, puoi inserire campi stringa o numerici e aggiungere collegamenti alle tabelle di riferimento (quando utilizzi un elenco di valori).
* Il **espr** Questo attributo consente di definire un attributo di schema come campo calcolato anziché come valore fisico impostato in una tabella. Questo può consentire l’accesso alle informazioni in un formato diverso (ad esempio per età e data di nascita) senza la necessità di memorizzare entrambi i valori. Questo è un buon modo per evitare la duplicazione dei campi. Ad esempio, la tabella Destinatario utilizza un’espressione per il dominio, che è già presente nel campo e-mail.
* Tuttavia, quando il calcolo dell’espressione è complesso, si sconsiglia di utilizzare il **espr** attributo come calcolo immediato può influire sulle prestazioni delle query.
* Il **XML** Il tipo è un buon modo per evitare di creare troppi campi. ma occupa anche spazio su disco in quanto utilizza una colonna CLOB nel database. Può inoltre causare query SQL complesse e influire sulle prestazioni.
* Lunghezza per un **stringa** deve sempre essere definito con la colonna. Per impostazione predefinita, la lunghezza massima in Adobe Campaign è 16K, ma l’Adobe consiglia di mantenere il campo più corto se sai già che la dimensione non supera una lunghezza più breve.
* È accettabile avere un campo più breve in Adobe Campaign rispetto a quello presente nel sistema di origine se si è certi che la dimensione nel sistema di origine è stata sovrastimata e non sarebbe raggiunta. Questo potrebbe significare una stringa più breve o un numero intero più piccolo in Adobe Campaign.

### Scelta dei campi {#choice-of-fields}

Un campo deve essere memorizzato in una tabella se ha uno scopo di targeting o personalizzazione. In altre parole, se un campo non viene utilizzato per inviare un’e-mail personalizzata o come criterio in una query, occuperà inutilmente spazio su disco.

### Scelta delle chiavi {#choice-of-keys}

Oltre al **autouuid** e **autopk** definite per impostazione predefinita nella maggior parte delle tabelle, è consigliabile aggiungere alcune chiavi logiche o aziendali (numero di conto, numero di client e così via). Può essere utilizzato successivamente per importazioni/riconciliazione o pacchetti di dati. Per ulteriori informazioni, consulta [Identificatori](#identifiers).

Chiavi efficienti sono essenziali per le prestazioni. Con Snowflake è possibile inserire tipi di dati numerici o basati su stringhe come chiavi per le tabelle.

>[!NOTE]
>
>Il **autouuid** attributo applicabile solo a [Distribuzioni aziendali (FFDA)](../architecture/enterprise-deployment.md).

## Identificatori {#identifiers}

Le risorse Adobe Campaign hanno tre identificatori ed è possibile aggiungere un identificatore aggiuntivo.

La tabella seguente descrive tali identificatori e il loro scopo.

| Identificatore | Descrizione | Best practice |
|--- |--- |--- |
| Id | <ul><li>L’ID è la chiave primaria fisica di una tabella Adobe Campaign. Per le tabelle integrate, è un ID universalmente univoco (UUID)</li><li>Questo identificatore deve essere univoco. </li><li>Un UUID può essere visibile in una definizione di schema.</li></ul> | <ul><li>Gli identificatori generati automaticamente non devono essere utilizzati come riferimento in un flusso di lavoro o in una definizione di pacchetto.</li><li>L’ID in una tabella è un UUID e questo tipo non deve essere modificato.</li></ul> |
| Nome (o nome interno) | <ul><li>Queste informazioni sono un identificatore univoco di un record in una tabella. Questo valore può essere aggiornato manualmente, in genere con un nome generato.</li><li>Questo identificatore mantiene il suo valore quando distribuito in un’istanza diversa di Adobe Campaign e non deve essere vuoto.</li></ul> | <ul><li>Rinomina il nome del record generato da Adobe Campaign se l’oggetto deve essere distribuito da un ambiente a un altro.</li><li>Quando un oggetto ha un attributo namespace (*schema* ad esempio), questo spazio dei nomi comune verrà utilizzato in tutti gli oggetti personalizzati creati. Alcuni spazi dei nomi riservati non devono essere utilizzati: *nms*, *xtk*, ecc.  Alcuni spazi dei nomi sono solo interni. [Ulteriori informazioni](schemas.md#reserved-namespaces).</li><li>Quando un oggetto non ha uno spazio dei nomi (*workflow* o *consegna* ad esempio), questa nozione di spazio dei nomi viene aggiunta come prefisso di un oggetto nome interno: *namespaceMyObjectName*.</li><li>Non utilizzare caratteri speciali come lo spazio &quot;&quot;, la semiconna &quot;:&quot; o il trattino &quot;-&quot;. Tutti questi caratteri verrebbero sostituiti da un carattere di sottolineatura &quot;_&quot; (carattere consentito). Ad esempio, &quot;abc-def&quot; e &quot;abc:def&quot; verrebbero memorizzati come &quot;abc_def&quot; e si sovrascriverebbero a vicenda.</li></ul> |
| Etichetta | <ul><li>L’etichetta è l’identificatore aziendale di un oggetto o di un record in Adobe Campaign.</li><li>Questo oggetto consente spazi e caratteri speciali.</li><li>Non garantisce l&#39;univocità di un record.</li></ul> | <ul><li>Si consiglia di determinare una struttura per le etichette degli oggetti.</li><li>Questa è la soluzione più semplice da usare per identificare un record o un oggetto per un utente di Adobe Campaign.</li></ul> |

Nell&#39;ambito di una [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), la chiave primaria di Adobe Campaign è un UUID generato automaticamente per tutte le tabelle integrate. Un UUID può essere utilizzato anche per le tabelle personalizzate. [Ulteriori informazioni](../architecture/keys.md)

Anche se il numero di ID è infinito, è necessario considerare le dimensioni del database per garantire prestazioni ottimali. Per evitare problemi, assicurati di regolare le impostazioni di eliminazione dell’istanza. Per ulteriori informazioni, consulta [questa sezione](#data-retention).


## Chiavi interne personalizzate {#custom-internal-keys}

Le chiavi primarie sono necessarie per ogni tabella creata in Adobe Campaign.

La maggior parte delle organizzazioni importa record da sistemi esterni. Anche se la chiave fisica della tabella dei destinatari è l’attributo &quot;id&quot;, è possibile determinare una chiave personalizzata in aggiunta.

Questa chiave personalizzata è la chiave primaria del record effettivo nel sistema esterno che alimenta Adobe Campaign.

Durante la creazione di una tabella personalizzata, sono disponibili due opzioni:
* Una combinazione di chiave (id) generata automaticamente e chiave interna (personalizzata). Questa opzione è interessante se la chiave di sistema è una chiave composita o non un numero intero. Con Snowflake, i numeri interi o le chiavi basate su stringhe forniranno prestazioni più elevate nelle tabelle di grandi dimensioni e l’unione con altre tabelle.
* Utilizzo della chiave primaria come chiave primaria del sistema esterno. Questa soluzione è in genere preferita in quanto semplifica l’approccio all’importazione e all’esportazione dei dati, con una chiave coerente tra i diversi sistemi. **Autouuid** deve essere disabilitato se la chiave è denominata &quot;id&quot; e deve essere compilata con valori esterni (non generati automaticamente).

>[!CAUTION]
>
>* Un autouuid non deve essere utilizzato come riferimento nei flussi di lavoro.
> * Il **autouuid** attributo applicabile solo a [Distribuzioni aziendali (FFDA)](../architecture/enterprise-deployment.md).
>

## Collegamenti e cardinalità {#links-and-cardinality}

### Collegamenti {#links}

Presta attenzione alla &quot;propria&quot; integrità sulle tabelle di grandi dimensioni. L’eliminazione di record con tabelle di grandi dimensioni con integrità &quot;propria&quot; può potenzialmente arrestare l’istanza. La tabella è bloccata e le eliminazioni vengono eseguite una alla volta. Quindi è meglio usare l&#39;integrità &quot;neutra&quot; su tavoli di bambini che hanno grandi volumi.

Dichiarare un collegamento come join esterno non è un vantaggio in termini di prestazioni. Il record con ID zero emula la funzionalità di join esterno. Nell&#39;ambito di una [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), non è necessario dichiarare join esterni se il collegamento utilizza **autouuid**.

Anche se è possibile unire qualsiasi tabella in un flusso di lavoro, l’Adobe consiglia di definire collegamenti comuni tra le risorse direttamente nella definizione della struttura dati.

Il collegamento deve essere definito in allineamento con i dati effettivi nelle tabelle. Una definizione errata potrebbe influire sui dati recuperati tramite collegamenti, ad esempio duplicando in modo imprevisto i record.

Assegna al collegamento un nome coerente con il nome della tabella: il nome del collegamento dovrebbe aiutare a comprendere cosa è la tabella lontana.

Non denominare un collegamento con &quot;id&quot; come suffisso. Ad esempio, denominalo &quot;transaction&quot; invece di &quot;transactionId&quot;.

Per impostazione predefinita, Adobe Campaign crea un collegamento utilizzando la chiave primaria della tabella esterna. Per maggiore chiarezza, è preferibile definire esplicitamente il join nella definizione del collegamento.

### Cardinalità {#cardinality}

Quando progetti un collegamento, accertati che il record di destinazione sia univoco quando è stata dichiarata una relazione 1-1. In caso contrario, il join può restituire più record quando ne è previsto solo uno. Ciò genera errori durante la preparazione della consegna quando &quot;la query restituisce più righe del previsto&quot;. Imposta il nome del collegamento sullo stesso nome dello schema di destinazione.

Definisci un collegamento con una cardinalità (1-N) nello schema sul lato (N). Ad esempio, la relazione Destinatario (1) - (N) Transazione deve essere definita nello schema della transazione.

Per impostazione predefinita, la cardinalità inversa di un collegamento è (N). È possibile definire un collegamento (1-1) aggiungendo l’attributo revCardinality=&#39;single&#39; alla definizione del collegamento.

Se il collegamento inverso non deve essere visibile all’utente, puoi nasconderlo con la definizione di collegamento revLink=’_NESSUNO_&quot;. Un buon caso d’uso consiste nel definire, ad esempio, un collegamento tra il destinatario e l’ultima transazione completata. È sufficiente visualizzare il collegamento tra il destinatario e l&#39;ultima transazione e non è necessario che dalla tabella delle transazioni sia visibile alcun collegamento inverso.

I collegamenti che eseguono un join esterno (1-0..1) devono essere utilizzati con cautela in quanto influiscono sulle prestazioni del sistema.

## Conservazione dei dati {#data-retention}

Adobe Campaign non è né un data warehouse né uno strumento di reporting. Pertanto, per garantire buone prestazioni della soluzione Adobe Campaign, la crescita del database deve rimanere sotto controllo. Per ottenere questo risultato, segui alcune delle best practice riportate di seguito.

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
>Le tabelle personalizzate non vengono eliminate con il processo di pulizia standard. Anche se questo potrebbe non essere necessario il primo giorno, non dimenticare di creare un processo di eliminazione per le tabelle personalizzate, in quanto ciò potrebbe comportare problemi di prestazioni.

Esistono alcune soluzioni per ridurre al minimo la necessità di record in Adobe Campaign:
* Esporta i dati in un data warehouse esterno a Adobe Campaign.
* Genera valori aggregati che utilizzeranno meno spazio pur essendo sufficienti per le tue pratiche di marketing. Ad esempio, non è necessario disporre della cronologia completa delle transazioni dei clienti in Adobe Campaign per tenere traccia degli ultimi acquisti.

È possibile dichiarare l’attributo &quot;deleteStatus&quot; in uno schema. È più efficiente contrassegnare il record come eliminato, quindi posticipare l’eliminazione nell’attività di pulizia.

![](../assets/do-not-localize/speech.png)  In qualità di utente di Cloud Service gestiti, rivolgiti ai consulenti o agli amministratori tecnici Adobe per ulteriori informazioni sulla conservazione o per impostare la conservazione per tabelle personalizzate.

## Prestazioni {#performance}

Per garantire prestazioni migliori in qualsiasi momento, segui le best practice riportate di seguito.

### Raccomandazioni generali {#general-recommendations}

* Evita di utilizzare operazioni come &quot;CONTAINS&quot; nelle query. Se sai cosa è previsto e desideri filtrare, applica la stessa condizione con un &quot;UGUALE A&quot; o altri operatori di filtro specifici.
* Prova ad assicurarti che i processi come l’importazione e l’esportazione avvengano al di fuori dell’orario di lavoro.
* Assicurati che sia presente una pianificazione per tutte le attività giornaliere e attieniti alla pianificazione.
* Se uno o più processi giornalieri non riescono e se è obbligatorio eseguirli nello stesso giorno, assicurarsi che non vi siano processi in conflitto in esecuzione quando il processo manuale viene avviato, in quanto ciò potrebbe influire sulle prestazioni del sistema.
* Assicurati che nessuna della campagna giornaliera venga eseguita durante il processo di importazione o quando viene eseguito un processo manuale.
* Utilizzare una o più tabelle di riferimento anziché duplicare un campo in ogni riga. Quando si utilizzano coppie chiave/valore, è preferibile scegliere una chiave numerica.
* Una stringa breve rimane accettabile. Se in un sistema esterno sono già presenti tabelle di riferimento, il riutilizzo delle stesse faciliterà l’integrazione dei dati con Adobe Campaign.

### Relazioni uno-a-molti {#one-to-many-relationships}

* La progettazione dei dati influisce su usabilità e funzionalità. Se progetti il modello dati con numerose relazioni uno-a-molti, per gli utenti diventa più difficile creare una logica significativa nell’applicazione. La logica del filtro &quot;uno-a-molti&quot; può essere difficile da costruire e comprendere correttamente per gli esperti di marketing non tecnici.
* È utile disporre di tutti i campi essenziali in una tabella, in quanto consente agli utenti di creare query in modo più semplice. A volte è utile anche per le prestazioni duplicare alcuni campi tra le tabelle, se si può evitare un join.
* Alcune funzionalità integrate non potranno fare riferimento a relazioni uno-a-molti, ad esempio Formula di ponderazione delle offerte e Consegne.

## Tabelle grandi {#large-tables}

Adobe Campaign si basa su motori di database di terze parti. A seconda del provider, l&#39;ottimizzazione delle prestazioni per tabelle di grandi dimensioni può richiedere una progettazione specifica.

Di seguito sono riportate alcune best practice comuni da seguire durante la progettazione del modello dati utilizzando tabelle di grandi dimensioni e join complessi.

* Quando utilizzi tabelle dei destinatari personalizzate aggiuntive, assicurati di disporre di una tabella di registro dedicata per ogni mappatura di consegna.
* Riduci il numero di colonne, in particolare identificando quelle non utilizzate.
* Ottimizza le relazioni del modello dati evitando join complessi, ad esempio join su più condizioni e/o colonne.
* Per le chiavi di join è possibile utilizzare valori numerici o basati su stringhe.
* Riduci il più possibile la profondità di conservazione dei registri. Se hai bisogno di una cronologia più approfondita, puoi aggregare il calcolo e/o gestire tabelle di registro personalizzate per memorizzare una cronologia più ampia.

### Dimensioni delle tabelle {#size-of-tables}

La dimensione della tabella è una combinazione del numero di record e del numero di colonne per record. Entrambi possono influire sulle prestazioni delle query.

* A **di piccole dimensioni** è simile alla tabella Delivery.
* A **dimensioni medie** corrisponde alle dimensioni della tabella Destinatario. Ha un record per cliente.
* A **grande** è simile alla tabella di registro Broad. Dispone di molti record per cliente.
Ad esempio, se il database contiene 10 milioni di destinatari, la tabella di registro Broad contiene circa 100-200 milioni di messaggi e la tabella Delivery contiene alcune migliaia di record.

Il numero di righe influisce anche sulle prestazioni. Il database di Adobe Campaign non è progettato per memorizzare dati storici che non vengono utilizzati attivamente a scopo di targeting o personalizzazione; si tratta di un database operativo.

Per evitare problemi di prestazioni relativi al numero elevato di righe, conserva nel database solo i record necessari. Qualsiasi altro record deve essere esportato in un data warehouse di terze parti e rimosso dal database operativo di Adobe Campaign.

Di seguito sono riportate alcune best practice relative alle dimensioni delle tabelle:

* Progettare tabelle di grandi dimensioni con meno campi e più dati numerici.
* Non utilizzare un tipo di colonna con numero elevato per memorizzare numeri piccoli come i valori booleani.
* Rimuovi le colonne non utilizzate dalla definizione della tabella.
* Non conservare dati storici o inattivi nel database di Adobe Campaign (esportazione e pulizia).
