---
product: Adobe Campaign
title: Guida introduttiva a Campaign v8
description: Scopri le funzionalità principali, l’interfaccia utente e le linee guida globali
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
source-git-commit: bf2c44adc560d2be700a27b02ab35f6630192d00
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 86%

---

# Introduzione ad Adobe Campaign{#gs-ac-v8}

Adobe Campaign fornisce una piattaforma per la progettazione di customer experience multicanale e un ambiente per l’orchestrazione visiva delle campagne, la gestione delle interazioni in tempo reale e l’esecuzione su più canali.

Utilizza Campaign per:

* **Stimolare la personalizzazione e il coinvolgimento attraverso un’unica vista accessibile del cliente**
* **Integrare nel percorso cliente canali e-mail, mobili, online e offline**
* **Automatizzare la consegna di messaggi e offerte significativi e tempestivi**

![](assets/ac-capabilities.png)

## Profilo cliente integrato {#integrated-customer-profile}

I profili sono centralizzati in un potente database cloud. Esistono molti possibili meccanismi per l’acquisizione di profili e la creazione di questo database: raccolta on-line tramite moduli web, importazione manuale o automatica di file di testo, replica con database aziendali o altri sistemi di informazioni. Con Adobe Campaign, puoi incorporare la cronologia di marketing, le informazioni di acquisto, le preferenze, i dati di gestione delle relazioni con i clienti ed eventuali dati PII rilevanti in una vista consolidata per analizzare e intraprendere azioni.

In Adobe Campaign, i destinatari sono i profili predefiniti oggetto di targeting per l’invio di consegne (e-mail, SMS, ecc.). Grazie ai dati sui destinatari archiviati nel database, potrai filtrare il target che riceverà una determinata consegna e aggiungere dati di personalizzazione nei contenuti della consegna. Nel database sono presenti altri tipi di profili. Essi sono progettati per diversi utilizzi. Ad esempio, i profili di seed vengono creati per testare le consegne prima che vengano inviate al target finale.

[!DNL :bulb:] Le nozioni di base sulla gestione dei profili sono illustrate in [questa sezione](audiences.md).

[!DNL :bulb:] Scopri come aggiungere profili a Campaign in [questa sezione](import.md).

## Segmentazione mirata {#targeted-segmentation}

 Adobe Campaign dispone di funzioni di segmentazione e targeting potenti e intuitive che ti consentono di creare offerte altamente mirate e differenziate. La funzionalità di analisi descrittiva ti consente di analizzare le informazioni a monte e a valle delle campagne di marketing, e la funzionalità di gestione dei filtri e di editor di query grafiche ti consente di filtrare la popolazione degli abbonati e di campionare o creare gruppi target in base a un numero illimitato di criteri.

La funzionalità avanzata di gestione dei dati estende le funzionalità di elaborazione dei dati. Semplifica e ottimizza il processo di targeting includendo dati non modellati nel data mart.

[!DNL :bulb:] Ulteriori informazioni sulla segmentazione, la creazione di tipi di pubblico e la personalizzazione sono disponibili in [questa sezione](audiences.md).

## Orchestrazione di campagne cross-channel {#cross-channel-campaign-orchestration}

 Adobe Campaign ti consente di progettare e orchestrare campagne mirate e personalizzate su più canali: e-mail, direct mail, SMS, notifica push. Un’unica interfaccia ti offre tutte le funzioni necessarie per pianificare, orchestrare, configurare, personalizzare, automatizzare, eseguire e misurare tutte le tue campagne e comunicazioni.

[!DNL :bulb:] Scopri come progettare, pianificare ed eseguire una campagna in [questa sezione](campaigns.md).

## Flussi di lavoro

Adobe Campaign offre un ambiente grafico completo che ti consente di progettare processi complessi, tra cui segmentazione, esecuzione di campagne, elaborazione di file, eccetera. Ad esempio, puoi utilizzare un flusso di lavoro per scaricare un file da un server, decomprimerlo e quindi importare i record nel database di Adobe Campaign.

Un flusso di lavoro può coinvolgere anche gli utenti, assegnando loro attività o facendogli approvare le attività eseguite. Ciò significa che puoi assegnare un’attività a uno o più utenti affinché lavorino sul contenuto oppure specificare destinazioni e approvare le bozze prima di inviare il messaggio.

I flussi di lavoro possono essere utilizzati in contesti diversi, ad esempio:

* Targeting per gestire il pubblico o inviare messaggi.
* Gestione dei dati (ETL) per manipolare i dati.
* Importazione dei dati nel database di Campaign.
* Processi tecnici come la pulizia del database, il recupero delle informazioni di tracciamento, eccetera.

[!DNL :bulb:] Scopri come progettare ed eseguire flussi di lavoro in [questa sezione](../config/workflows.md).

## Reporting e analisi {#analysis-and-reporting}

 Adobe Campaign ti consente di monitorare e interpretare il comportamento dei clienti arricchendo gradualmente i loro dati e profili. Gli strumenti di reporting e di analisi ti consentono di sfruttare al meglio ogni nuova campagna, di eseguire meglio il targeting delle iniziative di marketing e di ottimizzarne l’impatto e il ritorno sull’investimento.

[!DNL :bulb:] Ulteriori informazioni sulle funzionalità di report e tracking in  [questa sezione](reporting.md).

## Integrazioni con Adobe Experience Cloud {#adobe-experience-cloud-integrations}

Puoi combinare le funzionalità di consegna e le funzionalità avanzate di gestione delle campagne di Adobe Campaign con una serie di soluzioni create per aiutarti a personalizzare la user experience: Adobe Experience Manager, Adobe Analytics, Adobe Target o i trigger di Adobe Experience Cloud, ad esempio.

[!DNL :bulb:] Scopri come effettuare l’integrazione con i servizi e le soluzioni di Adobe in [questa sezione](../connect/integration.md).

## Ulteriori informazioni sulle funzionalità di Campaign {#core-capabilities-and-add-ons}

Adobe Campaign offre una serie di funzionalità per aiutarti a implementare e ottimizzare le funzionalità di marketing conversazionale in base alle tue esigenze e alla tua architettura. Alcune di queste sono funzionalità di base e altre dipendono dall’installazione di un pacchetto nella configurazione. Una descrizione dettagliata del prodotto è disponibile qui: [Adobe Campaign v8 Product Description](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-managed-cloud-services.html).

[!DNL :bulb:] Hai già familiarità con Campaign Classic? Scopri le differenze principali tra Campaign Classic e Campaign v8 in [questa pagina](capability-matrix.md).

## Area di lavoro e personalizzazione

L’area di lavoro di Campaign è disponibile tramite la [Console client](../dev/general-architecture.md).

![](assets/home-page.png)

[!DNL :bulb:] [Ulteriori informazioni sulla console client di Campaign](../start/connect.md).

L’area di lavoro di Campaign può essere adattata in base alle tue esigenze.

[!DNL :arrow_upper_right:]  Scopri come utilizzare l’area di lavoro di Campaign nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=it)

[!DNL :arrow_upper_right:]  Scopri come personalizzare gli elenchi nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=it)

Puoi anche accedere ad alcune funzionalità via web.

[!DNL :bulb:] [Ulteriori informazioni su Campaign Web Access](../start/connect.md#web-access).


## Lingue

L’interfaccia utente di Campaign v8 è disponibile nelle seguenti lingue:

* Inglese (Regno Unito)
* Inglese (Stati Uniti)
* Francese
* Tedesco
* Giapponese

La lingua viene selezionata durante il processo di installazione.

>[!CAUTION]
>
>La lingua non può essere modificata dopo la creazione dell’istanza.

Le date e i formati ora interessati dalla lingua. Per ulteriori informazioni, consulta la [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=en#date-and-time).

