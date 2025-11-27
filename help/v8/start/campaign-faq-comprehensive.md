---
title: Domande frequenti su Campaign v8
description: Risposte alle domande frequenti su Adobe Campaign v8 su configurazione, configurazione, messaggistica, flussi di lavoro e altro ancora
feature: Overview
role: User
level: Beginner
keywords: Domande frequenti, Campaign v8, domande, risposte, aiuto, supporto, risoluzione dei problemi
hide: true
hidefromtoc: true
source-git-commit: 561893e593a6c6f85d4c469ac09dd2e35a9b37e1
workflow-type: tm+mt
source-wordcount: '10163'
ht-degree: 22%

---

# Domande frequenti {#faq}

Risposte rapide alle domande più frequenti su Adobe Campaign v8. Se stai iniziando a lavorare o stai cercando aiuto per la configurazione avanzata, troverai le risposte organizzate per argomento di seguito.

**Ti avvicini ora a Campaign?** Inizia con [Domande generali](#general) e [Concetti chiave](#key-concepts).\
**Hai bisogno di assistenza tecnica?** Seleziona [Sviluppatori](#developers) e [Impostazioni campagna](#settings).\
**Impossibile trovare la risposta?** Visita i [forum della community](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} o [contatta l&#39;assistenza](#get-help).

>[!TIP]
>
>Utilizzare Ctrl+F (Comando+F su Mac) per cercare parole chiave specifiche in questa pagina. Fare clic su una domanda per espandere la risposta.


## Domande generali {#general}

Risposte alle domande più frequenti su Adobe Campaign v8, tra cui come connetterti, eseguire l’aggiornamento e ottenere supporto.

+++ Come posso collegarmi a Campaign v8?

Per connetterti ad Adobe Campaign, scarica e installa la console client di Campaign.

[Fai clic qui per ulteriori informazioni](connect.md).

A partire dalla versione v8.6 di Campaign, puoi accedere all&#39;**interfaccia utente di Campaign Web**, disponibile nell&#39;ambiente Adobe Experience Cloud centrale. Experience Cloud è un insieme integrato di applicazioni, prodotti e servizi Adobe per il marketing digitale.

Scopri come connetterti ad Adobe Experience Cloud e come accedere all’interfaccia di Adobe Campaign Web [in questa pagina](campaign-ui.md#ac-web-ui).

Ulteriori informazioni sono disponibili nella [documentazione dell’interfaccia utente di Adobe Campaign Web](https://experienceleague.adobe.com/it/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

>[!TIP]
>
>**Risoluzione dei problemi di connessione:**
>
>* Verifica che le credenziali di Adobe ID siano corrette
>* Verifica che la versione della console client corrisponda a quella del server
>* Verificare la connettività di rete e le impostazioni del firewall
>* Cancella cache della console client in caso di problemi
>* Contatta l’amministratore per verificare le autorizzazioni utente

**Argomenti correlati:**

* [Installare la console client](connect.md)
* [Interfaccia utente di Campaign](campaign-ui.md)
* [Autorizzazioni utente](gs-permissions.md)

+++

+++ Campaign v8 può essere installato in un ambiente locale o ibrido?

Campaign v8 è disponibile solo in Managed Cloud Services, interamente in hosting gestito da Adobe.

+++

+++ Come posso aggiornare Campaign alla versione più recente?

 Adobe Campaign viene aggiornato regolarmente. Versioni minori vengono rilasciate ogni anno con nuove funzioni, miglioramenti e correzioni. Inoltre, rilasciamo periodicamente build contenenti solo correzioni cumulative.

La frequenza regolare degli aggiornamenti è volta a far ottenere agli utenti il meglio e più recente, mantenendo l’ambiente sicuro e migliorando l’esperienza di utilizzo del prodotto. Per questo motivo riteniamo fondamentale eseguire sempre la versione più recente di Adobe Campaign.

>[!NOTE]
>
>In qualità di utente di Managed Cloud Services, l’istanza viene aggiornata da Adobe con le nuove versioni.

+++

+++ Come migliorare il recapito messaggi e-mail?

La capacità di recapito dei messaggi e-mail, un aspetto critico per il successo del programma di marketing di ogni mittente, è caratterizzata da criteri e regole in continua evoluzione. Per orientarsi nel mondo digitale e raggiungere al meglio i vari tipi di pubblico, è necessario ottimizzare regolarmente la strategia e-mail tenendo conto delle tendenze chiave di recapito messaggi.

Consulta questa guida per scoprire le [best practice per il recapito messaggi](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=it){target="_blank"}

Scopri come implementare la recapitabilità in Campaign [in questa guida](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=it){target="_blank"}

>[!TIP]
>
>**Suggerimenti chiave per il recapito messaggi:**
>
>* Gestisci un elenco e-mail pulito e rimuovi regolarmente gli abbonati inattivi
>* Utilizza il doppio consenso per garantire i destinatari coinvolti
>* Monitorare la reputazione del mittente e la reputazione IP
>* Autentica le e-mail con SPF, DKIM e DMARC
>* Rispetta immediatamente le richieste di annullamento dell’iscrizione
>* Verifica le e-mail prima di inviarle a tipi di pubblico di grandi dimensioni

**Argomenti correlati:**

* [Informazioni sul recapito messaggi](../send/about-deliverability.md)
* [Controllare il contenuto dei messaggi](../send/control-message-content.md)
* [Monitorare il recapito messaggi](../send/monitoring-deliverability.md)
* [SpamAssassin](../send/spamassassin.md)

+++

+++ Come posso assicurarmi che la consegna venga inviata senza errori?

 Adobe Campaign dispone di una serie di dashboard e strumenti per monitorare le consegne delle e-mail.

[Leggi la documentazione di Campaign Classic v7 per scoprire](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=it){target="_blank"} come assicurarti che i tuoi messaggi siano inviati, come monitorare l’esecuzione e intervenire in caso di errore.

+++

+++ Posso monitorare l’esecuzione di un flusso di lavoro?

Per scoprire come monitorare l’esecuzione di un flusso di lavoro di Campaign, consulta [questa pagina](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"}.

+++

+++ Con quali sistemi e componenti è compatibile Campaign v8?

Puoi ottenere l’elenco di tutti i sistemi e i componenti supportati per la build più recente di Campaign nella [Matrice di compatibilità di Adobe Campaign](compatibility-matrix.md).

+++

+++ Come posso scaricare Campaign?

È possibile ottenere il programma di installazione e Client Console da Adobe Download Center.

Come utente amministratore, accedi ad Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/it/campaign.html){target="_blank"} per scaricare Adobe Campaign.

Ulteriori informazioni sul Centro distribuzione [in questa pagina](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=it){target="_blank"}.

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

+++ Qual è la mia versione di Campaign?

Verifica il [numero della versione e della build](connect.md#ac-version) dal menu **Help > About…** della console del client di Campaign.

+++

+++ Quali sono le differenze tra Campaign Classic v7 e Campaign v8?

Campaign v8 è la versione di nuova generazione di Campaign, progettata per Managed Cloud Services. Offre notevoli miglioramenti a livello di infrastruttura, sicurezza, recapito messaggi e monitoraggio.

Adobe Campaign v8 è disponibile esclusivamente come **Cloud Service gestito** e non può essere distribuito in un ambiente locale o ibrido.

[Ulteriori informazioni sulla transizione da Campaign Classic v7 a v8](v7-to-v8.md).

+++

+++ Come posso impostare le autorizzazioni per gli utenti?

In qualità di amministratore di Campaign, puoi impostare le autorizzazioni per gli utenti della tua organizzazione.

Si tratta di una serie di diritti e limitazioni che autorizzano o negano l’autorizzazione a:

* Accesso a determinate funzionalità
* Accedere a determinati dati
* Creare, modificare e/o eliminare dati

[Ulteriori informazioni](../start/gs-permissions.md) sulle autorizzazioni utente in Campaign v8.

**Argomenti correlati:**

* [Introduzione alle autorizzazioni](gs-permissions.md)
* [Gestire le autorizzazioni utente](manage-permissions.md)
* [Aggiungere autorizzazioni sulle cartelle](folder-permissions.md)

+++

+++ Come si garantisce la conformità in materia di privacy con Campaign?

Adobe Campaign offre una serie di strumenti per aiutarti con la conformità in materia di privacy in relazione a RGPD, CCPA e altre normative sulla privacy.

[Ulteriori informazioni](../start/privacy.md) sulla gestione della privacy e sugli strumenti e le funzionalità forniti da Adobe Campaign per aiutarti con la conformità alla privacy.

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

* [Introduzione ai flussi di lavoro](../config/workflows.md)
* [Crea il tuo primo flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=it){target="_blank"}
* [Casi di utilizzo del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}
* [Monitorare l’esecuzione di un flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

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

* [Crea la prima consegna](create-message.md) - Guida dettagliata
* [Utilizzare i modelli di consegna](../send/create-templates.md) - Risparmia tempo con i modelli
* [Best practice per la consegna](delivery-best-practices.md) - Consigli per il successo
* [Definisci il contenuto dell&#39;e-mail](../send/defining-the-email-content.md) - Opzioni di creazione contenuto
* [Anteprima e bozze](../send/preview-and-proof.md) - Verifica prima dell&#39;invio
* [Configura e invia](../send/configure-and-send.md) - Passaggi finali per l&#39;invio
* [Personalizza contenuto](../send/personalize.md) - Aggiungi personalizzazione dinamica

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

* [Introduzione agli SMS](../send/sms/sms.md) - Guida completa agli SMS
* [Impostazioni di consegna SMS](../send/sms/sms-delivery-settings.md) - Opzioni di configurazione
* [Impostazioni account esterno SMPP](../send/sms/smpp-external-account.md) - Configurazione provider
* [Creare una consegna SMS](../send/sms/create-sms.md) - Creazione dettagliata
* [Contenuto SMS](../send/sms/sms-content.md) - Linee guida per la progettazione del contenuto
* [Invia bozze SMS](../send/sms/sms-proofs.md) - Verifica degli SMS
* [Monitorare gli SMS](../send/sms/sms-monitor.md) - Tracciare e analizzare le consegne

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

* [Creare e inviare notifiche push](../send/push.md) - Completare la guida push
* [Configurare il canale di notifica push](../send/push-settings.md) - Configurazione canale
* [Progetta un push avanzato Android](../send/rich-push-android.md) - Notifiche avanzate Android
* [Progetta un push avanzato iOS](../send/rich-push-ios.md) - Notifiche avanzate iOS
* [Configura con raccolta dati](../send/push-data-collection.md) - Metodo di integrazione rivisto moderno
* [Tracciare e monitorare](tracking.md) - Analizzare le prestazioni push

+++

+++ Come si crea una pagina di destinazione?

Puoi utilizzare l’editor di contenuti digitali di Adobe Campaign per progettare pagine di destinazione e definire la mappatura con i campi del database.

[Ulteriori informazioni](../dev/landing-pages.md) nella documentazione di Campaign v8.

Puoi anche utilizzare l&#39;interfaccia utente di Campaign Web per creare e pubblicare pagine di destinazione - [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}.

+++

+++ Come posso tracciare le consegne?

Puoi tenere traccia delle consegne inviate con Campaign v8 tramite [rapporti di consegna](../reporting/delivery-reports.md) dedicati e quindi monitorare le consegne.

Ulteriori informazioni sulla gestione del tracciamento nella campagna [sono disponibili in questa pagina](../start/tracking.md).

**Argomenti correlati:**

* [Tracciare e monitorare i messaggi](tracking.md)
* [Rapporti sulle consegne](../reporting/delivery-reports.md)
* [Errori di consegna](../send/delivery-failures.md)
* [Configurare i collegamenti tracciati](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"} (documentazione di Campaign Classic v7)

+++

+++ Come si traduce un messaggio di errore?

Un messaggio di errore viene visualizzato in una lingua straniera? Tutti i messaggi di errore e la relativa traduzione sono elencati in [questa pagina](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=it){target="_blank"}.

+++

+++ Posso creare un modulo web e raccogliere le risposte in Campaign?

Sì. Crea moduli web utilizzando **Applicazioni web di Campaign e Forms** (console client) per il controllo completo della logica e della convalida dei moduli oppure utilizza **Pagine di destinazione di Campaign** (interfaccia Web) con una moderna interfaccia di trascinamento per le sottoscrizioni e la generazione di lead. Entrambi raccolgono i dati direttamente in Campaign e si integrano con i flussi di lavoro per le azioni automatizzate.

[Ulteriori informazioni sulle applicazioni Web e sui moduli](../dev/webapps.md) | [Pagine di destinazione dell&#39;interfaccia utente Web di Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++



## Confronto tra Campaign v8 e le versioni precedenti {#v7-differences}

Comprendi le differenze principali tra Campaign v8 e le versioni precedenti (Classic v7 e Standard), tra cui architettura, distribuzione, percorsi di migrazione e modifiche alle funzioni. Che tu provenga da Campaign Classic v7 o Campaign Standard, scopri le novità e come effettuare una transizione fluida.

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

* [Da Campaign Classic v7 a v8](v7-to-v8.md) | Guida alla transizione da [v7 a v8](https://experienceleague.adobe.com/it/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}
* [Da Campaign Standard a v8](acs-to-v8.md) | [Transizione Campaign Standard](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"}
* [Guida all&#39;adozione di Campaign v8](https://experienceleague.adobe.com/it/docs/campaign-web/acs-to-ac/home){target="_blank"}
* [Matrice di funzionalità di Campaign v8](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
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
* Alcune implementazioni tecniche potrebbero essere diverse. Rivedi la [matrice delle funzionalità](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* La migrazione e il testing dei dati richiedono pianificazione e risorse
* **Per gli utenti di Campaign Standard** - La transizione è progettata per essere fluida con un&#39;interruzione minima del flusso di lavoro

**Passaggi successivi:**

Contatta il tuo rappresentante Adobe per:

* Valutare la fattibilità della migrazione e la tempistica
* Comprendere i vantaggi specifici del caso d’uso
* Pianificare la strategia di migrazione e l&#39;allocazione delle risorse
* Accedere agli strumenti di migrazione e al supporto

**Argomenti correlati:**

**Per utenti di Campaign Classic v7:**

* [Da Campaign Classic v7 a v8](v7-to-v8.md)
* Guida dettagliata da [v7 a v8](https://experienceleague.adobe.com/it/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}

**Per utenti Campaign Standard:**

* [Transizione Campaign Standard a v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"}
* [Guida all&#39;adozione di Campaign v8](https://experienceleague.adobe.com/it/docs/campaign-web/acs-to-ac/home){target="_blank"}
* [Panoramica da Campaign Standard a v8](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/overview){target="_blank"}
* [Introduzione per gli addetti al marketing](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/marketers){target="_blank"}
* [Introduzione per amministratori/sviluppatori](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/admin-developers){target="_blank"}

**Risorse generali:**

* [Matrice di funzionalità di Campaign v8](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [Matrice di compatibilità](compatibility-matrix.md)

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

* [Matrice di capacità](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} - Confronta le funzionalità tra le interfacce
* [Matrice di compatibilità](compatibility-matrix.md) - Sistemi e componenti supportati
* [Guardrail e limitazioni](ac-guardrails.md)
* [Guida alla transizione da v7 a v8](v7-to-v8.md)
* [Transizione da Campaign Standard a v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++

## Profili e tipi di pubblico {#audiences}

Risposte alle domande su gestione dei profili, creazione di tipi di pubblico, importazione di dati e targeting dei destinatari delle campagne.

+++ Come si creano i destinatari?

Crea i destinatari manualmente nella console client per i singoli profili, importa dai file (CSV/TXT) per le aggiunte in blocco, utilizza moduli web per l’auto-registrazione o integra tramite API da sistemi esterni. Utilizza i flussi di lavoro di importazione per carichi di dati ricorrenti.

[Creare i profili manualmente](../audiences/create-profiles.md) | [Importa profili da un file](../audiences/import-profiles.md) | [Raccogli profili con moduli web](../audiences/collect-profiles.md)

+++

+++ Come si importano i profili?

Campaign fornisce diversi metodi di importazione: importazione semplice dei file tramite l’importazione guidata, importazione basata su flusso di lavoro per trasformazioni complesse, importazioni ricorrenti con flussi di lavoro pianificati da SFTP e importazione API per l’integrazione programmatica.

Per le importazioni di file, prepara il file di dati (CSV/TXT, codifica UTF-8), utilizza l’importazione guidata o il flusso di lavoro, mappa le colonne sui campi di Campaign, definisci le regole di aggiornamento/inserimento e testa prima con un piccolo campione. Utilizza i flussi di lavoro per le importazioni ricorrenti e applica le regole di deduplicazione.

[Importa guida dati](../start/import.md) | [Flusso di lavoro di importazione ricorrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"} | [Attività di caricamento dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"}

+++

+++ Come posso definire la popolazione target per una campagna di marketing?

Campaign offre più metodi di targeting: crea query con criteri visivi, esegui il targeting di elenchi o segmenti esistenti, importa destinatari da file esterni (CSV, TXT) o applica filtri predefiniti. Puoi combinare i criteri con la logica AND/OR, escludere popolazioni specifiche, utilizzare gruppi di controllo e suddividerli per il test A/B. Visualizza sempre in anteprima la dimensione della popolazione target prima dell’invio.

[Definire i target della campagna](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=it){target="_blank"} | [Attività query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"} | [Crea pubblico](../audiences/create-audiences.md)

+++

+++ Come posso creare un elenco di profili?

Un elenco è un set statico di destinatari che puoi targetizzare nelle consegne e riutilizzare nelle campagne.

**Tre metodi di creazione:**

* **Creazione manuale:** Passare a **[!UICONTROL Profiles and Targets > Lists]** e fare clic su **[!UICONTROL Create]**. Aggiungi i destinatari da una query, da una selezione individuale o da una cartella.

* **Automazione del flusso di lavoro:** Utilizza l&#39;attività **[!UICONTROL List update]** per creare e gestire automaticamente elenchi dai risultati delle query o dai dati importati.

* **Durante l&#39;importazione:** Crea un elenco durante l&#39;importazione dei profili per salvarli come gruppo riutilizzabile.

>[!TIP]
>
>Utilizza i flussi di lavoro per gli elenchi che richiedono aggiornamenti regolari e la creazione manuale per la segmentazione una tantum.

[Crea pubblico](../audiences/create-audiences.md) | [Attività di aggiornamento elenco](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html){target="_blank"}

+++

+++ Come posso deduplicare una popolazione prima di inviare un messaggio?

Utilizzare l&#39;attività **[!UICONTROL Deduplication]** in un flusso di lavoro per rimuovere i destinatari duplicati prima della consegna. Posizionalo tra le attività **[!UICONTROL Query]** e **[!UICONTROL Delivery]**, quindi scegli i criteri di deduplicazione (in genere indirizzo e-mail o ID destinatario) e quale record mantenere.

>[!TIP]
>
>Deduplica sempre prima dell’invio affinché ogni persona riceva il messaggio una sola volta.

[Attività di deduplicazione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html){target="_blank"}

+++

+++ Come identificare ed eseguire il targeting degli abbonati a una newsletter?

Campaign tiene traccia automaticamente degli abbonamenti alle newsletter tramite i servizi di informazione. Per eseguire il targeting degli abbonati:

* Utilizza un&#39;attività **[!UICONTROL Query]** e filtra in base a **[!UICONTROL Subscriptions]** > seleziona il servizio newsletter
* Eseguire il targeting degli abbonati direttamente dalla consegna scegliendo **[!UICONTROL To > Subscribers of an information service]**
* Crea elenchi di sottoscrittori con l&#39;attività del flusso di lavoro **[!UICONTROL Subscription Services]**

Campaign tiene traccia della cronologia degli abbonamenti/annullamenti e gestisce automaticamente il consenso/diniego.

[Gestione sottoscrizioni](../start/subscriptions.md) | [Attività query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}

+++

+++ Qual è la best practice per escludere profili da una popolazione target?

Utilizza l&#39;attività **[!UICONTROL Exclusion]** in un flusso di lavoro per rimuovere i profili indesiderati dalla destinazione. Inseriscilo dopo le attività di targeting e definisci quale popolazione escludere.

[Attività di esclusione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html){target="_blank"}

+++

+++ Posso utilizzare profili esterni senza importarli in Campaign?

Sì, Campaign v8 consente di lavorare con profili esterni memorizzati in un database esterno senza caricarli in Adobe Campaign. [Ulteriori informazioni](../audiences/external-profiles.md).

+++

+++ Come posso creare profili di test per le consegne?

I profili di test sono destinatari speciali utilizzati per inviare bozze e convalidare le consegne senza influire sul database di produzione. Creali in **[!UICONTROL Profiles and Targets > Test profiles]** oppure utilizza la funzione **[!UICONTROL Seed addresses]** per aggiungere automaticamente i destinatari del test alle tue consegne per il controllo qualità e il monitoraggio della casella in entrata.

[Profili di test](../audiences/test-profiles.md)

+++

## Progettazione messaggio {#design}

Scopri come progettare messaggi di marketing efficaci in Campaign v8, inclusi modelli e-mail, tecniche di personalizzazione e contenuti multilingue. Progetta i tuoi messaggi nella console client o utilizza il moderno **Invia e-mail a Designer** nell&#39;interfaccia utente di Campaign Web per un&#39;esperienza di modifica visiva migliorata.

+++ Quali sono le best practice per la progettazione delle e-mail in Campaign?

Linee guida chiave: assicurati che la progettazione sia reattiva per dispositivi mobili, usa codice compatibile HTML 4.0/XHTML con CSS in linea, ottimizza le immagini (sotto i 100 KB) con testo alt, utilizza campi unione di personalizzazione, testa i client e-mail prima dell’invio e includi una versione in testo normale. Per una consegna dei messaggi ottimale, è necessario impostare la dimensione totale dell&#39;e-mail su un valore inferiore a 500 KB.

[Guida alla progettazione delle e-mail](../send/email.md) | [Best practice per la consegna](delivery-best-practices.md)

+++

+++ Che cos’è un modello di consegna?

Un modello di consegna è una consegna preconfigurata che salva tutte le impostazioni e i parametri per il riutilizzo in più campagne. I modelli includono regole di destinazione, progettazione del contenuto, personalizzazione, impostazioni tecniche (mittente, risposta a) e regole di tipologia. Crea una volta e riutilizza per mantenere la coerenza e accelerare la creazione delle campagne.

[Creare modelli di consegna](../send/create-templates.md)

+++

+++ Posso importare facilmente un HTML esistente per creare un’e-mail in Campaign?

Sì. Importa i contenuti HTML tramite copia/incolla diretta nell’editor dei contenuti, carica i file dal computer o carica da un URL. Assicurati che il tuo HTML utilizzi codice compatibile con le e-mail (HTML 4.0/XHTML) con CSS in linea e ospiti immagini su un server pubblico. Campaign aggiunge automaticamente la personalizzazione e il tracciamento al HTML importato.

>[!TIP]
>
>Per una migliore esperienza di progettazione delle e-mail, utilizza **E-mail Designer** nell&#39;interfaccia utente di Campaign Web, che offre funzionalità di trascinamento avanzate e modelli reattivi incorporati, anziché importare HTML non elaborati.

[Importare contenuti HTML](../send/defining-the-email-content.md)

+++

+++ Come posso creare una newsletter basata su abbonamento in Campaign?

Sì. Utilizza i servizi informativi di Campaign per gestire gli abbonamenti alle newsletter. Le funzionalità principali includono la gestione automatica di consenso/rinuncia, il tracciamento degli abbonamenti, la gestione della conformità (RGPD, CAN-SPAM), il supporto per più newsletter, l’integrazione web per i moduli di iscrizione e la consegna mirata agli abbonati.

[Gestire le iscrizioni](../start/subscriptions.md)

+++

+++ Come posso personalizzare i messaggi?

Campaign offre funzionalità di personalizzazione per creare messaggi pertinenti e mirati in base ai dati, al comportamento e alle preferenze dei destinatari.

**Opzioni Personalization:**

* **Campi di personalizzazione** - Inserire i dati del destinatario (ad esempio, `"Hello {{firstName}}")`
* **Blocchi di personalizzazione** - Utilizza blocchi di contenuto predefiniti o personalizzati
* **Contenuto condizionale** - Visualizza contenuto diverso in base ai criteri del destinatario
* **Dati comportamentali** - Sfrutta la cronologia di navigazione, i modelli di acquisto o le metriche di coinvolgimento

Test della personalizzazione prima dell’invio per verificare il corretto funzionamento dei campi di unione e della logica condizionale.

[Guida di Personalization](../send/personalize.md) | [Campi di personalizzazione](../send/personalization-fields.md) | [Contenuto condizionale](../send/conditions.md)

+++

+++ Posso inviare messaggi multilingue?

Sì. Campaign v8 offre funzionalità multilingue, con la **Interfaccia web di Campaign** che fornisce l’approccio più semplice. L’interfaccia utente web offre una distribuzione nativa multilingue con varianti di lingua: aggiungi varianti di lingua alla consegna e Campaign invia automaticamente la versione appropriata in base alla lingua preferita del destinatario. Disponibile per e-mail, notifiche push, SMS e messaggi transazionali.

Funzioni chiave: duplicazione automatica dei contenuti, invio automatico basato sulla lingua, fallback della lingua predefinito e gestione semplificata delle varianti.

La console client supporta anche contenuti multilingue utilizzando contenuti condizionali e flussi di lavoro, ma richiede una configurazione più manuale.

[Consegne multilingue (interfaccia Web)](https://experienceleague.adobe.com/en/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [Contenuto condizionale (console client)](../send/conditions.md)

+++

+++ Posso localizzare un modulo web?

Sì. Le applicazioni web di Campaign supportano la localizzazione multilingue. Definisci le traduzioni per tutti gli elementi del modulo (etichette, pulsanti, messaggi, testo di errore), con il rilevamento automatico della lingua in base al profilo del destinatario o alle impostazioni del browser. In un’unica applicazione web sono supportate più versioni linguistiche, con fallback a una lingua predefinita quando necessario.

[Localizzazione delle applicazioni web](../dev/webapps.md)

+++

+++ Posso utilizzare contenuti basati sull’intelligenza artificiale nelle e-mail?

Sì, ma **solo tramite l&#39;interfaccia utente Web di Campaign**. L’Assistente per l’intelligenza artificiale, con tecnologia Microsoft Azure OpenAI e Adobe Firefly, consente di creare contenuti professionali e coerenti per il brand per e-mail, SMS e notifiche push.

**Funzionalità chiave:**

* Genera testo (copia e-mail, righe dell’oggetto, contenuto SMS/push) e immagini allineate al brand
* Creare varianti di contenuto ottimizzate per diversi tipi di pubblico
* Ottimizzare il contenuto (elaborare, riepilogare, riformulare, semplificare)
* Caricare risorse del brand e ottenere un punteggio di allineamento del brand
* Utilizza il contenuto esistente come immagine di riferimento e carica come immagine di riferimento di stile

>[!NOTE]
>
>L’Assistente per l’intelligenza artificiale è disponibile esclusivamente nell’interfaccia utente web di Campaign e al momento supporta solo la lingua inglese. Gli utenti devono disporre delle autorizzazioni appropriate e devono accettare un contratto utente.

[Panoramica dell&#39;Assistente AI](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [Casi di utilizzo dell&#39;Assistente IA](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [Allineamento marchio](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Verifica e invio dei messaggi {#send}

Scopri le best practice per testare, convalidare, inviare e tracciare i messaggi di marketing per garantire la corretta consegna della campagna.

+++ Cos’è l’analisi della consegna?

L’analisi della consegna è una fase di convalida che Campaign esegue prima dell’invio. Calcola la popolazione target, convalida il contenuto, verifica la presenza di errori, applica le regole di tipologia e stima il volume di consegna.

Campaign genera registri che mostrano avvisi ed errori. Gli errori bloccano la consegna e devono essere corretti; gli avvisi sono indicativi. Rivedi sempre i registri di analisi prima dell’invio.

[Guida all’analisi della consegna](../send/delivery-analysis.md)

+++

+++ Perché dovrei creare delle prove?

Le bozze sono messaggi di test che convalidano la consegna prima di inviarla al pubblico principale. Utilizza le bozze per verificare la personalizzazione, testare il rendering del contenuto tra i client e-mail, confermare i collegamenti e il lavoro di tracciamento, controllare immagini e allegati e convalidare la reattività dei dispositivi mobili.

Le bozze consentono di rilevare gli errori prima che raggiungano migliaia di destinatari, abilitare l’approvazione delle parti interessate e testare il posizionamento della casella in entrata. Invia bozze a più client e dispositivi e-mail e ottieni sempre l’approvazione prima degli invii di produzione.

[Guida alle bozze e all’anteprima](../send/preview-and-proof.md)

+++

+++ Come si utilizzano gli indirizzi di seed in Adobe Campaign?

Gli indirizzi seed sono destinatari speciali aggiunti automaticamente a ogni consegna per test, controllo della qualità e monitoraggio, senza che soddisfino i criteri di destinazione. Utile per il monitoraggio continuo, il test di posizionamento della casella in entrata, la convalida della direct mailing e la visibilità delle parti interessate.

**Differenze chiave dalle bozze:**

* **Indirizzi seed** - Aggiunti automaticamente alle consegne di produzione, conteggiati per il volume di invio
* **Bozze** - Il test viene inviato prima della produzione, non conteggiare verso il volume, utilizzato per la convalida

Gestisci indirizzi seed in **[!UICONTROL Resources > Campaign management > Seed addresses]**. Mantieni gli elenchi piccoli per evitare di influenzare le metriche di consegna.

[Guida agli indirizzi seed](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html){target="_blank"}

+++

+++ Come posso impostare un processo di approvazione prima di inviare messaggi?

Campaign fornisce flussi di lavoro di approvazione per garantire che i messaggi soddisfino gli standard di qualità prima dell’invio. Configura le approvazioni per contenuto, destinazione, estrazione (direct mailing) e budget a livello di campagna o consegna.

**Configurazione:**

Crea gruppi di operatori in **[!UICONTROL Administration > Access management > Operator groups]**, quindi assegna gruppi di approvazione nelle proprietà della campagna o della consegna. Campaign invia e-mail di notifica ai revisori che possono approvare, rifiutare o richiedere modifiche.

**Per consegne autonome (non in una campagna):**

Utilizza **bozze come processo di approvazione**. Invia le bozze al gruppo di approvazione per la convalida e invia sempre una nuova bozza dopo aver apportato modifiche per garantire che le parti interessate rivedano la versione più recente.

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

[Configurare l’invio ondata](../send/configure-and-send.md#sending-using-multiple-waves)

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


>[!TIP]
>
>Utilizza l’interfaccia utente web di Campaign per creare e-mail in modo più rapido e intuitivo con strumenti di progettazione moderni. Utilizza la console client per campagne basate su flussi di lavoro avanzate o con targeting complesso.

[Crea la tua prima e-mail](create-message.md) | [Guida alla progettazione delle e-mail](../send/email.md)

+++

+++ Come si pianifica una consegna?

Campaign ti consente di pianificare le consegne per l’invio futuro, in modo da ottimizzare i tempi di invio e coordinare le campagne.

**Opzioni di pianificazione:**

* **Proprietà di consegna** - Invia immediatamente, pianifica per data/ora specifica o rinvia per ore/giorni
* **Livello della campagna** - Coordinare tutte le consegne all&#39;interno di una campagna
* **Attività Scheduler flusso di lavoro** - Per consegne ricorrenti, modelli complessi e campagne attivate da eventi

Campaign supporta anche l’ottimizzazione della data di contatto (ora di invio migliore per destinatario) e l’adattamento del fuso orario (stessa ora locale per tutti i destinatari).

[Pianificare l’invio della consegna](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ Posso aggiungere un allegato alle e-mail?

Sì. Campaign supporta allegati statici (lo stesso file per tutti i destinatari) e allegati personalizzati (file diversi per destinatario in base ai dati del profilo). Aggiungi allegati nella sezione **[!UICONTROL Attachments]** delle proprietà di consegna.

**Considerazioni importanti:**

* Mantieni gli allegati al di sotto di 1 MB per una consegna dei messaggi ottimale
* Gli allegati possono attivare i filtri anti-spam; verifica accuratamente prima dell’invio
* Evita i tipi di file comunemente bloccati dai client e-mail (.exe, .zip, .js)
* Per i file di grandi dimensioni, puoi utilizzare al loro posto i collegamenti di download tracciati

Utilizza formati di file sicuri (PDF, JPEG, PNG, DOCX) e testa con indirizzi seed prima degli invii di produzione.

[Guida agli allegati e-mail](../send/email.md#attachments)

+++

+++ Come posso configurare collegamenti tracciati in una consegna e-mail?

Campaign converte automaticamente tutti gli URL nell’e-mail in collegamenti tracciati per monitorare il coinvolgimento dei destinatari. Accedi alla sezione **[!UICONTROL Tracking]** della consegna per configurare le impostazioni di tracciamento per ogni collegamento.

**Opzioni di configurazione:**

* **Attiva/disattiva tracciamento** - Tracciamento controllo per collegamento
* **Etichette collegamento** - Aggiungi nomi descrittivi per il reporting (ad esempio, &quot;Acquista ora CTA&quot;)
* **Categorie di collegamenti** - Raggruppa i collegamenti per tipo per l&#39;analisi aggregata
* **Tipo di tracciamento** - Traccia clic, aperture o entrambi

Campaign tiene traccia dei collegamenti di contenuto, dei collegamenti alle pagine mirror e dei collegamenti per annullare l’abbonamento e può includere un pixel di tracciamento opzionale per le aperture delle e-mail. Utilizza etichette e categorie significative per semplificare la generazione di rapporti e identificare rapidamente i contenuti a prestazioni elevate.

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

>[!TIP]
>
>Monitora regolarmente l’elenco di quarantena. L’aumento dei tassi di quarantena segnala spesso problemi di qualità dei dati che richiedono attenzione prima che influiscano sulla reputazione del mittente.

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

* [Creare un flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=it){target="_blank"}
* [Attività del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"}
* [Best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}
* [Casi di utilizzo del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

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

* [Best practice per l’importazione](../start/import.md)
* [Attività di caricamento dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"}
* [Flusso di lavoro di importazione ricorrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"}

+++

+++ Posso monitorare l’esecuzione di un flusso di lavoro?

Sì. Campaign fornisce funzionalità complete di monitoraggio del flusso di lavoro per monitorare l’esecuzione, identificare i problemi e ottimizzare le prestazioni.

**Opzioni di monitoraggio:**

* **Dashboard del flusso di lavoro**: visualizzazione dello stato di esecuzione in tempo reale, dello stato di avanzamento e degli stati attività
* **Registri di esecuzione** - Accedere ai registri dettagliati per ogni attività e transizione
* **Audit trail** - Monitora modifiche del flusso di lavoro e cronologia di esecuzione
* **Avvisi e notifiche** - Configura gli avvisi e-mail per errori o condizioni specifiche

**Funzioni di monitoraggio chiave:**

* Indicatori di stato visivi (in sospeso, in corso, completato, non riuscito)
* Tracciamento del tempo di esecuzione per l’ottimizzazione delle prestazioni
* Messaggi di errore a livello di attività per la risoluzione dei problemi
* Sospendi, arresta o riavvia i flussi di lavoro in base alle esigenze

Accedere al monitoraggio da **[!UICONTROL Administration > Production > Objects created automatically > Campaign workflows]** o direttamente dal dashboard del flusso di lavoro.

**Argomenti correlati:**

* [Monitorare l’esecuzione di un flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}
* [Best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}
* [Avviare un flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/executing-a-workflow/start-a-workflow.html?lang=it){target="_blank"}

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

* [Aggiorna attività dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"}
* [Attività di gestione dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

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

* [Attività di gestione dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"}
* [Flussi di lavoro di targeting](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html){target="_blank"}
* [Attività di arricchimento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

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

* [Guida di Personalization](../send/personalize.md)
* [Casi di utilizzo del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=it){target="_blank"}
* [Attività di arricchimento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

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

* [Attività divisa](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html){target="_blank"}
* [Guida ai test A/B](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

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

* [Guida all’importazione dei dati](../start/import.md)
* [Attività di caricamento dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"}
* [Aggiorna attività dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"}

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

* [Attività Query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}
* [Utilizzo di aggregati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html){target="_blank"}
* [Programmi di benvenuto](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=it){target="_blank"}

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

* [Riferimento attività di targeting](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"}
* [Riferimento attività controllo flusso](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"}
* [Riferimento attività azione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html){target="_blank"}
* [Riferimento attività evento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html){target="_blank"}

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

* [Guida alle best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}
* [Creare un flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=it){target="_blank"}
* [Monitorare i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

+++

## Impostazioni campagna {#settings}

Configura l’istanza Campaign con le impostazioni, le integrazioni e le configurazioni giuste per ottimizzare le operazioni di marketing.

+++ Posso cambiare la lingua dell’interfaccia di Campaign?

La lingua di Campaign viene selezionata al momento della creazione dell’istanza. Non puoi modificarla in un secondo momento. Per ulteriori informazioni al riguardo, consulta [questa sezione](../start/connect.md).

L’interfaccia utente di Adobe Campaign è disponibile in diverse lingue: inglese, francese, tedesco, giapponese e altro ancora. Tieni presente che la console del client e il server devono essere impostati nella stessa lingua. Ogni istanza di Campaign può essere eseguita in una sola lingua.

Per l’inglese, durante l’installazione di Campaign puoi selezionare inglese US o inglese GB, che differiscono nei formati di data e ora.

+++

+++ Posso utilizzare Campaign v8 con altre soluzioni Adobe?

Puoi combinare le funzionalità di consegna e le funzionalità avanzate di gestione delle campagne di Adobe Campaign con una serie di soluzioni create per aiutarti a personalizzare la user experience.

[Scopri come utilizzare altre soluzioni Adobe](../connect/integration.md) e [come configurare IMS in Campaign](../start/connect.md).

+++

+++ Come posso impostare le funzionalità di tracciamento nella mia istanza di Campaign?

In qualità di utente esperto, puoi configurare le funzionalità di tracciamento nell’istanza Campaign.

[Ulteriori informazioni](../start/tracking.md).

+++

+++ Come configurare il recapito messaggi e-mail?

Oltre alla [Guida alle best practice per il recapito messaggi di Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=it){target="_blank"}, consulta le raccomandazioni tecniche per il recapito messaggi per scoprire come configurare la tua istanza per massimizzare le funzionalità di consegna di Campaign.

[Ulteriori informazioni](../send/about-deliverability.md).

+++

+++ Come posso implementare l’approvazione dei contenuti?

Campaign ti consente di impostare processi di approvazione per i passaggi principali della campagna di marketing, in modalità collaborativa. Per ogni campagna puoi approvare il target di consegna, i contenuti e i costi. Gli operatori Adobe Campaign incaricati dell’approvazione possono ricevere una notifica tramite e-mail e accettare o rifiutare l’approvazione dalla console o tramite una connessione web.

[Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=it){target="_blank"} e passaggi per implementare l&#39;approvazione dei contenuti della consegna in Campaign.

+++

+++ Come posso accedere ai dati memorizzati in un database esterno?

Adobe Campaign offre l’opzione Federated Data Access (FDA) per elaborare le informazioni archiviare in uno o più database esterni: puoi accedere ai dati esterni senza modificare la struttura dei dati di Adobe Campaign.

[Ulteriori informazioni](../connect/fda.md).

+++

+++ A quali database esterni posso collegare Campaign?

I database esterni compatibili con Campaign tramite Federated Data Access (FDA) sono elencati nella [Matrice di compatibilità](compatibility-matrix.md).

+++

+++ Adobe Campaign può integrarsi con i sistemi CRM?

Adobe Campaign fornisce diversi connettori di gestione delle relazioni con i clienti per collegare la piattaforma Adobe Campaign ai sistemi di terze parti. Questi connettori di gestione delle relazioni con i clienti ti consentono di sincronizzare contatti, account, acquisti, ecc. Facilitano l’integrazione dell’applicazione con varie applicazioni di terze parti e aziendali.

Questi connettori consentono un’integrazione rapida e semplice dei dati: Adobe Campaign fornisce un assistente dedicato per la raccolta e la selezione dalle tabelle disponibili nella gestione delle relazioni con i clienti. Ciò garantisce la sincronizzazione bidirezionale per far sì che i dati siano sempre aggiornati in tutti i sistemi.

[Ulteriori informazioni](../connect/crm.md) su come sincronizzare lo strumento CRM con Adobe Campaign.

+++

+++ Come si cancella la cache della console client?

In caso di problemi, ad esempio se i nuovi loghi non vengono rispecchiati correttamente o se si verificano problemi con l’esportazione dei dati, potrebbe essere necessario cancellare la cache della console client.

Esci e chiudi la console client. Passa alla seguente posizione in base al sistema operativo in uso:

* Windows: `C:\Users\<Username>\AppData\Roaming\Neolane\NL_5\`
* Mac: `~/Library/Application Support/Neolane/NL_5/`

Eliminare i file di configurazione XML (mantenendo `nlclient_cnx.xml`), quindi accedere nuovamente alla console client.

+++

+++ È possibile configurare le impostazioni dell&#39;interfaccia utente?

Sì, in qualità di amministratore, puoi personalizzare le impostazioni dell’interfaccia utente di Campaign per i tuoi utenti. [Ulteriori informazioni](../config/ui-settings.md).

+++

+++ È possibile creare campi e tabelle personalizzati?

Sì, Campaign v8 ti consente di estendere il modello dati con campi e tabelle personalizzati. Scopri come [estendere gli schemi](../dev/extend-schema.md).

+++

## Reporting {#reporting}

Ottieni informazioni sulle funzionalità di reporting di Campaign, inclusi rapporti incorporati, rapporti personalizzati e strumenti di analisi dei dati come i cubi.

+++ Come posso creare nuovi rapporti?

In aggiunta ai rapporti incorporati, Adobe Campaign consente di generare rapporti in vari contesti e di soddisfare esigenze diverse.

 Adobe Campaign non è uno strumento di reporting specializzato: i report creati in Adobe Campaign ti consentono principalmente di visualizzare i dati aggregati.

[Ulteriori informazioni](../reporting/gs-reporting.md) sulle funzionalità di reporting di Campaign.

+++

+++ Come posso progettare e condividere report statistici sulle popolazioni?

I [report di analisi descrittivi](../reporting/built-in-reports.md) di Adobe Campaign ti consentono di progettare e condividere report statistici sulle popolazioni.

[Ulteriori informazioni](../reporting/built-in-reports.md).

+++

+++ Come posso progettare report avanzati sui miei dati?

Con Campaign v8, puoi [creare report avanzati](../reporting/custom-reports.md). In qualità di utente esperto, potrai creare, aggiornare e distribuire rapporti personalizzati sui tuoi dati.

Per creare rapporti e dashboard è inoltre possibile utilizzare l’interfaccia utente di Campaign Web. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}.

+++

+++ Che cos’è un cubo e come si crea questo tipo di report?

Puoi estendere le capacità di esplorazione e di analisi del database e semplificare la configurazione di rapporti e tabelle da parte dell’utente finale: per elaborare calcoli, misure e statistiche, sarà sufficiente selezionare un cubo esistente (completamente configurato) durante la creazione del rapporto o della tabella .

Una volta creati e configurati, i cubi vengono utilizzati nelle caselle di query dei report e nelle applicazioni web. Possono essere utilizzati e manipolati all’interno di tabelle pivot.

Scopri come [esplorare i tuoi dati](../reporting/gs-cubes.md) con i cubi.

+++

+++ È possibile creare un report dalle risposte a un sondaggio online?

Campaign v8 non dispone di una funzione di sondaggio integrata. Per la creazione dei sondaggi è possibile utilizzare Adobe Experience Manager o altre soluzioni Web.

Tuttavia, puoi utilizzare le funzionalità di reporting per analizzare i dati raccolti e creare rapporti personalizzati.

+++

+++ Come posso condividere l’accesso al mio report nell’interfaccia di Campaign?

Puoi definire in quale contesto il report verrà visualizzato nell’interfaccia utente di Adobe Campaign. Per ulteriori informazioni sull’accesso ai report, consulta [questa sezione](../reporting/custom-reports.md).

+++

+++ Posso esportare i rapporti in formati diversi?

Sì, puoi esportare i rapporti di Campaign in diversi formati, ad esempio Excel, PDF o CSV. [Ulteriori informazioni](../reporting/custom-reports.md).

+++

## Sviluppatori {#developers}

Accedi alle informazioni tecniche per gli sviluppatori, inclusi i dettagli del modello dati, gli schemi, le API e le funzionalità di personalizzazione.

+++ Qual è il modello dati di Campaign?

Il modello dati concettuale del database di Adobe Campaign è costituito da una serie di tabelle incorporate e dalla loro interazione. La struttura fisica e logica dei dati trasferiti nell’applicazione è descritta in XML. Rispetta una grammatica specifica di Adobe Campaign, denominata schema.

[Ulteriori informazioni sul modello dati di Campaign](../dev/datamodel.md).

[In questa pagina sono elencate le best practice](../dev/datamodel-best-practices.md).

+++

+++ Come si utilizzano gli schemi di Campaign?

In Adobe Campaign, gli schemi di dati vengono utilizzati per:

* Definire il modo in cui gli oggetti dati all’interno dell’applicazione sono legati alle tabelle del database sottostanti.
* Definire i collegamenti tra i diversi oggetti dati all’interno dell’applicazione Campaign.
* Definire e descrivere i singoli campi inclusi in ciascun oggetto.

[Inizia a usare tabelle e schemi](../dev/schemas.md) per capire come utilizzare lo schema dei dati, estendere e personalizzare Campaign in base alle tue esigenze.

+++

+++ Come si utilizza una tabella dei destinatari personalizzata?

Puoi creare e implementare una tabella dei destinatari non incorporata in Campaign per inviare i messaggi.

[Ulteriori informazioni](../dev/custom-recipient.md)

+++

+++ Quali sono le best practice per definire le query in Campaign?

 L’editor di query di Adobe Campaign è uno strumento utile per esplorare i dati e creare segmenti.

Lo strumento di query di Adobe Campaign si trova su più livelli del software: per creare una popolazione target, segmentare i clienti, estrarre e filtrare i log di tracking, creare filtri, ecc.

Puoi eseguire query sul database di Campaign utilizzando l’editor di query generico. È accessibile tramite il menu **Strumenti > Editor di query generico…**. Ti consente di estrarre le informazioni archiviate in un database e organizzarle, raggrupparle, ordinarle, eccetera. Ad esempio, l’utente può recuperare i destinatari che hanno fatto clic più di “n” volte sul collegamento di una newsletter in un determinato periodo di tempo. Questo strumento ti consente di raccogliere, ordinare e visualizzare i risultati in base alle tue esigenze.

[Ulteriori informazioni](../start/query-editor.md). È inoltre possibile consultare la [Guida all&#39;automazione delle campagne](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}.

+++

+++ Come posso importare un pacchetto di dati?

 Adobe Campaign ti consente di esportare o importare la configurazione e i dati della piattaforma attraverso un sistema di pacchetti. I pacchetti di dati consentono la visualizzazione delle entità del database di Adobe Campaign tramite file in formato XML. Ogni entità contenuta in un pacchetto viene rappresentata con tutti i suoi dati.

Il principio dei pacchetti di dati è di esportare una configurazione di dati e integrarla in un altro sistema di Adobe Campaign.

[Ulteriori informazioni](../dev/packages.md) su come utilizzare i pacchetti di dati per importare ed esportare configurazioni di Campaign.

+++

+++ Dove posso trovare l’elenco delle API di Campaign v8?

Tutte le API di Campaign, inclusa la loro descrizione completa, sono disponibili in questa [&#128279;](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=it){target="_blank"}documentazione dedicata.

+++

+++ Cos’è l’API REST di Campaign?

Campaign v8 espone un set di API REST che consentono di creare integrazioni per Adobe Campaign e creare il proprio ecosistema interfacciando Adobe Campaign con il pannello di tecnologie utilizzato.

[Ulteriori informazioni](../dev/api/get-started-apis.md).

+++

+++ Come si monitorano i flussi di lavoro dall’API?

Scopri come monitorare i flussi di lavoro utilizzando le API di Campaign in [questa pagina dedicata](../dev/api/controlling-a-workflow.md).

+++

+++ Come posso aggiornare la struttura del database?

Se modifichi gli schemi di dati di Campaign, devi aggiornare la struttura del database. Scopri come in [questa sezione](../dev/update-database-structure.md).

+++

+++ Quali sono i limiti di Campaign v8?

Campaign v8 presenta alcune limitazioni rispetto a Campaign Classic v7, descritte in [questa pagina](../start/v7-to-v8.md#limitations).

+++

## Privacy {#privacy}

Scopri in che modo Adobe Campaign ti aiuta a rispettare le normative sulla privacy come RGPD e CCPA e a gestire le richieste dei soggetti interessati.

+++ Quali sono i termini chiave della privacy?

Gli elementi elencati di seguito rimandano ai termini e ai concetti chiave relativi alla privacy e al consenso in Adobe Campaign:

* [Normative sulla gestione della privacy](../start/privacy.md#privacy-regulations)
* [Dati personali e utenti tipo](../start/privacy.md#personal-data)
* [Diritto di accesso e diritto all’oblio](../start/privacy.md#right-access-forgotten)
* [Consenso, conservazione e ruoli](../start/privacy.md#consent-retention-roles)

+++

+++ Cosa suggerisce Adobe Campaign in merito al rispetto delle normative sulla privacy più recenti?

 Adobe non fornisce consulenza legale. Collabora con il tuo reparto legale per assicurarti che vengano eseguiti tutti i passaggi per garantire il rispetto di GDPR, CCPA, PDPA, LGPD o di qualsiasi altra normativa applicabile.

**Prepararsi per le richieste di accesso ed eliminazione dei dati**

* Identifica un processo per ricevere/rispondere alle richieste degli interessati, inclusa la nomina di un punto di contatto per la privacy.

* Esamina i vari dati dei clienti memorizzati in Adobe Campaign e determina identificatori univoci (probabilmente ce ne sarà più di uno).

* Determina un criterio e un processo di convalida/autenticazione per confermare l’identità dell’interessato.

* Assicurati che la risposta dell’interessato sia chiara e comprensibile.

**Considerare il consenso**

* Elenca e aggiorna, secondo necessità, tutti i punti di contatto per l’acquisizione dei dati per il GDPR (ovvero la lingua, il meccanismo per il consenso e i registri dei consensi).

* Assicurati che tutte le e-mail di marketing includano i collegamenti per annullare l’abbonamento.

* Valuta la strategia globale per l’e-mail marketing per determinare le implementazioni specifiche per le aree geografiche.

**Comprendere i dati**

* Controlla tutte le origini di importazione e acquisizione dei dati da cui i dati fluiscono in Adobe Campaign e documenta quali campi vengono utilizzati per le attività di marketing.

* Rimuovi eventuali attributi di dati inutilizzati dal database Adobe Campaign.

* Utilizza i dati disponibili in Adobe Campaign con l’intento per cui sono stati acquisiti e offri ai destinatari esperienze personalizzate migliorate.

* Esamina e aggiorna le autorizzazioni di accesso ai dati per garantire che gli utenti di Adobe Campaign possano sfruttare pienamente solo i dati necessari per eseguire le campagne, ma non accedere ad altri dati non correlati.

* Assicurati che ciascun utente di Adobe Campaign disponga dei diritti di accesso appropriati per eseguire le attività richieste, ma non disponga dei diritti per eseguire altre attività non correlate.

+++

+++ In che modo i titolari del trattamento possono ottenere il consenso con un impatto minimo sul coinvolgimento degli utenti?

Nei casi in cui si necessita il consenso per determinate attività di marketing, il consenso dei consumatori deve essere attivo (ovvero non può essere espresso in forma di silenzio-assenso o tramite caselle pre-selezionate), disaggregato e non può essere subordinato all’offerta dei servizi.

Possono verificarsi casi in cui è necessario aggiornare alcuni consensi per poter continuare a utilizzare i dati.

I marketer devono accettare questi requisiti di consenso avanzati come un vero indicatore di brand engagement e fedeltà, oltre che di soddisfazione e fiducia dei clienti.

+++

+++ In che modo i titolari del trattamento gestiscono il consenso in Adobe Campaign?

 Adobe Campaign offre già funzionalità per gestire il consenso a più livelli rispetto a quanto sfruttato dalla maggior parte degli esperti di marketing tramite campi dati personalizzati o attraverso uno o più servizi.

Gli esperti di marketing devono consultare il proprio reparto legale per informazioni su come procedere e sfruttare le funzionalità già incorporate in Adobe Campaign.

Ad esempio, estendere il modello dati in Adobe Campaign per monitorare non solo i consensi ricevuti, ma anche la marca temporale del consenso, e un tipo di indicatore che acquisisce l’ambito preciso del consenso.

+++

+++ Quali dati possono essere eliminati dai titolari del trattamento in Adobe Campaign in risposta a una richiesta da parte del cliente interessato?

Tutti i dati associati all’interessato verranno eliminati, incluse le tabelle pronte all’uso e personalizzate.

Tecnicamente, tutti i dati collegati all’interessato con `integrity="own"` verranno eliminati.

In qualità di titolare del trattamento, è possibile personalizzare questo passaggio modificando l’integrità dei collegamenti definiti negli schemi di dati (ad esempio, nel caso in cui si disponga di una giustificazione aziendale per non eliminare determinati dati).

+++

+++ Che effetto ha sui rapporti l’eliminazione dei registri di consegna e di tracciamento?

I rapporti in Adobe Campaign si basano su indicatori calcolati in base ai dati aggregati ricavati dai registri di consegna e di tracciamento. Di conseguenza, la rimozione dei singoli registri non dovrebbe avere alcun effetto sulle metriche visualizzate nei rapporti.

+++

+++ Devo prendere in considerazione una possibile reimportazione dei dati in un secondo momento?

In Adobe Campaign, i record vengono spesso caricati da un’origine dati esterna.

In qualità di titolare del trattamento assicurati che, quando ricevi una richiesta di eliminazione, tutti i dati necessari relativi all’interessato vengano eliminati da tutti i sistemi.

+++

+++ Un interessato i cui dati sono stati eliminati da Adobe Campaign può fornire di nuovo il consenso in un secondo momento?

È possibile che un interessato decida di fornire nuovamente il consenso o che venga aggiunto come nuovo destinatario dopo che i suoi dati sono stati eliminati da Adobe Campaign.

Puoi utilizzare l’audit trail, che illustra quando è avvenuta l’eliminazione precedente e quando è stato creato il nuovo destinatario.

+++

## Hai ancora bisogno di aiuto? {#get-help}

Non riesci a trovare quello che stai cercando? Risorse aggiuntive per la corretta esecuzione di Adobe Campaign v8.

### Supporto community

Entra in contatto con altri utenti di Campaign ed esperti di Adobe per condividere le conoscenze e ottenere le risposte.

* **[Community di Adobe Campaign](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}** - Poni domande, condividi soluzioni e collegati alla community di Campaign
* **[Forum Experience League](https://experienceleaguecommunities.adobe.com/){target="_blank"}** - Sfogliare discussioni tra tutti i prodotti Adobe
* **[Orario di lavoro della community di Campaign](https://experienceleague.adobe.com/){target="_blank"}** - Partecipa a sessioni live con esperti Adobe

### Documentazione e apprendimento

Accedi a guide complete, tutorial e materiali di formazione.

* **[Home della documentazione di Campaign v8](../campaign-home.md)** - Documentazione completa del prodotto
* **[Tutorial su Campaign](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html?lang=it){target="_blank"}** - Guide video dettagliate e tutorial pratici
* **[Novità](whats-new.md)** - Funzioni e funzionalità più recenti
* **[Note sulla versione](release-notes.md)** - Informazioni sulla versione corrente e precedente
* **[Best practice](delivery-best-practices.md)** - Approcci consigliati per le attività comuni

### Risorse tecniche

Trova documentazione tecnica dettagliata e risorse per sviluppatori.

* **[API di Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=it){target="_blank"}** - Documentazione completa di riferimento API
* **[Campaign GitHub](https://github.com/AdobeDocs/campaign.en)** - Contribuisci alla documentazione
* **[Note tecniche](https://experienceleague.adobe.com/it/docs/campaign/technotes-ac/technotes-home){target="_blank"}** - Articoli tecnici approfonditi
* **[Matrice di compatibilità](compatibility-matrix.md)** - Sistemi e versioni supportati

### Supporto e servizi

Chiedi aiuto al team di supporto di Adobe e gestisci la tua istanza.

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** - Registrazione dei casi di supporto e gestione degli utenti
* **[Assistenza clienti Adobe](https://helpx.adobe.com/it/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - Contatta il team di supporto
* **[Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it){target="_blank"}** - Gestisci le impostazioni dell&#39;istanza Campaign
* **[Stato del sistema](https://status.adobe.com/){target="_blank"}** - Verifica lo stato dei servizi Adobe

### Formazione e certificazione

Migliora le tue competenze con i programmi ufficiali di formazione e certificazione di Adobe.

* **[Adobe Digital Learning Services](https://learning.adobe.com/){target="_blank"}** - Corsi ufficiali con istruttore e autoapprendimento
* **[Certificazione Adobe Campaign](https://experienceleague.adobe.com/docs/certification/program/overview.html){target="_blank"}** - Convalida la tua esperienza con la certificazione professionale
* **[Percorsi di apprendimento Experience League](https://experienceleague.adobe.com/?lang=en#dashboard/learning){target="_blank"}** - percorsi di apprendimento guidato

### Altre risorse utili

* **[Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=it){target="_blank"}** - Riferimento per utenti di Classic v7
* **[Documentazione dell&#39;interfaccia utente Web di Campaign](https://experienceleague.adobe.com/it/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - Nuova guida dell&#39;interfaccia Web
* **[Best practice per il recapito dei messaggi](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=it){target="_blank"}** - Ottimizzare la consegna dei messaggi e-mail
* **[Aggiornamenti prodotti](https://experienceleague.adobe.com/en/docs/release-notes/experience-cloud/current){target="_blank"}** - Ultimi aggiornamenti Adobe Experience Cloud

**Ultimo aggiornamento:** novembre 2025 | **Si applica a:** Campaign v8.6 e versioni successive

*Errore rilevato o suggerimento di miglioramento? [Modifica questa pagina su GitHub](https://github.com/AdobeDocs/campaign.en/edit/main/help/v8/start/campaign-faq-comprehensive.md)*

