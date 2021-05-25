---
solution: Campaign v8
product: Adobe Campaign
title: Linee guida sull'implementazione
description: Scopri come implementare Campaign v8
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '1221'
ht-degree: 2%

---

# Linee guida sull’implementazione di Campaign

In questa sezione imparerai a regolare Adobe Campaign in base ai requisiti della tua azienda. Utilizza le seguenti linee guida per strutturare e organizzare l’implementazione.

1. **Definisci le impostazioni**: concedere l’accesso, condividere la console client, configurare i canali (e-mail, push, sms)
1. **Prepara l’ambiente**: importare profili, creare tipi di pubblico, progettare flussi di lavoro e modelli di campagne, creare regole di tipologia
1. **Personalizza l’istanza**: creare nuovi campi dati, aggiungere tabelle/schemi
1. **Estendi la distribuzione**: connessione a soluzioni di Adobe, altri prodotti e sistemi - connettori, impostazioni per più soluzioni

>[!CAUTION]
>
>Con **Cloud Services gestiti da Campaign**, l’ambiente e la configurazione iniziale sono stati impostati per Adobe, in base ai termini del contratto di licenza. Non è consentito modificare i pacchetti incorporati, gli schemi o i rapporti incorporati installati.
>
>Se devi utilizzare un componente aggiuntivo Campaign o una funzionalità specifica non disponibile, contatta l’ **Adobe Customer Care**.

## Prima di iniziare

Questa sezione contiene informazioni critiche sulla privacy e la sicurezza che devono essere esaminate e prese in considerazione prima di iniziare l&#39;implementazione effettiva.

### Privacy

Adobe Campaign viene fornito con processi e impostazioni che ti consentono di utilizzare Campaign in conformità alle leggi sulla privacy dei dati applicabili e alle preferenze del destinatario. Puoi gestire:

* **Acquisizione** dati: Adobe Campaign consente di raccogliere dati, comprese informazioni personali e riservate. È pertanto essenziale che tu riceva e gestisca il consenso dei destinatari. Ulteriori informazioni nella documentazione di [Campaign Classic v7](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#data-acquisition)

* **Consenso utente e conservazione** dei dati: Scopri come ottenere il consenso degli utenti, configurare i meccanismi di doppio consenso per l’abbonamento, facilitare la rinuncia e configurare la conservazione dei dati nella documentazione sulla privacy di  [Campaign Classic](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#consent)

* **Normative** sulla privacy e la protezione dei dati: consulta la documentazione  [Campaign Classic sulla privacy ](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html) per informazioni sul Regolamento generale sulla protezione dei dati (RGPD) dell’Unione europea, sul California Consumer Privacy Act (CCPA) e su altri requisiti internazionali sulla privacy, e su come questi regolamenti influiscono sulla tua organizzazione e su Adobe Campaign.

### Sicurezza

Scopri le linee guida e i principi di sicurezza con Adobe Campaign in [Lista di controllo sicurezza delle campagne](../config/security.md).

## Definire le impostazioni di Campaign

### Aggiungere utenti e concedere autorizzazioni

Puoi aggiungere manualmente gli utenti a Campaign e associarli ai gruppi, allineati alla gerarchia dei ruoli. Gli utenti potranno quindi accedere ai dati e alle autorizzazioni appropriate per loro.

:arrow_Upper_right: Scopri come aggiungere utenti ad Adobe Campaign in [questa sezione](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=en#getting-started).

### Installare la console client di Campaign

L&#39;interfaccia utente principale dell&#39;applicazione è un client avanzato, in altre parole un&#39;applicazione nativa (Windows) che comunica con il server dell&#39;applicazione Adobe Campaign esclusivamente con i protocolli Internet standard (SOAP, HTTP, ecc.). La console client di Adobe Campaign offre una grande facilità di utilizzo per la produttività, utilizza una larghezza di banda molto ridotta (tramite l’utilizzo di una cache locale) ed è progettata per una facile distribuzione. Questa console può essere implementata da un browser Internet, può essere aggiornata automaticamente e non richiede alcuna configurazione di rete specifica perché genera solo traffico HTTP(S).

:lampadina: [Ulteriori informazioni sulla console client di Campaign](connect.md).

## Preparare l’ambiente

Prima di iniziare a inviare messaggi e creare campagne di marketing, devi:

1. Importare profili e creare tipi di pubblico

   Campaign ti consente di aggiungere contatti al database Cloud. È possibile caricare un file, pianificare e automatizzare più aggiornamenti dei contatti, raccogliere dati sul Web o immettere informazioni di profilo direttamente nella tabella dei destinatari.

   :lampadina: [Scopri come importare profili](import.md).

   I tipi di pubblico sono raggruppati in elenchi e possono essere creati tramite flussi di lavoro. Possono quindi essere indirizzati alle consegne cross-channel.

   :lampadina: [Scopri come definire i tipi di pubblico](audiences.md).

1. Creare modelli

   Campagne, consegne, lavori o flussi di lavoro si basano tutti su un modello, che memorizza le impostazioni e le funzionalità chiave. Per ciascun componente viene fornito un modello incorporato per il quale non è stata definita alcuna configurazione specifica. Devi configurare e adattare i modelli alle tue esigenze e renderli disponibili agli utenti finali.

   :arrow_Upper_right: [Ulteriori informazioni sui modelli e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)

   :arrow_Upper_right: Scopri come utilizzare i modelli di campagna in [questa pagina](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)

   :arrow_Upper_right: Scopri come configurare un modello di flusso di lavoro in [questa pagina](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=en#workflow-templates)

1. Configurare le regole di tipologia

   Utilizza le regole di tipologia Campaign per filtrare, controllare e monitorare l’invio delle consegne. Ad esempio, le regole di affaticamento controllano la frequenza e la quantità di messaggi per evitare un’eccessiva sollecitazione dei destinatari. Una volta implementate, nelle consegne viene fatto riferimento alle regole di tipologia.

   :arrow_Upper_right: [Ulteriori informazioni sulle tipologie e sulla gestione dell&#39;affaticamento](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=en#orchestrating-campaigns)

1. Acquisisci familiarità con il modello dati integrato di Campaign

   Adobe Campaign viene fornito con un modello dati predefinito. Per implementare e personalizzare l’ambiente, è necessario avere familiarità con le tabelle integrate del modello dati di Adobe Campaign e con le rispettive relazioni.

   :lampadina: [Ulteriori informazioni sul modello dati di Campaign](../dev/datamodel.md).

## Personalizza l’istanza

Puoi personalizzare diverse aree e funzionalità di Campaign. La maggior parte dei nostri clienti personalizza tre cose:

1. **Tabelle e schemi**

   Adobe Campaign include schemi comuni per identificare dati quali: destinatari, registri di consegna, abbonamenti e altro ancora.

   :lampadina: Fai riferimento a questa sezione per ulteriori informazioni su [Modello dati integrato di Campaign](../dev/datamodel.md).

   :lampadina: Puoi estendere gli schemi esistenti o creare nuovi schemi da zero. Ulteriori informazioni in [questa pagina](../dev/customize.md).

1. **Dashboard ed elenchi**

   È possibile configurare facilmente gli elenchi, aggiungere e rimuovere campi e personalizzare le colonne.

   :lampadina: Scopri come gestire filtri ed elenchi in Campaign in [questa pagina](../dev/customize.md#gs-lists-and-filters).

   Puoi anche creare nuove dashboard per visualizzare i dati di Campaign in base alle tue esigenze.

   :lampadina: Ulteriori informazioni in [questa pagina](../dev/customize.md#gs-custom-dashboards).

1. **Rapporti**

   Campaign fornisce una serie di rapporti incorporati sul monitoraggio della consegna, sugli URL e sui flussi di clic, sul tracciamento, sugli indicatori di recapito e altro ancora.

   In aggiunta ai report incorporati, Adobe Campaign ti consente di generare report in vari contesti e di soddisfare esigenze diverse. I principi relativi alle modalità di utilizzo e di implementazione sono descritti nel presente documento.

   :lampadina: Ulteriori informazioni sulle funzionalità di reporting in Campaign in [questa pagina](reporting.md).


## Imposta l&#39;automazione della campagna

Per orchestrare campagne di marketing complesse per diversi tipi di pubblico su più canali, sfrutta le funzionalità di automazione di Campaign.

* Flussi di lavoro: gestire processi e dati

* Abbonamenti e pagine di destinazione

* Regole di tipologia: gestione dell&#39;affaticamento e del controllo

## Estendere la distribuzione

### Implementazione di più soluzioni

Se utilizzi altre soluzioni Adobe, puoi collegarle all’ambiente Campaign e combinare le funzionalità.

* Campagna - Journey Orchestration
* Campaign - Real-time CDP
* Campaign - Trigger di Experience Cloud
* Campaign - Experience Manager
* Campaign - Target
* Campaign - Servizio core Audience Manager / Persone
* Campaign - Risorsa
* Campaign - Connettori dati di Analytics


Puoi anche utilizzare Single Sign-On (SSO) per connettersi a Campaign. Ulteriori informazioni in [questa pagina](connect.md).

:lampadina: Scopri l&#39;elenco completo della soluzione Adobe che può essere integrata con Adobe Campaign [in questa pagina](../connect/integration.md).

### Connettori

Collega Campaign a sistemi di terze parti per combinare un’ampia gamma di funzionalità e automatizzare i processi.

:lampadina: Ulteriori informazioni sui connettori disponibili in [questa sezione](../connect/integration.md).

**Collegare il CRM a Campaign**

Puoi collegare la tua piattaforma Adobe Campaign ai sistemi di terze parti CRM e sincronizzare i dati: contatti, conti, acquisti, ecc.

:lampadina: Scopri come collegare il sistema CRM a Campaign in [questa sezione](../connect/integration.md#gs-crm-connectors)

**Connessione a un database esterno**

Puoi collegare il database di Campaign Cloud a sistemi esterni tramite il modulo Federated Data Access (FDA) .

:lampadina: Scopri come configurare il modulo FDA di Campaign per definire i parametri di accesso in [questa sezione](../connect/integration.md#gs-fda)
