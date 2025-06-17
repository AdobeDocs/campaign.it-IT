---
title: Informazioni sui componenti e sui processi di Campaign
description: Informazioni sui componenti e sui processi di Campaign
feature: Overview, Architecture, Configuration
role: User
level: Beginner
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: e4f6c70ecdcf7414b5f49a43933cfd1c967a0905
workflow-type: ht
source-wordcount: '637'
ht-degree: 100%

---

# Informazioni sui componenti e sui processi di Campaign {#components-and-processes}

Adobe Campaign è una soluzione di marketing cross-channel che automatizza le campagne e-mail, su dispositivi mobili, social e offline. Adobe Campaign fornisce una posizione centrale per accedere ai dati e ai profili della clientela. Utilizza Adobe Campaign per orchestrare esperienze coerenti per la clientela, progettare, eseguire e personalizzare il marketing tra canali diversi, migliorando al contempo le esperienze cliente su ogni dispositivo e punto di contatto. Con Adobe Campaign, puoi gestire più origini dati, definire i segmenti di pubblico, pianificare ed eseguire campagne cross-channel in più passaggi tramite un’interfaccia visiva con trascinamento per i flussi di lavoro.

Ulteriori informazioni sulle funzionalità chiave di Campaign sono disponibili [in questa pagina](../start/get-started.md).

## Componenti di Campaign {#ac-components}

Di seguito sono descritti i componenti e l’architettura globale di Adobe Campaign.

![](assets/do-not-localize//ac-components.png)

### Livello di presentazione{#presentation-layer}

Puoi accedere ad Adobe Campaign tramite un client avanzato, un thin client o un’integrazione API.

* Client avanzato

  Il client avanzato di Campaign è un’applicazione nativa che comunica con il server applicazioni di Adobe Campaign tramite protocolli Internet standard, come SOAP e HTTP. [Ulteriori informazioni sulla console client di Campaign](../start/connect.md).

* Thin client

  Le funzionalità di accesso web di Adobe Campaign consentono di accedere a un sottoinsieme di funzioni di Campaign con un browser web, utilizzando un’interfaccia utente HTML. Utilizza questa interfaccia web per accedere ai rapporti, verificare e convalidare i messaggi, accedere alle dashboard di monitoraggio e altro ancora.  [Ulteriori informazioni sull’accesso a Campaign Web](../start/connect.md).

* Applicazioni esterne con API

  In alcuni casi, il sistema può essere chiamato da applicazioni esterne utilizzando le API dei servizi web esposte tramite il protocollo SOAP. [Ulteriori informazioni sulle API di Campaign](../dev/api.md).

### Livello di persistenza{#persistance-layer}

I database di Campaign vengono utilizzati come livelli di persistenza e contengono quasi tutte le informazioni e i dati gestiti da Adobe Campaign. Ciò include: dati funzionali, tra cui profili, iscrizioni, contenuti; dati tecnici, tra cui processi e registri di consegna, registri di tracciamento; dati di lavoro (acquisti, lead).

L’affidabilità del database è di fondamentale importanza perché la maggior parte dei componenti di Adobe Campaign richiede l’accesso al database per eseguire le proprie attività (ad eccezione del modulo di reindirizzamento).

### Livello logico dell’applicazione{#logical-app-layer}

Il livello logico dell’applicazione di Campaign è facilmente configurabile per soddisfare esigenze aziendali complesse. Puoi utilizzare Campaign come una singola piattaforma con diverse applicazioni che si combinano per creare un’architettura aperta e scalabile. Ogni istanza di Campaign è una raccolta di processi nel livello dell’applicazione, alcuni dei quali sono condivisi e altri dedicati.

## Campaign Managed Cloud Services{#ac-managed-services}

Adobe Campaign v8 è implementato come Managed Service: tutti i componenti di Adobe Campaign, inclusa l’interfaccia utente, il motore di gestione dell’esecuzione e i database di Campaign, sono completamente ospitati da Adobe, compresi l’esecuzione delle e-mail, le pagine mirror, il server di tracciamento e i componenti web accessibili esternamente, tra cui la pagina di annullamento dell’iscrizione/il centro preferenze e le pagine di destinazione.

## Processi di Campaign

Il server di Campaign Web controlla l’accesso ai processi di Campaign Web. JavaScript è il linguaggio lato server utilizzato per le funzioni principali e la personalizzazione del prodotto. Tomcat è il motore back-end ed è incorporato nel prodotto Campaign come parte del processo web. JavaScript viene utilizzato, ad esempio, nelle pagine JSP o JSSP per eseguire il rendering del contenuto dinamico.

![](assets/do-not-localize/ac-processes.png)

La console client di Campaign si connette al server web utilizzando SOAP XML su HTTP. Il server web fornisce il livello di sicurezza, trasmette le richieste al livello dell’applicazione utilizzando JavaScript e i processi interni di Campaign accedono al database utilizzando SQL.

<!--The overall communication between Campaign processes are described in the following standalone deployment diagram: all Campaign components are installed in the same machine.

![](assets/do-not-localize//ac-standalone.png) -->

L’utente si connette al server applicazioni di Campaign utilizzando il protocollo HTTP. Tutti i dati e le informazioni vengono gestiti nel database di Campaign. Se uno sviluppatore di Campaign apporta modifiche alla configurazione, queste vengono acquisite nel database. Se un marketer crea una nuova campagna, nel database vengono gestite anche tutte le informazioni e i dati relativi ad essa. Quando un markter esegue una campagna, le consegne e-mail vengono inviate ai profili dal server di Campaign tramite il server SMTP. Quando i profili interagiscono con le consegne e-mail, ad esempio l’apertura dell’e-mail, i dati di tracciamento vengono rimandati al server di tracciamento.

[Ulteriori informazioni sui processi di Campaign](../architecture/general-architecture.md#dev-env).
