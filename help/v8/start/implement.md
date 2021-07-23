---
product: Adobe Campaign
title: Linee guida sull’implementazione
description: Scopri come implementare Campaign v8
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: ht
source-wordcount: '1214'
ht-degree: 100%

---

# Linee guida sull’implementazione di Campaign

In questa sezione imparerai a regolare Adobe Campaign in base ai requisiti della tua azienda. Utilizza le linee guida seguenti per strutturare e organizzare l’implementazione.

1. **Definisci le impostazioni**: concedi l’accesso, condividi la console client e configura i canali (e-mail, push, sms)
1. **Prepara l’ambiente**: importa profili, crea tipi di pubblico, progetta i flussi di lavoro e i modelli di campagne, crea regole di tipologia
1. **Personalizza l’istanza**: crea nuovi campi dati, aggiungi tabelle/schemi
1. **Estendi la distribuzione**: collegati a soluzioni di Adobe, altri prodotti e sistemi; con connettori e impostazioni a più soluzioni

>[!CAUTION]
>
>Con **Campaign Managed Cloud Services**, l’ambiente e la configurazione iniziale sono stati impostati da Adobe, in base ai termini del contratto di licenza. Non ti è consentito modificare i pacchetti, gli schemi e i report integrati.
>
>Se hai la necessità di utilizzare un componente aggiuntivo di Campaign o una funzionalità specifica non fornita, contatta l’**Assistenza clienti di Adobe**.

## Prima di iniziare

Questa sezione contiene informazioni critiche sulla privacy e sulla sicurezza che devono essere esaminate e prese in considerazione prima di iniziare l’implementazione effettiva.

### Privacy

Adobe Campaign viene fornito con processi e impostazioni che ti consentono di utilizzare Campaign in conformità alle leggi sulla privacy dei dati applicabili e alle preferenze del destinatario. Puoi gestire:

* **Raccolta dati**: Adobe Campaign ti consente di raccogliere dati, incluse informazioni personali e riservate. È pertanto essenziale ricevere e gestire il consenso dei destinatari. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=it#data-acquisition)

* **Consenso utente e conservazione dei dati**: scopri come ottenere il consenso degli utenti, configurare meccanismi di abbonamento a doppio consenso esplicito, facilitare la rinuncia e configurare la conservazione dei dati nella [documentazione sulla privacy di Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=it#consent).

* **Normative sulla privacy e sulla protezione dei dati**: consulta la [documentazione sulla privacy di Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=it){target=&quot;_blank&quot;} per informazioni sul Regolamento generale sulla protezione dei dati (GDPR) dell’Unione europea, sul California Consumer Privacy Act (CCPA) e su altri requisiti internazionali riguardanti la privacy e come questi regolamenti influiscono sulla tua organizzazione e su Adobe Campaign.

### Sicurezza

Scopri le linee guida e i principi di sicurezza con Adobe Campaign in [Elenco di controlli di sicurezza di Campaign](../config/security.md).

## Definire le impostazioni di Campaign

### Aggiungere utenti e concedere autorizzazioni

Puoi aggiungere manualmente gli utenti a Campaign e associarli ai gruppi, allineati alla gerarchia dei ruoli. Gli utenti potranno quindi accedere ai dati e alle autorizzazioni a loro appropriate.

↗️ Scopri come aggiungere utenti ad Adobe Campaign in [questa sezione](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=it#getting-started){target=&quot;_blank&quot;}.

### Installare la console client di Campaign

L’interfaccia utente principale dell’applicazione è un client avanzato, ovvero un’applicazione nativa (Windows) che comunica con il server dell’applicazione Adobe Campaign esclusivamente tramite protocolli Internet standard (SOAP, HTTP, eccetera.). La console client di Adobe Campaign consente una produttività semplice e intuitiva, utilizza una larghezza di banda molto ridotta (grazie a una cache locale) ed è progettata per una facile distribuzione. Questa console può essere distribuita da un browser Internet, può essere aggiornata automaticamente e non richiede alcuna configurazione di rete specifica perché genera solo traffico HTTP(S).

?? [Ulteriori informazioni su Campaign Client Console](connect.md).

## Preparare l’ambiente

Prima di iniziare a inviare messaggi e creare campagne di marketing, devi:

1. Importare profili e creare tipi di pubblico

   Campaign ti aiuta ad aggiungere contatti al database Cloud. Puoi caricare un file, pianificare e automatizzare più aggiornamenti dei contatti alla volta, raccogliere dati sul web o inserire informazioni di profilo direttamente nella tabella dei destinatari.

   ?? [Scopri come importare i profili](import.md).

   I tipi di pubblico sono raggruppati in elenchi e possono essere creati tramite flussi di lavoro. Quindi possono essere indirizzati alle consegne cross-channel.

   ?? [Scopri come definire i tipi di pubblico](audiences.md).

1. Creare modelli

   Campagne, consegne, lavori o flussi di lavoro si basano tutti su un modello, che memorizza le impostazioni e le funzionalità principali. Per ciascun componente viene fornito un modello incorporato per il quale non è stata definita alcuna configurazione specifica. Devi configurare e adattare i modelli alle tue esigenze e renderli disponibili per gli utenti finali.

   ↗️ [Ulteriori informazioni sui modelli e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=it){target=&quot;_blank&quot;}

   ↗️ Scopri come utilizzare i modelli di campagna nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=it#orchestrating-campaigns){target=&quot;_blank&quot;}

   ↗️ Scopri come configurare un modello di flusso di lavoro nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=it#workflow-templates){target=&quot;_blank&quot;}

1. Configurare le regole di tipologia

   Utilizza le regole di tipologia di Campaign per filtrare, controllare e monitorare l’invio delle consegne. Ad esempio, le regole di affaticamento controllano la frequenza e la quantità di messaggi per evitare un’eccessiva sollecitazione dei destinatari. Una volta implementate, nelle consegne viene fatto riferimento alle regole di tipologia.

   ↗️ Ulteriori informazioni sulle tipologie e la gestione dell’eccesso nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=it#orchestrating-campaigns){target=&quot;_blank&quot;}

1. Acquisisci familiarità con il modello dati integrato di Campaign

   Adobe Campaign viene fornito con un modello dati predefinito. Per implementare e personalizzare l’ambiente, è necessario avere familiarità con le tabelle integrate del modello dati di Adobe Campaign e con le rispettive relazioni.

   ?? [Ulteriori informazioni sul modello dati di Campaign](../dev/datamodel.md).

## Personalizzare l’istanza

Puoi personalizzare diverse aree e funzionalità di Campaign. La maggior parte dei nostri clienti personalizza tre elementi:

1. **Tabelle e schemi**

   Adobe Campaign include schemi comuni per identificare dati quali: destinatari, registri di consegna, abbonamenti e altro ancora.

   ?? Fai riferimento a questa sezione per ulteriori informazioni sul [Modello dati integrato di Campaign](../dev/datamodel.md).

   ?? Puoi estendere gli schemi esistenti o creare nuovi schemi da zero. Per ulteriori informazioni, consulta [questa pagina](../dev/customize.md).

1. **Dashboard ed elenchi**

   È possibile configurare facilmente gli elenchi, aggiungere e rimuovere campi e personalizzare le colonne.

   ?? Scopri come gestire filtri ed elenchi in Campaign consultando [questa pagina](../dev/customize.md#gs-lists-and-filters).

   Puoi anche creare nuovi dashboard per visualizzare i dati di Campaign in base alle tue esigenze.

   ?? Per ulteriori informazioni, consulta [questa pagina](../dev/customize.md#gs-custom-dashboards).

1. **Rapporti**

   Campaign fornisce una serie di rapporti incorporati sul monitoraggio della consegna, sugli URL e sui flussi di clic, sul tracciamento, sugli indicatori di recapito e altro ancora.

   In aggiunta ai report incorporati, Adobe Campaign ti consente di generare report in vari contesti e di soddisfare esigenze diverse. I principi relativi alle modalità di utilizzo e di implementazione sono descritti nel presente documento.

   ?? Scopri le funzionalità di reporting disponibili in Campaign, in [questa pagina](reporting.md).


## Impostare l’automazione della campagna

Per orchestrare campagne di marketing complesse che siano adatte a diversi tipi di pubblico su più canali, sfrutta le funzionalità di automazione di Campaign.

* Flussi di lavoro: gestire processi e dati

* Abbonamenti e pagine di destinazione

* Regole di tipologia: gestione dell’affaticamento e del controllo

## Estendere la distribuzione

### Implementazione di più soluzioni

Se utilizzi altre soluzioni Adobe, puoi collegarle all’ambiente Campaign e combinare le funzionalità.

* Campaign: Journey Orchestration
* Campaign: Real-time CDP
* Campaign: Trigger di Experience Cloud
* Campaign: Experience Manager
* Campaign: Target
* Campaign: servizio core People/Audience Manager
* Campaign: Assets
* Campaign: connettori dati di Analytics


Puoi anche utilizzare Single Sign-On (SSO) per connetterti a Campaign. Per ulteriori informazioni, consulta [questa pagina](connect.md).

?? Scopri l’elenco completo delle soluzioni Adobe che possono essere integrate con Adobe Campaign, in [questa pagina](../connect/integration.md).

### Connettori

Collega Campaign a sistemi di terze parti per combinare un’ampia gamma di funzionalità e automatizzare i processi.

?? Scopri i connettori disponibili, in [questa sezione](../connect/integration.md).

**Collegare il CRM a Campaign**

Puoi collegare la tua piattaforma Adobe Campaign ai sistemi di terze parti CRM e sincronizzare i dati (contatti, account, acquisti, eccetera).

?? Scopri come collegare il sistema CMR con Campaign in [questa sezione](../connect/integration.md#gs-crm-connectors)

**Connessione a un database esterno**

Puoi collegare il database di Campaign Cloud a sistemi esterni tramite il modulo Federated Data Access (FDA).

?? Scopri come configurare il modulo FDA di Campaign per definire i parametri di accesso, in [questa sezione](../connect/integration.md#gs-fda)
