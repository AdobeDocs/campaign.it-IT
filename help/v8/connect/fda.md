---
title: Utilizzare Campaign e i database esterni (FDA)
description: Scopri come utilizzare Campaign e i database esterni
feature: Federated Data Access
role: Data Engineer
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '1699'
ht-degree: 3%

---

# Federated Data Access (FDA){#gs-fda}

Usa il connettore FDA (Federated Data Access) per collegare Campaign a uno o più **database esterni** e elabora le informazioni archiviate senza influire sui dati del database di Campaign Cloud. Puoi quindi accedere ai dati esterni senza modificare la struttura dei dati di Adobe Campaign.

>[!NOTE]
>
>* I database compatibili per FDA sono elencati in [Matrice di compatibilità](../start/compatibility-matrix.md).
>
>* Nel contesto di un [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), è disponibile un account esterno specifico per gestire la comunicazione tra il database locale di Campaign e il database cloud di Snowflake. Questo account esterno è configurato per l&#39;utente tramite Adobe e non deve essere modificato.
>


L’opzione FDA di Campaign ti consente di estendere il modello dati in un database di terze parti. Rileva automaticamente la struttura delle tabelle di destinazione e utilizza i dati dalle origini SQL.

Specifico **permissions** sono richieste [!DNL Adobe Campaign] e sul database esterno per interagire insieme. Ulteriori informazioni in [questa sezione](#fda-permissions).

## Best practice e limitazioni

* **Ottimizzazione della personalizzazione delle e-mail con dati esterni**

   Puoi preelaborare la personalizzazione dei messaggi in un flusso di lavoro dedicato. Per eseguire questa operazione, utilizza la **[!UICONTROL Prepare the personalization data with a workflow]** disponibile nella **[!UICONTROL Analysis]** scheda delle proprietà di consegna.

   Durante l’analisi della consegna, questa opzione crea ed esegue automaticamente un flusso di lavoro che memorizza in una tabella temporanea tutti i dati collegati alla destinazione, inclusi i dati provenienti da tabelle collegate in un database esterno.

   Questa opzione migliora notevolmente le prestazioni durante l’esecuzione del passaggio di personalizzazione.

* **Limiti FDA**

   L’opzione FDA viene eseguita per manipolare i dati in database esterni in modalità batch nei flussi di lavoro. Per evitare problemi di prestazioni, si sconsiglia di utilizzare il modulo FDA nel contesto di operazioni unitarie, ad esempio: personalizzazione, interazione, messaggistica in tempo reale, ecc.

   Evita le operazioni che devono utilizzare il più possibile sia Adobe Campaign che il database esterno. A questo scopo, puoi:

   * Esporta il database Adobe Campaign nel database esterno ed esegui le operazioni solo dal database esterno prima di reimportare i risultati in Adobe Campaign.

   * Raccogli i dati dal database Adobe Campaign esterno ed esegui le operazioni localmente.

   Se desideri eseguire la personalizzazione nelle consegne utilizzando i dati del database esterno, raccogli i dati da utilizzare in un flusso di lavoro per renderli disponibili in una tabella temporanea. Quindi utilizza i dati della tabella temporanea per personalizzare la consegna.

   L’opzione FDA è soggetta alle limitazioni del sistema di database esterno utilizzato.


## Passaggi di configurazione{#fda-configuration-steps}

Per impostare l&#39;accesso a un database esterno con FDA, i passaggi di configurazione sono i seguenti:

1. In qualità di utente di Adobe Managed Services, contatta l’Adobe per installare i driver nell’istanza Campaign.
1. Una volta installati i driver, configura l&#39;account esterno corrispondente al database sul server Adobe Campaign e verifica l&#39;account esterno. [Ulteriori informazioni](#fda-external-account)
1. Crea lo schema del database esterno in Adobe Campaign. Ciò ti consente di identificare la struttura dati del database esterno. [Ulteriori informazioni](#create-data-schema)

<!--
1. If needed, create a new target mapping from the previously created schema. This is required if the recipients of your deliveries come from the external database. This implementation comes with limitations related to message personalization. [Learn more](#define-data-mapping)
-->

Tieni presente che con Campaign [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), non è possibile creare una mappatura di destinazione da uno schema memorizzato in un database esterno a cui si accede da FDA. Di conseguenza, i destinatari delle consegne non possono provenire dal database esterno.

## Account esterno database esterno esterno{#fda-external-account}

Devi creare un account esterno specifico per collegare l’istanza Campaign al database esterno.

A questo scopo, segui i passaggi seguenti:

1. Da campagna **[!UICONTROL Explorer]**, sfoglia fino a **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

1. Fai clic su **[!UICONTROL New]**.

   >[!NOTE]
   >
   > Per essere attivo, il **[!UICONTROL Enabled]** deve essere selezionata. Se necessario, deselezionare questa opzione per disabilitare l&#39;accesso a questo database senza eliminarne la configurazione.

1. Seleziona **[!UICONTROL External database]** come account esterno **[!UICONTROL Type]**.

1. Scegli il database esterno nell’elenco a discesa e configura l’account esterno. È necessario specificare:

   * **[!UICONTROL Server]**: URL del server

   * **[!UICONTROL Account]**: Nome dell’utente

   * **[!UICONTROL Password]**: Password account utente

   * **[!UICONTROL Database]**: Nome del database

      ![](assets/snowflake.png)

1. Fai clic sul pulsante **[!UICONTROL Parameters]** quindi seleziona **[!UICONTROL Deploy functions]** per creare funzioni.

1. Una volta immessi i parametri, fai clic sul pulsante **[!UICONTROL Test the connection]** per approvarli.

1. Per consentire ad Adobe Campaign di accedere a questo database, è necessario distribuire le funzioni SQL. Fai clic sul pulsante **[!UICONTROL Parameters]** quindi seleziona **[!UICONTROL Deploy functions]** pulsante .

È possibile definire tablespace di lavoro specifiche per le tabelle e per l&#39;indice nel **[!UICONTROL Parameters]** scheda .

Per [!DNL Snowflake], il connettore supporta le seguenti opzioni:

| Opzione | Descrizione |
|---|---|
| schema di lavoro | Schema di database da utilizzare per le tabelle di lavoro |
| magazzino | Nome del magazzino predefinito da utilizzare. Sostituirà il valore predefinito dell’utente. |
| TimeZoneName | Per impostazione predefinita è vuoto e indica che viene utilizzato il fuso orario del sistema dell’app server Campaign Classic. L’opzione può essere utilizzata per forzare il parametro di sessione TIMEZONE. <br>Per ulteriori informazioni, consulta [questa pagina](https://docs.snowflake.net/manuals/sql-reference/parameters.html#timezone). |
| WeekStart | Parametro di sessione WEEK_START. Per impostazione predefinita, è impostato su 0. <br>Per ulteriori informazioni, consulta [questa pagina](https://docs.snowflake.com/en/sql-reference/parameters.html#week-start). |
| UseCachedResult | Parametro di sessione USE_CACHED_RESULTS . Per impostazione predefinita, è impostato su TRUE. Questa opzione può essere utilizzata per disabilitare i risultati della cache del Snowflake. <br>Per ulteriori informazioni, consulta [questa pagina](https://docs.snowflake.net/manuals/user-guide/querying-persisted-results.html). |


## Creare lo schema dati{#create-data-schema}

Per creare lo schema del database esterno in Adobe Campaign, effettua le seguenti operazioni:

1. Fai clic sul pulsante **[!UICONTROL New]** pulsante sopra l’elenco degli schemi di dati e scegli **[!UICONTROL Access external data]**.

   ![](assets/wf_new_schema_fda.png)

1. Immetti un nome e una descrizione per lo schema e seleziona l’account esterno che abiliterà la connessione al database. Ciò consente l’accesso all’elenco delle tabelle disponibili nella base esterna. Scegliere la tabella contenente i dati da raccogliere.

   ![](assets/wf_new_schema_select_table_fda.png)

1. Fai clic su **[!UICONTROL OK]** per confermare. Adobe Campaign rileva automaticamente la struttura della tabella selezionata e genera lo schema logico. Tieni presente che Adobe Campaign non genera collegamenti.

1. Fai clic su **[!UICONTROL Save]** per confermare la creazione.

<!-- 
## Define the target mapping{#define-data-mapping}

You can define a mapping on the data in an external table.

To do this, once the schema of the external table has been created, you need to create a new delivery mapping to use the data in this table as a delivery target.

To do this, follow these steps:

1. Browse to **[!UICONTROL Administration]** `>` **[!UICONTROL Campaign Management]** `>` **[!UICONTROL Target mappings]** from Adobe Campaign explorer.

1. Create a new target mapping and select the schema you just created as the targeting dimension.

   ![](assets/new-target-mapping.png)


1. Indicate the fields where the delivery information is stored (last name, first name, email, address, etc.).

   ![](assets/wf_new_mapping_define_join.png)

1. Specify the parameters for information storage, including the suffix of the extension schemas for them to be easily identifiable.

   ![](assets/wf_new_mapping_define_names.png)

   You can choose whether to store exclusions (**excludelog**), with messages (**broadlog**) or in a separate table.

   You can also choose whether to manage tracking for this delivery mapping (**trackinglog**).

1. Then select the extensions to be taken into account. The extension type depends on your platform's parameters and options (view your license contract).

   ![](assets/wf_new_mapping_define_extensions.png)

   Click the **[!UICONTROL Save]** button to launch delivery mapping creation: all linked tables are created automatically based on the selected parameters.
-->

## Autorizzazioni{#fda-permissions}

Specifico **permissions** sono richieste [!DNL Adobe Campaign] e sul database esterno per interagire insieme.

In primo luogo, affinché l&#39;utente possa eseguire operazioni su un database esterno tramite FDA, l&#39;operatore deve avere un diritto specifico denominato in [!DNL Adobe Campaign].

1. Seleziona la **[!UICONTROL Administration > Access Management > Named Rights]** in Adobe Campaign Explorer.
1. Crea un nuovo diritto specificando l’etichetta selezionata.
1. Immettere il nome del diritto denominato nel formato seguente **utente:base@server**, dove :

   * **user** è il nome dell&#39;utente nel database esterno
   * **base** è il nome del database esterno
   * **server** è il nome del server di database esterno

1. Salva il diritto con nome e collegalo all’operatore scelto dal **[!UICONTROL Administration > Access Management > Operators]** nodo di Adobe Campaign explorer.

Quindi, per elaborare i dati contenuti in un database esterno, l&#39;operatore Adobe Campaign deve disporre di almeno le autorizzazioni &quot;Write&quot; sul database per poter creare tabelle di lavoro. Queste tabelle vengono eliminate automaticamente da Adobe Campaign.

Sono necessarie le seguenti autorizzazioni:

* **CONNECT**: connessione al database remoto
* **LEGGI i dati**: accesso in sola lettura alle tabelle contenenti i dati dei clienti
* **LEGGI &#39;MetaData&#39;**: accesso ai cataloghi di dati del server per ottenere la struttura della tabella
* **CARICA**: carico di massa nelle tabelle di lavoro (richiesto quando si lavora su raccolte e giunti)
* **CREA/RILASCIA** per **TABELLA/INDICE/PROCEDURA/FUNZIONE** (solo per tabelle di lavoro generate da Adobe Campaign)
* **SPIEGARE** (consigliato): per il monitoraggio delle prestazioni in caso di problemi
* **SCRIVERE i dati** (a seconda dello scenario di integrazione)

L’amministratore del database deve fare in modo che questi diritti corrispondano ai diritti specifici di ciascun motore di database, come descritto di seguito.

|   | Snowflake |  Amazon Redshift |
|:-:|:-:|:-:|
| **Connessione al database remoto** | UTILIZZO SU WAREHOUSE, UTILIZZO SU DATABASE E UTILIZZO SU privilegi SCHEMA | Creazione di un utente collegato all’account AWS |
| **Creazione di tabelle** | CREA IL privilegio TABELLA SU SCHEMA | Privilegio CREATE |
| **Creazione degli indici** | N/D | Privilegio CREATE |
| **Creazione di funzioni** | CREA FUNZIONE SUL privilegio SCHEMA | UTILIZZARE IL privilegio plpythonu LINGUAGE per poter chiamare script python esterni |
| **Creazione di procedure** | N/D | UTILIZZARE IL privilegio di pitone LINGUISTICO per poter chiamare script di pitone esterni |
| **Rimozione di oggetti (tabelle, indici, funzioni, procedure)** | Proprietario dell&#39;oggetto | Proprietario dell&#39;oggetto o utente avanzato |
| **Monitoraggio delle esecuzioni** | Privilegio MONITOR sull&#39;oggetto richiesto | Nessun privilegio richiesto per l&#39;utilizzo del comando EXPLAIN |
| **Scrittura dei dati** | Privilegi INSERT e/o UPDATE (a seconda dell&#39;operazione di scrittura) | Privilegi INSERT e UPDATE |
| **Caricamento dei dati nelle tabelle** | CREA FASE SU SCHEMA, SELEZIONA e INSERISCI sui privilegi della tabella di destinazione | Privilegi SELECT e INSERT |
| **Accesso ai dati client** | SELEZIONARE (FUTURO) TABELLA(I) o privilegio(i) VISUALIZZAZIONE(I) | Privilegio SELECT |
| **Accesso ai metadati** | SELEZIONARE il privilegio SCHEMA INFORMATION_SCHEMA | Privilegio SELECT |


## Utilizzare dati esterni in un flusso di lavoro

Una volta creato lo schema di dati, i dati possono essere elaborati nei flussi di lavoro Adobe Campaign.

Attività multiple consentono di interagire con i dati provenienti da un database esterno:

* **Filtrare dati esterni** - **[!UICONTROL Query]** l’attività ti consente di aggiungere dati esterni e di utilizzarli nelle configurazioni di filtro definite.

* **Creare sottoinsiemi** - **[!UICONTROL Split]** consente di creare sottoinsiemi. Puoi utilizzare dati esterni per definire i criteri di filtro da utilizzare.

* **Carica database esterno** - Puoi utilizzare i dati esterni nella **[!UICONTROL Data loading (RDBMS)]** attività.

* **Aggiunta di informazioni e collegamenti** - **[!UICONTROL Enrichment]** consente di aggiungere dati aggiuntivi alla tabella di lavoro del flusso di lavoro e collegamenti a una tabella esterna. In questo contesto, può utilizzare dati provenienti da un database esterno.


Puoi anche definire direttamente una connessione a un database esterno da queste attività del flusso di lavoro, per un utilizzo temporaneo. In questo caso, si trova in un database esterno locale, riservato all’interno di un flusso di lavoro corrente: non verrà salvato negli account esterni.

>[!CAUTION]
>
>Questo tipo di configurazione deve essere utilizzato solo temporaneamente per raccogliere i dati. La configurazione dell’account esterno deve essere preferita per qualsiasi altro utilizzo.

Ad esempio, nella **[!UICONTROL Query]** attività, puoi definire una connessione temporanea a un database esterno come segue:

1. Apri l’attività e fai clic su **[!UICONTROL Add data...]**
1. Seleziona la **[!UICONTROL External data]** options
1. Seleziona la **[!UICONTROL Locally defining the data source]** opzione
1. Selezionare il motore di database di destinazione nell&#39;elenco a discesa. Immetti il nome del server e fornisci i parametri di autenticazione. Specifica anche il nome del database esterno.
1. Selezionare la tabella in cui sono memorizzati i dati. È possibile immettere il nome della tabella direttamente nel campo corrispondente oppure fare clic sull&#39;icona di modifica per accedere all&#39;elenco delle tabelle del database.
1. Fai clic sul pulsante **[!UICONTROL Add]** per definire uno o più campi di riconciliazione tra i dati del database esterno e i dati del database Adobe Campaign. La **[!UICONTROL Edit expression]** icone **[!UICONTROL Remote field]** e **[!UICONTROL Local field]** consente di accedere all’elenco dei campi di ciascuna tabella.
1. Se necessario, specifica una condizione di filtro e la modalità di ordinamento dei dati.
1. Selezionare i dati aggiuntivi da raccogliere nel database esterno. A questo scopo, fai doppio clic sui campi che desideri aggiungere per visualizzarli nel **[!UICONTROL Output columns]**.
1. Fai clic su **[!UICONTROL Finish]** per confermare questa configurazione.
