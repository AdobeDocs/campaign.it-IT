---
product: Adobe Campaign
title: Architettura generale
description: Architettura generale di Campaign v8
exl-id: 1d9ff6c5-974d-4a8a-a0d7-641685bbe26e
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '1214'
ht-degree: 2%

---

# Architettura generale{#general-architecture}

La tipica implementazione della soluzione Adobe Campaign consiste dei seguenti componenti:

* **Ambiente client personalizzato**

   Interfaccia grafica intuitiva in cui gli utenti possono comunicare e monitorare le offerte di marketing, creare campagne, rivedere e gestire tutte le attività, i programmi e i piani di marketing, incluse e-mail, flussi di lavoro e pagine di destinazione, creare e gestire i profili dei clienti e creare un pubblico.

* **Ambiente di sviluppo**

   Software lato server che esegue le campagne di marketing attraverso i canali di comunicazione selezionati, inclusi e-mail, SMS, notifiche push, direct mail, web o social, in base alle regole e ai flussi di lavoro definiti nell’interfaccia utente.

* **Contenitori di database**

   In base alla tecnologia di database relazionale, il database di Adobe Campaign Cloud memorizza tutte le informazioni sui clienti, i componenti della campagna, le offerte e i flussi di lavoro, nonché i risultati della campagna nei contenitori di database dei clienti.

## Ambiente client personalizzato {#client-env}

L’accesso all’applicazione può essere effettuato in diversi modi: Integrazione con client avanzati, thin client o API.

* **Console** client: L&#39;interfaccia utente principale dell&#39;applicazione è un&#39;applicazione nativa (su Windows) che comunica con il server dell&#39;applicazione Adobe Campaign con i protocolli Internet standard (SOAP, HTTP, ecc.). La console client di Adobe Campaign consente una produttività semplice e intuitiva, utilizza una larghezza di banda molto ridotta (grazie a una cache locale) ed è progettata per una facile distribuzione. Questa console può essere implementata da un browser Internet, può essere aggiornata automaticamente e non richiede alcuna configurazione di rete specifica in quanto genera solo traffico HTTP(S).

   [!DNL :bulb:] [Ulteriori informazioni sulla console client di Campaign](../start/connect.md).

* **Accesso** Web: parti dell&#39;applicazione sono accessibili tramite un semplice browser web che utilizza un&#39;interfaccia utente HTML, tra cui il modulo di reporting, le fasi di approvazione della consegna, il monitoraggio dell&#39;istanza, ecc.

   [!DNL :bulb:] [Ulteriori informazioni su Campaign Web Access](../start/connect.md).

* **API** di Campaign: In alcuni casi, il sistema può essere chiamato da un’applicazione esterna utilizzando le API dei servizi Web esposte tramite il protocollo SOAP.

   [!DNL :bulb:] [Ulteriori informazioni sulle API di Campaign](../dev/api.md).

## Ambiente di sviluppo {#dev-env}

Adobe Campaign è una piattaforma singola con diverse applicazioni per creare un’architettura aperta e scalabile. La piattaforma Adobe Campaign è scritta su un livello di applicazione flessibile ed è facilmente configurabile per soddisfare le tue esigenze aziendali. L&#39;architettura distribuita garantisce una scalabilità lineare del sistema, che passa da migliaia di messaggi a milioni di messaggi.

Alcuni moduli di Campaign operano continuamente, mentre altri vengono avviati occasionalmente per eseguire attività amministrative (ad esempio per configurare la connessione al database) o per eseguire un’attività ricorrente (ad esempio per consolidare le informazioni di tracciamento).

Esistono tre tipi di moduli Adobe Campaign:

* **Moduli** a più istanze: viene eseguito un singolo processo per tutte le istanze. Questo vale per i seguenti moduli: web, syslogd, trackinglogd e watchdog.
* **Moduli** a istanza mono: viene eseguito un processo per istanza. Questo vale per i seguenti moduli: mta, wfserver, inMail, sms e stat.
* **Moduli** di utilità: si tratta di moduli che vengono eseguiti occasionalmente per eseguire operazioni occasionali o ricorrenti (pulizia, configurazione, download di log di tracciamento, ecc.).

I processi principali sono i seguenti:

**Server applicazioni**  (web nlserver)

Questo processo espone l’intera gamma di funzionalità di Adobe Campaign tramite le API dei servizi web (SOAP / HTTP + XML). Inoltre, può generare in modo dinamico le pagine web utilizzate per l’accesso basato su HTML (rapporti, moduli web, ecc.). Per ottenere questo risultato, questo processo include un server Apache Tomcat JSP. Questo è il processo a cui la console si connette.

**Motore del flusso di lavoro**  (nlserver wfserver)

Esegue i processi del flusso di lavoro definiti nell&#39;applicazione.

Inoltre, gestisce periodicamente i flussi di lavoro tecnici eseguiti, tra cui:

* **Tracciamento**: Recupero e consolidamento dei registri di tracciamento. Consente di recuperare i registri dal server di reindirizzamento e di creare gli indicatori aggregati utilizzati dal modulo di reporting.
* **Pulizia**: Pulizia del database. Utilizzato per eliminare i vecchi record ed evitare la crescita esponenziale del database.
* **Fatturazione**: Invio automatico di un rapporto di attività per la piattaforma (dimensioni del database, numero di azioni di marketing, ecc.).

**Server di consegna**  (nlserver mta)

Adobe Campaign dispone di funzionalità di trasmissione e-mail native. Questo processo funziona come agente di trasferimento della posta SMTP (MTA). Esegue la personalizzazione &quot;uno a uno&quot; dei messaggi e gestisce la loro consegna fisica. Viene eseguito utilizzando i processi di consegna e gestisce i tentativi automatici. Inoltre, quando il tracciamento è abilitato, sostituisce automaticamente gli URL in modo che puntino al server di reindirizzamento.

Questo processo può gestire la personalizzazione e l&#39;invio automatico a un router di terze parti per SMS, fax e direct mail.

**Server di reindirizzamento**  (nlserver webmdl)

Per le e-mail, Adobe Campaign gestisce automaticamente il tracciamento dei clic e delle pagine aperte (il tracciamento transazionale a livello di sito Web è un’ulteriore possibilità). A tal fine, gli URL incorporati nei messaggi e-mail vengono riscritti per puntare a questo modulo, che registra il passaggio dell’utente Internet prima di reindirizzarli all’URL richiesto.

Per garantire la massima disponibilità, questo processo è completamente indipendente dal database: gli altri processi server comunicano con esso utilizzando solo chiamate SOAP (HTTP, HTTP(S) e XML). Tecnicamente, questa funzionalità viene implementata in un modulo di estensione di un server HTTP (estensione ISAPI in IIS, o un modulo DSO Apache, ecc.) ed è disponibile solo in Windows.

Sono inoltre disponibili altri processi più tecnici:

**Gestione delle e-mail non recapitate**  (nlserver inMail)

Questo processo consente di raccogliere automaticamente e-mail dalle cassette postali configurate per ricevere messaggi rimbalzati che vengono restituiti in caso di errore di consegna. Questi messaggi vengono quindi elaborati in base a regole per determinare i motivi della mancata consegna (destinatario sconosciuto, quota superata, ecc.) e per aggiornare lo stato di consegna nel database.

Tutte queste operazioni sono completamente automatiche e preconfigurate.

**Stato di consegna SMS**  (nlserver sms)

Questo processo controlla il router SMS per raccogliere lo stato di avanzamento e aggiornare il database.

**Scrittura dei messaggi di log**  (nlserver syslogd)

Questo processo tecnico acquisisce i messaggi di log e le tracce generate dagli altri processi e li scrive sul disco rigido. Questo rende disponibili ampie informazioni per la diagnosi in caso di problemi.

**Scrittura dei registri di tracciamento**  (nlserver trackinglogd)

Questo processo consente di salvare su disco i registri di tracciamento generati dal processo di reindirizzamento.

**Scrittura di eventi in entrata**  (interazioni nlserver)

Questo processo assicura la registrazione sul disco di eventi in entrata, nel quadro di Interaction.

**Moduli di supervisione**  (nlserver watchdog)

Questo processo tecnico agisce come un processo primario che genera gli altri. Inoltre, li controlla e li riavvia automaticamente in caso di incidenti, mantenendo il massimo tempo di attività del sistema.

**Server**  statistiche (statistica nlserver)

Questo processo mantiene le statistiche sul numero di connessioni, i messaggi inviati per ogni server di posta a cui vengono inviati i messaggi e le relative limitazioni (numero più elevato di connessioni simultanee, messaggi all’ora/e e/o connessione). Consente inoltre di raggruppare più istanze o computer se condividono gli stessi indirizzi IP pubblici.

## Contenitori di database {#db-containers}

Il database di Adobe Campaign Cloud si basa su [!DNL Snowflake] che contiene i dati funzionali (profili, abbonamenti, contenuto, ecc.), i dati tecnici (processi di consegna e registri, registri di tracciamento, ecc.) e i dati di lavoro (acquisti, lead) della soluzione e tutti i componenti di Adobe Campaign comunicano con il database al fine di eseguire le attività specifiche.

I clienti possono implementare Adobe Campaign utilizzando il database e gli schemi predefiniti e, se necessario, questo ambiente predefinito può essere esteso. Tutti i dati all’interno del data mart sono accessibili da Adobe Campaign tramite chiamate SQL. Adobe Campaign fornisce inoltre un complemento completo degli strumenti di estrazione trasformazione e caricamento (ETL) per eseguire l’importazione e l’esportazione di dati all’interno e all’esterno del sistema.

![](assets/data-flow-diagram.png)


>[!CAUTION]
>
>Con **Cloud Services gestiti da Campaign**, l’ambiente e la configurazione iniziale sono stati impostati per Adobe, in base ai termini del contratto di licenza. Non è consentito modificare i pacchetti incorporati, gli schemi o i rapporti incorporati installati.
>
>Se devi utilizzare un componente aggiuntivo Campaign o una funzionalità specifica non disponibile, contatta l’ **Adobe Customer Care**.