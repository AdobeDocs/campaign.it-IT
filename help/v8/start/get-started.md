---
title: Introduzione a Campaign v8
description: Ti avvicini ora ad Adobe Campaign? Consulta la documentazione su come rendere il software operativo e dove iniziare con l’interfaccia.
feature: Overview, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d
source-git-commit: 86a6979b8258bbe3136ed9e4de6ce44a8164d5d9
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 97%

---

# Introduzione ad Adobe Campaign{#gs-ac-v8}

Adobe Campaign fornisce una piattaforma per la progettazione di esperienze cliente cross-channel e un ambiente per l’orchestrazione visiva delle campagne, la gestione delle interazioni in tempo reale e l’esecuzione su più canali.

Adobe Campaign v8 è lo strumento per campagne di nuova generazione creato per vari canali di marketing come e-mail, notifiche push, SMS e direct mail. Fornisce solide funzionalità di ETL e gestione dei dati per aiutare a creare e curare la campagna perfetta. Il motore di orchestrazione fornisce programmi di marketing multi-touch avanzati con un focus principale sui percorsi basati su batch. Viene inoltre fornito di un server di messaggistica in tempo reale scalabile che consente ai team di marketing di inviare messaggi predefiniti basati su un payload completo da qualsiasi sistema IT per scopi quali reimpostazione della password, conferma dell’ordine, ricezione elettronica e molto altro ancora.

Adobe Campaign v8 offre notevoli miglioramenti a livello di infrastruttura, sicurezza, recapito messaggi e monitoraggio. È disponibile come **Cloud Service gestito** che combina i servizi con una supervisione proattiva e modifiche tempestive. Ulteriori informazioni sui Cloud Service gestiti da Campaign [in questa pagina](whats-new.md#acms-desc).

Utilizza Campaign per:

* **Stimolare** la personalizzazione e il coinvolgimento attraverso un’unica vista accessibile del cliente
* **Integrare** nel percorso cliente canali e-mail, mobili, online e offline
* **Automatizzare** la consegna di messaggi e offerte significativi e tempestivi

![](assets/do-not-localize/ac-capabilities.png)

## Integrated Customer Profile {#integrated-customer-profile}

I profili sono centralizzati in un potente database cloud. Esistono molti possibili meccanismi per l’acquisizione di profili e la creazione di questo database: raccolta online tramite moduli web, importazione manuale o automatica di file di testo, replica con database aziendali o altri sistemi di informazioni. Con Adobe Campaign, puoi incorporare la cronologia di marketing, le informazioni di acquisto, le preferenze, i dati di gestione delle relazioni con i clienti ed eventuali dati PII rilevanti in una vista consolidata per analizzare e intraprendere azioni.

In Adobe Campaign, i destinatari sono i profili predefiniti oggetto di targeting per l’invio di consegne (e-mail, SMS, ecc.). Grazie ai dati sui destinatari archiviati nel database, potrai filtrare il target che riceverà una determinata consegna e aggiungere dati di personalizzazione nei contenuti della consegna. Nel database sono presenti altri tipi di profili. Essi sono progettati per diversi utilizzi. Ad esempio, i profili di seed vengono creati per testare le consegne prima che vengano inviate al target finale.

![](../assets/do-not-localize/glass.png) Le nozioni di base sulla gestione dei profili sono illustrate in [questa sezione](audiences.md).

![](../assets/do-not-localize/glass.png) Scopri come aggiungere profili a Campaign in [questa sezione](import.md).

## Segmentazione mirata {#targeted-segmentation}

Adobe Campaign dispone di funzioni di segmentazione e targeting potenti e intuitive che ti consentono di creare offerte altamente mirate e differenziate. La funzionalità di analisi descrittiva ti consente di analizzare le informazioni a monte e a valle delle campagne di marketing, e la funzionalità di gestione dei filtri e di editor di query grafiche ti consente di filtrare la popolazione degli abbonati e di campionare o creare gruppi target in base a un numero illimitato di criteri.

La funzionalità avanzata di gestione dei dati estende le funzionalità di elaborazione dei dati. Semplifica e ottimizza il processo di targeting includendo dati non modellati nel data mart.

![](../assets/do-not-localize/glass.png) Ulteriori informazioni sulla segmentazione e la creazione di pubblico sono disponibili in [questa sezione](audiences.md).

## Orchestrazione di campagne cross-channel {#cross-channel-campaign-orchestration}

 Adobe Campaign ti consente di progettare e orchestrare campagne mirate e personalizzate su più canali: e-mail, direct mail, SMS, notifica push. Un’unica interfaccia ti offre tutte le funzioni necessarie per pianificare, orchestrare, configurare, personalizzare, automatizzare, eseguire e misurare tutte le tue campagne e comunicazioni.

![](../assets/do-not-localize/glass.png) Scopri come progettare, pianificare ed eseguire una campagna in [questa sezione](campaigns.md).

## Flussi di lavoro {#wf-gsv8}

Adobe Campaign offre un ambiente grafico completo che ti consente di progettare processi complessi, tra cui segmentazione, esecuzione di campagne, elaborazione di file, eccetera. Ad esempio, puoi utilizzare un flusso di lavoro per scaricare un file da un server, decomprimerlo e quindi importare i record nel database di Adobe Campaign.

Un flusso di lavoro può coinvolgere anche gli utenti, assegnando loro attività o facendogli approvare le attività eseguite. Ciò significa che puoi assegnare un’attività a uno o più utenti affinché lavorino sul contenuto oppure specificare destinazioni e approvare le bozze prima di inviare il messaggio.

I flussi di lavoro possono essere utilizzati in contesti diversi, ad esempio:

* Targeting per gestire il pubblico o inviare messaggi.
* Gestione dei dati (ETL) per manipolare i dati.
* Importazione dei dati nel database di Campaign.
* Processi tecnici come la pulizia del database, il recupero delle informazioni di tracciamento, eccetera.

![](../assets/do-not-localize/glass.png) Scopri come progettare ed eseguire flussi di lavoro in [questa sezione](../config/workflows.md).

## Reporting e analisi {#analysis-and-reporting}

 Adobe Campaign ti consente di monitorare e interpretare il comportamento dei clienti arricchendo gradualmente i loro dati e profili. Gli strumenti di reporting e di analisi ti consentono di sfruttare al meglio ogni nuova campagna, di eseguire meglio il targeting delle iniziative di marketing e di ottimizzarne l’impatto e il ritorno sull’investimento.

Oltre ai potenti modelli di reporting predefiniti, Adobe Campaign consente di creare rapporti personalizzati a livello di consegna, campagna, utente o segmento. Effettua analisi descrittive, riepiloga il ROI o esporta dati in Adobe Analytics e altre soluzioni per ulteriore visualizzazione e analisi dei dati.

La funzione di reporting della campagna facilita la creazione di rapporti dinamici. Puoi trascinare e rilasciare le variabili per personalizzare i rapporti e analizzare il successo delle campagne. A seconda della complessità delle query e dei calcoli, è possibile aggregare i dati in una visualizzazione elenco o accedervi in un formato che semplifichi la generazione di rapporti di analisi marketing.


![](../assets/do-not-localize/glass.png) Scopri le funzionalità di reporting e tracciamento in [questa sezione](../reporting/gs-reporting.md).

## Integrazioni con Adobe Experience Cloud {#adobe-experience-cloud-integrations}

Puoi combinare le funzionalità di consegna e le funzionalità avanzate di gestione campagne di Adobe Campaign con una serie di soluzioni create per aiutarti a personalizzare l’esperienza utente: Adobe Experience Manager, Adobe Analytics, Adobe Target o i trigger di Adobe Experience Cloud, ad esempio.

![](../assets/do-not-localize/glass.png) Scopri come effettuare l’integrazione con i servizi e le soluzioni di Adobe in [questa sezione](../connect/integration.md).

## Ulteriori informazioni sulle funzionalità di Campaign {#core-capabilities-and-add-ons}

Adobe Campaign offre una serie di funzionalità per aiutarti a implementare e ottimizzare le funzionalità di marketing conversazionale in base alle tue esigenze e alla tua architettura. Alcune di queste sono funzionalità di base e altre dipendono dall’installazione di un pacchetto nella configurazione. Una descrizione dettagliata del prodotto è disponibile qui: [Adobe Campaign v8 Product Description](https://helpx.adobe.com/it/legal/product-descriptions/adobe-campaign-managed-cloud-services.html).

![](../assets/do-not-localize/glass.png) Hai già familiarità con Campaign Classic? Scopri le differenze principali tra Campaign Classic e Campaign v8 in [questa pagina](v7-to-v8.md).

**Vedi anche**

* [Area di lavoro di Campaign](campaign-ui.md)
* [Matrice di compatibilità per Campaign v8](compatibility-matrix.md)
* [Connessione a Campaign](connect.md)
* [Domande frequenti](campaign-faq.md)
