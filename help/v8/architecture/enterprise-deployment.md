---
title: Guida introduttiva all’implementazione FFDA di Campaign
description: Guida introduttiva all’implementazione FFDA di Campaign
feature: Overview
role: Data Engineer
level: Beginner
source-git-commit: 13d19f0052880c0b0930e96441163f26038c071a
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 53%

---

# [!DNL Campaign] Distribuzione FFDA{#gs-ac-ffda}

Sfruttando [[!DNL Snowflake]](https://www.snowflake.com/), una tecnologia di database cloud, l’implementazione di Adobe Campaign Enterprise Full Federated Access (FFDA) migliora notevolmente la sua scala e velocità, con la possibilità di gestire un numero più significativo di profili cliente, oltre a tassi di consegna e transazioni molto più elevati all’ora.

## Vantaggi {#ffda-benefits}

Campaign v8 Enterprise (FFDA) porta la scala end-to-end in qualsiasi fase del processo, dal targeting al reporting finale:

* Scalabilità del volume di dati gestibile (fino a 8 TB)
* Scalabilità delle prestazioni delle query per la segmentazione e il targeting, oltre che per l’acquisizione e l’uscita dei dati
* Scalabilità della preparazione della consegna (da ore a minuti)

Questo è un cambiamento fondamentale nell’architettura del software. Adesso i dati sono remoti e Campaign unisce tutti i dati, inclusi i profili. I processi di [!DNL Campaign] ora vengono scalati in modalità end-to-end, dal targeting all’esecuzione dei messaggi: in genere l’acquisizione dei dati, la segmentazione, il targeting, le query e le consegne vengono eseguite in pochi minuti. Questa nuova versione risolve l’intera sfida della scalabilità mantenendo lo stesso livello di flessibilità ed estensibilità. Il numero di profili è quasi illimitato e la conservazione dei dati può essere estesa.

L’archiviazione cloud viene eseguita in **[!DNL Snowflake]**: un nuovo **account esterno** integrato garantisce la connettività con il database cloud. È configurato da Adobe e non deve essere modificato. [Ulteriori informazioni](../config/external-accounts.md)

Le tabelle o gli schemi integrati che devono essere spostati o replicati nel database cloud hanno un’estensione di schema integrato nello spazio dei nomi **xxl**. Tali estensioni contengono eventuali modifiche necessarie per spostare gli schemi integrati dal database locale di [!DNL Campaign] al database cloud [!DNL Snowflake] e per adattarne di conseguenza la struttura: nuovo UUID, collegamenti aggiornati, ecc.

>[!CAUTION]
>
> I dati dei clienti non vengono memorizzati nel database locale di [!DNL Campaign]. Di conseguenza, eventuali tabelle personalizzate devono essere create nel database cloud.

## Architettura Campaign Enterprise (FFDA){#ffda-archi}

In un [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] v8 funziona con due database: locale [!DNL Campaign] database per la messaggistica in tempo reale e le query unitarie dell’interfaccia utente e per la scrittura tramite API e un cloud [!DNL Snowflake] database per l’esecuzione della campagna, le query batch e l’esecuzione del flusso di lavoro.

Campaign v8 Enterprise introduce il concetto di **Accesso completo ai dati federati** (FFDA): tutti i dati sono ora remoti nel database cloud.

Sono disponibili API specifiche per la gestione dei dati tra il database locale e quello cloud. Per scoprire come funzionano queste nuove API e come utilizzarle, visita [questa pagina](new-apis.md).

La comunicazione generale tra server e processi viene eseguita secondo il seguente schema:

![](assets/architecture.png)

* I moduli di esecuzione e gestione dei messaggi non recapitati sono disabilitati nell’istanza.
* L’applicazione è configurata per eseguire l’esecuzione dei messaggi su un server remoto &quot;mid-sourced&quot;, gestito utilizzando chiamate SOAP (su HTTP o HTTPS).

La [!DNL Snowflake] database sul lato marketing viene utilizzato per:

* Archivia tutti i dati dei clienti: profili, dati personalizzati quali transazioni, prodotti, posizioni, ecc.
* Memorizza tutti gli eventi e i dati di comportamento generati o raccolti da Campaign, come registri di consegna, registri di tracciamento, registrazioni push, ecc.
* Memorizza tutti gli aggregati di dati di cui sopra.
* Memorizza una copia (h+1) delle tabelle di riferimento (come consegne, enumerazioni, paesi, ecc.) utilizzati nei flussi di lavoro, nelle campagne e nei rapporti.
* Esegui tutti i processi e i carichi di lavoro batch


Il database PostgreSQL nell&#39;istanza di marketing viene utilizzato per:

* Esegui alcuni carichi di lavoro, ad esempio API per volumi ridotti.
* Archivia tutti i dati di Campaign, comprese le impostazioni di consegna e campagna, il flusso di lavoro e le definizioni dei servizi.
* Memorizza tutte le tabelle di riferimento integrate (enumerazioni, paesi, ecc.) che vengono replicati in [!DNL Snowflake].

   Tuttavia, non puoi:
   * creare personalizzazioni per i dati dei clienti, ad esempio non creare una tabella di famiglia in PostgreSQL, ma solo in Snowflake
   * archivia eventuali registri di consegna, registri di tracciamento, ecc. sulla dimensione di targeting FFDA.
   * memorizza grandi volumi di dati.


Il database PostgreSQL nell&#39;istanza di mid-sourcing viene utilizzato per:

* Esegui consegne batch e in tempo reale (RT).
* Invio di registri di consegna e di tracciamento : gli ID di registro di consegna e di tracciamento sono UUID e non ID a 32 bit.
* Raccogliere e memorizzare i dati di tracciamento.


## Impatto{#ffda-impacts}

### [!DNL Campaign] Meccanismo di staging per le API{#staging-api}

Con [!DNL Campaign] Database cloud, le chiamate unitarie di esplosione non sono raccomandate a causa delle prestazioni (latenza e concorrenza). L&#39;operazione batch è sempre preferita. Per garantire prestazioni ottimali delle API, Campaign continua a gestire le chiamate API a livello di database locale.

![](../assets/do-not-localize/glass.png) [Il meccanismo di staging API è descritto in questa pagina](staging.md)

### Nuove API{#new-apis}

Sono disponibili nuove API per gestire la sincronizzazione dati tra [!DNL Campaign] database locale e database cloud. È stato inoltre introdotto un nuovo meccanismo per gestire le chiamate API a livello di database locale per evitare la latenza e migliorare le prestazioni complessive.

![](../assets/do-not-localize/glass.png) [Le nuove API sono descritte in dettaglio in questa pagina](new-apis.md)


### Replica dei dati{#data-replication}

Un flusso di lavoro tecnico specifico gestisce la replica delle tabelle che devono essere presenti su entrambi i lati (database Cloud e database locale di Campaign). Questo flusso di lavoro viene attivato ogni ora e si basa su una nuova libreria JavaScript integrata.

>[!NOTE]
>
> Sono stati creati diversi criteri di replica in base alle dimensioni della tabella (XS, XL, eccetera).
> Alcune tabelle vengono replicate in tempo reale, altre vengono replicate su base oraria. Alcune tabelle avranno aggiornamenti incrementali, altre avranno un aggiornamento completo.

[Ulteriori informazioni sulla replica dei dati](replication.md)

### Gestione ID{#id-mgt-ffda}

Ora gli oggetti di Campaign v8 utilizzano un **ID universalmente univoco (UUID)**, che consente l’identificazione dei dati tramite valori univoci illimitati.

Tieni presente che questo ID è basato su stringhe e non è sequenziale. La chiave primaria non è un valore numerico in Campaign v8 e devi utilizzare gli attributi **autouuid** e **autopk** negli schemi.

In Campaign Classic v7 e versioni precedenti, l’unicità di una chiave all’interno di uno schema (ovvero una tabella) viene gestita a livello di motore del database. Più in generale, i motori di database classici come PostgreSQL, Oracle o SQL Server includono un meccanismo nativo per impedire l’inserimento di righe duplicate basate su una colonna o su un set di colonne attraverso l’uso di chiavi primarie e/o indici univoci. Quando l’indice e le chiavi primarie sono impostati correttamente a livello di database, l’ID duplicato non esiste in queste versioni.

Adobe Campaign v8 viene fornito con Snowflake come database di base. Poiché aumenta notevolmente la scalabilità delle query, l’architettura distribuita del database Snowflake non fornisce i meccanismi che consentono di gestire e dunque applicare l’unicità di una chiave all’interno di una tabella. Di conseguenza, in Adobe Campaign v8, è possibile effettuare l’inserimento di chiavi duplicate all’interno di una tabella. Gli utenti finali sono ora responsabili di garantire la coerenza delle chiavi all’interno del database di Adobe Campaign. [Ulteriori informazioni](keys.md)

**Argomenti correlati**

* [Best practice per i modelli di dati](../dev/datamodel-best-practices.md)
