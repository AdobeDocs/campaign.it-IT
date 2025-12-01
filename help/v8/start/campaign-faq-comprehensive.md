---
title: Domande frequenti su Campaign v8
description: Risposte alle domande frequenti su Adobe Campaign v8 su configurazione, configurazione, messaggistica, flussi di lavoro e altro ancora
feature: Overview
role: User
level: Beginner
keywords: Domande frequenti, Campaign v8, domande, risposte, aiuto, supporto, risoluzione dei problemi
version: Campaign v8
hide: true
hidefromtoc: true
source-git-commit: 26fededf0ee83299477e45e891df30a46c6d40fe
workflow-type: tm+mt
source-wordcount: '13482'
ht-degree: 6%

---

# Domande frequenti {#faq}

Risposte rapide alle domande più frequenti su Adobe Campaign v8. Se stai iniziando a lavorare o stai cercando aiuto per la configurazione avanzata, troverai le risposte organizzate per argomento di seguito.

**Ti avvicini ora a Campaign?** Inizia con [Domande generali](#general) e [Concetti chiave](#key-concepts).\
**Hai bisogno di assistenza tecnica?** Seleziona [Sviluppatori](#developers) e [Impostazioni campagna](#settings).\
**Impossibile trovare la risposta?** Visita i [forum della community](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} o [contatta l&#39;assistenza](#get-help).

**Suggerimento:** utilizzare Ctrl+F (Comando+F su Mac) per cercare parole chiave specifiche in questa pagina. Fare clic su una domanda per espandere la risposta.


## Domande generali {#general}

Risposte alle domande più frequenti su Adobe Campaign v8, tra cui come connetterti, eseguire l’aggiornamento e ottenere supporto.

+++ Come posso collegarmi a Campaign v8?

Per connetterti ad Adobe Campaign, scarica e installa la console client di Campaign. [Ulteriori informazioni](connect.md).

A partire dalla versione v8.6 di Campaign, puoi accedere all&#39;**interfaccia utente di Campaign Web**, disponibile nell&#39;ambiente Adobe Experience Cloud centrale. Experience Cloud è un insieme integrato di applicazioni, prodotti e servizi Adobe per il marketing digitale.

Scopri come connetterti a Adobe Experience Cloud e accedere all&#39;interfaccia Web di Adobe Campaign [in questa pagina](campaign-ui.md#ac-web-ui). Ulteriori informazioni sono disponibili nella [documentazione dell’interfaccia utente di Adobe Campaign Web](https://experienceleague.adobe.com/it/docs/campaign-web/v8/campaign-web-home){target="_blank"}.


**Argomenti correlati:**

[Installa la console client](connect.md) | [Interfaccia utente di Campaign](campaign-ui.md) | [Autorizzazioni utente](gs-permissions.md)

+++

+++ Come migliorare il recapito messaggi e-mail?

La capacità di recapito dei messaggi e-mail, un aspetto critico per il successo del programma di marketing di ogni mittente, è caratterizzata da criteri e regole in continua evoluzione. Per orientarsi nel mondo digitale e raggiungere al meglio i vari tipi di pubblico, è necessario ottimizzare regolarmente la strategia e-mail tenendo conto delle tendenze chiave di recapito messaggi.

Consulta questa guida per scoprire le [best practice per il recapito messaggi](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=it){target="_blank"}

Scopri come implementare la recapitabilità in Campaign [in questa guida](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=it){target="_blank"}

**Argomenti correlati:**

[Introduzione al recapito messaggi](../send/about-deliverability.md) | [Controllare il contenuto del messaggio](../send/control-message-content.md) | [Monitorare il recapito messaggi](../send/monitoring-deliverability.md) | [SpamAssassin](../send/spamassassin.md)

+++

+++ Come posso assicurarmi che la consegna venga inviata senza errori?

Per garantire la corretta consegna, segui i passaggi seguenti:

**Prima dell&#39;invio:**

* Esegui l’analisi della consegna per rilevare gli errori (personalizzazione mancante, destinatari non validi, problemi di contenuto)
* Inviare bozze di test per verificare il rendering e la personalizzazione
* Controlla gli avvisi durante la preparazione
* Verificare il conteggio della popolazione target

**Durante e dopo l&#39;invio:**

* Monitora il dashboard di consegna per statistiche in tempo reale (invio, consegna, mancati recapiti, errori)
* Controlla i registri di consegna per lo stato a livello di messaggio
* Tracciare il tasso di successo, il tasso di mancato recapito e i messaggi di errore
* Rivedi indirizzi messi in quarantena

**Best practice:**

* Impostare gli avvisi per le soglie di errore
* Utilizza ondate (invio batch) per volumi di grandi dimensioni
* Eseguire prima il test con volumi ridotti
* Pulire regolarmente il database dei destinatari
* Monitorare la reputazione del mittente

Ulteriori informazioni sulle [best practice per il monitoraggio delle consegne](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=it){target="_blank"} e [consegne](delivery-best-practices.md).

+++

+++ Posso monitorare l’esecuzione di un flusso di lavoro?

Sì. Campaign fornisce diversi strumenti per monitorare l’esecuzione dei flussi di lavoro:

* **[Dashboard del flusso di lavoro](https://experienceleague.adobe.com/it/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"}** - Visualizza stato, avanzamento ed errori in tempo reale per ogni attività del flusso di lavoro
* **[Registri del flusso di lavoro](https://experienceleague.adobe.com/it/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#displaying-logs){target="_blank"}** - Accedi ai registri di esecuzione dettagliati per risolvere i problemi
* **[Heatmap](https://experienceleague.adobe.com/it/docs/campaign/automation/workflows/monitoring-workflows/heatmap){target="_blank"}** - Visualizza l&#39;attività del flusso di lavoro e identifica i colli di bottiglia delle prestazioni
* **[Audit trail](../reporting/audit-trail.md)** - Monitora tutte le modifiche apportate ai flussi di lavoro
* **[Avvisi](https://experienceleague.adobe.com/it/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators){target="_blank"}** - Imposta le notifiche per gli errori o i ritardi del flusso di lavoro

Per monitorare un flusso di lavoro, aprilo e fai clic sulla scheda **Registri**. Le attività non riuscite sono evidenziate in rosso e puoi visualizzare i dettagli dell’errore facendo clic su di esse.

Ulteriori informazioni su [monitoraggio dell&#39;esecuzione del flusso di lavoro](https://experienceleague.adobe.com/it/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} e [best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=it){target="_blank"}.

+++

+++ Come posso scaricare Campaign?

È possibile ottenere il programma di installazione e Client Console da Adobe Download Center.

Come utente amministratore, accedi ad Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/it/campaign.html){target="_blank"} per scaricare Adobe Campaign.

Ulteriori informazioni sul Centro distribuzione [in questa pagina](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=it){target="_blank"}.

+++

+++ Qual è la procedura per la delega del dominio?

Un sottodominio è una divisione del dominio che può essere utilizzata per isolare i brand o vari tipi di traffico (messaggi transazionali, informazioni di marketing, ecc.).

>[!NOTE]
>
>In qualità di utente di Managed Cloud Services, contatta Adobe per delegare i sottodomini ad Adobe.

+++

+++ Come posso segnalare un problema?

La creazione di un caso consente di contattare il team Assistenza clienti di Adobe per eventuali problemi riscontrati con i prodotti Adobe. Per aiutarti a risolvere un problema, Adobe Admin Console consente di chattare con l’Assistenza clienti di Adobe.

Per segnalare un problema o avviare una sessione di chat nel nuovo sistema, connettiti ad [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"}.

Il sistema richiede account individuali per ogni utente, con le autorizzazioni corrette. Se non riesci ad accedere con il tuo Adobe ID, richiedi l’accesso tramite Experience League e il team di Assistenza clienti completerà la configurazione il prima possibile. [Ulteriori informazioni](https://helpx.adobe.com/it/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

Iscriviti alla community di Campaign: puoi cercare le risposte nelle domande esistenti o chiedere agli esperti. [Partecipa alla conversazione](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}

+++


## Concetti chiave {#key-concepts}

Scopri i concetti fondamentali di Campaign, tra cui autenticazione, interfaccia utente, flussi di lavoro e funzionalità di base per iniziare in modo efficace.

+++ Posso collegarmi a Campaign v8 con un Adobe ID?

Sì! Grazie all’integrazione con IMS (Adobe Identity Management System), gli utenti si connettono alla console Adobe Campaign utilizzando il proprio Adobe ID. Questa integrazione offre i seguenti vantaggi:

* Lo stesso ID può essere utilizzato per tutte le soluzioni Experience Cloud.
* Il collegamento viene memorizzato quando si utilizza Adobe Campaign con diverse integrazioni.
* Policy di gestione password più sicure.
* Utilizzo di account Federated ID (provider di ID esterno).

[Ulteriori informazioni](connect.md) sull&#39;accesso a Campaign v8 con un Adobe ID.

+++

+++ Come posso impostare le autorizzazioni per gli utenti?

In qualità di amministratore di Campaign, puoi impostare le autorizzazioni per gli utenti della tua organizzazione.

Si tratta di una serie di diritti e limitazioni che autorizzano o negano l’autorizzazione a:

* Accesso a determinate funzionalità
* Accedere a determinati dati
* Creare, modificare e/o eliminare dati

[Ulteriori informazioni](../start/gs-permissions.md) sulle autorizzazioni utente in Campaign v8.

**Argomenti correlati:**

[Introduzione alle autorizzazioni](gs-permissions.md) | [Gestione autorizzazioni utente](manage-permissions.md) | [Aggiungere autorizzazioni alle cartelle](folder-permissions.md)

+++

+++ Quali concetti dell’interfaccia utente di Campaign dovrei conoscere?

Fai riferimento a [questa sezione](campaign-ui.md) per ulteriori informazioni sulle nozioni di base dell&#39;interfaccia utente di Adobe Campaign.

A partire dalla versione v8.6 di Campaign, potrai accedere anche alla nuova **interfaccia utente di Campaign Web**, disponibile nell&#39;ambiente Adobe Experience Cloud centrale.

[Ulteriori informazioni sono disponibili nella documentazione relativa all&#39;interfaccia utente Web di Adobe Campaign](https://experienceleague.adobe.com/it/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

+++

+++ Come posso selezionare il pubblico dei miei messaggi?

Con Adobe Campaign, puoi utilizzare strategie diverse per creare tipi di pubblico e selezionare i destinatari target.

[Ulteriori informazioni](../audiences/gs-audiences.md) su come definire i tipi di pubblico in Campaign v8.

+++

+++ Che cos’è un flusso di lavoro?

Adobe Campaign include flussi di lavoro per orchestrare l’intera gamma di processi e attività tra i diversi moduli del server dell’applicazione. Questo ambiente grafico completo ti consente di progettare processi inclusi segmentazione, esecuzione di campagne, elaborazione di file, partecipazione di utenti, ecc. Il motore del flusso di lavoro esegue e traccia tali processi.

Ad esempio, puoi utilizzare un flusso di lavoro per scaricare un file da un server, decomprimerlo e quindi importare i record contenuti all’interno nel database di Adobe Campaign.

Un flusso di lavoro può inoltre coinvolgere uno o più operatori da avvisare o che possono effettuare scelte e approvare processi. In questo modo, è possibile creare un’azione di consegna, assegnare un’attività a uno o più operatori per lavorare sul contenuto, specificare dei target e approvare le prove prima di avviare la consegna.

[Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=it){target="_blank"} sui workflow. Puoi inoltre consultare le [best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=it){target="_blank"}.

**Argomenti correlati:**

[Introduzione ai flussi di lavoro](../config/workflows.md) | [Crea il tuo primo flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=it){target="_blank"} | [Casi di utilizzo del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [Monitorare l&#39;esecuzione del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=it){target="_blank"}

+++

+++ Come si crea e invia una prima e-mail?

La creazione della prima e-mail in Campaign v8 prevede diversi passaggi chiave:

1. **Crea la consegna**. Per iniziare, crea una nuova consegna e-mail da un modello o da zero
1. **Definisci il pubblico** - Seleziona i destinatari di destinazione utilizzando query, elenchi o flussi di lavoro
1. **Progetta il contenuto**. Utilizza la finestra di progettazione e-mail per creare il messaggio con la personalizzazione
1. **Prova con bozze** - Invia e-mail di prova per convalidare il contenuto e la personalizzazione
1. **Analizza e invia** - Esegui l&#39;analisi della consegna per verificare la presenza di errori, quindi invia l&#39;e-mail

Campaign v8 offre due interfacce per la creazione di e-mail:

* **Console client** - Applicazione desktop completa con funzionalità avanzate
* **Interfaccia web di Campaign** - Interfaccia web moderna e intuitiva per una creazione più rapida delle e-mail

[Ulteriori informazioni sulla progettazione e la convalida delle e-mail](../send/email.md) in Campaign v8.

**Argomenti correlati:**

[Crea la prima consegna](create-message.md) | [Utilizzare i modelli di consegna](../send/create-templates.md) | [Best practice per la consegna](delivery-best-practices.md) | [Definisci il contenuto dell&#39;e-mail](../send/defining-the-email-content.md) | [Anteprima e bozze](../send/preview-and-proof.md) | [Configura e invia](../send/configure-and-send.md) | [Personalizzare il contenuto](../send/personalize.md)

+++

+++ Come si inviano i messaggi SMS?

L’invio di messaggi SMS con Campaign v8 richiede la configurazione iniziale e segue quindi un processo di consegna semplice:

**Configurazione iniziale (configurazione una tantum):**

1. **Configura canale SMS** - Configura le impostazioni di consegna SMS e l&#39;account esterno
1. **Configura connessione SMPP** - Connetti al provider di servizi SMS tramite il protocollo SMPP
1. **Verifica la connessione** - Convalida la connettività con il provider SMS
1. **Imposta routing** - Definisci il modo in cui i messaggi SMS vengono instradati attraverso il provider

**Creazione e invio di SMS:**

1. **Crea consegna SMS** - Avvia una nuova consegna SMS da un modello
1. **Definisci i destinatari** - Seleziona il pubblico mobile utilizzando i campi del numero di telefono
1. **Scrivi contenuto SMS** - Crea il messaggio (160 caratteri standard o più a lungo con concatenazione)
1. **Aggiungi personalizzazione** - Includi campi dinamici specifici per ciascun destinatario
1. **Invia bozze** - Verifica consegna SMS per convalidare contenuto e consegna
1. **Analizza e invia** - Esegui analisi e invia al tuo pubblico

**Funzionalità SMS chiave:**

* **Più connettori SMPP** - Supporto per vari provider e protocolli SMS
* **Rapporti di recapito** - Tracciamento dei messaggi inviati, recapitati e non riusciti
* **Codifica caratteri** - Supporto per GSM7, Unicode e caratteri speciali
* **Supporto SMS lunghi** - Concatenazione automatica dei messaggi per testi più lunghi
* **SMS bidirezionale** - Gestisce le risposte SMS in entrata con i flussi di lavoro

[Ulteriori informazioni sulla configurazione e l&#39;invio di SMS](../send/sms/sms.md) in Campaign v8.

**Argomenti correlati:**

[Introduzione agli SMS](../send/sms/sms.md) | [Impostazioni di consegna SMS](../send/sms/sms-delivery-settings.md) | [Impostazioni account esterno SMPP](../send/sms/smpp-external-account.md) | [Creare una consegna SMS](../send/sms/create-sms.md) | [Contenuto SMS](../send/sms/sms-content.md) | [Invia bozze SMS](../send/sms/sms-proofs.md) | [Monitorare SMS](../send/sms/sms-monitor.md)

+++

+++ Come si inviano le notifiche push?

L’invio di notifiche push con Campaign v8 comporta la configurazione dell’integrazione dell’app mobile e la creazione di notifiche coinvolgenti:

**Configurazione iniziale (configurazione una tantum):**

1. **Configurare il canale push** - Configurare le impostazioni del canale di notifica push in Campaign
1. **Integrare Campaign SDK** - Aggiungere Adobe Campaign SDK alla tua app mobile (o utilizzare Raccolta dati)
1. **Configura l&#39;app mobile** - Registra le tue app iOS e Android in Campaign
1. **Configurazione certificati** - Configurazione certificato APNs (iOS) e chiave FCM (Android)
1. **Verifica registrazione** - Verificare che i dispositivi possano registrare e ricevere token

**Creazione e invio di notifiche push:**

1. **Crea consegna push** - Avvia una nuova notifica push da un modello
1. **Seleziona piattaforma** - Scegli iOS, Android o entrambe le piattaforme
1. **Definisci pubblico** - Effettua il targeting degli abbonati all&#39;app utilizzando i dati di abbonamento all&#39;app mobile
1. **Notifica di progettazione** - Crea titolo, messaggio e contenuti rich media
1. **Configura comportamento** - Imposta azioni clic, collegamenti profondi e dati personalizzati
1. **Invia notifiche test** - Convalida su dispositivi reali prima dell&#39;invio
1. **Analizza e invia** - Rivedi il targeting e invia al tuo pubblico di dispositivi mobili

**Funzionalità di notifica push:**

* **Notifiche push potenziate** - Includi immagini, video e pulsanti interattivi (iOS e Android)
* **Personalization** - Contenuto dinamico basato sul profilo utente e sul comportamento
* **Collegamenti profondi** - Indirizza gli utenti a schermi o contenuti specifici dell&#39;app
* **Pianificazione** - Invia in tempi ottimali in base al fuso orario dell&#39;utente
* **Test A/B** - Verifica messaggi diversi e ottimizza il coinvolgimento
* **Tracciamento** - Monitora aperture, clic e conversioni

**Caratteristiche specifiche della piattaforma:**

* **iOS** - Notifiche silenziose, categorie di notifica, personalizzazione audio
* **Android** - Modelli push avanzati, canali di notifica, layout personalizzati

[Ulteriori informazioni sulla configurazione delle notifiche push](../send/push-settings.md) in Campaign v8.

**Argomenti correlati:**

[Creare e inviare notifiche push](../send/push.md) | [Configurare il canale di notifica push](../send/push-settings.md) | [Progettare un push avanzato Android](../send/rich-push-android.md) | [Progettare un push avanzato iOS](../send/rich-push-ios.md) | [Configura con raccolta dati](../send/push-data-collection.md) | [Tracciare e monitorare](tracking.md)

+++

+++ Come si crea una pagina di destinazione?

Puoi utilizzare l’editor di contenuti digitali di Adobe Campaign per progettare pagine di destinazione e definire la mappatura con i campi del database.

[Ulteriori informazioni](../dev/landing-pages.md) nella documentazione di Campaign v8.

Puoi anche utilizzare l&#39;interfaccia utente di Campaign Web per creare e pubblicare pagine di destinazione - [Ulteriori informazioni](https://experienceleague.adobe.com/it/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}.

+++

+++ Come posso tracciare le consegne?

Puoi tenere traccia delle consegne inviate con Campaign v8 tramite [rapporti di consegna](../reporting/delivery-reports.md) dedicati e quindi monitorare le consegne.

Ulteriori informazioni sulla gestione del tracciamento nella campagna [sono disponibili in questa pagina](../start/tracking.md).

**Argomenti correlati:**

[Tracciare e monitorare i messaggi](tracking.md) | [Rapporti di consegna](../reporting/delivery-reports.md) | [Errori di consegna](../send/delivery-failures.md) | [Configurare i collegamenti tracciati](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"}

+++

+++ Come si traduce un messaggio di errore?

Un messaggio di errore viene visualizzato in una lingua straniera? Tutti i messaggi di errore e la relativa traduzione sono elencati in [questa pagina](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=it){target="_blank"}.

+++

+++ Posso creare un modulo web e raccogliere le risposte in Campaign?

Sì. Crea moduli web utilizzando **Applicazioni web di Campaign e Forms** (console client) per il controllo completo della logica e della convalida dei moduli oppure utilizza **Pagine di destinazione di Campaign** (interfaccia Web) con una moderna interfaccia di trascinamento per le sottoscrizioni e la generazione di lead. Entrambi raccolgono i dati direttamente in Campaign e si integrano con i flussi di lavoro per le azioni automatizzate.

**Argomenti correlati:**

[Ulteriori informazioni sulle applicazioni Web e sui moduli](../dev/webapps.md) | [Pagine di destinazione dell&#39;interfaccia utente Web di Campaign](https://experienceleague.adobe.com/it/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++



## Confronto tra Campaign v8 e le versioni precedenti {#v7-differences}

Comprendi le differenze principali tra Campaign v8 e le versioni precedenti (Classic v7 e Standard), tra cui architettura, distribuzione, percorsi di migrazione e modifiche alle funzioni. Che tu provenga da Campaign Classic v7 o Campaign Standard, scopri le novità e come effettuare una transizione fluida.

### Implementazione e architettura

+++ Campaign v8 può essere installato in un ambiente locale o ibrido?

No. Campaign v8 è disponibile esclusivamente come **Managed Cloud Service**, completamente ospitato da Adobe.

**Vantaggi principali di Managed Cloud Services:**

* Prestazioni e scalabilità superiori
* Aggiornamenti automatici: sempre nella versione più recente
* Maggiore sicurezza con monitoraggio continuo
* Nessuna gestione dell&#39;infrastruttura o sovraccarico IT
* Elevata disponibilità integrata e disaster recovery

Ulteriori informazioni sull&#39;architettura di [Campaign v8](../architecture/architecture.md) e sulle [differenze tra Campaign v8 e Classic v7](../start/v7-to-v8.md).

+++

+++ Quali sono le principali differenze tra Campaign v8 e le versioni precedenti?

Campaign v8 è una riprogettazione completa di Adobe Campaign, progettata per una moderna architettura nativa per il cloud e apporta miglioramenti significativi rispetto a Campaign Classic v7 e Campaign Standard:

**Modello di distribuzione:**

* **v8:** solo Managed Cloud Services - completamente in hosting e gestito da Adobe
* **v7/Standard:** Opzioni on-premise, ibride o in hosting disponibili
* **Vantaggio:** nessuna gestione dell&#39;infrastruttura, scalabilità automatica, sicurezza di livello enterprise, monitoraggio proattivo

**Architettura e prestazioni:**

* **v8:** architettura Full FDA (FFDA) avanzata con database PostgreSQL
* **v8:** Velocità effettiva di elaborazione batch che raggiunge un massimo di **20 milioni di operazioni all&#39;ora**
* **v8:** Velocità effettiva messaggi transazionali di **1 milioni all&#39;ora**
* **v8:** Esplorazione dei dati in tempo reale e generazione rapida di tipi di pubblico (minuti anziché ore)
* **Vantaggio:** Prestazioni migliori per operazioni su larga scala e campagne complesse

**Interfaccia utente:**

* **v8:** Nuova **interfaccia utente Web di Campaign** insieme alla console client: intuitiva, accessibile, ideale per gli addetti al marketing
* **v8:** progettazione moderna e reattiva con funzionalità di trascinamento della selezione
* **v8:** workflow semplificati di creazione e gestione delle campagne
* **v8:** condivide molte somiglianze con l&#39;interfaccia di Campaign Standard
* **Vantaggio:** onboarding più rapido, esecuzione più semplice delle campagne, migliore accessibilità, curva di apprendimento minima

**Nuove funzionalità chiave:**

* **Notifiche push potenziate** con immagini, video, pulsanti interattivi, caroselli e timer
* **Assistente AI** per la generazione di contenuti (e-mail, SMS, push) con punteggio di allineamento del brand
* **Infrastruttura SMS aggiornata (SMS v2.0)** con affidabilità e compatibilità migliorate
* **Integrazione di Adobe Experience Manager as a Cloud Service** per una gestione dei contenuti ottimale
* **Reporting avanzato** incluso il Reporting dinamico per gli utenti di Campaign Standard

**Aggiornamenti e manutenzione:**

* **v8:** Aggiornamenti automatici gestiti da Adobe - sempre all&#39;ultima versione stabile con modello di consegna continua
* **v7/Standard:** Pianificazione ed esecuzione dell&#39;aggiornamento manuale richieste
* **Vantaggio:** riduzione degli oneri di manutenzione, accesso immediato alle nuove funzionalità, nessun downtime

**API e integrazione:**

* **v8:** API REST moderne con prestazioni e affidabilità migliorate
* **v8:** Integrazione perfetta con Adobe Experience Cloud e Adobe Experience Platform
* **Vantaggio:** Integrazioni più semplici, migliore interoperabilità, pratiche di sviluppo moderne

[Ulteriori informazioni sulle funzionalità chiave di Campaign v8](whats-new.md)

**Argomenti correlati:**

[Da Campaign Classic v7 a v8](v7-to-v8.md) | Guida alla transizione da [v7 a v8](https://experienceleague.adobe.com/it/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"} | [Da Campaign Standard a v8](acs-to-v8.md) | [Transizione Campaign Standard](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [Guida all&#39;adozione di Campaign v8](https://experienceleague.adobe.com/it/docs/campaign-web/acs-to-ac/home){target="_blank"} | [Matrice di funzionalità di Campaign v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [Architettura di Campaign v8](../architecture/architecture.md)
* [Guardrail e limitazioni](ac-guardrails.md)

+++

+++ Devo effettuare la migrazione da Campaign Classic v7 o Campaign Standard a v8?

**Campaign v8 è ideale per le organizzazioni che richiedono:**

* **Campagne dal volume elevato** - Invia milioni di messaggi con prestazioni e affidabilità migliorate (20 milioni di operazioni/ora)
* **Scalabilità aziendale**: aumento del database e delle campagne senza problemi di prestazioni
* **Interfaccia utente Web moderna** - Interfaccia utente Web di Campaign intuitiva e reattiva per creare campagne più rapidamente e migliorare l&#39;esperienza utente
* **Vantaggi nativi per il cloud** - Utilizzo di aggiornamenti automatici, infrastruttura gestita, scalabilità elastica e monitoraggio proattivo
* **Supporto a lungo termine** - Campaign v8 è la piattaforma strategica di Adobe con supporto esteso, mentre le versioni precedenti raggiungeranno la fine del supporto nei prossimi anni
* **Riduzione del sovraccarico IT** - Eliminazione della gestione dell&#39;infrastruttura e della pianificazione degli aggiornamenti
* **Funzionalità avanzate** - Assistente AI, push avanzato, SMS avanzato, integrazione con Adobe Experience Platform

**Per utenti Campaign Standard:**

Gli utenti di Campaign Standard ora possono effettuare la transizione a Campaign v8 Managed Cloud Services. I vantaggi principali includono:

* **Interfaccia familiare** - L&#39;interfaccia utente Web di Campaign ha molte somiglianze con Campaign Standard, riducendo al minimo la curva di apprendimento
* **Parità di funzionalità** - Le funzionalità principali di Campaign Standard sono state aggiunte a v8 (Reporting dinamico, Branding centralizzato, API REST, pagine di destinazione, frammenti visivi)
* **Supporto avanzato** - Assistenza di prim&#39;ordine per una transizione senza problemi e un monitoraggio continuo della piattaforma
* **Migrazione dati** - Tutti i dati da Campaign Standard vengono importati con interruzioni minime
* **Esperienza utente coerente** - Continua a lavorare con flussi di lavoro e interfacce familiari

**Per utenti di Campaign Classic v7:**

Campaign v8 offre miglioramenti sostanziali mantenendo al contempo le funzionalità di base di Campaign:

* **Doppia interfaccia** - Accedi alla potente console client e alla moderna interfaccia web di Campaign
* **Prestazioni migliori** - Prestazioni delle query ed elaborazione dei dati notevolmente migliorate
* **Vantaggi per il cloud** - Aggiornamenti automatici, patch di sicurezza, backup e ripristino gestiti da Adobe
* **Architettura moderna** - Architettura FFDA migliorata con PostgreSQL per una migliore scalabilità

**Quando considerare la migrazione:**

* L’istanza Campaign corrente gestisce grandi volumi di dati (milioni di profili)
* Stai riscontrando problemi di prestazioni con flussi di lavoro complessi o targeting
* Per ridurre i costi di gestione e manutenzione dell&#39;infrastruttura
* È necessaria un&#39;integrazione perfetta con Adobe Experience Cloud o Adobe Experience Platform
* Stai comunque pianificando un aggiornamento importante o un aggiornamento dell&#39;infrastruttura
* **Tecnologia a prova di futuro** - Le versioni precedenti raggiungeranno la fine del supporto
* **Il tuo team ha bisogno di un&#39;interfaccia moderna** - L&#39;interfaccia Web di Campaign offre una migliore accessibilità per gli addetti al marketing

**Considerazioni sulla migrazione:**

* Adobe fornisce supporto, guida e strumenti per la migrazione
* v8 è solo Managed Cloud Service (nessuna distribuzione on-premise o ibrida)
* Alcune implementazioni tecniche potrebbero essere diverse. Rivedi la [matrice delle funzionalità](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* La migrazione e il testing dei dati richiedono pianificazione e risorse
* **Per gli utenti di Campaign Standard** - La transizione è progettata per essere fluida con un&#39;interruzione minima del flusso di lavoro

**Passaggi successivi:**

Contatta il tuo rappresentante Adobe per:

* Valutare la fattibilità della migrazione e la tempistica
* Comprendere i vantaggi specifici del caso d’uso
* Pianificare la strategia di migrazione e l&#39;allocazione delle risorse
* Accedere agli strumenti di migrazione e al supporto

**Argomenti correlati:**

**Per utenti di Campaign Classic v7:** [Da Campaign Classic v7 a v8](v7-to-v8.md) | Guida dettagliata da [v7 a v8](https://experienceleague.adobe.com/it/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}

**Per gli utenti di Campaign Standard:** [Transizione di Campaign Standard alla versione v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [Guida all&#39;adozione di Campaign v8](https://experienceleague.adobe.com/it/docs/campaign-web/acs-to-ac/home){target="_blank"} | [Panoramica da Campaign Standard a v8](https://experienceleague.adobe.com/it/docs/campaign-web/acs-to-ac/overview){target="_blank"} | [Introduzione per gli addetti al marketing](https://experienceleague.adobe.com/it/docs/campaign-web/acs-to-ac/marketers){target="_blank"} | [Introduzione per amministratori/sviluppatori](https://experienceleague.adobe.com/it/docs/campaign-web/acs-to-ac/admin-developers){target="_blank"}

**Risorse generali:** [Matrice di funzionalità di Campaign v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [Matrice di compatibilità](compatibility-matrix.md)

+++

+++ Come posso eseguire la migrazione dell’ambiente Campaign Classic v7 on-premise o ibrido ad Adobe Managed Services?

La migrazione dell’ambiente Campaign Classic v7 on-premise o ibrido ad Adobe Managed Services rappresenta spesso un passaggio strategico prima della transizione a Campaign v8. Questa migrazione offre vantaggi immediati e allo stesso tempo pone le basi per la futura adozione di v8.

**Perché effettuare la migrazione a Managed Services?**

* **Percorso di Campaign v8** - Managed Services fornisce un percorso di aggiornamento a v8 più fluido con la sua interfaccia web e le funzionalità GenAI
* **Scalabilità e affidabilità** - Sfrutta l&#39;infrastruttura cloud di Adobe per migliorare le prestazioni e la scalabilità automatica
* **Sicurezza avanzata** - Vantaggi del monitoraggio continuo, delle patch di sicurezza automatiche e della protezione di livello enterprise
* **Supporto specialistico** - Accesso alle risorse del team di supporto e dell&#39;infrastruttura di Adobe
* **Sovraccarico IT ridotto** - Nessuna gestione dell&#39;infrastruttura, backup automatici e disaster recovery inclusi
* **Integrazione Adobe Experience Platform** - Integrazione perfetta con Adobe Experience Platform per soluzioni di marketing complete

**Considerazioni importanti:**

* **Nessuna migrazione automatizzata** - Attualmente non è disponibile alcuno strumento di migrazione automatizzata. Pianificazione ed esecuzione manuale sono necessarie
* **Supporto Adobe Professional Services**: si consiglia vivamente di rivolgersi a Adobe Professional Services per assistenza e competenze
* **Preparazione richiesta**: organizza i dati, valuta i requisiti, controlla le pratiche correnti e assicurati che siano compatibili
* **Complessità della migrazione** - Considerare fattori quali complessità dell&#39;ambiente, volume dei dati, personalizzazioni e dipendenze degli oggetti

**Problemi chiave da pianificare per:**

1. **Limitazioni per l&#39;importazione di dati XML/Blob** - Può essere importato solo utilizzando pacchetti o metodi di dump e ripristino
2. **Tabelle di dati di grandi dimensioni** - Le tabelle dei destinatari e i registri di consegna/tracciamento richiedono speciali strategie di ottimizzazione
3. **ID oggetto** - Ogni oggetto importato riceve un nuovo ID, che richiede il riallineamento dell&#39;ID per la continuità
4. **Aggiornamenti build** - Pianifica l&#39;aggiornamento alla versione più recente disponibile v7 prima della migrazione

**Roadmap di migrazione di alto livello:**

1. **Due diligence e definizione dell&#39;ambito** - Eseguire un&#39;analisi approfondita, definire l&#39;ambito e valutare le esigenze di provisioning con il team di Adobe Managed Services
2. **Controllo e ottimizzazione dell&#39;ambito** - Rivedi le pratiche correnti, valuta il modello di dati e i flussi, identifica le pratiche non valide e riduce gli elementi di migrazione non necessari
3. **Pulizia e preparazione** - Risolvi i problemi identificati, rimuovi i dati inutilizzati ed esegui gli aggiornamenti della build alla versione più recente
4. **Migrazione iniziale (fase)** - Provisioning di una nuova istanza cloud, struttura di backup, importazione di pacchetti, configurazione di sequenze/contatori, importazione di oggetti, riallineamento di ID, importazione di dati non XML e convalida
5. **Migrazione finale (produzione)** - Aggiorna la produzione con un&#39;istanza di fase verificata, esegui test delle prestazioni, esegui la migrazione diretta alla produzione e abilita il tracciamento e le funzionalità in tempo reale

**Best practice:** esegui sempre la migrazione iniziale su un&#39;istanza di staging prima di procedere alla produzione per ridurre al minimo i rischi e convalidare il processo.

**Guida introduttiva:**

Contatta il tuo rappresentante Adobe e chiedi a Adobe Professional Services di:

* Valuta l’ambiente corrente e la fattibilità della migrazione
* Sviluppare un piano di migrazione dettagliato con tempistiche e dipendenze
* Ricevi consigli da esperti durante l’intero processo di migrazione
* Sfruttare le best practice comprovate ed evitare problemi comuni

Ulteriori informazioni sulla [migrazione a Managed Services](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic-blogs/migrate-your-adobe-campaign-v7-onprem-hybrid-environment-to/ba-p/681605){target="_blank"} nella community Adobe Campaign.

**Argomenti correlati:**

[Da Campaign Classic v7 a v8](v7-to-v8.md) | Guida alla transizione da [v7 a v8](https://experienceleague.adobe.com/it/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"} | [Architettura di Campaign v8](../architecture/architecture.md) | [Adobe Professional Services](https://business.adobe.com/it/customers/consulting-services/main.html){target="_blank"}

+++

+++ Quali sono le principali differenze terminologiche e di funzionalità in Campaign v8?

Campaign v8 offre la maggior parte delle funzionalità di Campaign Classic v7 e Campaign Standard con miglioramenti, ma alcune funzionalità hanno subito modifiche a causa dell’architettura nativa per il cloud e alcuni termini differiscono tra le versioni.

**Differenze terminologiche (da Campaign Standard a v8):**

* **Le risorse personalizzate** sono ora **Schemi**
* **I messaggi** sono denominati **Consegne**
* **Gli utenti del prodotto** sono ora **Operatori**
* **I ruoli** sono configurati con **diritti denominati**
* **I gruppi di sicurezza** sono ora **Gruppi di operatori**
* **Le unità organizzative** sono gestite tramite **autorizzazioni cartella**

**Aggiornamenti terminologici interfaccia utente Web di Campaign:**

I seguenti termini sono stati aggiornati nell’interfaccia utente di Campaign Web (la console client utilizza termini tradizionali):

* **I destinatari** sono ora **Profili**
* **Gli indirizzi seed** sono ora **Profili di test**
* **L&#39;analisi della consegna** è ora **Preparazione consegna** (fai clic sul pulsante **Prepara**)
* **Anteprima e-mail** è disponibile tramite il pulsante **Simula contenuto**
* **Gli elenchi** sono diventati **Tipi di pubblico**

**Non disponibile nella versione 8:**

* **Distribuzioni locali e ibride** - v8 è solo Managed Cloud Services
* **Accesso diretto al database**. Utilizzare le API e gli strumenti forniti
* **Infrastruttura gestita dal cliente**: Adobe gestisce tutte le infrastrutture
* **Aggiornamenti build manuali** - Ora automatici (Adobe gestiti)

**Diverse implementazioni in v8:**

* **Flussi di lavoro tecnici** - Alcuni ottimizzati per l&#39;architettura cloud, potrebbero funzionare in modo diverso
* **Struttura del database** - L&#39;architettura FFDA avanzata potrebbe richiedere adattamenti dello schema
* **Integrazioni personalizzate** - Potrebbero essere necessari aggiornamenti per l&#39;architettura basata su cloud
* **Personalizzazioni di basso livello** - Alcune richiedono approcci diversi nell&#39;ambiente gestito

**Migliorato o sostituito in v8:**

* **Aggiornamenti build** - Automatico con modello di consegna continua anziché manuale
* **Ottimizzazione delle prestazioni** - Gestito dall&#39;ottimizzazione dell&#39;infrastruttura Adobe
* **Patch di sicurezza** - Applicate automaticamente da Adobe
* **Backup e ripristino** - Gestito da Adobe come parte del servizio
* **Interfaccia utente** - Nuova interfaccia utente di Campaign Web con la console client

**Funzionalità aggiunte per gli utenti di Campaign Standard che passano alla versione v8:**

* **Reporting dinamico**: report personalizzabili in tempo reale con analisi demografica
* **Branding centralizzato**: definizione delle linee guida visive e tecniche per il brand
* **API REST** - Crea integrazioni e crea il tuo ecosistema
* **Miglioramenti alle pagine di destinazione** - Parità di funzionalità migliorata con Campaign Standard
* **Frammenti visivi** - Componenti visivi riutilizzabili per e-mail e modelli di contenuto

**Importante:** la maggior parte delle funzioni di marketing e operative sono disponibili e migliorate nella versione v8. Le funzioni tecniche e a livello di infrastruttura sono gestite da Adobe nell’ambiente cloud.

**Argomenti correlati:**

[Matrice di capacità](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [Matrice di compatibilità](compatibility-matrix.md) | [Guardrail e limitazioni](ac-guardrails.md) | Guida alla transizione da [v7 a v8](v7-to-v8.md)

[Transizione da Campaign Standard a v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++

### Versioni e aggiornamenti

+++ Qual è la mia versione di Campaign?

Verifica il [numero della versione e della build](upgrades.md#version) dal menu **Help > About…** della console del client di Campaign.

+++

+++ Come posso aggiornare Campaign alla versione più recente?

 Adobe Campaign viene aggiornato regolarmente. Versioni minori vengono rilasciate ogni anno con nuove funzioni, miglioramenti e correzioni. Inoltre, rilasciamo periodicamente build contenenti solo correzioni cumulative.

La frequenza regolare degli aggiornamenti è volta a far ottenere agli utenti il meglio e più recente, mantenendo l’ambiente sicuro e migliorando l’esperienza di utilizzo del prodotto. Per questo motivo riteniamo fondamentale eseguire sempre la versione più recente di Adobe Campaign.

**Nota:** in qualità di utente di Managed Cloud Services, l&#39;istanza viene aggiornata da Adobe con le nuove versioni.

Ulteriori informazioni su [Versioni e aggiornamenti di Campaign](upgrades.md).

+++

+++ Come posso essere informato del rilascio di una nuova versione?

Resta informato sulle nuove versioni di Campaign tramite questi canali:

* **Rappresentante Adobe** - Contatta direttamente l&#39;utente quando è disponibile una nuova versione
* **Note sulla versione** - Tutte le versioni e le modifiche sono documentate in [Note sulla versione di Campaign](release-notes.md)
* **Aggiornamenti dei prodotti con priorità Adobe** - [Abbonati](https://www.adobe.com/it/subscription/priority-product-update.html){target="_blank"} per ricevere notifiche e-mail
* **Community di Campaign** - Partecipa a [discussioni](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} per aggiornamenti anticipati

In qualità di utente di Managed Cloud Services, Adobe gestisce gli aggiornamenti e coordina i tempi con te.

**Argomenti correlati:**

[Note sulla versione](release-notes.md) | [Novità](whats-new.md) | [Versioni e aggiornamenti di Campaign](upgrades.md)

+++

+++ Perché la mia organizzazione ha bisogno di un aggiornamento?

L’aggiornamento alla versione più recente di Campaign è fondamentale per la sicurezza, le prestazioni e la qualità del supporto.

**Vantaggi chiave:**

* **Sicurezza migliorata** - Protezione contro vulnerabilità, ultime patch e protezione avanzata dei dati
* **Supporto migliorato** - Risoluzione più rapida dei problemi, accesso alle correzioni di bug, supporto prioritario per le versioni recenti
* **Prestazioni migliorate** - Ottimizzazioni del database e del flusso di lavoro, migliore scalabilità, operazioni più affidabili
* **Nuove funzionalità** - Funzioni più recenti, integrazioni Adobe Experience Cloud migliorate, miglioramenti all&#39;interfaccia utente moderni

Adobe consiglia vivamente di eseguire la versione più recente. In qualità di cliente di Managed Cloud Services, gli aggiornamenti vengono eseguiti da Adobe con interruzioni minime.

**Argomenti correlati:**

[Versioni e aggiornamenti di Campaign](upgrades.md) | [Novità](whats-new.md) | [Matrice di compatibilità](compatibility-matrix.md)

+++

+++ Qual è il processo e la tempistica per un aggiornamento?

In qualità di cliente di Managed Cloud Services, Adobe gestisce l’intero processo di aggiornamento con un impatto minimo sulle operazioni.

**Processo:**

1. **Notifica** - Adobe ti avvisa con settimane di anticipo
2. **Pianificazione** - Pianifica l&#39;aggiornamento al momento ottimale con il tuo rappresentante Adobe
3. **Preparazione** - Adobe prepara l&#39;ambiente e convalida
4. **Esecuzione** - Adobe aggiorna l&#39;infrastruttura con tempi di inattività minimi
5. **Convalida** - Test post-aggiornamento da parte di Adobe
6. **Aggiornamento console client** - Le console client vengono aggiornate in modo che corrispondano alla versione del server

**Le tue responsabilità:**

* Coordinare le parti interessate interne per la programmazione
* [Aggiorna le console client](connect.md#upgrade-ac-console) alla nuova versione
* Test di campagne e flussi di lavoro dopo l’aggiornamento
* Segnala i problemi al supporto Adobe

Adobe esegue l’aggiornamento dell’infrastruttura. Non è necessario eseguire alcuna azione tecnica sui server.

**Argomenti correlati:**

[Versioni e aggiornamenti di Campaign](upgrades.md) | [Aggiorna console client](connect.md#upgrade-ac-console) | [Note sulla versione](release-notes.md)

+++

### Domande sulla migrazione

+++ Come utente Campaign Classic v7, posso effettuare la migrazione a Campaign v8?

La migrazione automatizzata da un ambiente esistente di Campaign Classic v7 non è ancora disponibile.

Campaign v8 è disponibile **solo** come Managed Cloud Service e non può essere distribuito in ambienti on-premise o ibridi.

Per ulteriori informazioni sul processo di migrazione, contatta il tuo rappresentante Adobe.

+++

### Compatibilità e integrazioni

+++ Con quali sistemi e componenti è compatibile Campaign v8?

Puoi ottenere l’elenco di tutti i sistemi e i componenti supportati per la build più recente di Campaign nella [Matrice di compatibilità di Adobe Campaign](compatibility-matrix.md).

+++

+++ Posso utilizzare Campaign v8 con altre soluzioni Adobe?

Sì. Campaign v8 si integra perfettamente con le soluzioni Adobe Experience Cloud per creare un potente ecosistema di marketing unificato. In qualità di Managed Cloud Service, v8 è progettato per l’integrazione nativa con le applicazioni aziendali di Adobe.

**Integrazioni chiave disponibili:**

* **Adobe Experience Platform** - Utilizzo di profili cliente unificati e dati in tempo reale
* **Adobe Analytics** - Misura le prestazioni della campagna e il comportamento del cliente nei diversi canali
* **Adobe Target** - Personalizza i contenuti in base ai segmenti e al comportamento dei clienti
* **Adobe Experience Manager** - Centralizzazione della creazione di contenuti e della gestione delle risorse
* **Adobe Audience Manager** - Crea e attiva segmenti di pubblico su più piattaforme

**Vantaggi:** dati cliente unificati, esperienze utente coerenti, flussi di lavoro semplificati e funzionalità di personalizzazione avanzate.

**Configurazione:** l&#39;integrazione con le soluzioni Adobe richiede l&#39;autenticazione Adobe Identity Management System (IMS), configurata automaticamente per Campaign v8 Managed Cloud Services.

**Argomenti correlati:**

[Integrazioni Adobe Campaign](../connect/integration.md) | [Connessione con Adobe ID](connect.md)

+++

### Limitazioni e considerazioni

+++ Quali sono i limiti di Campaign v8?

Campaign v8 introduce modifiche architetturali (in particolare nelle implementazioni FFDA) che apportano miglioramenti significativi alle prestazioni, ma anche alcune differenze rispetto a Campaign Classic v7. Comprendere queste funzioni aiuta a pianificare le migrazioni e a definire le aspettative appropriate.

**Considerazioni principali su v8:**

* **Architettura FFDA** - Le distribuzioni Enterprise utilizzano il database cloud (Snowflake) con diversi modelli di accesso ai dati
* **Aggiornamenti di unità** - Gli aggiornamenti dei dati devono essere eseguiti in flussi di lavoro, non tramite API o accesso diretto al database
* **Scritture in tempo reale**: ottimizzate per le operazioni batch anziché per singoli aggiornamenti ad alta frequenza
* **Modello dati** - Alcune personalizzazioni dello schema richiedono approcci diversi
* **Accesso al database esterno** - La configurazione FDA (Federated Data Access) è diversa da quella di v7

**Funzionalità non disponibili nelle distribuzioni FFDA:**

* Indagini (disponibili nelle implementazioni standard di v8)
* Gestione delle risorse marketing (MRM)
* Alcune configurazioni di connettori specifiche

**Considerazioni sulla migrazione:**

* Il codice personalizzato con scritture dirette del database richiede il refactoring
* Le integrazioni API possono richiedere un adeguamento per l’elaborazione in batch
* I flussi di lavoro devono seguire le best practice FFDA per le operazioni sui dati
* I test sono essenziali per convalidare gli sviluppi personalizzati

**Importante:** queste limitazioni si stanno evolvendo man mano che Adobe continua a migliorare v8. Consulta la documentazione più recente per lo stato corrente e la roadmap.

**Argomenti correlati:**

[Migrazione da Campaign v7 a v8](../start/v7-to-v8.md#limitations) | [Architettura FFDA](../architecture/enterprise-deployment.md)

+++

## Profili e tipi di pubblico {#audiences}

Risposte alle domande su gestione dei profili, creazione di tipi di pubblico, importazione di dati e targeting dei destinatari delle campagne.

+++ Come si creano i destinatari?

Crea i destinatari manualmente nella console client per i singoli profili, importa dai file (CSV/TXT) per le aggiunte in blocco, utilizza moduli web per l’auto-registrazione o integra tramite API da sistemi esterni. Utilizza i flussi di lavoro di importazione per carichi di dati ricorrenti.

**Argomenti correlati:**

[Creare i profili manualmente](../audiences/create-profiles.md) | [Importa profili da un file](../audiences/import-profiles.md) | [Raccogli profili con moduli web](../audiences/collect-profiles.md)

+++

+++ Come si importano i profili?

Campaign fornisce diversi metodi di importazione: importazione semplice dei file tramite l’importazione guidata, importazione basata su flusso di lavoro per trasformazioni complesse, importazioni ricorrenti con flussi di lavoro pianificati da SFTP e importazione API per l’integrazione programmatica.

Per le importazioni di file, prepara il file di dati (CSV/TXT, codifica UTF-8), utilizza l’importazione guidata o il flusso di lavoro, mappa le colonne sui campi di Campaign, definisci le regole di aggiornamento/inserimento e testa prima con un piccolo campione. Utilizza i flussi di lavoro per le importazioni ricorrenti e applica le regole di deduplicazione.

**Argomenti correlati:**

[Importa guida dati](../start/import.md) | [Flusso di lavoro di importazione ricorrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=it){target="_blank"} | [Attività di caricamento dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=it){target="_blank"}

+++

+++ Come posso definire la popolazione target per una campagna di marketing?

Campaign offre più metodi di targeting: crea query con criteri visivi, esegui il targeting di elenchi o segmenti esistenti, importa destinatari da file esterni (CSV, TXT) o applica filtri predefiniti. Puoi combinare i criteri con la logica AND/OR, escludere popolazioni specifiche, utilizzare gruppi di controllo e suddividerli per il test A/B. Visualizza sempre in anteprima la dimensione della popolazione target prima dell’invio.

[Definire i target della campagna](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=it){target="_blank"} | [Attività query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=it){target="_blank"} | [Crea pubblico](../audiences/create-audiences.md)

+++

+++ Come posso creare un elenco di profili?

Un elenco è un set statico di destinatari che puoi targetizzare nelle consegne e riutilizzare nelle campagne.

**Tre metodi di creazione:**

* **Creazione manuale:** Passare a **[!UICONTROL Profiles and Targets > Lists]** e fare clic su **[!UICONTROL Create]**. Aggiungi i destinatari da una query, da una selezione individuale o da una cartella.

* **Automazione del flusso di lavoro:** Utilizza l&#39;attività **[!UICONTROL List update]** per creare e gestire automaticamente elenchi dai risultati delle query o dai dati importati.

* **Durante l&#39;importazione:** Crea un elenco durante l&#39;importazione dei profili per salvarli come gruppo riutilizzabile.

**Suggerimento:** utilizza i flussi di lavoro per gli elenchi che richiedono aggiornamenti regolari e la creazione manuale per la segmentazione una tantum.

**Argomenti correlati:**

[Crea pubblico](../audiences/create-audiences.md) | [Attività di aggiornamento elenco](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html?lang=it){target="_blank"}

+++

+++ Come posso deduplicare una popolazione prima di inviare un messaggio?

Utilizzare l&#39;attività **[!UICONTROL Deduplication]** in un flusso di lavoro per rimuovere i destinatari duplicati prima della consegna. Posizionalo tra le attività **[!UICONTROL Query]** e **[!UICONTROL Delivery]**, quindi scegli i criteri di deduplicazione (in genere indirizzo e-mail o ID destinatario) e quale record mantenere.

**Suggerimento:** deduplicare sempre prima dell&#39;invio per assicurarsi che ogni persona riceva il messaggio una sola volta.

Ulteriori informazioni sull&#39;[attività Deduplication](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=it){target="_blank"}

+++

+++ Come identificare ed eseguire il targeting degli abbonati a una newsletter?

Campaign tiene traccia automaticamente degli abbonamenti alle newsletter tramite i servizi di informazione. Per eseguire il targeting degli abbonati:

* Utilizza un&#39;attività **[!UICONTROL Query]** e filtra in base a **[!UICONTROL Subscriptions]** > seleziona il servizio newsletter
* Eseguire il targeting degli abbonati direttamente dalla consegna scegliendo **[!UICONTROL To > Subscribers of an information service]**
* Crea elenchi di sottoscrittori con l&#39;attività del flusso di lavoro **[!UICONTROL Subscription Services]**

Campaign tiene traccia della cronologia degli abbonamenti/annullamenti e gestisce automaticamente il consenso/diniego.

**Argomenti correlati:**

[Gestione sottoscrizioni](../start/subscriptions.md) | [Attività query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=it){target="_blank"}

+++

+++ Qual è la best practice per escludere profili da una popolazione target?

Utilizza l&#39;attività **[!UICONTROL Exclusion]** in un flusso di lavoro per rimuovere i profili indesiderati dalla destinazione. Inseriscilo dopo le attività di targeting e definisci quale popolazione escludere.

Ulteriori informazioni sull&#39;[attività di esclusione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html?lang=it){target="_blank"}

+++

+++ Posso utilizzare profili esterni senza importarli in Campaign?

Sì, Campaign v8 consente di lavorare con profili esterni memorizzati in un database esterno senza caricarli in Adobe Campaign. [Ulteriori informazioni](../audiences/external-profiles.md).

+++

+++ Come posso creare profili di test per le consegne?

I profili di test sono destinatari speciali utilizzati per inviare bozze e convalidare le consegne senza influire sul database di produzione. Creali in **[!UICONTROL Profiles and Targets > Test profiles]** oppure utilizza la funzione **[!UICONTROL Seed addresses]** per aggiungere automaticamente i destinatari del test alle tue consegne per il controllo qualità e il monitoraggio della casella in entrata.

Ulteriori informazioni su [Profili di test](../audiences/test-profiles.md)

+++

## Progettazione messaggio {#design}

Scopri come progettare messaggi di marketing efficaci in Campaign v8, inclusi modelli e-mail, tecniche di personalizzazione e contenuti multilingue. Progetta i tuoi messaggi nella console client o utilizza il moderno **Invia e-mail a Designer** nell&#39;interfaccia utente di Campaign Web per un&#39;esperienza di modifica visiva migliorata.

+++ Quali sono le best practice per la progettazione delle e-mail in Campaign?

Linee guida chiave: assicurati che la progettazione sia reattiva per dispositivi mobili, usa codice compatibile HTML 4.0/XHTML con CSS in linea, ottimizza le immagini (sotto i 100 KB) con testo alt, utilizza campi unione di personalizzazione, testa i client e-mail prima dell’invio e includi una versione in testo normale. Per una consegna dei messaggi ottimale, è necessario impostare la dimensione totale dell&#39;e-mail su un valore inferiore a 500 KB.

[Guida alla progettazione delle e-mail](../send/email.md) | [Best practice per la consegna](delivery-best-practices.md)

+++

+++ Che cos’è un modello di consegna?

Un modello di consegna è una consegna preconfigurata che salva tutte le impostazioni e i parametri per il riutilizzo in più campagne. I modelli includono regole di destinazione, progettazione del contenuto, personalizzazione, impostazioni tecniche (mittente, risposta a) e regole di tipologia. Crea una volta e riutilizza per mantenere la coerenza e accelerare la creazione delle campagne.

Scopri come [creare modelli di consegna](../send/create-templates.md)

+++

+++ Posso importare facilmente un HTML esistente per creare un’e-mail in Campaign?

Sì. Importa i contenuti HTML tramite copia/incolla diretta nell’editor dei contenuti, carica i file dal computer o carica da un URL. Assicurati che il tuo HTML utilizzi codice compatibile con le e-mail (HTML 4.0/XHTML) con CSS in linea e ospiti immagini su un server pubblico. Campaign aggiunge automaticamente la personalizzazione e il tracciamento al HTML importato.

**Suggerimento:** Per una migliore esperienza di progettazione delle e-mail, utilizza **E-mail Designer** nell&#39;interfaccia utente di Campaign Web, che offre funzionalità di trascinamento e modelli reattivi incorporati, anziché importare HTML non elaborati.

Scopri come [importare contenuti HTML](../send/defining-the-email-content.md)

+++

+++ Come posso creare una newsletter basata su abbonamento in Campaign?

Sì. Utilizza i servizi informativi di Campaign per gestire gli abbonamenti alle newsletter. Le funzionalità principali includono la gestione automatica di consenso/rinuncia, il tracciamento degli abbonamenti, la gestione della conformità (RGPD, CAN-SPAM), il supporto per più newsletter, l’integrazione web per i moduli di iscrizione e la consegna mirata agli abbonati.

Scopri come [gestire gli abbonamenti](../start/subscriptions.md)

+++

+++ Come posso personalizzare i messaggi?

Campaign offre funzionalità di personalizzazione per creare messaggi pertinenti e mirati in base ai dati, al comportamento e alle preferenze dei destinatari.

**Opzioni Personalization:**

* **Campi di personalizzazione** - Inserire i dati del destinatario (ad esempio, `"Hello {{firstName}}")`
* **Blocchi di personalizzazione** - Utilizza blocchi di contenuto predefiniti o personalizzati
* **Contenuto condizionale** - Visualizza contenuto diverso in base ai criteri del destinatario
* **Dati comportamentali** - Sfrutta la cronologia di navigazione, i modelli di acquisto o le metriche di coinvolgimento

Test della personalizzazione prima dell’invio per verificare il corretto funzionamento dei campi di unione e della logica condizionale.

**Argomenti correlati:**

[Guida di Personalization](../send/personalize.md) | [Campi di personalizzazione](../send/personalization-fields.md) | [Contenuto condizionale](../send/conditions.md)

+++

+++ Posso inviare messaggi multilingue?

Sì. Campaign v8 offre funzionalità multilingue, con la **Interfaccia web di Campaign** che fornisce l’approccio più semplice. L’interfaccia utente web offre una distribuzione nativa multilingue con varianti di lingua: aggiungi varianti di lingua alla consegna e Campaign invia automaticamente la versione appropriata in base alla lingua preferita del destinatario. Disponibile per e-mail, notifiche push, SMS e messaggi transazionali.

Funzioni chiave: duplicazione automatica dei contenuti, invio automatico basato sulla lingua, fallback della lingua predefinito e gestione semplificata delle varianti.

La console client supporta anche contenuti multilingue utilizzando contenuti condizionali e flussi di lavoro, ma richiede una configurazione più manuale.

[Consegne multilingue (interfaccia Web)](https://experienceleague.adobe.com/it/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [Contenuto condizionale (console client)](../send/conditions.md)

+++

+++ Posso localizzare un modulo web?

Sì. Le applicazioni web di Campaign supportano la localizzazione multilingue. Definisci le traduzioni per tutti gli elementi del modulo (etichette, pulsanti, messaggi, testo di errore), con il rilevamento automatico della lingua in base al profilo del destinatario o alle impostazioni del browser. In un’unica applicazione web sono supportate più versioni linguistiche, con fallback a una lingua predefinita quando necessario.

Ulteriori informazioni sulla [localizzazione applicazioni Web](../dev/webapps.md)

+++

+++ Posso utilizzare contenuti basati sull’intelligenza artificiale nelle e-mail?

Sì, ma **solo tramite l&#39;interfaccia utente Web di Campaign**. L’Assistente per l’intelligenza artificiale, con tecnologia Microsoft Azure OpenAI e Adobe Firefly, consente di creare contenuti professionali e coerenti per il brand per e-mail, SMS e notifiche push.

**Funzionalità chiave:**

* Genera testo (copia e-mail, righe dell’oggetto, contenuto SMS/push) e immagini allineate al brand
* Creare varianti di contenuto ottimizzate per diversi tipi di pubblico
* Ottimizzare il contenuto (elaborare, riepilogare, riformulare, semplificare)
* Caricare risorse del brand e ottenere un punteggio di allineamento del brand
* Utilizza il contenuto esistente come immagine di riferimento e carica come immagine di riferimento di stile

**Nota:** l&#39;Assistente all&#39;intelligenza artificiale è disponibile esclusivamente nell&#39;interfaccia utente Web di Campaign e attualmente supporta solo la lingua inglese. Gli utenti devono disporre delle autorizzazioni appropriate e devono accettare un contratto utente.

[Panoramica dell&#39;Assistente AI](https://experienceleague.adobe.com/it/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [Casi di utilizzo dell&#39;Assistente IA](https://experienceleague.adobe.com/it/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [Allineamento marchio](https://experienceleague.adobe.com/it/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Verifica e invio dei messaggi {#send}

Scopri le best practice per testare, convalidare, inviare e tracciare i messaggi di marketing per garantire la corretta consegna della campagna.

+++ Cos’è l’analisi della consegna?

L’analisi della consegna è una fase di convalida che Campaign esegue prima dell’invio. Calcola la popolazione target, convalida il contenuto, verifica la presenza di errori, applica le regole di tipologia e stima il volume di consegna.

Campaign genera registri che mostrano avvisi ed errori. Gli errori bloccano la consegna e devono essere corretti; gli avvisi sono indicativi. Rivedi sempre i registri di analisi prima dell’invio.

Ulteriori informazioni nella [Guida all&#39;analisi della consegna](../send/delivery-analysis.md)

+++

+++ Perché dovrei creare delle prove?

Le bozze sono messaggi di test che convalidano la consegna prima di inviarla al pubblico principale. Utilizza le bozze per verificare la personalizzazione, testare il rendering del contenuto tra i client e-mail, confermare i collegamenti e il lavoro di tracciamento, controllare immagini e allegati e convalidare la reattività dei dispositivi mobili.

Le bozze consentono di rilevare gli errori prima che raggiungano migliaia di destinatari, abilitare l’approvazione delle parti interessate e testare il posizionamento della casella in entrata. Invia bozze a più client e dispositivi e-mail e ottieni sempre l’approvazione prima degli invii di produzione.

Ulteriori informazioni sono disponibili nella [guida Bozze e anteprima](../send/preview-and-proof.md)

+++

+++ Come si utilizzano gli indirizzi di seed in Adobe Campaign?

Gli indirizzi seed sono destinatari speciali aggiunti automaticamente a ogni consegna per test, controllo della qualità e monitoraggio, senza che soddisfino i criteri di destinazione. Utile per il monitoraggio continuo, il test di posizionamento della casella in entrata, la convalida della direct mailing e la visibilità delle parti interessate.

**Differenze chiave dalle bozze:**

* **Indirizzi seed** - Aggiunti automaticamente alle consegne di produzione, conteggiati per il volume di invio
* **Bozze** - Il test viene inviato prima della produzione, non conteggiare verso il volume, utilizzato per la convalida

Gestisci indirizzi seed in **[!UICONTROL Resources > Campaign management > Seed addresses]**. Mantieni gli elenchi piccoli per evitare di influenzare le metriche di consegna.

[Guida agli indirizzi seed](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html?lang=it){target="_blank"}

+++

+++ Come posso impostare un processo di approvazione prima di inviare messaggi?

Campaign fornisce flussi di lavoro di approvazione per garantire che i messaggi soddisfino gli standard di qualità prima dell’invio. Configura le approvazioni per contenuto, destinazione, estrazione (direct mailing) e budget a livello di campagna o consegna.

**Configurazione:**

Crea gruppi di operatori in **[!UICONTROL Administration > Access management > Operator groups]**, quindi assegna gruppi di approvazione nelle proprietà della campagna o della consegna. Campaign invia e-mail di notifica ai revisori che possono approvare, rifiutare o richiedere modifiche.

**Per consegne autonome (non in una campagna):**

Utilizza **bozze come processo di approvazione**. Invia le bozze al gruppo di approvazione per la convalida e invia sempre una nuova bozza dopo aver apportato modifiche per garantire che le parti interessate rivedano la versione più recente.

**Argomenti correlati:**

[Convalida della consegna](../send/preview-and-proof.md) | [Approvazioni campagne](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=it){target="_blank"}

+++

+++ Cos’è una regola di tipologia?

Le regole di tipologia sono regole aziendali automatizzate applicate durante l’analisi della consegna per convalidare e ottimizzare l’invio dei messaggi. Garantiscono la conformità alle politiche di marketing, proteggono il recapito messaggi e prevengono l’affaticamento dei clienti.

**Tipi di regole principali:**

* **Regole di filtro** - Escludi destinatari (inseriti nell&#39;elenco Bloccati, non sottoscritti, in quarantena)
* **Regole di pressione** - Controlla la frequenza dei messaggi per evitare di sopraffare i destinatari
* **Regole di capacità** - Limita il volume dei messaggi per l&#39;elaborazione dei limiti di capacità o ISP
* **Regole di controllo** - Verifica la validità del messaggio (oggetto, collegamento per annullare l&#39;iscrizione, formato mittente)

Le regole sono raggruppate in tipologie e applicate durante l’analisi della consegna. Campaign può escludere i destinatari, bloccare la consegna o generare avvisi in base alle regole.

[Guida alle regole di tipologia](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=it){target="_blank"}

+++

+++ Come posso inviare le e-mail in modo graduale?

Sì. L’invio ondata suddivide la consegna in più batch inviati a intervalli pianificati. Questo è essenziale per le campagne su grandi volumi per bilanciare il carico del server, impedire la limitazione dell’ISP, creare la reputazione del mittente con i nuovi IP e gestire gli opt-out/bounce tra un’ondata e l’altra.

**Configurazione:**

Nelle proprietà di consegna, abilita l’invio delle onde e definisci il numero di onde (o dimensione batch), l’intervallo tra le onde e la distribuzione delle onde (percentuali lineari o personalizzate). Campaign divide automaticamente la popolazione target e invia ogni ondata secondo la pianificazione.

Utilizza le ondate per le campagne di grandi dimensioni, monitora le prestazioni della prima ondata prima di continuare e lascia un tempo sufficiente tra un’ondata e l’altra per elaborare i mancati recapiti e le rinunce.

Scopri come [configurare l&#39;invio ondata](../send/configure-and-send.md#sending-using-multiple-waves)

+++

+++ Quali sono i passaggi chiave per creare un’e-mail in Campaign?

La creazione di un’e-mail in Campaign v8 prevede i seguenti passaggi chiave: creare la consegna, definire il pubblico target, progettare il contenuto, aggiungere personalizzazioni, configurare le impostazioni (mittente, oggetto, risposta), eseguire analisi della consegna, inviare bozze per il test e infine inviare o pianificare.

**Passaggi chiave:**

1. **Crea la consegna** - Scegli e-mail come canale e facoltativamente seleziona un modello di consegna
1. **Definisci la destinazione** - Seleziona il pubblico del destinatario utilizzando query, elenchi o file importati
1. **Progetta il contenuto** - Crea il messaggio utilizzando l&#39;editor e-mail (Designer e-mail interfaccia Web o editor console client)
1. **Aggiungi personalizzazione** - Inserisci campi dinamici, blocchi di personalizzazione e contenuto condizionale
1. **Configura impostazioni** - Imposta l&#39;indirizzo del mittente, la riga dell&#39;oggetto, la risposta e i parametri di consegna
1. **Esegui analisi consegna** - Campaign convalida il contenuto, calcola la destinazione e verifica la presenza di errori
1. **Invia bozze** - Verifica l&#39;e-mail con i gruppi di approvazione per convalidare il rendering e il contenuto
1. **Invia o pianifica** - Invia immediatamente alla destinazione principale o alla pianificazione per una data successiva

**Due opzioni di interfaccia:**

* **Interfaccia Web di Campaign** - Interfaccia moderna con funzionalità avanzate di E-mail Designer, Assistente AI e multilingue
* **Console client** - Interfaccia tradizionale con funzionalità di targeting e flusso di lavoro avanzate

**Suggerimento:** utilizza l&#39;interfaccia utente Web di Campaign per creare e-mail in modo più rapido e intuitivo con strumenti di progettazione moderni. Utilizza la console client per campagne basate su flussi di lavoro avanzate o con targeting complesso.

**Argomenti correlati:**

[Crea la tua prima e-mail](create-message.md) | [Guida alla progettazione delle e-mail](../send/email.md)

+++

+++ Come si pianifica una consegna?

Campaign ti consente di pianificare le consegne per l’invio futuro, in modo da ottimizzare i tempi di invio e coordinare le campagne.

**Opzioni di pianificazione:**

* **Proprietà di consegna** - Invia immediatamente, pianifica per data/ora specifica o rinvia per ore/giorni
* **Livello della campagna** - Coordinare tutte le consegne all&#39;interno di una campagna
* **Attività Scheduler flusso di lavoro** - Per consegne ricorrenti, modelli complessi e campagne attivate da eventi

Campaign supporta anche l’ottimizzazione della data di contatto (ora di invio migliore per destinatario) e l’adattamento del fuso orario (stessa ora locale per tutti i destinatari).

Scopri come [pianificare l’invio della consegna](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ Posso aggiungere un allegato alle e-mail?

Sì. Campaign supporta allegati statici (lo stesso file per tutti i destinatari) e allegati personalizzati (file diversi per destinatario in base ai dati del profilo). Aggiungi allegati nella sezione **[!UICONTROL Attachments]** delle proprietà di consegna.

**Considerazioni importanti:**

* Mantieni gli allegati al di sotto di 1 MB per una consegna dei messaggi ottimale
* Gli allegati possono attivare i filtri anti-spam; verifica accuratamente prima dell’invio
* Evita i tipi di file comunemente bloccati dai client e-mail (.exe, .zip, .js)
* Per i file di grandi dimensioni, puoi utilizzare al loro posto i collegamenti di download tracciati

Utilizza formati di file sicuri (PDF, JPEG, PNG, DOCX) e testa con indirizzi seed prima degli invii di produzione.

Ulteriori informazioni nella [Guida agli allegati e-mail](../send/email.md#attachments)

+++

+++ Come posso configurare collegamenti tracciati in una consegna e-mail?

Campaign converte automaticamente tutti gli URL nell’e-mail in collegamenti tracciati per monitorare il coinvolgimento dei destinatari. Accedi alla sezione **[!UICONTROL Tracking]** della consegna per configurare le impostazioni di tracciamento per ogni collegamento.

**Opzioni di configurazione:**

* **Attiva/disattiva tracciamento** - Tracciamento controllo per collegamento
* **Etichette collegamento** - Aggiungi nomi descrittivi per il reporting (ad esempio, &quot;Acquista ora CTA&quot;)
* **Categorie di collegamenti** - Raggruppa i collegamenti per tipo per l&#39;analisi aggregata
* **Tipo di tracciamento** - Traccia clic, aperture o entrambi

Campaign tiene traccia dei collegamenti di contenuto, dei collegamenti alle pagine mirror e dei collegamenti per annullare l’abbonamento e può includere un pixel di tracciamento opzionale per le aperture delle e-mail. Utilizza etichette e categorie significative per semplificare la generazione di rapporti e identificare rapidamente i contenuti a prestazioni elevate.

**Argomenti correlati:**

[Guida al tracciamento dei collegamenti](../start/tracking.md) | [Best practice per il tracciamento](../send/send.md)

+++

+++ Dove posso accedere ai registri di consegna e di tracciamento?

Accedi ai registri di consegna e tracciamento direttamente da ogni dashboard di consegna. Nella console del client, fare clic sulla scheda **[!UICONTROL Delivery]** in basso. Nell’interfaccia utente di Campaign Web, passa alla sezione **[!UICONTROL Logs]**.

**Registri disponibili:**

* **Registri di consegna** - Messaggi inviati con i dettagli e lo stato del destinatario (inviati, in sospeso, non riusciti)
* **Registri di tracciamento** - Interazioni del destinatario (aperture, clic) con timestamp
* **Registri di esclusione** - Destinatari esclusi per motivi (quarantena, regole di tipologia, duplicati)
* **Registri di trasmissione** - Cronologia di invio completa, inclusi tentativi ed errori

Utilizza questi registri per risolvere i problemi di consegna, analizzare il coinvolgimento e mantenere l’igiene degli elenchi.

**Argomenti correlati:**

[Monitoraggio della consegna](../send/send.md) | [Guida al tracciamento](../start/tracking.md)

+++

+++ Dove posso ottenere i report di consegna?

Campaign fornisce rapporti completi incorporati per analizzare le prestazioni di consegna, il coinvolgimento dei destinatari e l’efficacia della campagna. Accedi ai rapporti dalla scheda **[!UICONTROL Reports]** in qualsiasi consegna, dal dashboard della campagna o dal menu globale **[!UICONTROL Reports]** per l&#39;analisi tra campagne.

**I report chiave includono:**

* **Riepilogo consegne** - Invia statistiche, aperture, clic, mancate consegne e annullamenti di abbonamenti
* **Hot click** - Mappa di calore visiva delle prestazioni dei collegamenti
* **Indicatori di tracciamento** - Tassi di click-through e metriche di coinvolgimento
* **Non recapitabili** - Analisi delle e-mail non consegnate con motivi di errore

I rapporti sono disponibili sia nella console client che nell’interfaccia utente web di Campaign con visualizzazioni moderne.

**Argomenti correlati:**

[Rapporti di consegna incorporati](../reporting/delivery-reports.md) | [Generazione rapporti per campagne](../reporting/gs-reporting.md)

+++

+++ In che modo Adobe Campaign definisce e gestisce gli indirizzi in quarantena?

Campaign gestisce automaticamente un elenco di quarantena per proteggere la reputazione del mittente e migliorare il recapito messaggi. Gli indirizzi messi in quarantena vengono automaticamente esclusi dalle consegne future fino a quando non vengono convalidati o rimossi dalla quarantena.

**Perché gli indirizzi vengono messi in quarantena:**

* **Mancati recapiti permanenti** - Errori di recapito permanenti (indirizzo e-mail non valido, dominio inesistente, cassetta postale eliminata)
* **Soglia di mancato recapito non permanente** - Errori temporanei ripetuti (cassetta postale piena, server temporaneamente non disponibile) che superano la soglia di errore
* **Reclami spam** - Destinatari che contrassegnano le e-mail come spam
* **Indirizzi non validi** - Indirizzi con errori di sintassi o che non superano la convalida
* inserire nell&#39;elenco Bloccati **&#x200B;**&#x200B;- Destinatari che hanno rinunciato o richiesto di essere esclusi

**Funzionamento della quarantena:**

Campaign tiene traccia degli errori di consegna per ogni indirizzo. Quando un indirizzo raggiunge la soglia di errore configurata, viene automaticamente messo in quarantena ed escluso da tutte le consegne future durante l’analisi. I mancati recapiti permanenti (errori permanenti) vengono posti immediatamente in quarantena, mentre i mancati recapiti non permanenti richiedono più errori prima della quarantena.

**Gestione degli indirizzi messi in quarantena:**

Accesso alla gestione della quarantena in **[!UICONTROL Administration > Campaign Management > Non deliverables Management]**. Puoi visualizzare gli indirizzi messi in quarantena, rimuovere manualmente gli indirizzi convalidati dalla quarantena o configurare regole di pulizia automatica.

**Suggerimento:** controlla regolarmente l&#39;elenco di quarantena. L’aumento dei tassi di quarantena segnala spesso problemi di qualità dei dati che richiedono attenzione prima che influiscano sulla reputazione del mittente.

**Argomenti correlati:**

[Guida alla quarantena](../send/quarantines.md) | [Gestione delle e-mail non consegnate](../send/delivery-failures.md)

+++

## Flussi di lavoro {#workflows}

Scopri come utilizzare i flussi di lavoro per automatizzare i processi, gestire i dati e orchestrare campagne di marketing complesse in Adobe Campaign.

+++ Quali sono i passaggi chiave per creare un flusso di lavoro?

Crea flussi di lavoro per automatizzare i processi di marketing in Campaign:

1. **Crea un nuovo flusso di lavoro**. Passare a **[!UICONTROL Profiles and Targets > Jobs > Targeting workflows]** o **[!UICONTROL Administration > Production > Technical workflows]** e fare clic su **[!UICONTROL Create]**
1. **Aggiungi attività** - Trascina le attività dalla palette (targeting, controllo del flusso, attività di azione)
1. **Configura attività** - Fai doppio clic su ogni attività per impostare i parametri e definire la logica
1. **Attività di connessione** - Collega attività con transizioni per definire il flusso di esecuzione
1. **Verifica e convalida** - Utilizza il diagramma del flusso di lavoro per verificare la logica, quindi verifica con un set di dati ridotto
1. **Esegui** - Avvia il flusso di lavoro manualmente o pianificalo per l&#39;esecuzione automatica

Modelli di flusso di lavoro comuni: importazione di dati, segmentazione del pubblico, invio di consegne, arricchimento dei dati e orchestrazione cross-channel.

**Argomenti correlati:**

[Crea un flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=it){target="_blank"} | [Attività del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"} | [Best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=it){target="_blank"} | [Casi di utilizzo del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ Come posso importare dati in Campaign?

Importa dati in Campaign utilizzando più metodi a seconda delle tue esigenze:

**Importazione file semplice:**

* Utilizza l’Importazione guidata per importare in modalità CSV/TXT una tantum con un’interfaccia guidata
* Ideale per caricamenti manuali e rapidi di dati

**Importazione basata su flusso di lavoro:**

* Crea flussi di lavoro con attività **[!UICONTROL Data loading (file)]** per importazioni complesse
* Aggiunta di trasformazioni, arricchimento e deduplicazione dei dati
* Pianificazione delle importazioni ricorrenti da SFTP, directory locali o archiviazione cloud

**Integrazione API:**

* Utilizzare le API REST per importare i dati a livello di programmazione da sistemi esterni
* Ideale per la sincronizzazione in tempo reale con CRM, e-commerce o altre piattaforme

**Best practice:** verifica sempre con campioni di piccole dimensioni, utilizza la codifica UTF-8, mappa correttamente i campi, applica regole di deduplicazione e pianifica importazioni di grandi dimensioni nelle ore di minore utilizzo.

**Argomenti correlati:**

[Best practice per l&#39;importazione](../start/import.md) | [Attività di caricamento dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=it){target="_blank"} | [Flusso di lavoro di importazione ricorrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=it){target="_blank"}

+++

+++ Quali sono i casi d’uso comuni dei flussi di lavoro in Campaign?

I flussi di lavoro delle campagne possono automatizzare praticamente qualsiasi processo di marketing. Di seguito sono riportati i casi d’uso più comuni:

**Gestione dati:**

* **Importare e caricare dati** - Automatizzare le importazioni di file da SFTP, API o archiviazione cloud
* **Pulizia dati** - Deduplicazione dei profili, standardizzazione dei formati, rimozione dei record non validi
* **Arricchimento dei dati** - Migliora i profili con dati esterni o campi calcolati
* **Gestione elenchi**: aggiorna automaticamente i segmenti in base al comportamento o ai criteri

**Automazione campagna:**

* **Serie di benvenuto** - Attiva le e-mail di onboarding automatico per i nuovi abbonati
* **Campagne di compleanno** - Invia messaggi personalizzati in occasione di compleanni o anniversari del cliente
* **Nuovo coinvolgimento** - Esegui il targeting degli abbonati inattivi con campagne di riconquista
* **Abbandono carrello** - Invia promemoria ai clienti che hanno lasciato elementi nel carrello

**Destinazione avanzata:**

* **Test A/B** - Dividi i tipi di pubblico e testa diverse varianti di contenuto
* **Segmentazione dinamica** - Crea segmenti in base a comportamenti o attributi in tempo reale
* **Punteggio lead** - Calcola e aggiorna i punteggi lead in base al coinvolgimento
* **Orchestrazione cross-channel** - Coordinare la messaggistica tra e-mail, SMS e push

**Monitoraggio e avvisi:**

* **Monitoraggio del flusso di lavoro** - Traccia lo stato del flusso di lavoro e invia avvisi in caso di errori
* **Monitoraggio della consegna** - Monitora le prestazioni della campagna e le percentuali di mancato recapito
* **Manutenzione del database** - Pulizia automatica dei vecchi registri e dei dati temporanei

**Integrazione e sincronizzazione:**

* **Sincronizzazione CRM** - Mantieni i dati del cliente sincronizzati con Salesforce, Dynamics, ecc.
* **Integrazioni API** - Connessione con piattaforme di e-commerce, strumenti di analisi o sistemi personalizzati
* **Flussi di lavoro attivati da eventi** - Reagire a eventi in tempo reale da siti Web o app

**Argomenti correlati:**

[Libreria dei casi di utilizzo del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [Crea un flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=it){target="_blank"} | [Best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=it){target="_blank"} | [Flussi di lavoro di targeting](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html?lang=it){target="_blank"} | [Flussi di lavoro di gestione dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/about-data-management.html){target="_blank"}

+++

+++ Come posso aggiornare i dati di Campaign con un flusso di lavoro?

Utilizza l&#39;attività **[!UICONTROL Update data]** nei flussi di lavoro per eseguire operazioni in blocco sul database:

**Operazioni supportate:**

* **Inserisci** - Aggiungi nuovi record al database
* **Aggiornamento** - Modifica i record esistenti in base ai criteri corrispondenti
* **Inserisci o aggiorna** - Aggiungi nuovi record o aggiorna quelli esistenti (upsert)
* **Elimina** - Rimuovi i record che corrispondono a criteri specifici

**Casi d&#39;uso comuni:**

* Aggiorna attributi profilo dopo l’arricchimento dei dati
* Sincronizzare i dati con sistemi esterni
* Gestisci appartenenze a elenchi in base al comportamento
* Pulire e deduplicare i dati
* Applica modifiche di stato in blocco (ad esempio rinuncia, quarantena)

Configura le chiavi di riconciliazione in modo che corrispondano accuratamente ai record e scegli le opzioni di aggiornamento (aggiorna tutti i campi o solo quelli vuoti).

**Argomenti correlati:**

[Aggiorna attività dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=it){target="_blank"} | [Attività di gestione dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ Come posso sfruttare le funzionalità di gestione dati?

Le attività di gestione dati di Campaign consentono operazioni di dati sofisticate all’interno dei flussi di lavoro per operazioni di targeting e segmentazione complesse.

**Attività di gestione dati chiave:**

* **Arricchimento** - Aggiungi dati da tabelle o origini esterne correlate alla tua popolazione di lavoro
* **Dividi** - Segmenta le popolazioni in base ai criteri o distribuiscili in modo casuale
* **Deduplicazione** - Rimuovi i record duplicati in base alle chiavi specificate
* **Aggiornare i dati** - Eseguire operazioni di inserimento, aggiornamento o eliminazione in blocco
* **Modifica dimensione** - Cambia dimensioni di targeting (ad esempio, da destinatari a sottoscrizioni)
* **Intersection/Union/Exclusion** - Combina o filtra più popolazioni

**Casi d&#39;uso comuni:**

* Arricchire i profili con la cronologia degli acquisti o i dati sul comportamento
* Segmentare i tipi di pubblico in più gruppi per messaggi diversi
* Rimuovi duplicati prima della consegna
* Integrare dati da database esterni (FDA - Federated Data Access)
* Creare query e join di più tabelle complessi

Queste attività ti consentono di lavorare con i dati non direttamente nella tabella dei destinatari principale ed eseguire operazioni avanzate sul database.

**Argomenti correlati:**

[Attività di gestione dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"} | [Flussi di lavoro di targeting](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html?lang=it){target="_blank"} | [Attività di arricchimento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=it){target="_blank"}

+++

+++ Posso automatizzare l’invio di messaggi personalizzati?

Sì. I flussi di lavoro consentono campagne di messaggi personalizzati completamente automatizzate in base ai dati dei destinatari, al comportamento e ai criteri personalizzati.

**Struttura del flusso di lavoro di automazione:**

1. **Query** - Seleziona il pubblico di destinazione in base ai criteri
1. **Arricchimento** - Aggiungere dati di personalizzazione da tabelle correlate
1. **Dividi** - Segmento in gruppi per diverse varianti di messaggio (facoltativo)
1. **Consegna** - Invia messaggi personalizzati con campi unione
1. **Scheduler** - Configura esecuzione ricorrente per campagne automatizzate

**Opzioni Personalization:**

* Utilizzare i dati del profilo del destinatario (nome, posizione, preferenze)
* Includi dati comportamentali (cronologia acquisti, punteggi di coinvolgimento)
* Applicare contenuto condizionale in base a segmenti o attributi
* Calcola i valori dinamici (punti fedeltà, date di scadenza)

Scenari comuni: campagne di compleanno, abbandono del carrello, programmi fedeltà, campagne di riconquista e messaggi attivati da eventi.

**Argomenti correlati:**

[Guida di Personalization](../send/personalize.md) | [Casi di utilizzo del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=it){target="_blank"} | [Attività di arricchimento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=it){target="_blank"}

+++

+++ Come posso dividere un pubblico in sottoinsiemi con un flusso di lavoro?

Utilizzare l&#39;attività **[!UICONTROL Split]** per suddividere una singola popolazione in più sottoinsiemi in base a criteri o regole di distribuzione.

**Metodi di suddivisione:**

* **Condizioni di filtro** - Crea sottoinsiemi in base a criteri (ad esempio, gruppi di età, posizione, stato VIP)
* **Distribuzione percentuale** - Dividi in modo casuale in percentuali uguali o personalizzate per il test A/B
* **Limita record** - Limita le dimensioni del sottoinsieme (primi N record, primi X%, selezione casuale)
* **Raggruppamento dati** - Crea un sottoinsieme per valore distinto (ad esempio, un sottoinsieme per paese)

**Casi d&#39;uso comuni:**

* Test A/B con gruppi di controllo
* Indirizzamento delle preferenze del canale (e-mail e SMS)
* Rollout progressivo (invia al 10%, quindi al 90%)
* Messaggistica specifica per il segmento (VIP, clienti standard e nuovi)
* Bilanciamento del carico tra più server di consegna

Ogni sottoinsieme suddiviso scorre in una transizione separata, consentendo un’elaborazione o una consegna diversa per ciascun gruppo.

**Argomenti correlati:**

[Attività divisa](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html?lang=it){target="_blank"} | [Guida ai test A/B](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ Come posso aggiornare i dati sui destinatari da un file esterno?

Sì. Utilizza i flussi di lavoro per aggiornare i dati di Campaign con i valori di file esterni (CSV, TXT).

**Struttura del flusso di lavoro:**

1. **Caricamento dati (file)** - Carica il file esterno e mappa le colonne
1. **Arricchimento** (facoltativo) - Aggiungere dati o trasformazioni aggiuntive
1. **Riconciliazione** - Definisci le chiavi per far corrispondere i record dei file con i record del database (ad esempio, indirizzo e-mail, ID destinatario)
1. **Aggiorna dati** - Scegliere le opzioni di aggiornamento:
   * Aggiorna solo record corrispondenti
   * Aggiorna campi esistenti o solo quelli vuoti
   * Inserisci nuovi record se non viene trovata alcuna corrispondenza

**Scenari comuni:**

* Aggiornare gli attributi del profilo dalle esportazioni CRM
* Aggiorna gli stati di abbonamento da sistemi esterni
* Sincronizzare punti fedeltà o punteggi cliente
* Aggiornare le preferenze di consenso/rinuncia
* Arricchire i profili con i dati comportamentali

**Best practice:** utilizza identificatori univoci per la riconciliazione, convalida i dati prima dell&#39;aggiornamento, verifica con campioni di piccole dimensioni e pianifica aggiornamenti regolari per la sincronizzazione in corso.

**Argomenti correlati:**

[Importa guida dati](../start/import.md) | [Attività di caricamento dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=it){target="_blank"} | [Aggiorna attività dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=it){target="_blank"}

+++

+++ Come posso identificare ed eseguire il targeting dei nuovi destinatari?

Utilizza i flussi di lavoro con le attività di query per identificare i destinatari aggiunti di recente e attivare le campagne di benvenuto automatizzate.

**Approccio query:**

Creare un filtro di query nel campo **[!UICONTROL Created date]** per selezionare i destinatari aggiunti entro un intervallo di tempo specifico (ad esempio, ultime 24 ore, ultima settimana).

**Struttura del flusso di lavoro di benvenuto automatica:**

1. **Scheduler** - Esecuzione giornaliera o a intervalli specifici
1. **Query** - Selezionare i destinatari creati dall&#39;ultima esecuzione
1. **Deduplicazione** (facoltativo) - Assicurati che non vi siano duplicati
1. **Consegna** - Invia messaggio di benvenuto
1. **Aggiorna dati** (facoltativo) - Contrassegna i destinatari come &quot;accolti&quot;

**Tecnica avanzata con aggregati:**

Utilizza le funzioni di aggregazione per identificare in modo dinamico le aggiunte più recenti e confrontare con i destinatari elaborati in precedenza per un sofisticato rilevamento dei nuovi destinatari.

**Argomenti correlati:**

[Attività query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=it){target="_blank"} | [Utilizzo di aggregati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=it){target="_blank"} | [Programmi di benvenuto](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=it){target="_blank"}

+++

+++ Come si utilizzano le attività del flusso di lavoro?

I flussi di lavoro delle campagne vengono generati utilizzando quattro categorie principali di attività, ciascuna con scopi specifici:

**Attività di targeting** - Definisci e perfeziona il pubblico

* Query, suddivisione, deduplicazione, arricchimento, intersezione, unione, esclusione
* Utilizza questi per selezionare i destinatari, segmentare le popolazioni e combinare le origini dati

**Attività di controllo del flusso di lavoro** - Gestisci logica e tempistica del flusso di lavoro

* Scheduler, Wait, Test, Fork, AND-join, OR-join, Jump
* Controllare il flusso di esecuzione, aggiungere condizioni e gestire percorsi paralleli

**Attività azione** - Eseguire operazioni e inviare messaggi

* Consegna, Aggiorna dati, Caricamento dati (file), Estrazione dati (file), Codice JavaScript
* Eseguire operazioni di database, trasferimenti di file e invio di messaggi

**Attività evento** - Reagire ai trigger esterni

* Segnale esterno, raccoglitore file, trasferimento HTTP, SMS, e-mail
* Gestire i dati in arrivo e le interazioni con sistemi esterni

Per utilizzare le attività, trascinale dalla palette all’area di lavoro del flusso di lavoro, fai doppio clic per configurare i parametri e collegali con le transizioni.

**Argomenti correlati:**

[Riferimento attività di targeting](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=it){target="_blank"} | [Riferimento attività controllo flusso](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=it){target="_blank"} | [Riferimento attività azione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=it){target="_blank"} | [Riferimento attività evento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html?lang=it){target="_blank"}

+++

+++ Quali sono le best practice per i flussi di lavoro?

Segui queste best practice per creare flussi di lavoro efficienti, manutenibili e affidabili:

**Progettazione e organizzazione:**

* Utilizza nomi chiari e descrittivi per flussi di lavoro e attività
* Aggiungere etichette e descrizioni alla logica del documento
* Raggruppa visivamente le attività correlate per migliorarne la leggibilità
* Suddividere processi complessi in più flussi di lavoro più piccoli

**Ottimizzazione delle prestazioni:**

* Limitare le dimensioni dei risultati delle query con i filtri appropriati
* Utilizzare tabelle temporanee per l&#39;archiviazione dati intermedia
* Pianificazione di flussi di lavoro a uso intensivo di risorse nelle ore di minore utilizzo
* Evitare cicli inutili e iterazioni eccessive

**Gestione e monitoraggio degli errori:**

* Aggiungere percorsi di gestione degli errori con i supervisori
* Configurare gli avvisi per i flussi di lavoro non riusciti
* Test con campioni di dati di piccole dimensioni prima dell’esecuzione completa
* Esamina regolarmente i registri di esecuzione per individuare eventuali problemi di prestazioni

**Manutenzione e governance:**

* Archiviare o eliminare flussi di lavoro obsoleti
* Modifiche al flusso di lavoro del controllo delle versioni e modifiche ai documenti
* Limita la complessità del flusso di lavoro (obiettivo per &lt; 20 attività)
* Utilizzare i modelli di flusso di lavoro per i modelli ricorrenti

**Sicurezza e gestione dati:**

* Applica le autorizzazioni operatore appropriate
* Pulire i dati temporanei con la pulizia del flusso di lavoro
* Evitare i valori di codifica fissa: utilizzare variabili e opzioni
* Rivedere e ottimizzare regolarmente i flussi di lavoro con prestazioni scadenti

**Argomenti correlati:**

[Guida alle best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=it){target="_blank"} | [Crea un flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=it){target="_blank"} | [Monitorare i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=it){target="_blank"}

+++

## Impostazioni campagna {#settings}

Configura l’istanza Campaign con le impostazioni, le integrazioni e le configurazioni giuste per ottimizzare le operazioni di marketing.

+++ Posso cambiare la lingua dell’interfaccia di Campaign?

Dipende dall’interfaccia in uso. La lingua della **console client** è fissa, ma la **interfaccia utente Web di Campaign** consente ai singoli utenti di modificare le preferenze della lingua.

**Console client (applicazione desktop):**

* La lingua viene impostata al momento della creazione dell’istanza e non può essere modificata
* La console client e il server devono utilizzare la stessa lingua
* Ogni istanza di Campaign funziona in una singola lingua
* Per le installazioni in inglese, è possibile scegliere tra inglese US o inglese UK (differiscono nei formati di data e ora)

**Interfaccia Web di Campaign:**

* Gli utenti possono modificare la lingua dell’interfaccia in modo indipendente tramite le preferenze del profilo
* Sono supportate più lingue con formattazione specifica per le impostazioni internazionali per date, ore e numeri
* La preferenza della lingua dell’interfaccia web è indipendente dalla lingua del server Campaign e della console client


**Argomenti correlati:**

[Cambia lingua nell&#39;interfaccia utente di Campaign Web](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [Introduzione alla console client di Campaign](connect.md)

+++

+++ Cos’è Campaign Pannelli di controllo Campaign e come posso accedervi?

Campaign Pannelli di controllo Campaign è un’interfaccia amministrativa basata su web che consente agli amministratori di Campaign di aumentare l’efficienza gestendo le impostazioni e monitorando l’utilizzo tra le istanze di Campaign. Fornisce funzionalità self-service per gestire le configurazioni delle istanze critiche senza contattare il supporto Adobe.

**Funzionalità chiave:**

* **Gestione dei sottodomini** - Delega e gestione dei sottodomini, monitoraggio dei certificati SSL
* **Monitoraggio archiviazione** - Monitoraggio dell&#39;utilizzo del database e prevenzione dei problemi di archiviazione
* inserire nell&#39;elenco Consentiti **Gestione SFTP** - Monitoraggio dell&#39;archiviazione SFTP, gestione dei IP e delle chiavi SSH
* **Impostazioni dell&#39;istanza** - Configurare i inserisce nell&#39;elenco Consentiti IP, gestire le autorizzazioni URL, esaminare i dettagli dell&#39;istanza
* **Monitoraggio profili attivi** - Monitoraggio dell&#39;utilizzo dei profili attivi rispetto ai diritti
* **Monitoraggio delle prestazioni** - Monitoraggio delle prestazioni del database e del flusso di lavoro
* **Recapito messaggi e-mail** - Configura DMARC, BIMI e altri record di autenticazione

**Requisiti di accesso:**

* **Solo utenti amministratori** - Il Pannello di controllo Campaign è limitato agli utenti con diritti di amministratore
* **Autenticazione Adobe IMS** - Accesso tramite Adobe Experience Cloud con il tuo Adobe ID
* **Campaign v8 Managed Cloud Services** - Disponibile solo per le istanze in hosting

**Risorse aggiuntive:**

[Documentazione del Pannello di controllo Campaign](https://experienceleague.adobe.com/it/docs/control-panel/using/control-panel-home){target="_blank"} | [Video tutorial di Pannello di controllo Campaign](https://experienceleague.adobe.com/it/docs/control-panel-learn/tutorials/control-panel-overview){target="_blank"}

+++

+++ Come posso impostare le funzionalità di tracciamento nella mia istanza di Campaign?

Campaign v8 fornisce un tracciamento completo per monitorare le interazioni dei destinatari con i messaggi. Il tracciamento richiede la corretta configurazione dell’istanza e delle impostazioni del messaggio.

**Elementi di cui tenere traccia:**

* **Apertura e-mail** - Tramite pixel di tracciamento (1x1 immagine trasparente)
* **Clic collegamento** - Tutti gli URL vengono convertiti automaticamente in collegamenti tracciati
* **Annullamenti iscrizione** - Tracciamento collegamento rinuncia
* **Visualizzazioni pagina mirror** - Quando i destinatari visualizzano la versione Web
* **Parametri personalizzati** - Aggiungi i dati di tracciamento agli URL per l&#39;analisi avanzata

**Passaggi chiave per la configurazione:**

1. Configura l’URL del server di tracciamento nelle impostazioni dell’istanza (gestito da Adobe per v8)
2. Abilitare il tracciamento nelle proprietà di consegna
3. Imposta automaticamente il tracciamento per i singoli collegamenti o per tutti i collegamenti
4. Definire il periodo di validità del tracciamento e la conservazione del registro

**Best practice:** verifica sempre il tracciamento con le bozze prima di inviarlo al pubblico principale per garantire il corretto funzionamento dei collegamenti e l&#39;acquisizione dei dati.

**Argomenti correlati:**

[Tracciare e monitorare le consegne](tracking.md) | [Configurare i collegamenti tracciati](../send/email.md)

+++

+++ Come configurare il recapito messaggi e-mail?

Il recapito messaggi e-mail dipende dalla configurazione tecnica, dalla qualità dei contenuti e dalla reputazione del mittente. Campaign v8 fornisce strumenti e impostazioni per ottimizzare il posizionamento della casella in entrata.

**Passaggi di configurazione essenziali:**

* **Autenticazione dominio** - Configura i record SPF, DKIM e DMARC per verificare il dominio di invio
* **Riscaldamento IP** - Aumenta gradualmente il volume di invio sui nuovi IP per costruire la reputazione
* **Configurazione mittente** - Utilizza nomi e indirizzi del mittente coerenti e riconoscibili
* **Gestione delle e-mail non consegnate** - Configura le regole di quarantena per gestire automaticamente le e-mail non consegnate permanenti
* **Cicli di feedback** - Configura la gestione dei reclami per gestire i report di posta indesiderata

**Best practice per i contenuti:**

* Test delle e-mail con SpamAssassin per verificare il punteggio di spam
* Mantenere proporzioni testo-immagine corrette
* Includi versione in testo normale insieme a HTML
* Fornisci sempre collegamento per annullare l’abbonamento
* Evitare parole di attivazione spam e l&#39;utilizzo eccessivo delle maiuscole

**Monitoraggio:** utilizza i rapporti sul recapito messaggi di Campaign per tenere traccia delle percentuali di mancato recapito, delle percentuali di reclami e del posizionamento nella casella in entrata. Per Campaign v8, Adobe fornisce l’ottimizzazione del recapito messaggi a livello di infrastruttura.

**Argomenti correlati:**

[Informazioni sul recapito messaggi in Campaign](../send/about-deliverability.md) | [Guida alle procedure consigliate per la consegna](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=it){target="_blank"}

+++

+++ A quali database esterni posso collegare Campaign?

Campaign v8 supporta le connessioni Federated Data Access (FDA) ai principali sistemi di database aziendali, consentendo di sfruttare l’infrastruttura di dati esistente.

**Database supportati:**

* **Database cloud:** Amazon Redshift, Google BigQuery, Snowflake, Azure Synapse Analytics
* **Database aziendali:** Oracle, Microsoft SQL Server, PostgreSQL, MySQL
* **Data warehouse:** Teradata, Vertica, SAP HANA
* **Big data:** Hadoop tramite Hive

**Considerazioni specifiche per la piattaforma:** Le versioni del database supportate e i requisiti di connessione variano. Campaign v8 as a Managed Cloud Service può presentare requisiti di rete e sicurezza specifici per l’accesso al database esterno.

**Importante:** controlla sempre la matrice di compatibilità ufficiale per la versione di Campaign v8 per confermare il supporto di versioni di database specifiche e garantire la licenza corretta per i connettori di database esterni.

**Argomenti correlati:**

[Matrice di compatibilità](compatibility-matrix.md) | [Configurare le connessioni FDA](../connect/fda.md)

+++

+++ Adobe Campaign può integrarsi con i sistemi CRM?

Sì. Campaign fornisce connettori CRM nativi per una sincronizzazione bidirezionale fluida tra Campaign e il sistema di gestione delle relazioni con i clienti, garantendo la coerenza dei dati dei clienti su tutte le piattaforme.

**Sistemi CRM supportati:**

* **Salesforce** - Lead, contatti, account, opportunità, campagne
* **Microsoft Dynamics 365** - Contatti, account, lead, entità personalizzate
* Altri CRM tramite integrazioni API personalizzate

**Sincronizzazioni:**

* **Da CRM a Campaign:** record di contatto, informazioni account, lead, campi personalizzati, dati di segmentazione
* **Da Campaign a CRM:** registri di consegna, dati di tracciamento, metriche di coinvolgimento, risposte alle campagne, stato abbonamento

**Modalità di sincronizzazione:**

* **Pianificato** - Sincronizzazione automatica a intervalli definiti (ogni ora, ogni giorno)
* **Manuale** - Sincronizzazione su richiesta attivata dagli operatori
* **In tempo reale** - Tramite API per aggiornamenti immediati (sviluppo personalizzato)

**Configurazione:** utilizza l&#39;assistente del connettore CRM integrato di Campaign per mappare i campi del CRM agli attributi di Campaign, selezionare le tabelle da sincronizzare e pianificare la sincronizzazione. Il connettore gestisce la risoluzione dei conflitti e mantiene la coerenza dei dati.

**Best practice:** inizia con la sincronizzazione di sola lettura per testare la mappatura, quindi abilita la sincronizzazione bidirezionale. Monitora i registri di sincronizzazione per individuare eventuali errori e conserva dati puliti in entrambi i sistemi.

**Argomenti correlati:**

[Configurazione connettore CRM](../connect/crm.md) | [Attività CRM per flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html?lang=it){target="_blank"}

+++

+++ Come si cancella la cache della console client?

La cancellazione della cache della console client risolve molti problemi comuni di visualizzazione e funzionalità. La cache memorizza i file di configurazione locali che a volte possono danneggiarsi o non essere più aggiornati.

**Quando cancellare la cache:**

* I nuovi elementi di branding (logo, colori) non vengono visualizzati correttamente
* Errore imprevisto delle funzioni di esportazione/importazione
* Gli elementi dell’interfaccia non vengono aggiornati dopo le modifiche alla configurazione
* Problemi di prestazioni o risposta lenta della console
* Dopo l’aggiornamento a una nuova versione della console client

**Passaggi per cancellare la cache:**

1. Apri la console del client Campaign.
2. Vai al menu **[!UICONTROL File]**
3. Seleziona **[!UICONTROL Clear the local cache...]**
4. Conferma l’azione quando richiesto
5. Riavvia la console client

**Argomenti correlati:**

[Installare e configurare la console client](connect.md)

+++

+++ È possibile configurare le impostazioni dell&#39;interfaccia utente?

Sì. Gli amministratori di Campaign possono personalizzare l’interfaccia utente in base al marchio dell’organizzazione e ottimizzare l’esperienza utente. Configura le impostazioni a livello di istanza o utente.

**Personalizzazione possibile:**

* **Marchio** - Logo, colori ed elementi di identità visiva
* **Visualizzazioni predefinite** - Layout della home page, visibilità della struttura delle cartelle
* **Configurazioni elenco** - Colonne predefinite, ordinamento e filtri negli elenchi dati
* **Navigazione** - Voci di menu e scelte rapide disponibili
* **Impostazioni internazionali** - Formati data/ora, formati numero, fusi orari
* **Notifiche** - Avvisi e-mail, notifiche in-app, avvisi flusso di lavoro

**Livelli di configurazione:**

* **A livello di istanza** - Applica a tutti gli utenti (richiede diritti di amministratore)
* **Specifico per l&#39;utente** - Preferenze individuali e impostazioni personali
* **Gruppo di operatori** - Impostazioni ereditate da tutti i membri del gruppo

**Argomenti correlati:**

[Configurare le impostazioni dell&#39;interfaccia utente](../config/ui-settings.md) | [Autorizzazioni utente](gs-permissions.md)

+++

+++ È possibile creare campi e tabelle personalizzati?

Sì. Il modello dati flessibile di Campaign consente di estendere gli schemi integrati con campi personalizzati e di creare tabelle completamente nuove per soddisfare le esigenze aziendali specifiche.

**Personalizzazione possibile:**

* **Aggiungi campi alle tabelle esistenti** - Estendi la tabella dei destinatari con punti fedeltà, preferenze personalizzate, ID esterni
* **Crea nuove tabelle personalizzate** - Archivia prodotti, transazioni, livelli fedeltà, entità personalizzate
* **Definisci relazioni** - Collega tabelle personalizzate a tabelle Campaign esistenti
* **Estendi moduli** - Aggiorna l&#39;interfaccia utente per visualizzare e modificare i campi personalizzati

**Casi d&#39;uso comuni:**

* Memorizza attributi di profilo aggiuntivi (valore del ciclo di vita del cliente, store preferito, stato VIP)
* Gestire i cataloghi di prodotti con attributi personalizzati
* Tracciare eventi personalizzati e interazioni
* Integrare gli ID di sistema esterni per la sincronizzazione dei dati
* Creare modelli di dati specifici per il settore (retail, finanza, viaggi)

**Argomenti correlati:**

[Estendi modello dati](../dev/extend-schema.md) | [Struttura dello schema](../dev/schemas.md) | [Best practice per i modelli di dati](../dev/datamodel-best-practices.md)

+++

## Reporting {#reporting}

Ottieni informazioni sulle funzionalità di reporting di Campaign, inclusi rapporti incorporati, rapporti personalizzati e strumenti di analisi dei dati come i cubi.

+++ Come posso creare nuovi rapporti?

Campaign offre diverse opzioni di reporting in base alle tue esigenze e competenze tecniche. Puoi utilizzare i rapporti incorporati, creare rapporti personalizzati nella console client o progettare dashboard visive nell’interfaccia utente web di Campaign.

**Opzioni di reporting:**

* **Rapporti incorporati** - Rapporti di consegna, campagne e tracciamento pronti all&#39;uso accessibili dalla scheda **[!UICONTROL Reports]**
* **Analisi descrittiva** - Rapporti statistici rapidi su qualsiasi dato con un&#39;interfaccia guidata
* **Rapporti personalizzati** - Rapporti avanzati creati da utenti tecnici tramite l&#39;editor di rapporti
* **Dashboard dell&#39;interfaccia Web** - Report visivi e dashboard moderni con interfaccia di trascinamento della selezione
* **Cubi** - Esplorazione dei dati multidimensionali e analisi della tabella pivot

**Importante:** Campaign è progettato per la generazione di rapporti sulle operazioni di marketing e non come strumento specializzato di business intelligence. Per esigenze analitiche complesse, è consigliabile integrare con Adobe Analytics o piattaforme BI dedicate.

**Argomenti correlati:**

[Introduzione al reporting](../reporting/gs-reporting.md) | [Rapporti sull&#39;interfaccia utente web di Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

+++ Come posso progettare e condividere report statistici sulle popolazioni?

Utilizza lo strumento di analisi descrittiva di Campaign per generare rapidamente rapporti statistici su qualsiasi dato della popolazione. Questa funzione guidata consente di analizzare distribuzioni, tendenze e modelli senza competenze tecniche.

**Elementi da analizzare:**

* Dati demografici dei destinatari e suddivisioni della segmentazione
* Metriche delle prestazioni e percentuali di risposta di Campaign
* Distribuzione degli attributi del profilo (età, posizione, preferenze)
* Statistiche sulla consegna e modelli di coinvolgimento
* Valori di campi personalizzati e metriche di qualità dei dati

**Come creare:** Selezionare un elenco o un risultato della query → Fare clic con il pulsante destro del mouse → **[!UICONTROL Actions > Analyze]** → Scegliere il tipo di analisi (qualitativa o quantitativa) → Configurare le opzioni di visualizzazione → Generare il report.

**Condivisione:** Esporta i report in Excel/PDF o salvali nella cartella **[!UICONTROL Reports]** per l&#39;accesso al team con le autorizzazioni appropriate.

Ulteriori informazioni su [Analisi descrittiva](../reporting/built-in-reports.md)

+++

+++ Come posso progettare report avanzati sui miei dati?

Campaign offre due approcci per la creazione di rapporti personalizzati avanzati: rapporti tecnici nella console client per analisi complesse e dashboard visivi per la creazione di rapporti più semplice.

Nella console client puoi effettuare le seguenti operazioni:

* Creare report complessi utilizzando query SQL e calcoli personalizzati
* Creare rapporti su più pagine con grafici, tabelle e tabelle pivot
* Progettare la formattazione condizionale e il contenuto dinamico
* Accedere al modello dati completo di Campaign e ai database esterni (FDA)

Scopri come [creare rapporti personalizzati (console client)](../reporting/custom-reports.md)

+++

+++ Cos’è un cubo e come posso utilizzarlo per il reporting?

I cubi sono strutture di dati multidimensionali che consentono agli utenti aziendali di esplorare e analizzare i dati di Campaign tramite tabelle pivot senza competenze tecniche. Considerali come modelli di dati preconfigurati che semplificano la generazione di rapporti complessi.


* Gli utenti tecnici creano e configurano cubi che definiscono dimensioni (tempo, area geografica, canali) e misure (aperture, clic, ricavi).
* Gli utenti aziendali selezionano un cubo durante la creazione di rapporti e trascinano le dimensioni per esplorare i dati
* I dati vengono aggregati e calcolati automaticamente in base alla configurazione del cubo
* I risultati possono essere visualizzati come tabelle pivot, grafici o esportati in Excel

Scopri come [esplorare i dati con i cubi](../reporting/gs-cubes.md)

+++

+++ È possibile creare un report dalle risposte a un sondaggio online?

Sì! Campaign include un modulo Survey che consente di creare questionari online e generare rapporti incorporati sulle risposte ai sondaggi.

**Importante:** la gestione dei sondaggi non è disponibile nelle distribuzioni Campaign v8 Enterprise (FFDA). [Ulteriori informazioni](../architecture/enterprise-deployment.md).

**Funzionalità sondaggio:**

* Creazione di questionari online con più pagine e tipi di domande
* Raccogliere le risposte nel database o nelle variabili locali
* Visualizza il tracciamento in tempo reale delle risposte al sondaggio
* Genera report dedicati sulle risposte ai sondaggi (suddivisione per domanda, statistiche generali)
* Esporta le risposte ai sondaggi in Excel, PDF o CSV per ulteriori analisi
* Utilizzare i dati dei sondaggi nei flussi di lavoro di targeting per personalizzare le campagne

**Report sondaggi incorporati:**

* **Rapporto generale** - Tendenze delle risposte nel tempo, distribuzione per origine e lingua
* **Raggruppamento delle risposte** - Raggruppamento dettagliato delle risposte per ogni domanda
* **Rapporto sulla documentazione** - Rappresentazione visiva della struttura del sondaggio

**Analisi avanzata:**

* Accedere alle risposte al sondaggio dalla scheda **[!UICONTROL Responses]** ed esportare i dati
* Utilizza l&#39;attività **[!UICONTROL Survey responses]** nei flussi di lavoro per eseguire il targeting dei destinatari in base alle loro risposte
* Combina i dati dei sondaggi con altri dati di Campaign per la segmentazione e la personalizzazione
* Creare rapporti e cubi personalizzati per l’analisi di sondaggi multidimensionali

**Argomenti correlati:**

[Introduzione ai sondaggi](https://experienceleague.adobe.com/it/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [Report sondaggi](https://experienceleague.adobe.com/it/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ Come posso condividere l’accesso ai miei report?

Campaign offre opzioni flessibili per la condivisione di rapporti con diversi gruppi di utenti, il controllo della visibilità e delle autorizzazioni di accesso in base a ruoli e responsabilità.

**Controllo dell&#39;accesso al report:**

* **Autorizzazioni cartella** - Posiziona i report in cartelle con accesso in lettura/scrittura appropriato per i gruppi di utenti
* **Diritti denominati** - Assegna diritti specifici per visualizzare, creare o modificare i report
* **Contesto di visualizzazione** - Definisci dove vengono visualizzati i report: nella cartella **[!UICONTROL Reports]**, nelle schede della campagna o nelle schermate di consegna
* **Condivisione dell&#39;interfaccia utente Web** - Condividere i collegamenti del dashboard con i membri del team tramite l&#39;interfaccia utente Web di Campaign

**Come configurare l&#39;accesso:**

1. Salvare il report in una cartella specifica nella console client
2. Configurare le autorizzazioni di accesso alle cartelle per i gruppi di operatori rilevanti
3. Definire le proprietà del rapporto: tipo di rapporto, contesto di visualizzazione e disponibilità
4. Verifica l’accesso con un utente del gruppo target prima di un rollout più ampio

**Best practice:** crea cartelle di rapporti dedicate per diversi team (marketing, operazioni, gestione) con autorizzazioni di accesso personalizzate. Documenta lo scopo del rapporto e le pianificazioni di aggiornamento.

**Argomenti correlati:**

[Rapporti personalizzati](../reporting/custom-reports.md) | [Autorizzazioni utente](gs-permissions.md)

+++

+++ Posso esportare i rapporti in formati diversi?

Sì, Campaign supporta più formati di esportazione per i rapporti della console client e dell’interfaccia web, consentendo una facile condivisione con le parti interessate e l’integrazione con altri strumenti.

**Formati di esportazione disponibili:**

* **Excel (.xlsx)** - Ideale per la manipolazione dei dati, ulteriori analisi e tabelle pivot
* **PDF** - Ideale per presentazioni, riepiloghi e report stampati
* **CSV** - Ideale per l&#39;importazione di dati in altri sistemi e strumenti di business intelligence
* **OpenDocument (.ods)** - Formato foglio di calcolo open-source
* **XML** - Per integrazioni di sistema ed elaborazione automatizzata

**Come esportare:**

* **Console client:** Apri report → Fai clic sul pulsante **[!UICONTROL Export]** → Scegli il formato → Salva file
* **Interfaccia Web:** Apri dashboard → Fai clic sull&#39;icona di esportazione → Seleziona formato → Scarica
* **Esportazioni automatizzate:** Pianifica esportazioni regolari utilizzando flussi di lavoro con attività di esportazione

**Best practice:**

* Utilizza Excel per i rapporti che richiedono analisi e annotazioni delle parti interessate
* Utilizzare PDF per i report statici inviati ai dirigenti o archiviati per conformità
* Utilizza CSV per le integrazioni con data warehouse o strumenti di analisi esterni
* Testare i rapporti esportati per garantire la formattazione e l’accuratezza dei dati

**Argomenti correlati:**

[Rapporti personalizzati](../reporting/custom-reports.md) | [Rapporti sull&#39;interfaccia utente web di Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

## Sviluppatori {#developers}

Accedi alle informazioni tecniche per gli sviluppatori, inclusi i dettagli del modello dati, gli schemi, le API e le funzionalità di personalizzazione.

+++ Qual è il modello dati di Campaign?

Il modello dati di Campaign è una struttura di database relazionale basata su schema che definisce il modo in cui i dati di marketing sono organizzati e correlati. È costituito da tabelle integrate per i principali oggetti di marketing (destinatari, consegne, campagne) e può essere esteso per soddisfare esigenze aziendali specifiche.

**Concetti chiave del modello dati:**

* **Schemi** - Definizioni XML che descrivono la struttura, i campi e le relazioni della tabella
* **Tabelle incorporate** - Entità marketing di base (destinatari, consegne, flussi di lavoro, campagne)
* **Collegamenti** - Relazioni tra tabelle (1-1, 1-N, N-N)
* **Enumerazioni** - Elenchi di valori predefiniti per i campi a discesa
* **Estensioni** - Campi e tabelle personalizzati aggiunti al modello standard

**Schemi principali incorporati:**

* **Destinatario (nms:recipient)** - Profili cliente e informazioni di contatto
* **Consegna (nms:delivery)** - Campagne e-mail, SMS e push
* **Flusso di lavoro (xtk:workflow)** - Processi di automazione
* **Campagna (nms:operation)** - Orchestrazione campagna di marketing
* **Registri di tracciamento** - Aperture, clic e dati di coinvolgimento

**Perché è importante:** Comprendere il modello di dati è essenziale per creare flussi di lavoro, creare query, estendere schemi e sviluppare integrazioni personalizzate. L’approccio basato su schema garantisce la coerenza dei dati e abilita potenti funzionalità di query.

**Argomenti correlati:**

[Modello dati campagna](../dev/datamodel.md) | [Best practice per i modelli di dati](../dev/datamodel-best-practices.md)

+++

+++ Come si utilizzano gli schemi di Campaign?

Gli schemi sono alla base della struttura dati di Campaign e definiscono tabelle, campi e relazioni in formato XML. Comprendere gli schemi è fondamentale per la personalizzazione, l’integrazione e lo sviluppo avanzato dei flussi di lavoro.

**Quali schemi definiscono:**

* **Struttura della tabella** - Tabelle di database e oggetti applicativi corrispondenti
* **Proprietà campo** - Tipi di dati, etichette, regole di convalida e valori predefiniti
* **Relazioni** - Collegamenti tra tabelle (join) e cardinalità
* **Indici** - Ottimizzazione del database per le prestazioni delle query
* **Controllo dell&#39;accesso** - Quali campi gli utenti possono visualizzare e modificare

**Utilizzo degli schemi:**

* **Visualizza schemi:** Accesso tramite **[!UICONTROL Administration > Configuration > Data schemas]** nella console client
* **Estendi schemi:** Crea schemi di estensione (ad esempio, `cus:recipient` estende `nms:recipient`) per aggiungere campi personalizzati senza modificare gli schemi di base
* **Creare schemi personalizzati:** Creare tabelle completamente nuove per dati specifici dell&#39;azienda
* **Aggiorna database:** Applica le modifiche allo schema utilizzando **[!UICONTROL Tools > Advanced > Update database structure]**

**Casi d&#39;uso comuni:**

* Aggiunta di campi personalizzati alla tabella dei destinatari (ID società, livello fedeltà, preferenze)
* Creazione di tabelle personalizzate per prodotti, archivi o transazioni
* Definizione delle relazioni tra tabelle personalizzate e integrate
* Implementazione di modelli di dati specifici per le aziende

**Importante:** non modificare mai direttamente gli schemi incorporati. Utilizza sempre gli schemi di estensione per mantenere la compatibilità dell’aggiornamento e il supporto di Adobe.

**Argomenti correlati:**

[Introduzione agli schemi](../dev/schemas.md) | [Estendere uno schema](../dev/extend-schema.md)

+++

+++ Come si utilizza una tabella dei destinatari personalizzata?

Campaign ti consente di utilizzare una tabella personalizzata invece della tabella dei destinatari incorporata quando la tua azienda richiede una diversa struttura di dati per il targeting (ad esempio, account B2B, abbonati, lead o contatti esterni).

**Perché utilizzare una tabella dei destinatari personalizzata:**

* Aziende o unità organizzative B2B di destinazione invece di contatti individuali
* Separa i dati dell’abbonato dal database principale del cliente
* Usa una tabella clienti esistente da un altro sistema
* Implementazione di architetture multi-brand con tabelle di contatto separate
* Conformità a specifici requisiti di governance dei dati

**Passaggi di implementazione:**

1. Creare uno schema personalizzato che definisca la struttura della tabella dei destinatari
2. Includi campi obbligatori (e-mail, chiave primaria, flag di esclusione)
3. Configurare le mappature di destinazione per collegare la tabella con le consegne
4. Aggiornare i modelli di consegna per utilizzare la nuova mappatura di destinazione
5. Adattare flussi di lavoro e query per fare riferimento alla tabella personalizzata

**Considerazioni chiave:**

* Le tabelle dei destinatari personalizzate devono includere campi obbligatori per le consegne (e-mail, esclusioni, tracciamento)
* I flussi di lavoro e i moduli devono essere adattati per funzionare con la struttura personalizzata
* Alcune funzioni incorporate potrebbero richiedere la personalizzazione
* I test sono fondamentali prima della migrazione delle campagne di produzione

**Best practice:** inizia con l&#39;estensione della tabella dei destinatari standard prima di prendere in considerazione una tabella personalizzata. Le tabelle dei destinatari personalizzate aggiungono complessità e devono essere utilizzate solo quando è veramente necessario.

**Argomenti correlati:**

[Tabella dei destinatari personalizzata](../dev/custom-recipient.md) | [Mappature di destinazione](../audiences/target-mappings.md)

+++

+++ Quali sono le best practice per definire le query in Campaign?

L’editor delle query di Campaign è un potente strumento visivo per la creazione di query nel database senza conoscenze SQL. La padronanza è essenziale per il targeting, la segmentazione e l’analisi dei dati efficaci.

**Dove vengono utilizzate le query:**

* **Attività del flusso di lavoro** - Query, suddivisione, aggiornamento dati, attività di arricchimento
* **Destinazione consegna** - Definisci le popolazioni dei destinatari per le campagne
* **Elenchi** - Crea elenchi di destinatari dinamici o statici
* **Rapporti** - Generazione di estrazioni e analisi di dati personalizzati
* **Filtri** - Crea criteri di targeting riutilizzabili

**Best practice per le query:**

* **Inizio semplice** - Genera le query in modo incrementale, eseguendo il test a ogni passaggio
* **Usa dimensioni filtro** - Sfrutta le relazioni tra tabelle (destinatari → consegne → registri di tracciamento)
* **Ottimizza prestazioni** - Indicizza i campi con query frequenti, evita i campi calcolati complessi
* **Utilizzo di filtri predefiniti** - Riutilizzare e combinare i filtri esistenti per coerenza
* **Test con campioni di piccole dimensioni** - Convalida logica di query prima dell&#39;esecuzione nel database completo
* **Documenta query complesse** - Aggiungi descrizioni per manutenzione e trasferimento delle conoscenze

**Modelli di query comuni:**

* Destinatari che hanno aperto una consegna specifica: filtra i registri di tracciamento collegati ai destinatari
* Trova contatti inattivi: esegui una query sull’ultima data di consegna o sull’attività di tracciamento
* Segmento per comportamento: combina i criteri di consegna, tracciamento e profilo
* Escludi destinatari precedenti: utilizza le operazioni set (unione, intersezione, esclusione)

**Accesso all&#39;editor di query generico:** **[!UICONTROL Tools > Generic query editor]** per l&#39;esplorazione di database ad hoc e l&#39;estrazione di dati all&#39;esterno dei flussi di lavoro.

**Argomenti correlati:**

[Editor query](../start/query-editor.md) | [Attività query nei flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=it){target="_blank"}

+++

+++ Come posso importare un pacchetto di dati?

I pacchetti di dati ti consentono di esportare e importare configurazioni di Campaign (schemi, flussi di lavoro, tipologie, filtri) e dati tra istanze. Ciò è essenziale per la distribuzione di configurazioni dallo sviluppo alla produzione o per la condivisione di componenti tra organizzazioni diverse.

**Cosa è possibile imballare:**

* **Oggetti di configurazione** - Schemi, flussi di lavoro, regole di tipologia, moduli, filtri
* **Componenti di Campaign** - Modelli di consegna, modelli di campagna, blocchi di contenuto
* **Impostazioni applicazione** - Operatori, gruppi di operatori, strutture di cartelle
* **Dati** - Elenchi destinatari, indirizzi seed, frammenti di contenuto
* **Sviluppi personalizzati** - Codice JavaScript, script SQL, applicazioni Web


**Tipi di pacchetto:**

* **Pacchetto utente** - Configurazioni personalizzate create ed esportate
* **Pacchetto piattaforma** - Funzioni e aggiornamenti forniti da Adobe
* **Pacchetto dati** - Contiene record di dati effettivi, non solo la struttura

**Best practice:**

* Esporta sempre pacchetti dalla stessa versione di Campaign o da una versione precedente
* Importazioni del pacchetto di prova nell’ambiente di sviluppo prima della produzione
* Contenuto e dipendenze del pacchetto documenti
* Usa controllo della versione per i file XML del pacchetto
* Esegui il backup dell’istanza prima delle importazioni dei pacchetti principali

Ulteriori informazioni su come [Utilizzare i pacchetti dati](../dev/packages.md)

+++

+++ Dove posso trovare l’elenco delle API di Campaign v8?

Campaign v8 fornisce una documentazione API completa che copre sia le API SOAP (per le interazioni con la console client) che le API REST (per le integrazioni moderne). Il riferimento API include tutti i metodi, parametri e formati di risposta disponibili.

**Tipi di API di Campaign:**

* **API SOAP** - API tradizionali per le operazioni della console client di Campaign, la manipolazione dello schema e il controllo del flusso di lavoro
* **API REST** - API HTTP moderne per integrazioni di sistema esterne, gestione dei profili e attivazione di eventi
* **API JavaScript** - API di scripting lato server per attività del flusso di lavoro e logica di business personalizzata

**Risorse di documentazione API:**

* **Riferimento API completo:** Documentazione API SOAP completa con firme di metodo, parametri ed esempi
* **Guida REST API:** endpoint REST moderni per profili, eventi e unità organizzative
* **API JavaScript:** funzioni lato server disponibili negli script del flusso di lavoro e nelle applicazioni Web

**Casi d&#39;uso comuni per l&#39;API:**

* Integrare Campaign con applicazioni CRM, ERP o personalizzate
* Automatizzare le operazioni della campagna e l’esecuzione dei flussi di lavoro
* Sincronizzazione dei dati tra sistemi in tempo reale
* Creare soluzioni di monitoraggio e avvisi personalizzate
* Creare interfacce esterne per dati e operazioni di Campaign

**Accesso:** [Documentazione API di Campaign v8](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=it){target="_blank"}

+++


+++ Come si monitorano i flussi di lavoro dall’API?

Le API di Campaign consentono di controllare e monitorare in modo programmatico l’esecuzione dei flussi di lavoro, abilitando sistemi di monitoraggio esterni, avvisi automatizzati e soluzioni di orchestrazione personalizzate.

**Operazioni possibili tramite API:**

* **Avvia flussi di lavoro** - Attiva l&#39;esecuzione del flusso di lavoro a livello di programmazione
* **Sospendi/Riprendi flussi di lavoro** - Controlla il flusso di esecuzione del flusso di lavoro
* **Interrompi flussi di lavoro** - Termina flussi di lavoro in esecuzione
* **Stato flusso di lavoro query** - Verificare se i flussi di lavoro sono in esecuzione, in pausa o completati
* **Recupera registri** - Accedi ai registri di esecuzione del flusso di lavoro e ai messaggi di errore
* **Monitorare l&#39;avanzamento dell&#39;attività** - Monitorare il completamento delle singole attività del flusso di lavoro

**Endpoint API:**

Tutti i comandi di controllo del flusso di lavoro utilizzano lo stesso endpoint POST con parametri di metodo diversi:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

**Comandi disponibili:**

* `{"method":"start"}` - Avvia un flusso di lavoro
* `{"method":"pause"}` - Sospendi un flusso di lavoro in esecuzione
* `{"method":"resume"}` - Riprendi un flusso di lavoro in pausa
* `{"method":"stop"}` - Interrompere un flusso di lavoro

**Casi d&#39;uso comuni:**

* Creare dashboard di monitoraggio personalizzati che mostrino lo stato del flusso di lavoro
* Implementare avvisi automatici in caso di errore o durata eccessiva dei flussi di lavoro
* Orchestrazione dei flussi di lavoro da scheduler o sistemi di eventi esterni
* Creare dipendenze del flusso di lavoro tra più istanze di Campaign
* Generare rapporti di esecuzione del flusso di lavoro personalizzati

**Best practice:** combina il monitoraggio API con l&#39;audit trail del flusso di lavoro per una governance completa del flusso di lavoro. Utilizza strumenti di monitoraggio esterni per tenere traccia degli SLA del flusso di lavoro e delle metriche delle prestazioni.

Scopri come [controllare i flussi di lavoro tramite API](../dev/api/controlling-a-workflow.md)

+++

+++ Come posso aggiornare la struttura del database?

Dopo aver modificato gli schemi di Campaign (aggiunta di campi, creazione di tabelle, modifica dei tipi di dati), devi aggiornare la struttura fisica del database per applicare le modifiche. Questa sincronizzazione garantisce che il database corrisponda alle definizioni dello schema.

**Quando sono necessari aggiornamenti del database:**

* Aggiunta di nuovi campi agli schemi esistenti
* Creazione di tabelle personalizzate o estensione di tabelle incorporate
* Modifica delle proprietà del campo (tipo di dati, lunghezza, stato richiesto)
* Aggiunta o rimozione di collegamenti tra tabelle
* Creazione di nuovi indici per l’ottimizzazione delle query


**Considerazioni importanti:**

* **Esegui prima il backup**: esegui sempre il backup del database prima delle modifiche strutturali
* **Test in sviluppo** - Convalida modifiche schema in ambiente di sviluppo prima della produzione
* **Pianificazione dei tempi di inattività** - Modifiche strutturali di grandi dimensioni potrebbero richiedere brevi finestre di manutenzione
* **Per Managed Cloud Services** - Coordinare le modifiche principali con il supporto Adobe
* **Reversibilità** - Alcune modifiche (come la rimozione dei campi) possono causare la perdita di dati

**Best practice:** utilizzare il controllo delle versioni dello schema e il rilevamento delle modifiche. Documenta tutte le modifiche allo schema personalizzato per manutenzione e risoluzione dei problemi.

**Argomenti correlati:**

[Aggiorna struttura database](../dev/update-database-structure.md) | [Estendi schema](../dev/extend-schema.md)

+++

## Privacy {#privacy}

Scopri in che modo Adobe Campaign ti aiuta a rispettare le normative sulla privacy come RGPD e CCPA e a gestire le richieste dei soggetti interessati.

+++ Quali sono i concetti chiave sulla privacy in Campaign?

Campaign ti aiuta a rispettare le normative sulla privacy (GDPR, CCPA, PDPA, LGPD) tramite strumenti per la gestione dei diritti, del consenso e della conservazione dei dati dell’interessato. I concetti chiave includono normative sulla privacy, identificazione dei dati personali, diritti degli interessati (accesso, eliminazione, portabilità), gestione del consenso e criteri di conservazione dei dati.

In qualità di titolare del trattamento, sei responsabile della gestione delle richieste dei soggetti interessati, della gestione dei record di consenso e della garanzia di un utilizzo trasparente dei dati.

Ulteriori informazioni sulla [gestione della privacy](../start/privacy.md)

+++

+++ Come posso garantire la conformità in materia di privacy in Campaign?

Campaign fornisce strumenti per la conformità alla privacy, ma la responsabilità legale spetta a te. Collabora con il consulente legale per il tuo programma sulla privacy.

**Azioni essenziali:**

* Stabilire processi per la gestione delle richieste degli interessati (accesso, cancellazione)
* Implementa la gestione del consenso con marche temporali e tracciamento dell’ambito
* Includi collegamenti per annullare l’iscrizione in tutte le e-mail di marketing
* Controlla le origini dati e rimuovi i dati inutilizzati
* Applicazione dei controlli di accesso con privilegi minimi

Campaign offre l’integrazione del servizio core per la privacy, il tracciamento del consenso, i flussi di lavoro di eliminazione automatizzata e le piste di controllo per la conformità.

Ulteriori informazioni sulla [gestione della privacy](../start/privacy.md)

+++

+++ Come posso raccogliere e gestire il consenso degli utenti in Campaign?

Un consenso valido richiede un accordo attivo, specifico, informato e revocabile. Gli utenti devono intraprendere azioni esplicite, senza caselle preselezionate o silenzio come consenso. Consensi separati per scopi diversi (disaggregati), forniscono spiegazioni chiare e conservano i record con marca temporale.

**Best practice:** fornisce opzioni di consenso granulari, aggiorna periodicamente il consenso, semplifica l&#39;accesso ai centri preferenze e inquadra il consenso come creazione di un trust.

**Implementazione tecnica in Campaign:**

Campaign fornisce servizi di abbonamento, centri preferenze, flag di rinuncia e campi di consenso personalizzati per il tracciamento del consenso.

* Estendere lo schema dei destinatari per i campi del consenso (data, tipo, origine)
* Creare servizi di abbonamento per ogni tipo di consenso
* Creare moduli web per i centri preferenze
* Utilizzare i flussi di lavoro per applicare il consenso nel targeting
* Gestisci piste di controllo

Consulta il consulente legale per assicurarti che l&#39;implementazione soddisfi i requisiti normativi.

**Argomenti correlati:**

[Servizi di abbonamento](../start/subscriptions.md) | [Privacy e consenso](../start/privacy.md#consent-retention-roles) | [Gestione della privacy](../start/privacy.md)

+++

+++ Quali dati vengono eliminati quando si elabora una richiesta di eliminazione?

Campaign elimina automaticamente tutti i dati collegati a un interessato: il profilo del destinatario, i registri di consegna e tracciamento, i dati personalizzati con relazioni di proprietà, la cronologia degli abbonamenti e i dati di tracciamento web.

**Funzionamento:** Campaign elimina tutti i dati in cui il collegamento al destinatario contiene `integrity="own"` nella definizione dello schema, garantendo l&#39;eliminazione a catena nelle tabelle correlate.

Puoi personalizzare l’ambito di eliminazione modificando l’integrità dei collegamenti negli schemi, ma prima di tutto rivolgiti al consulente legale. L’eliminazione è permanente e non può essere annullata.

**Argomenti correlati:**

[Gestione della privacy](../start/privacy.md) | [Collegamenti schema](../dev/schemas.md)

+++

+++ Le eliminazioni della privacy influiscono sui rapporti di consegna?

No. I rapporti delle campagne si basano su metriche aggregate precalcolate (totale inviato, aperture, clic) e non su query live sui singoli registri. L’eliminazione dei dati dei singoli destinatari non modifica le statistiche aggregate storiche.

Le statistiche generali sulla consegna e le metriche delle prestazioni rimangono intatte, mentre i singoli registri di tracciamento e i dettagli personali vengono rimossi. Questo ti consente di mantenere le analisi di marketing nel rispetto dei diritti degli interessati.

**Argomenti correlati:**

[Gestione della privacy](../start/privacy.md) | [Rapporti](../reporting/gs-reporting.md)

+++

+++ Come posso impedire la reimportazione dei dati eliminati?

È necessario eliminare i dati da tutti i sistemi di origine, non solo da Campaign. I dati spesso provengono da sistemi esterni (CRM, e-commerce, data warehouse).

**Azioni necessarie:** Identificare tutte le origini dati, eliminare dai sistemi di origine, aggiungere agli elenchi di esclusione/soppressione, aggiornare i flussi di lavoro di importazione in modo da rispettare i flag di eliminazione e documentare il processo.

In qualità di titolare del trattamento, sei responsabile della completa rimozione dei dati dall’intero ecosistema tecnologico.

**Argomenti correlati:**

[Gestione della privacy](../start/privacy.md) | [Flussi di lavoro di importazione](../config/workflows.md)

+++

+++ Gli utenti eliminati possono fornire nuovamente il consenso?

Sì. Le persone interessate possono dare di nuovo il consenso dopo l’eliminazione. Campaign crea un record destinatario completamente nuovo senza alcun collegamento ai dati eliminati in precedenza: il profilo inizia con una nuova lavagna.

L’audit trail di Campaign registra sia l’evento di eliminazione che la creazione di nuovi profili, dimostrando la conformità e mostrando il nuovo consenso dato liberamente dopo l’eliminazione.

**Argomenti correlati:**

[Gestione della privacy](../start/privacy.md) | [Abbonamenti](../start/subscriptions.md)

+++

## Hai ancora bisogno di aiuto? {#get-help}

Non riesci a trovare quello che stai cercando? Risorse aggiuntive per la corretta esecuzione di Adobe Campaign v8.

### Supporto community

Entra in contatto con altri utenti di Campaign ed esperti di Adobe per condividere le conoscenze e ottenere le risposte.

* **[Community di Adobe Campaign](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}** - Poni domande, condividi soluzioni e collegati alla community di Campaign
* **[Forum Experience League](https://experienceleaguecommunities.adobe.com/){target="_blank"}** - Sfogliare discussioni tra tutti i prodotti Adobe
* **[Orario di lavoro della community di Campaign](https://experienceleague.adobe.com/it){target="_blank"}** - Partecipa a sessioni live con esperti Adobe

### Documentazione e apprendimento

Accedi a guide complete, tutorial e materiali di formazione.

* **[Tutorial su Campaign](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html?lang=it){target="_blank"}** - Guide video dettagliate e tutorial pratici
* **[Novità](whats-new.md)** - Funzioni e funzionalità più recenti
* **[Note sulla versione](release-notes.md)** - Informazioni sulla versione corrente e precedente
* **[Versioni e aggiornamenti](upgrades.md)** - Scopri le versioni, gli aggiornamenti e come controllare la versione di Campaign

### Risorse tecniche

Trova documentazione tecnica dettagliata e risorse per sviluppatori.

* **[API di Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=it){target="_blank"}** - Documentazione completa di riferimento API
* **[Matrice di compatibilità](compatibility-matrix.md)** - Sistemi e versioni supportati
* **[Domande frequenti su versioni e aggiornamenti](upgrades.md#upgrades-faq)** - Controlla la versione e scopri gli aggiornamenti

### Supporto e servizi

Chiedi aiuto al team di supporto di Adobe e gestisci la tua istanza.

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** - Registrazione dei casi di supporto e gestione degli utenti
* **[Assistenza clienti Adobe](https://helpx.adobe.com/it/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - Contatta il team di supporto
* **[Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it){target="_blank"}** - Gestisci le impostazioni dell&#39;istanza Campaign
* **[Stato del sistema](https://status.adobe.com/){target="_blank"}** - Verifica lo stato dei servizi Adobe

### Formazione e certificazione

Migliora le tue competenze con i programmi ufficiali di formazione e certificazione di Adobe.

* **[Guida di Experience League](https://experienceleague.adobe.com/it/browse/campaign/campaign-v8){target="_blank"}** - Risorse di aiuto per Campaign v8 (interfaccia utente Web e console CLient)
* **[Adobe Digital Learning Services](https://learning.adobe.com/){target="_blank"}** - Corsi ufficiali con istruttore e autoapprendimento
* **[Certificazione Adobe Campaign](https://experienceleague.adobe.com/docs/certification/program/overview.html?lang=it){target="_blank"}** - Convalida la tua esperienza con la certificazione professionale
* **[Percorsi di apprendimento Experience League](https://experienceleague.adobe.com/it?lang=en#dashboard/learning){target="_blank"}** - percorsi di apprendimento guidato

### Altre risorse utili

* **[Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=it){target="_blank"}** - Riferimento per utenti di Classic v7
* **[Documentazione dell&#39;interfaccia utente Web di Campaign](https://experienceleague.adobe.com/it/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - Nuova guida dell&#39;interfaccia Web
* **[Best practice per il recapito dei messaggi](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=it){target="_blank"}** - Ottimizzare la consegna dei messaggi e-mail

