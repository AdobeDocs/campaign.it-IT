---
title: Pacchetti integrati
description: Scopri cosa sono i pacchetti incorporati in Campaign v8, come differiscono dai pacchetti di dati personalizzati e quali sono disponibili
feature: Architecture
role: Admin, Developer
level: Beginner
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: bae31391-3416-5fbd-bc4b-2cdcae2922db
    internal-label: Architecture
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e656c701-3899-4db3-989c-de0980ddfffa
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: a2ca220e4be9dfb4a90465b69dd08a3552040a07
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 15%
---
# Pacchetti integrati {#built-in-packages}

I pacchetti incorporati (noti anche come pacchetti standard) contengono le funzioni di Adobe Campaign. In Campaign v8, Adobe installa e gestisce questi pacchetti per te. Non è necessario installarli.

## Pacchetti incorporati e pacchetti personalizzati {#built-in-vs-custom}

Campaign utilizza due tipi di pacchetti. Assicurati di lavorare con quello giusto.

| | Pacchetti integrati | Pacchetti personalizzati |
|---|---|---|
| Scopo | Fornisci le funzioni di Campaign, ad esempio canali, integrazioni e componenti aggiuntivi. | Esporta e importa la tua configurazione e i tuoi dati, ad esempio da un ambiente di staging a uno di produzione. |
| Chi li gestisce | Adobe li installa e li gestisce. Managed Cloud Services non consente di modificare i pacchetti incorporati installati. | Puoi crearli, esportarli e importarli. |
| Dove saperne di più | Questa pagina. | [Utilizzare i pacchetti dati](../dev/packages.md) |

## Verifica i pacchetti installati {#check-installed-packages}

Per verificare quali pacchetti incorporati sono installati nell&#39;istanza, passare a **[!UICONTROL Administration > Configuration > Package management > Installed packages]**. Puoi anche visualizzarli nel monitoraggio dell’istanza del Pannello di controllo Campaign. Ulteriori informazioni nella [Panoramica sul monitoraggio di Campaign](../start/monitor.md#monitor-instance).

Se hai bisogno di un pacchetto o di un componente aggiuntivo non fornito, contatta l’Assistenza clienti di Adobe o il tuo Adobe Transition Manager.

## Elenco dei pacchetti incorporati {#list-of-built-in-packages}

Nella tabella seguente sono elencati i pacchetti incorporati a scopo informativo. La disponibilità di ciascun pacchetto è soggetta al contratto di licenza e al modello di distribuzione.

| Pacchetto | Descrizione |
|---|---|
| Consegna | Pacchetto core obbligatorio di Adobe Campaign. Ti consente di inviare consegne. [Ulteriori informazioni](../start/gs-message.md) |
| Campagne di marketing (campagna) | Definisce, ottimizza, esegue e analizza campagne di comunicazione e marketing. [Ulteriori informazioni](../start/campaigns.md) |
| Risorse di marketing (MRM) | Controlla le azioni di marketing in modalità collaborativa, con gestione e tracciamento di attività, budget e risorse di marketing. [Ulteriori informazioni](../../automation/mrm/about-marketing-resource-management.md) |
| Motore di offerta (interazione) | Risponde in tempo reale durante un’interazione con un contatto facendo una o più offerte adattate. [Ulteriori informazioni](../interaction/interaction.md) |
| Social network (social marketing) | Sincronizza Adobe Campaign con X (precedentemente Twitter). [Ulteriori informazioni](../connect/ac-tw.md) |
| Controllo ed esecuzione dei messaggi transazionali (Centro messaggi) | Gestisce i messaggi di attivazione generati dagli eventi nei sistemi informativi, con maggiore disponibilità e una migliore gestione del carico. [Ulteriori informazioni](../send/transactional.md) |
| Canale LINE | Invia le consegne tramite il canale LINE. [Ulteriori informazioni](../send/line/line.md) |
| Canale direct mail | Invia le consegne tramite il canale di direct mailing. [Ulteriori informazioni](../send/direct-mail.md) |
| Canale mobile (SMS) | Invia consegne tramite il canale mobile (SMS), incluso il connettore SMS v2 (generalmente disponibile dalla versione 8.9.1). [Ulteriori informazioni](../send/sms/sms.md) |
| Canale app mobile | Invia notifiche personalizzate ai dispositivi iOS e Android tramite app. [Ulteriori informazioni](../send/push.md) |
| Gestione dei contenuti | Crea newsletter o siti Web ricorrenti, quindi convalida e pubblica i messaggi. [Ulteriori informazioni](../../automation/workflow/content-management.md) |
| Sondaggi online (Gestione sondaggi) | Crea e gestisce moduli online per aggiungere o modificare informazioni sul profilo, iscriversi, annullare l’iscrizione o partecipare a un concorso. [Ulteriori informazioni](../dev/surveys/about-surveys.md) |
| Analisi di marketing | Analizza e misura i dati, calcola le statistiche e semplifica la creazione dei rapporti. [Ulteriori informazioni](../reporting/gs-reporting.md) |
| Gestione della risposta | Misura il successo e la redditività delle campagne di marketing o delle offerte su tutti i canali. [Ulteriori informazioni](../../automation/response/about-response-manager.md) |
| Accesso a dati esterni (Federated Data Access) | Elabora le informazioni memorizzate in database esterni senza modificare la struttura dei dati di Adobe Campaign. [Ulteriori informazioni](../connect/fda.md) |
| Ottimizzazione di Campaign | Controlla, filtra e monitora le consegne in modo che i messaggi soddisfino le esigenze dei clienti e le politiche di comunicazione aziendali. [Ulteriori informazioni](../../automation/campaign-opt/campaign-typologies.md) |
| Monitoraggio del recapito messaggi (recapito messaggi e-mail) | Misura se i messaggi raggiungono la casella in entrata senza essere rimbalzati o contrassegnati come spam. [Ulteriori informazioni](../send/monitoring-deliverability.md) |
| Gestione coupon | Crea set di coupon da aggiungere alle offerte di marketing. [Ulteriori informazioni](../send/personalized-coupons.md) |
| Rendering casella in entrata (IR) | Visualizza in anteprima i messaggi nei contesti in cui possono essere ricevuti e verifica la compatibilità con i principali client di posta elettronica Web e desktop. [Ulteriori informazioni](../send/inbox-rendering.md) |
| Marketing centrale e locale (marketing distribuito) | Implementa campagne di cooperazione tra entità centrali, come la sede centrale, ed entità locali, come i punti vendita. [Ulteriori informazioni](../../automation/distributed-marketing/about-distributed-marketing.md) |
| Connettori CRM | Collega Adobe Campaign a sistemi CRM di terze parti. [Ulteriori informazioni](../connect/crm.md) |
| Connettori di analisi web | Consente ad Adobe Campaign e Adobe Analytics di interagire. [Ulteriori informazioni](../connect/ac-aa.md) |
| Integrazione AEM | Gestisce il contenuto delle e-mail e dei moduli in Adobe Experience Manager. [Ulteriori informazioni](../connect/ac-aem.md) |
| Integrazione dei tipi di pubblico condivisi di Adobe Experience Cloud | Scambia e condivide tipi di pubblico con soluzioni e app [!DNL Adobe CX Enterprise] (precedentemente Adobe Experience Cloud). [Ulteriori informazioni](../start/shared-audiences.md) |
| Integrazione con Adobe Experience Cloud | Importa ed esporta tipi di pubblico da [!DNL Adobe CX Enterprise] (precedentemente Adobe Experience Cloud) soluzioni in Adobe Campaign. [Ulteriori informazioni](../connect/integration.md) |
| Regolamento sulla protezione dei dati sulla privacy | Aggiunge funzionalità per facilitare la conformità in materia di privacy. [Ulteriori informazioni](../start/privacy.md) |
| Supporto AMP | Invia e-mail dinamiche con l’AMP interattivo per il formato e-mail. [Ulteriori informazioni](../send/defining-interactive-content.md) |


>[!NOTE]
>
>I pacchetti di risorse di marketing (MRM), gestione dei coupon e sondaggi online non sono disponibili nel contesto di una distribuzione Enterprise (FFDA) di Campaign. Ulteriori informazioni sono disponibili in [Disponibilità delle funzionalità](../architecture/enterprise-deployment.md#feature-availability).

## Argomenti correlati {#related-topics}

* [Utilizzare i pacchetti dati](../dev/packages.md): creare, esportare e importare pacchetti personalizzati.
* [Flussi di lavoro tecnici](../../automation/workflow/technical-workflows.md): i flussi di lavoro tecnici incorporati e il pacchetto che li installa.
* [Disponibilità delle funzionalità nelle distribuzioni FFDA](enterprise-deployment.md#feature-availability): le funzionalità non disponibili nelle distribuzioni Enterprise (FFDA).
* [Funzioni non supportate](../start/v7-to-v8.md#gs-removed): le funzionalità di Campaign Classic v7 non più supportate in v8.
* [Principi globali](general-architecture.md): cosa è possibile modificare in un ambiente Managed Cloud Services.
* [Introduzione a Campaign v8](../start/get-started.md): panoramica delle funzionalità di base e dei componenti aggiuntivi.
