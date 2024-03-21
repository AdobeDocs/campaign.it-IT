---
title: Architettura generale
description: Scopri l’architettura e i componenti di Adobe Campaign. Ulteriori informazioni sulla personalizzazione della console client e dell’ambiente.
feature: Architecture, Deployment
role: Admin, Developer
level: Beginner
exl-id: 1d9ff6c5-974d-4a8a-a0d7-641685bbe26e
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '1136'
ht-degree: 7%

---

# Architettura generale{#general-architecture}

La tipica distribuzione della soluzione Adobe Campaign è costituita dai seguenti componenti:

* **Ambiente client personalizzato**

  Interfaccia grafica intuitiva che consente agli utenti di comunicare e tenere traccia delle offerte di marketing, creare campagne, rivedere e gestire tutte le attività, i programmi e i piani di marketing, inclusi e-mail, flussi di lavoro e pagine di destinazione, creare e gestire profili cliente e creare tipi di pubblico.

* **Ambiente di sviluppo**

  Software lato server che esegue le campagne di marketing tramite canali di comunicazione scelti, tra cui e-mail, SMS, notifiche push, direct mail, web o social, in base alle regole e ai flussi di lavoro definiti nell’interfaccia utente.

* **Contenitori database**

  Basato sulla tecnologia del database relazionale, Adobe Campaign Cloud Database memorizza tutte le informazioni, i componenti della campagna, le offerte, i flussi di lavoro e i risultati della campagna in contenitori di database.

## Ambiente client personalizzato {#client-env}

È possibile accedere all’applicazione in diversi modi: tramite interfaccia utente web, console client (rich client), accesso web (thin client) o integrazione API.

[Ulteriori informazioni sull’interfaccia utente di Campaign](../start/campaign-ui.md).

## Ambiente di sviluppo {#dev-env}

Adobe Campaign è un&#39;unica piattaforma con diverse applicazioni che consente di creare un&#39;architettura aperta e scalabile. La piattaforma Adobe Campaign è scritta su un livello di applicazione flessibile ed è facilmente configurabile per soddisfare le esigenze aziendali. L&#39;architettura distribuita garantisce scalabilità lineare del sistema, da migliaia di messaggi a milioni di messaggi.

Alcuni moduli di Campaign funzionano in modo continuo, mentre altri vengono avviati occasionalmente per eseguire attività amministrative (ad esempio per configurare la connessione al database) o per eseguire un’attività ricorrente (ad esempio per consolidare le informazioni di tracciamento).

Esistono tre tipi di moduli Adobe Campaign:

* **Moduli a più istanze**: viene eseguito un singolo processo per tutte le istanze. Questo vale per i seguenti moduli: web, syslogd, trackinglogd e watchdog.
* **Moduli a istanza singola**: viene eseguito un processo per istanza. Questo vale per i seguenti moduli: mta, wfserver, inMail, sms e stat.
* **Moduli di utilità**: si tratta di moduli eseguiti occasionalmente per eseguire operazioni occasionali o ricorrenti (pulizia, configurazione, download dei registri di tracciamento, ecc.).

I processi principali sono i seguenti:

* **Server applicazioni** (nlserver web) - Questo processo espone l’intera gamma di funzionalità di Adobe Campaign tramite API di servizi web (SOAP / HTTP + XML). Inoltre, può generare in modo dinamico le pagine web utilizzate per l’accesso basato su HTML (report, moduli web, ecc.). Per ottenere questo risultato, questo processo include un server Apache Tomcat JSP. Questo è il processo a cui si connette la console.

* **Motore flusso di lavoro** (nlserver wfserver): questo processo esegue i processi del flusso di lavoro definiti nell&#39;applicazione. Gestisce inoltre flussi di lavoro tecnici eseguiti periodicamente, tra cui:

   * **Tracciamento**: recupera e consolida i registri di tracciamento, in modo da poterli recuperare dal server di reindirizzamento e creare gli indicatori aggregati utilizzati dal modulo di reporting.
   * **Pulizia**: pulisce il database ed elimina i record obsoleti ed evita una crescita esponenziale del database.
   * **Fatturazione**: invia un rapporto di attività per la piattaforma (dimensioni del database, numero di azioni di marketing, ecc.).

* **Server di consegna** (mta nlserver) - Adobe Campaign dispone di funzionalità di trasmissione e-mail native. Questo processo funziona come agente di trasferimento di posta SMTP (MTA). Esegue la personalizzazione &quot;uno a uno&quot; dei messaggi e ne gestisce la consegna fisica. Viene eseguito utilizzando processi di consegna e gestisce i tentativi automatici. Inoltre, quando il tracciamento è abilitato, sostituisce automaticamente gli URL in modo che puntino al server di reindirizzamento. Questo processo può gestire la personalizzazione e l’invio automatico a un router di terze parti per SMS, fax e direct mail.

* **Server di reindirizzamento** (nlserver webmdl): per le e-mail, Adobe Campaign gestisce automaticamente il tracciamento di aperture e clic (un’ulteriore possibilità è il tracciamento transazionale a livello di sito web). A questo scopo, gli URL incorporati nei messaggi e-mail vengono riscritti in modo da puntare a questo modulo, che registra il passaggio dell’utente Internet prima di reindirizzarlo all’URL richiesto.

  Per garantire la massima disponibilità, questo processo è completamente indipendente dal database: gli altri processi server comunicano con esso utilizzando solo chiamate SOAP (HTTP, HTTP(S) e XML). Tecnicamente, questa funzionalità viene implementata in un modulo di estensione di un server HTTP (estensione ISAPI in IIS, o un modulo Apache DSO, ecc.) ed è disponibile solo in Windows.

Sono disponibili anche altri processi più tecnici:

* **Gestione delle e-mail non recapitate** (nlserver inMail) - Questo processo consente di raccogliere automaticamente le e-mail dalle cassette postali configurate per ricevere messaggi non recapitati restituiti in caso di errore di consegna. Questi messaggi vengono quindi sottoposti a elaborazione basata su regole per determinare i motivi della mancata consegna (destinatario sconosciuto, quota superata, ecc.) e per aggiornare lo stato di consegna nel database. Tutte queste operazioni sono completamente automatiche e preconfigurate.

* **Stato della consegna SMS** (nlserver sms) - Questo processo esegue il polling del router SMS per raccogliere lo stato di avanzamento e aggiornare il database.

* **Scrittura di messaggi di registro** (nlserver syslogd) - Questo processo tecnico acquisisce i messaggi di registro e le tracce generate dagli altri processi e li scrive sul disco rigido. In questo modo è possibile disporre di numerose informazioni per la diagnosi in caso di problemi.

* **Scrittura dei registri di tracciamento** (nlserver trackinglogd) - Questo processo salva su disco i registri di tracciamento generati dal processo di reindirizzamento.

* **Scrittura di eventi in entrata** (nlserver interaction) - Questo processo garantisce la registrazione sul disco degli eventi in entrata, nel quadro di Interaction.

* **Supervisione dei moduli** (watchdog nlserver): questo processo tecnico agisce come processo primario che genera gli altri. Vengono inoltre monitorati e riavviati automaticamente in caso di problemi, mantenendo così il massimo tempo di attività del sistema.

* **Server statistiche** (nlserver stat) - Questo processo mantiene statistiche sul numero di connessioni, sui messaggi inviati per ciascun server di posta a cui vengono inviati i messaggi, nonché sulle relative limitazioni (numero massimo di connessioni simultanee, messaggi all’ora/ e/o connessione). Consente inoltre di federare più istanze o computer se condividono gli stessi indirizzi IP pubblici.


## Contenitori database {#db-containers}

Nel suo [Distribuzione aziendale (FFDA)](enterprise-deployment.md), il database di Adobe Campaign Cloud si basa su [!DNL Snowflake] che contiene i dati funzionali (profili, abbonamenti, contenuti, ecc.), i dati tecnici (processi e registri di consegna, registri di tracciamento, ecc.) e i dati di lavoro (acquisti, lead) della soluzione e tutti i componenti di Adobe Campaign comunicano con il database per eseguire le attività specifiche.

Puoi distribuire Adobe Campaign utilizzando il database e gli schemi predefiniti e, se necessario, estendere questo ambiente predefinito. Adobe Campaign accede a tutti i dati all’interno del data mart tramite chiamate SQL. Adobe Campaign fornisce inoltre una serie completa di strumenti ETL (Extract Transform and Load) per eseguire l’importazione e l’esportazione dei dati all’interno e all’esterno del sistema.

![](assets/data-flow-diagram.png)


>[!CAUTION]
>
>Con **Campaign Managed Cloud Services**, l’ambiente e la configurazione iniziale sono stati impostati da Adobe, in base ai termini del contratto di licenza. Non ti è consentito modificare i pacchetti, gli schemi e i report integrati.
>
>Se hai la necessità di utilizzare un componente aggiuntivo di Campaign o una funzionalità specifica non fornita, contatta l’**Assistenza clienti di Adobe**.

## Archiviazione del database {#db-storage}

Lo spazio di archiviazione totale è suddiviso tra il database principale e il database secondario di Snowflake (facoltativo). La posizione in cui vengono memorizzati i dati deve essere determinata al momento dell’implementazione o dell’aggiornamento, in base ai casi d’uso specifici per il cliente.

Scopri come monitorare l’utilizzo del database in [Documentazione del Pannello di controllo Campaign della campagna](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring/database-monitoring.html){target="_blank"}.