---
title: Comprendere i processi e i componenti di Campaign
description: Comprendere i processi e i componenti di Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 1%

---

# Comprendere i processi e i componenti di Campaign {#components-and-processes}

Adobe Campaign è una soluzione di marketing cross-channel che automatizza le campagne e-mail, mobile, social e offline. Adobe Campaign offre una posizione centrale per accedere ai dati e ai profili dei clienti. Utilizza Adobe Campaign per orchestrare esperienze coerenti per i tuoi clienti, progettare, eseguire e personalizzare il tuo marketing tra canali diversi, migliorando al contempo l&#39;esperienza dei clienti su ogni dispositivo e punto di contatto. Con Adobe Campaign puoi gestire più origini dati, definire i segmenti di pubblico e pianificare ed eseguire campagne multicanale in più passaggi tramite un’interfaccia di flusso di lavoro visiva con trascinamento della selezione.

Ulteriori informazioni sulle funzionalità chiave di Campaign in [questa pagina](../start/get-started.md).

## Componenti per Campaign {#ac-components}

I componenti e l’architettura globale di Adobe Campaign sono descritti di seguito.

![](assets/ac-components.png)

### Livello presentazione{#presentation-layer}

Puoi accedere ad Adobe Campaign tramite un client Rich, un client Thin o un’integrazione API.

* Client avanzato

   Campaign Rich Client è un’applicazione nativa che comunica con il server applicazioni Adobe Campaign tramite protocolli Internet standard, come SOAP e HTTP.

   La console del client di Campaign centralizza tutte le funzionalità e le impostazioni e richiede una larghezza di banda minima in quanto si basa su una cache locale. Progettata per una facile implementazione, la console del client Campaign può essere distribuita da un browser Internet, aggiornata automaticamente e non richiede alcuna configurazione di rete specifica in quanto genera solo traffico HTTP(S).

   ![](../assets/do-not-localize/glass.png) [Ulteriori informazioni su Campaign Client Console](../start/connect.md).

* Thin client

   Le funzionalità di accesso web di Adobe Campaign consentono di accedere a un sottoinsieme di funzioni di Campaign con un browser web, utilizzando un’interfaccia utente di HTML. Utilizza questa interfaccia web per accedere ai rapporti, controllare e convalidare i messaggi, accedere a dashboard di monitoraggio e altro ancora.

   ![](../assets/do-not-localize/glass.png) [Scopri come accedere a Campaign dal web](../start/connect.md).

* Applicazioni esterne con API

   In alcuni casi, il sistema può essere chiamato da applicazioni esterne utilizzando le API dei servizi Web esposte tramite il protocollo SOAP.

   ![](../assets/do-not-localize/glass.png) [Ulteriori informazioni sulle API di Campaign](../dev/api.md).

### Livello di persistenza{#persistance-layer}

I database di Campaign vengono utilizzati come livelli di persistenza e contengono quasi tutte le informazioni e i dati gestiti da Adobe Campaign. Ciò include: dati funzionali, quali profili, abbonamenti, contenuti; dati tecnici, quali processi di consegna e registri, registri di tracciamento; e dati di lavoro (acquisti, lead).

L’affidabilità del database è della massima importanza perché la maggior parte dei componenti Adobe Campaign richiede l’accesso al database per eseguire le proprie attività (ad eccezione del modulo di reindirizzamento).

### Livello applicazione logico{#logical-app-layer}

Il livello di applicazione logica Campaign è facilmente configurabile per soddisfare esigenze aziendali complesse. Puoi utilizzare Campaign come piattaforma singola con diverse applicazioni che si combinano per creare un’architettura aperta e scalabile. Ogni istanza di Campaign è una raccolta di processi nel livello dell’applicazione, alcuni dei quali sono condivisi e alcuni sono dedicati.

## Managed Services di Campaign{#ac-managed-services}

Adobe Campaign v8 è distribuito as a Managed Service: tutti i componenti di Adobe Campaign, inclusa l’interfaccia utente, il motore di gestione dell’esecuzione e i database di Campaign, sono interamente ospitati per Adobe, inclusi l’esecuzione di e-mail, le pagine mirror, il server di tracciamento e i componenti web rivolti all’esterno, come l’annullamento della sottoscrizione a un centro pagine/preferenze e le pagine di destinazione.

## Processi campagna

Il server Web di Campaign controlla l’accesso ai processi Web di Campaign. Javascript è il linguaggio lato server utilizzato per le funzioni di base del prodotto e la personalizzazione. Tomcat è il motore back-end ed è incorporato nel prodotto Campaign come parte del processo Web. Javascript viene utilizzato, ad esempio, nelle pagine JSP o JSSP per il rendering del contenuto dinamico.

![](assets/ac-processes.png)

La console del client Campaign si connette al server web utilizzando SOAP XML su HTTP. Il server Web fornisce il livello di protezione, trasmette le richieste al livello Applicazione utilizzando Javascript e l&#39;accesso al database tramite l&#39;interfaccia SQL viene elaborato dall&#39;interno di Campaign.

La comunicazione complessiva tra i processi Campaign è descritta nel seguente diagramma di distribuzione indipendente: tutti i componenti Campaign sono installati nello stesso computer.

![](assets/ac-standalone.png)

L’utente si connette al server dell’applicazione Campaign utilizzando il protocollo HTTP. Tutti i dati e le informazioni vengono gestiti nel database di Campaign. Se uno sviluppatore di Campaign esegue delle modifiche di configurazione, viene acquisito nel database. Se un addetto al marketing crea una nuova campagna, anche tutte le informazioni e i dati relativi a questa nuova campagna vengono gestiti nel database. Quando un addetto al marketing esegue una campagna, le consegne e-mail vengono inviate ai profili dal server Campaign tramite il server SMTP. Man mano che i profili interagiscono con le consegne e-mail, ad esempio aprendo l’e-mail, i dati di tracciamento vengono rimandati al server di tracciamento.

![](../assets/do-not-localize/glass.png) [Ulteriori informazioni sui processi di Campaign](../architecture/general-architecture.md#dev-env).
