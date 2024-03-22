---
title: Linee guida sull’implementazione
description: Scopri come implementare Campaign v8
feature: Overview
role: User
level: Intermediate
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 79%

---

# Linee guida sull’implementazione di Campaign{#gs-implementation}

In questa sezione, scopri come adeguare Adobe Campaign ai requisiti della tua azienda. Utilizza le linee guida seguenti per strutturare e organizzare l’implementazione.

1. **Definire le impostazioni**: concedi l’accesso, condividi la console client e configura i canali (e-mail, push, sms). [Ulteriori informazioni](#implementation-ac-settings)
1. **Prepara l’ambiente**: importa profili, crea tipi di pubblico, progetta i flussi di lavoro e i modelli di campagne, crea regole di tipologia. [Ulteriori informazioni](#implementation-prepare-your-env)
1. **Personalizza l’istanza**: crea nuovi campi dati, aggiungi tabelle/schemi. [Ulteriori informazioni](#implementation-custom-your-instance)
1. **Automatizza i processi**: configura le funzionalità di automazione di Adobe Campaign. [Ulteriori informazioni](#implementation-automation)
1. **Estendi la distribuzione**: collegati a soluzioni di Adobe, altri prodotti e sistemi; con connettori e impostazioni a più soluzioni. [Ulteriori informazioni](#implementation-extend)

>[!CAUTION]
>
>Con **Campaign Managed Cloud Services**, l’ambiente e la configurazione iniziale sono impostati da Adobe in base ai termini del contratto di licenza. Non ti è consentito modificare i pacchetti installati incorporati, gli schemi o i rapporti integrati.
>
>Se devi utilizzare un componente aggiuntivo di Campaign o una funzionalità specifica non fornita, devi contattare il tuo **Gestione transizione Adobe**.

## Prima di iniziare{#before-starting}

Questa sezione contiene informazioni critiche sulla privacy e sulla sicurezza che devono essere esaminate e prese in considerazione prima di iniziare l’implementazione effettiva.

### Privacy{#implementation-privacy}

Adobe Campaign viene fornito con processi e impostazioni che ti consentono di utilizzare Campaign in conformità alle leggi sulla privacy dei dati applicabili e alle preferenze del destinatario. Puoi gestire:

* **Raccolta dati**: Adobe Campaign ti consente di raccogliere dati, incluse informazioni personali e riservate. È pertanto essenziale ricevere e gestire il consenso dei destinatari.

  Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=it#data-acquisition){target="_blank"}

* **Consenso utente e conservazione dei dati**: è necessario ottenere il consenso degli utenti, configurare i meccanismi di abbonamento a doppio consenso, facilitare la rinuncia e configurare la conservazione dei dati.

  Ulteriori informazioni sono disponibili nella [documentazione sulla privacy di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=it#consent){target="_blank"}

* **Normative sulla privacy e la protezione dei dati**: fai riferimento a [questa sezione](privacy.md) per informazioni sui requisiti di privacy e su come questi regolamenti influiscono sulla tua organizzazione e su Adobe Campaign.

### Sicurezza

Scopri le linee guida e i principi di sicurezza con Adobe Campaign in [Elenco di controlli di sicurezza di Campaign](../config/security.md).

## Definire le impostazioni di Campaign{#implementation-ac-settings}

### Aggiungere utenti e concedere autorizzazioni{#implementation-add-users}

Puoi aggiungere manualmente gli utenti a Campaign e associarli ai gruppi, in base alla gerarchia dei ruoli. Una volta eseguito l’accesso, gli utenti potranno quindi accedere ai dati e alle autorizzazioni pertinenti per il loro ruolo.

Scopri come aggiungere utenti ad Adobe Campaign in [questa sezione](../start/gs-permissions.md).

### Installare la console client di Campaign{#implementation-install-console}

L’interfaccia utente principale dell’applicazione è un client avanzato, ovvero un’applicazione nativa (Windows) che comunica con il server dell’applicazione Adobe Campaign esclusivamente tramite protocolli Internet standard (SOAP, HTTP, eccetera.). La console client di Adobe Campaign offre una produttività semplice e intuitiva, utilizza una larghezza di banda molto ridotta (tramite l’utilizzo di una cache locale) ed è progettata per una facile distribuzione. Questa console può essere distribuita da un browser Internet, può essere aggiornata automaticamente e non richiede alcuna configurazione di rete specifica perché genera solo traffico HTTP(S).

[Ulteriori informazioni sulla console client di Campaign](connect.md).

## Preparare l’ambiente{#implementation-prepare-your-env}

Prima di iniziare a inviare messaggi e creare campagne di marketing, devi:

1. **Importare profili e creare tipi di pubblico**

   Campaign ti aiuta ad aggiungere contatti al database Cloud. Puoi caricare un file, pianificare e automatizzare più aggiornamenti dei contatti alla volta, raccogliere dati sul web o inserire informazioni di profilo direttamente nella tabella dei destinatari.

   [Scopri come importare i profili](import.md).

   I tipi di pubblico sono raggruppati in elenchi e possono essere creati tramite flussi di lavoro. Quindi possono essere indirizzati alle consegne cross-channel.

   [Scopri come definire i tipi di pubblico](audiences.md).

1. **Utilizzare i modelli**

   Campagne, consegne, lavori o flussi di lavoro si basano tutti su un modello, che memorizza le impostazioni e le funzionalità principali. Per ciascun componente viene fornito un modello incorporato per il quale non è stata definita alcuna configurazione specifica. Devi configurare e adattare i modelli alle tue esigenze e renderli disponibili per gli utenti finali.


   Scopri come utilizzare i modelli di campagna in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-templates.html?lang=it){target="_blank"}.

   Scopri come configurare un modello di flusso di lavoro in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=it){target="_blank"}.

   Ulteriori informazioni sui modelli e-mail in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=it){target="_blank"}.


1. **Configurare le regole di tipologia**

   Utilizza le regole di tipologia di Campaign per filtrare, controllare e monitorare l’invio delle consegne. Ad esempio, le regole di affaticamento controllano la frequenza e la quantità di messaggi per evitare un’eccessiva sollecitazione dei destinatari. Una volta implementate, nelle consegne viene fatto riferimento alle regole di tipologia.

   Ulteriori informazioni sulle tipologie e sulla gestione dell’eccesso in [questa sezione](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=it){target="_blank"}.

1. **Acquisisci familiarità con il modello dati integrato di Campaign**

   Adobe Campaign viene fornito con un modello dati predefinito. Per implementare e personalizzare l’ambiente, è necessario avere familiarità con le tabelle integrate del modello dati di Adobe Campaign e con le rispettive relazioni.

   [Ulteriori informazioni sul modello dati di Campaign](../dev/datamodel.md).

## Personalizzare l’istanza{#implementation-custom-your-instance}

Puoi personalizzare diverse aree e funzionalità di Campaign. La maggior parte dei nostri clienti personalizza tre elementi:

1. **Tabelle e schemi**

   Adobe Campaign include schemi comuni per identificare dati quali: destinatari, registri di consegna, abbonamenti e altro ancora.

   Fai riferimento a questa sezione per ulteriori informazioni su [Modello dati integrato di Campaign](../dev/datamodel.md).

   Puoi estendere gli schemi esistenti o creare nuovi schemi da zero. Per ulteriori informazioni, consulta [questa pagina](../dev/customize.md).

1. **Dashboard ed elenchi**

   È possibile configurare facilmente gli elenchi, aggiungere e rimuovere campi e personalizzare le colonne.

   Scopri come gestire filtri ed elenchi in Campaign in [questa pagina](../dev/customize.md#gs-lists-and-filters).

   Puoi anche creare nuovi dashboard per visualizzare i dati di Campaign in base alle tue esigenze.

   Per ulteriori informazioni, consulta [questa pagina](../dev/customize.md#gs-custom-dashboards).

1. **Rapporti**

   Campaign fornisce una serie di rapporti incorporati sul monitoraggio della consegna, sugli URL e sui flussi di clic, sul tracciamento, sugli indicatori di recapito e altro ancora.

   In aggiunta ai report incorporati, Adobe Campaign ti consente di generare report in vari contesti e di soddisfare esigenze diverse. I principi relativi alle modalità di utilizzo e di implementazione sono descritti nel presente documento.

   Ulteriori informazioni sulle funzionalità di reporting in Campaign in [questa pagina](../reporting/gs-reporting.md).


## Impostare l’automazione della campagna{#implementation-automation}

Per orchestrare campagne di marketing complesse che siano adatte a diversi tipi di pubblico su più canali, sfrutta le funzionalità di automazione di Campaign.

* Utilizza i **flussi di lavoro** per gestire processi e dati. Per ulteriori informazioni consulta [questa documentazione](../../automation/workflow/about-workflows.md)

* Configura i processi di **abbonamento** e le **pagine di destinazione**.  Per ulteriori informazioni, consulta [questa pagina](../start/subscriptions.md)

* Configura le **regole di tipologia** per definire la gestione dell&#39;affaticamento e del controllo.  Per ulteriori informazioni consulta [questa documentazione](../../automation/campaign-opt/campaign-typologies.md)


## Estendere la distribuzione{#implementation-extend}

### Implementazione di più soluzioni{#implementation-multi-solutions}

Se utilizzi altre soluzioni Adobe, puoi collegarle all’ambiente Campaign e combinare le funzionalità.

* Campaign: Journey Orchestration
* Campaign: Real-time CDP
* Campaign: Trigger di Experience Cloud
* Campaign: Experience Manager
* Campaign: Target
* Campaign: servizio core People/Audience Manager
* Campaign: Assets
* Campaign: connettori dati di Analytics


Puoi anche utilizzare il Single Sign-On (SSO) per connetterti a Campaign. Per ulteriori informazioni, consulta [questa pagina](connect.md).

Scopri l’elenco completo delle soluzioni Adobe che possono essere integrate con Adobe Campaign [in questa pagina](../connect/integration.md).

### Connettori{#implementation-connectors}

Collega Campaign a sistemi di terze parti per combinare un’ampia gamma di funzionalità e automatizzare i processi.

Ulteriori informazioni sui connettori disponibili in [questa sezione](../connect/integration.md).

**Collegare il CRM a Campaign**

Puoi collegare la tua piattaforma Adobe Campaign ai sistemi di terze parti CRM e sincronizzare i dati (contatti, account, acquisti, eccetera).

Scopri come collegare il sistema CRM a Campaign in [questa sezione](../connect/integration.md#gs-crm-connectors)

**Connessione a un database esterno**

Puoi collegare il database di Campaign Cloud a sistemi esterni tramite il modulo Federated Data Access (FDA).

Scopri come configurare il modulo FDA di Campaign per definire i parametri di accesso in [questa sezione](../connect/integration.md#gs-fda)
