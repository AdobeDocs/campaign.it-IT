---
title: Linee guida sul tracciamento e-mail in pixel
description: Scopri le linee guida normative sui pixel di tracciamento delle e-mail e le funzionalità di Adobe Campaign che supportano le attività di conformità.
version: Campaign v8, Campaign Classic v7
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
source-git-commit: 93335b46b1c706a9409f0816b2ced4ebc612d5fe
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 0%
---

# Linee guida sul tracciamento e-mail in pixel

Questo post è solo a scopo informativo. Non si tratta di una consulenza legale e non garantisce il rispetto delle leggi applicabili da parte dell&#39;utente. Le funzionalità del prodotto Adobe Campaign descritte di seguito sono elementi di base che, configurati e gestiti in modo appropriato, possono supportare un’implementazione conforme. Ciascun cliente è responsabile della determinazione e del rispetto degli obblighi derivanti dalla legge applicabile.

## Panoramica

Il 14 aprile 2026 la _Commission nationale de l&#39;informatique et des libertés_ (CNIL), l&#39;autorità francese per la protezione dei dati, ha pubblicato una [raccomandazione sull&#39;uso dei pixel di tracciamento nelle e-mail](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf). Poco dopo, l&#39;autorità italiana indipendente per la protezione dei dati (&quot;Garante&quot;) ha pubblicato la disposizione n. 284 (la &quot;disposizione Garante&quot;) del 17 aprile 2026. Entrambi i documenti di guida, anche se non sono giuridicamente vincolanti, chiariscono quando è necessario il consenso e sottolineano l’importanza di pratiche di consenso appropriate per il tracciamento dei pixel delle e-mail. Questa politica potrebbe influire sulle pratiche di invio per qualsiasi entità che consegna e-mail agli abbonati ai sensi della normativa UE sulla privacy applicabile.

Man mano che le autorità di regolamentazione chiariscono le linee guida sui pixel di tracciamento e sui problemi correlati, Adobe continuerà a monitorare le modifiche e informerà i clienti sulle funzionalità tecniche dei prodotti Adobe che supportano il marketing via e-mail, incluso Adobe Campaign. La documentazione di Adobe sui pixel di tracciamento delle e-mail riflette le attuali linee guida normative. Adobe continuerà ad aggiornare la documentazione in base alle esigenze per riflettere le modifiche rilevanti che possono influire sull’utilizzo dei prodotti CXO di Adobe con l’evolversi dei requisiti normativi. I ritardi nell’aggiornamento dei materiali non costituiscono un errore per conto di Adobe.

Le applicazioni di esecuzione del marketing via e-mail di Adobe, tra cui Adobe Journey Optimizer, Journey Optimizer B2B, Adobe Campaign e Marketo Engage, forniscono controlli che possono aiutare i clienti a gestire il tracciamento delle aperture a livello di consegna o e-mail. I clienti sono responsabili della determinazione dei propri obblighi di conformità in base alle linee guida applicabili e ad altre leggi, ma queste funzionalità possono supportare le attività di conformità dei clienti.

## Cos’è un pixel di tracciamento e-mail?

Un pixel di tracciamento e-mail è un’immagine trasparente 1x1 incorporata nel HTML di un’e-mail. Quando il client e-mail del destinatario carica l’immagine, il pixel invia un ping a un server che registra dati quali marca temporale, tipo di dispositivo, client e-mail e, a volte, un indirizzo IP per la posizione approssimativa. Il registro viene quindi associato al record di un destinatario, consentendo agli addetti al marketing di verificare se è stata aperta un’e-mail.

## Assistenza clienti

I clienti che necessitano di assistenza per implementare le modifiche descritte qui sopra possono interagire con il loro ecosistema Adobe esistente. Per domande tecniche sulle funzionalità Adobe a cui si fa riferimento, contatta il tuo Customer Success Manager o Technical Account Manager.

## Funzionalità Adobe Campaign relative al tracciamento e-mail

I clienti possono utilizzare i meccanismi nativi di tracciamento, schema e personalizzazione di Adobe Campaign per affrontare alcuni elementi durante la configurazione dell’architettura, in modo da soddisfare le indicazioni relative ai pixel di tracciamento delle e-mail:

* **Classificazione della consegna.** Estendere `nms:delivery` con un attributo `emailType` (autenticazione, solo recapito messaggi, transazionale, marketing, servizio pubblico, ricerca B2B). La classificazione guida i pixel consentiti senza consenso.

* **Acquisizione del consenso.** Estendi `nms:recipient` con una struttura di consenso per ogni scopo che includa la versione del testo, la marca temporale, l&#39;origine di acquisizione e la scadenza. Estendi i moduli di iscrizione e i centri preferenze per raccogliere il consenso dei pixel separatamente dall’opt-in dell’e-mail.

* **Emissione pixel.** Definisci un `NmsTracking_OpenFormula` per scopo pixel (autenticazione, recapito messaggi, prestazioni, profiling, rilevamento frodi). Una regola di tipologia di consegna seleziona le formule da emettere in base a e-mailType e al consenso per finalità del destinatario. I blocchi di personalizzazione incapsulano la logica in modo che non viva in singole creatività.

* **Ritiro.** Aggiungi un collegamento **Gestisci preferenze tracker** a ogni piè di pagina e-mail, diverso dal collegamento per annullare l&#39;iscrizione. Il collegamento punta a una pagina di destinazione `nms:webApp` autenticata tramite `idTracking`. Il destinatario ritira il consenso con un clic, senza reimmettere l&#39;indirizzo e-mail. Un passaggio di filtro aggiunto al flusso di lavoro standard **Tracking** impedisce che le riaperture delle e-mail consegnate in precedenza vengano sfruttate dopo il ritiro.

* **Prova del consenso.** Acquisisci ogni evento di consenso in un registro di sola aggiunta (ad esempio, uno spazio dei nomi di estensione `pix:consentLog`), con la versione del testo memorizzata separatamente per consentirne la recuperabilità dopo la modifica del testo. Faccia emergere il registro attraverso Adobe Campaign Explorer e come esportazione periodica.
* **Governance della sollecitazione.** Un campo `lastPixelRefusalDate` e una regola di tipologia di filtro impediscono la richiesta di nuovo per almeno sei mesi dopo un rifiuto. Un flusso di lavoro periodico può aiutare a gestire la scadenza del consenso.

* **Generazione rapporti.** I rapporti di Adobe Campaign esistenti continuano a funzionare sui nuovi campi (urlCategory, emailType, i flag di consenso) senza modifiche al codice.

Per ulteriori informazioni sul tracciamento delle e-mail nelle applicazioni di esecuzione del marketing via e-mail di Adobe, consulta la documentazione qui:

| Prodotto | Documentazione di riferimento |
|---|---|
| Campaign v8 | [Verifica messaggi](https://experienceleague.adobe.com/it/docs/campaign/campaign-v8/analytics/tracking/url-tracking){target="_blank"} |
| Campaign Classic | [Introduzione al tracciamento dei messaggi](https://experienceleague.adobe.com/it/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-message-tracking){target="_blank"} |
| Journey Optimizer | [Documentazione di verifica messaggi](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/email/design-email/add-content/message-tracking){target="_blank"} |
| Marketo Engage | [Disattivazione del tracciamento per un collegamento e-mail](https://experienceleague.adobe.com/it/docs/marketo/using/product-docs/email-marketing/general/functions-in-the-editor/disable-tracking-for-an-email-link){target="_blank"} |
| Journey Optimizer B2B | [Documentazione sulle impostazioni e-mail](https://experienceleague.adobe.com/it/docs/journey-optimizer-b2b/user/journey-content/email-channel/add-email){target="_blank"} |


