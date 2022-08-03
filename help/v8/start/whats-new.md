---
title: Novità di Campaign v8
description: Scopri le funzionalità chiave in Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Novità di Adobe Campaign v8 {#ac-gs-what-is-new}

Adobe Campaign v8 è progettato per gli esperti di marketing cross-channel che necessitano della soluzione cloud all’avanguardia per la gestione delle campagne cross-channel con scalabilità aziendale. Fornisce solide funzionalità di ETL e gestione dei dati per aiutare a creare e curare la campagna perfetta. Il motore di orchestrazione fornisce programmi di marketing multi-touch avanzati con un focus principale sui percorsi basati su batch. Viene inoltre fornito con un server di messaggistica scalabile in tempo reale che consente ai team di marketing di inviare messaggi predefiniti basati su un payload completo da qualsiasi sistema IT per elementi quali reimpostazione della password, conferma dell’ordine, ricezione elettronica e molto altro ancora.

Adobe Campaign v8 offre notevoli miglioramenti a livello di infrastruttura, sicurezza, recapito messaggi e monitoraggio.

![](assets/home-page.png)

## Funzionalità principali{#key-capabilities}

Le funzionalità principali includono:

* **Gestione centrale del flusso di lavoro**. Migliora la velocità e la scala di ogni aspetto delle campagne di marketing, dalla creazione di segmenti e preparazione dei messaggi alla consegna.

   Adobe Campaign semplifica la sincronizzazione dei canali con un’unica interfaccia di facile utilizzo per l’orchestrazione delle campagne. Quindi, i tuoi canali online, come e-mail, web, mobile e social, corrispondono ai tuoi canali offline, inclusi direct mailing, call center, in-store e così via. Ti consente di offrire ai clienti un’esperienza coerente e contestuale sia nei canali digitali che tradizionali. Adobe Campaign semplifica la distribuzione dei contenuti a tutti i percorsi seguiti dai clienti, su qualsiasi canale.

   ![](../assets/do-not-localize/glass.png) [Ulteriori informazioni sui flussi di lavoro di Campaign](../config/workflows.md)

* **Marketing e-mail personalizzato**. Crea e-mail personalizzate e contestualmente pertinenti, coerenti con il resto dell’esperienza del cliente.

   Con Adobe Campaign, puoi rendere le e-mail migliori, più personalizzate e più redditizie. Le e-mail sono semplici da creare e facili da consegnare. Campaign v8 offre la flessibilità di progettare, personalizzare, testare, perfezionare e migliorare ogni messaggio inviato.

   ![](../assets/do-not-localize/glass.png) [Ulteriori informazioni sulle funzionalità di personalizzazione](create-message.md)

* **Gestione dei dati dei clienti**. Visualizza l’immagine completa dei tuoi clienti per creare rapidamente campagne personalizzate su scala aziendale.

   Adobe Campaign ti aiuta a creare profili cliente dai dati raccolti su tutti i tuoi canali. Con questo profilo, puoi orchestrare campagne tra canali diversi. Collegando tutti i canali di marketing, sarai in grado di personalizzare il percorso che prenderanno i clienti nel modo che avrà senso per loro.

   ![](../assets/do-not-localize/glass.png) [Ulteriori informazioni sulla gestione dei dati dei clienti](audiences.md)

* **Gestione di campagne all’avanguardia**. Adobe Campaign v8 offre agli addetti al marketing funzionalità all’avanguardia per pianificare, avviare e misurare le campagne tra i canali.

   Le funzionalità includono un profilo integrato che fornisce una singola vista del cliente. Gestione dei dati e segmentazione per la creazione di tipi di pubblico per le campagne su larga scala. Gestione del flusso di lavoro cross-channel per automatizzare le campagne multicanale e a più onde. E-mail integrata, riducendo la dipendenza da ESP costosi. Reporting e analisi per comprendere il comportamento dei clienti e le prestazioni della campagna.

   ![](../assets/do-not-localize/glass.png) [Ulteriori informazioni sulla gestione delle campagne](campaigns.md)


* **Connessioni ad Adobe Experience Platform**. Adobe Campaign v8 supporta i connettori dati con Real-Time CDP e Adobe Experience Platform, in modo che le organizzazioni possano sfruttare il profilo cliente unificato in tempo reale.

   Inoltre, Adobe Campaign v8 è integrato in modo nativo con le funzionalità di orchestrazione del percorso in tempo reale, in modo che gli esperti di marketing possano riutilizzare gli stessi modelli e le stesse funzionalità di consegna in Adobe Campaign per interagire con i clienti in tempo reale. Questi investimenti ottimizzano l’esperienza del cliente di Adobe Campaign e consentono nuovi casi d’uso, come la possibilità di aggiungere percorsi del cliente personalizzati in tempo reale alle campagne.

   Inoltre puoi configurare l’ottimizzazione del tempo di invio e il valore di engagement, entrambi in modalità predittiva, con il servizio IA gestione percorsi, per aumentare i tassi di apertura, i clic e i ricavi.

   ![](../assets/do-not-localize/glass.png) [Ulteriori informazioni sulle integrazioni di Campaign](../connect/integration.md)


* **Cloud Services gestiti**. Adobe Campaign v8 è disponibile come Cloud Services gestito, fornisce supervisione proattiva, avvisi tempestivi e governance dei servizi.

   Il Cloud Service gestito da Adobe offre agli addetti al marketing una soluzione di gestione delle campagne cross-channel più agile, sicura e scalabile con un basso costo totale di proprietà. La nuova offerta unisce i servizi a una sorveglianza proattiva e a un avviso tempestivo.

* **Velocità e scalabilità**. Adobe Campaign ora può sfruttare le tecnologie di database su scala cloud per migliorarne notevolmente la scalabilità e la velocità.

   [Campaign v8 Enterprise](../architecture/enterprise-deployment.md) introduce il concetto di **Full Federated Data Access** (FFDA): adesso tutti i dati sono remoti, nel Cloud Database. Con questa nuova offerta, Campaign v8 semplifica la gestione dati: nel database cloud non è richiesto alcun indice. È sufficiente creare le tabelle, copiare i dati e iniziare. [!DNL Snowflake] è il database cloud di Campaign che ti offre velocità e resistenza, senza il rischio di sovraccarichi per picchi di attività del sistema. La tecnologia del database Cloud non richiede una manutenzione specifica per garantire la qualità del servizio.

   ![](../assets/do-not-localize/glass.png) [Ulteriori informazioni sull’implementazione di Enterprise (FFDA)](../architecture/enterprise-deployment.md)


>[!CAUTION]
>
>* Campaign v8 è disponibile **solo** come Cloud Service gestito e non può essere distribuito in ambienti on-premise o ibridi.
>
>* La migrazione da un ambiente esistente di Campaign Classic v7 non è ancora disponibile.




## Interfaccia di amministrazione self-service{#self-service-admin}

In qualità di amministratore di prodotto, puoi gestire le impostazioni e monitorare gli utilizzi di ciascuna istanza di Campaign v8 mediante il **Pannello di controllo Campaign**.

Grazie a un’interfaccia utente intuitiva, gli amministratori possono monitorare l’utilizzo delle risorse chiave, eseguire attività avanzate come l’inserimento di indirizzi IP nell’elenco Consentiti, il monitoraggio dell’archiviazione SFTP, la gestione delle chiavi e altro ancora. Questa interfaccia self-service offre maggiore flessibilità e consente di:

* Apporta rapidamente e in autonomia le modifiche alle impostazioni senza rivolgerti al Supporto Adobe
* Configura le impostazioni in base alle diverse esigenze aziendali in momenti diversi
* Migliora la sicurezza controllando le impostazioni di accesso in base alle necessità

![](assets/subdomain1.png)

![](../assets/do-not-localize/glass.png) [Ulteriori informazioni sul Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=it){target=&quot;_blank&quot;}


