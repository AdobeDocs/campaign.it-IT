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
source-git-commit: 3453820bb0eca7847ec55d7e6ea15766a57ab94e
workflow-type: tm+mt
source-wordcount: '10161'
ht-degree: 7%

---

# Domande frequenti {#faq}

Risposte rapide alle domande più frequenti su Adobe Campaign v8. Se stai iniziando a lavorare o stai cercando aiuto per la configurazione avanzata, troverai le risposte organizzate per argomento di seguito.

**Ti avvicini ora a Campaign?** Inizia con [Guida introduttiva](#getting-started) per apprendere le nozioni di base.\
**Hai bisogno di assistenza per le versioni?** Controllare [Aggiornamenti](#upgrades) per informazioni sulla versione e sui processi di aggiornamento.\
**Migrazione da v7 o Standard?** Per informazioni sulle differenze e sulla transizione, consulta [Campaign v8 rispetto alle versioni precedenti](#v7-differences).\
**Hai bisogno di assistenza tecnica?** Seleziona [Sviluppatori](#developers) e [Impostazioni campagna](#settings).\
**Impossibile trovare la risposta?** Visita i [forum della community](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} o [contatta l&#39;assistenza](#get-help).

**Suggerimento:** utilizzare Ctrl+F (Comando+F su Mac) per cercare parole chiave specifiche in questa pagina. Fare clic su una domanda per espandere la risposta.


## Guida introduttiva {#getting-started}

Scopri le funzionalità di base per iniziare a utilizzare Adobe Campaign v8, dall’installazione e dalla connessione alla creazione delle prime campagne.

+++ Cos’è Adobe Campaign v8?

Adobe Campaign v8 è una potente piattaforma di automazione del marketing cross-channel che consente di creare, coordinare e distribuire campagne personalizzate tra canali e-mail, mobili, social e offline. Combina un solido database di marketing, un motore di orchestrazione delle campagne e funzionalità di interazione in tempo reale per coinvolgere i clienti in tutto il percorso.

**Funzionalità chiave:** gestione di campagne multicanale, segmentazione del pubblico e targeting, automazione dei flussi di lavoro, personalizzazione su larga scala, messaggistica in tempo reale e in batch, reporting e analisi, integrazione con Adobe Experience Cloud.

**Elementi che rendono la versione 8 unica:** Architettura nativa per il cloud (solo Managed Cloud Services), prestazioni su scala aziendale con tecnologia del database Snowflake, aggiornamenti automatici, protezione avanzata e integrazione bidirezionale con Adobe Experience Platform.

**Ideale per:** i team di marketing aziendale che gestiscono campagne complesse e a volume elevato su più canali e punti di contatto con i clienti.

**Argomenti correlati:**

[Descrizione del prodotto Campaign v8](https://helpx.adobe.com/it/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"} | [Novità della versione 8](whats-new.md) | [Guida introduttiva](get-started.md)

+++

+++ Come posso scaricare Campaign?

È possibile ottenere il programma di installazione e Client Console da Adobe Download Center.

Come utente amministratore, accedi ad Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/it/campaign.html){target="_blank"} per scaricare Adobe Campaign.

Ulteriori informazioni sul Centro distribuzione [in questa pagina](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=it){target="_blank"}.

+++

+++ Come posso collegarmi a Campaign v8?

Per connetterti ad Adobe Campaign, scarica e installa la console client di Campaign. [Ulteriori informazioni](connect.md).

A partire dalla versione v8.6 di Campaign, puoi accedere all&#39;**interfaccia utente di Campaign Web**, disponibile nell&#39;ambiente Adobe Experience Cloud centrale. Experience Cloud è un insieme integrato di applicazioni, prodotti e servizi Adobe per il marketing digitale.

Scopri come connetterti a Adobe Experience Cloud e accedere all&#39;interfaccia Web di Adobe Campaign [in questa pagina](campaign-ui.md#ac-web-ui). Ulteriori informazioni sono disponibili nella [documentazione dell’interfaccia utente di Adobe Campaign Web](https://experienceleague.adobe.com/it/docs/campaign-web/v8/campaign-web-home){target="_blank"}.


**Argomenti correlati:**

[Installa la console client](connect.md) | [Interfaccia utente di Campaign](campaign-ui.md) | [Autorizzazioni utente](gs-permissions.md)

+++

+++ Posso collegarmi a Campaign v8 con un Adobe ID?

Sì! Grazie all’integrazione con IMS (Adobe Identity Management System), gli utenti si connettono alla console Adobe Campaign utilizzando il proprio Adobe ID. Questa integrazione offre i seguenti vantaggi:

* Lo stesso ID può essere utilizzato per tutte le soluzioni Experience Cloud.
* Il collegamento viene memorizzato quando si utilizza Adobe Campaign con diverse integrazioni.
* Policy di gestione password più sicure.
* Utilizzo di account Federated ID (provider di ID esterno).

[Ulteriori informazioni](connect.md) sull&#39;accesso a Campaign v8 con un Adobe ID.

+++

+++ Quali concetti dell’interfaccia utente di Campaign dovrei conoscere?

Fai riferimento a [questa sezione](campaign-ui.md) per ulteriori informazioni sulle nozioni di base dell&#39;interfaccia utente di Adobe Campaign.

A partire dalla versione v8.6 di Campaign, potrai accedere anche alla nuova **interfaccia utente di Campaign Web**, disponibile nell&#39;ambiente Adobe Experience Cloud centrale.

[Ulteriori informazioni sono disponibili nella documentazione relativa all&#39;interfaccia utente Web di Adobe Campaign](https://experienceleague.adobe.com/it/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

+++

+++ Come posso impostare le autorizzazioni per gli utenti?

In qualità di amministratore di Campaign, puoi impostare le autorizzazioni per gli utenti della tua organizzazione.

Si tratta di una serie di diritti e limitazioni che autorizzano o negano l’autorizzazione a:

* Accesso a determinate funzionalità
* Accedere a determinati dati
* Creare, modificare e/o eliminare dati

**Argomenti correlati:**

[Introduzione alle autorizzazioni](gs-permissions.md) | [Gestione autorizzazioni utente](manage-permissions.md) | [Aggiungere autorizzazioni alle cartelle](folder-permissions.md)

+++

+++ Come posso selezionare il pubblico dei miei messaggi?

Campaign offre più metodi di targeting per selezionare il pubblico adatto ai messaggi:

**Metodi di targeting:**

* **Editor query** - Crea tipi di pubblico utilizzando filtri visivi sugli attributi, i comportamenti o le caratteristiche demografiche dei destinatari
* **Elenchi** - Utilizza elenchi di destinatari statici o dinamici predefiniti
* **Importazione file** - Carica i file dei destinatari esterni per le campagne una tantum
* **Flussi di lavoro** - Crea una logica di targeting complessa con attività di query, suddivisione e arricchimento
* **Filtri predefiniti** - Applica filtri pronti all&#39;uso (clienti attivi, abbonati, VIP)
* **Segmenti da Adobe Experience Platform** - Utilizzo di profili unificati e segmenti in tempo reale

Puoi combinare più criteri (posizione, cronologia acquisti, coinvolgimento) e utilizzare esclusioni, intersezioni o unioni per perfezionare il pubblico.

**Argomenti correlati:**

[Definire il pubblico in Campaign v8](../audiences/gs-audiences.md) | [Editor query](query-editor.md) | [Mappature di destinazione](../audiences/target-mappings.md)

+++

+++ Come si crea e invia una prima e-mail?

La creazione della prima e-mail in Campaign v8 è semplice. Parti da un modello, seleziona il pubblico di destinazione, progetta i contenuti con la personalizzazione, testali con le bozze, e infine inviali. Campaign offre due interfacce per la creazione di e-mail: la **console client** completa per gli utenti avanzati e la moderna **interfaccia utente Web di Campaign** per una creazione di e-mail più rapida e intuitiva.

**5 passaggi chiave:**

1. **Crea consegna** - Inizia da un modello e-mail o crea da zero
2. **Definisci pubblico** - Seleziona i destinatari tramite query, elenchi o flussi di lavoro
3. **Contenuto progettazione** - Utilizza e-mail designer per creare il messaggio con i campi di personalizzazione
4. **Invia bozze di test** - Convalida rendering e contenuto tra dispositivi e client e-mail
5. **Analizza e invia** - Esegui l&#39;analisi della consegna per verificare la presenza di errori, quindi invia l&#39;e-mail

**Argomenti correlati:**

[Progettazione e convalida e-mail](../send/email.md) | [Crea prima consegna](create-message.md) | [Modelli di consegna](../send/create-templates.md) | [Personalizza contenuto](../send/personalize.md)

+++

+++ Come si traduce un messaggio di errore?

Un messaggio di errore viene visualizzato in una lingua straniera? Tutti i messaggi di errore e la relativa traduzione sono elencati in [questa pagina](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=it){target="_blank"}.

+++

+++ Come posso segnalare un problema?

Per contattare l&#39;Assistenza clienti Adobe, connettiti a [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"} per creare un caso o avviare una sessione di chat.

Richiede account individuali con le autorizzazioni corrette. Se non riesci ad accedere, richiedi l’accesso tramite Experience League. [Ulteriori informazioni](https://helpx.adobe.com/it/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

In alternativa, partecipa a [Community Campaign](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} per cercare risposte o chiedere agli esperti.

+++

+++ Con quali sistemi e componenti è compatibile Campaign v8?

Puoi ottenere l’elenco di tutti i sistemi e i componenti supportati per la build più recente di Campaign nella [Matrice di compatibilità di Adobe Campaign](compatibility-matrix.md).

+++

+++ Posso utilizzare Campaign v8 con altre soluzioni Adobe?

Sì. Campaign v8 si integra perfettamente con le soluzioni Adobe Experience Cloud per un ecosistema di marketing unificato.

**Integrazioni chiave:** Adobe Experience Platform (profili unificati, dati in tempo reale), Adobe Analytics (misurazione prestazioni), Adobe Target (personalizzazione), Adobe Experience Manager (gestione contenuti), Adobe Audience Manager (segmenti di pubblico).

**Configurazione:** richiede l&#39;autenticazione Adobe IMS, configurata automaticamente per Campaign v8 Managed Cloud Services.

**Argomenti correlati:**

[Integrazioni Adobe Campaign](../connect/integration.md) | [Connessione con Adobe ID](connect.md)

+++

+++ Quali sono i limiti di Campaign v8?

Campaign v8 offre miglioramenti significativi delle prestazioni, ma presenta alcune differenze a livello di architettura rispetto a Campaign Classic v7, in particolare nelle implementazioni FFDA.

**Considerazioni chiave:**

* **Architettura FFDA** - Utilizza il database cloud (Snowflake) con diversi modelli di accesso ai dati
* **Aggiornamenti dati** - Devono essere eseguiti nei flussi di lavoro e non tramite accesso diretto al database
* **Ottimizzato per batch**: ottimizzato per le operazioni batch anziché per singoli aggiornamenti ad alta frequenza
* **Non disponibile in FFDA** - Indagini, Marketing Resource Management (MRM), alcuni connettori specifici

**Impatto della migrazione:** Il codice personalizzato che utilizza le scritture dirette del database richiede il refactoring; le integrazioni API potrebbero richiedere un adeguamento per l&#39;elaborazione batch.

Queste limitazioni si stanno evolvendo man mano che Adobe migliora v8. Consulta la documentazione più recente per informazioni sullo stato corrente.

**Argomenti correlati:**

[Migrazione da Campaign v7 a v8](../start/v7-to-v8.md#limitations) | [Architettura FFDA](../architecture/enterprise-deployment.md)

+++

+++ Come utente Campaign Classic v7, posso effettuare la migrazione a Campaign v8?

La migrazione automatizzata da un ambiente esistente di Campaign Classic v7 non è ancora disponibile.

Campaign v8 è disponibile **solo** come Managed Cloud Service e non può essere distribuito in ambienti on-premise o ibridi.

Per ulteriori informazioni sul processo di migrazione, contatta il tuo rappresentante Adobe.

Ulteriori informazioni sono disponibili nella sezione [Confronto tra Campaign v8 e le versioni precedenti](#v7-differences).

+++


## Aggiornamenti {#upgrades}

Scopri come controllare la versione di Campaign, comprendere il processo di aggiornamento e rimanere informato sulle nuove versioni. Campaign v8 Managed Cloud Services gestisce gli aggiornamenti automaticamente con interruzioni minime.

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


## Confronto tra Campaign v8 e le versioni precedenti {#v7-differences}

Comprendi le differenze principali tra Campaign v8 e le versioni precedenti (Classic v7 e Standard), tra cui architettura, distribuzione, percorsi di migrazione e modifiche alle funzioni. Che tu provenga da Campaign Classic v7 o Campaign Standard, scopri le novità e come effettuare una transizione fluida.


+++ Quali sono le principali differenze tra Campaign v8 e le versioni precedenti?

Campaign v8 è basato su una moderna architettura nativa per il cloud con miglioramenti significativi:

* **Solo Managed Cloud Services** - Completamente ospitato da Adobe (nessuna opzione on-premise/ibrida)
* **Prestazioni superiori** - Fino a 20 milioni di operazioni/ora, con architettura Full Federated Data Access (FFDA)
* **Nuova interfaccia Web di Campaign** - Interfaccia moderna e intuitiva accanto alla console classica
* **Aggiornamenti automatici** - Sempre alla versione più recente senza tempi di inattività
* **Funzionalità avanzate** - Assistente AI, notifiche push potenziate, SMS aggiornati, integrazioni migliorate con Adobe Experience Cloud

**Per gli utenti di Campaign Classic v7:** Scopri [la transizione da v7 a v8](v7-to-v8.md), incluse le modifiche all&#39;architettura, le funzionalità non disponibili e considerazioni sulla migrazione.

**Per gli utenti di Campaign Standard:** Scopri il [percorso di transizione a v8](acs-to-v8.md) e la [guida alla migrazione di Campaign Standard](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

**Argomenti correlati:**

[Funzionalità chiave di Campaign v8](whats-new.md) | [Architettura di Campaign v8](../architecture/architecture.md) | [Matrice di capacità](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [Guardrail e limitazioni](ac-guardrails.md)

+++

+++ Devo effettuare la migrazione da Campaign Classic v7 o Campaign Standard a v8?

Campaign v8 è la piattaforma strategica di Adobe, ideale per le organizzazioni che necessitano di campagne dal volume elevato (20 milioni di operazioni all’ora), interfaccia web moderna, vantaggi nativi per il cloud e supporto a lungo termine. Le versioni precedenti raggiungeranno la fine del supporto nei prossimi anni.

**Vantaggi chiave:**

* **Per gli utenti di Campaign Standard** - Interfaccia utente Web familiare, parità di funzioni (Reporting dinamico, API REST, pagine di destinazione), migrazione dei dati fluida
* **Per utenti Campaign Classic v7** - Doppia interfaccia (console + interfaccia Web), prestazioni migliori, aggiornamenti automatici, architettura FFDA migliorata

**Prova a eseguire la migrazione se:**

* Gestire grandi volumi di dati o problemi di prestazioni
* Desideri ridurre il sovraccarico IT e la gestione dell&#39;infrastruttura
* Necessità di integrazione Adobe Experience Cloud/Platform
* Desiderate una tecnologia a prova di futuro con aggiornamenti automatici

**Passaggi successivi:** Contatta il tuo rappresentante Adobe per valutare la fattibilità della migrazione e accedere agli strumenti di migrazione.

**Argomenti correlati:**

[Da Campaign Classic v7 a v8](v7-to-v8.md) | [Guida alla transizione di Campaign Standard](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [Matrice di capacità](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}

+++

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

+++ Come posso eseguire la migrazione dell’ambiente Campaign Classic v7 on-premise o ibrido ad Adobe Managed Services?

La migrazione ad Adobe Managed Services offre un percorso strategico dalla versione on-premise/ibrida v7 al cloud, che offre scalabilità, sicurezza e sovraccarico IT ridotti. Spesso rappresenta un punto di partenza prima della transizione a Campaign v8.

**Punti chiave:**

* Nessuno strumento di migrazione automatizzata disponibile: è necessaria la pianificazione e l&#39;esecuzione manuale
* Supporto Adobe Professional Services altamente consigliato
* I vantaggi includono infrastruttura cloud, patch di sicurezza automatiche, supporto specialistico e percorso più semplice verso v8
* La migrazione prevede la dovuta diligenza, l’audit dell’ambiente, la pulizia dei dati, la migrazione degli ambienti di staging e il cutover di produzione

**Guida introduttiva:** Contatta il tuo rappresentante Adobe per valutare il tuo ambiente e sviluppare un piano di migrazione dettagliato con Adobe Professional Services.

Ulteriori informazioni sulla [migrazione a Managed Services](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic-blogs/migrate-your-adobe-campaign-v7-onprem-hybrid-environment-to/ba-p/681605){target="_blank"}, incluse le sfide, le best practice e la roadmap dettagliata per la migrazione.

+++

+++ Quali sono le principali differenze terminologiche e di funzionalità in Campaign v8?

Campaign v8 offre la maggior parte delle funzionalità v7/Standard con miglioramenti, ma alcuni termini e funzioni differiscono. Di seguito è riportato un riepilogo delle modifiche principali.

**Modifiche terminologiche chiave (Campaign Standard → v8):**

* Risorse personalizzate → **Schemi** | Messaggi → **Consegne** | Utenti del prodotto → **Operatori**
* Gruppi di sicurezza → **Gruppi di operatori** | Unità organizzative → **autorizzazioni cartella**

**Aggiornamenti all&#39;interfaccia utente Web di Campaign:**

* Destinatari → **Profili** | Indirizzi seed → **Profili di test** | Analisi della consegna → **Preparazione della consegna**
* Elenchi → **Tipi di pubblico** | Anteprima e-mail → **Simula contenuto**

**Non disponibile nella versione 8:**

* Distribuzioni on-premise/ibride (solo Managed Cloud Services)
* Accesso diretto al database (tramite API)
* Gestione manuale dell’infrastruttura (gestito da Adobe)

**Nuove funzionalità per gli utenti di Campaign Standard:**

* Reporting dinamico, branding centralizzato, API REST, miglioramenti delle pagine di destinazione, frammenti visivi

**Argomenti correlati:**

[Matrice di capacità](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | Guida alla transizione da [v7 a v8](v7-to-v8.md) | [Transizione da Campaign Standard a v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"}

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

[Importa guida dati](../start/import.md) | [Flusso di lavoro di importazione ricorrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"} | [Attività di caricamento dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"}

+++

+++ Come posso creare profili di test per le consegne?

I profili di test (indirizzi seed) ti consentono di eseguire il targeting dei destinatari che non soddisfano i criteri di targeting definiti, consentendoti di testare la consegna prima di inviarla al pubblico principale. Aggiungerli tramite **[!UICONTROL Seed addresses]** nelle proprietà di consegna o utilizzare la cartella **[!UICONTROL Seed addresses]**.

Ulteriori informazioni sui [profili di test](../audiences/test-profiles.md).

+++

+++ Come posso definire la popolazione target per una campagna di marketing?

Campaign offre più metodi di targeting: crea query con criteri visivi, esegui il targeting di elenchi o segmenti esistenti, importa destinatari da file esterni (CSV, TXT) o applica filtri predefiniti. Puoi combinare i criteri con la logica AND/OR, escludere popolazioni specifiche, utilizzare gruppi di controllo e suddividerli per il test A/B. Visualizza sempre in anteprima la dimensione della popolazione target prima dell’invio.

**Argomenti correlati:**

[Definire i target della campagna](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=it){target="_blank"} | [Attività query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"} | [Crea pubblico](../audiences/create-audiences.md)

+++

+++ Come posso creare un elenco di profili?

Un elenco è un set statico di destinatari che puoi targetizzare nelle consegne e riutilizzare nelle campagne.

**Tre metodi di creazione:**

* **Creazione manuale:** Passare a **[!UICONTROL Profiles and Targets > Lists]** e fare clic su **[!UICONTROL Create]**. Aggiungi i destinatari da una query, da una selezione individuale o da una cartella.

* **Automazione del flusso di lavoro:** Utilizza l&#39;attività **[!UICONTROL List update]** per creare e gestire automaticamente elenchi dai risultati delle query o dai dati importati.

* **Durante l&#39;importazione:** Crea un elenco durante l&#39;importazione dei profili per salvarli come gruppo riutilizzabile.

**Suggerimento:** utilizza i flussi di lavoro per gli elenchi che richiedono aggiornamenti regolari e la creazione manuale per la segmentazione una tantum.

**Argomenti correlati:**

[Crea pubblico](../audiences/create-audiences.md) | [Attività di aggiornamento elenco](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html){target="_blank"}

+++

+++ Come posso deduplicare una popolazione prima di inviare un messaggio?

Utilizzare l&#39;attività **[!UICONTROL Deduplication]** in un flusso di lavoro per rimuovere i destinatari duplicati prima della consegna. Posizionalo tra le attività **[!UICONTROL Query]** e **[!UICONTROL Delivery]**, quindi scegli i criteri di deduplicazione (in genere indirizzo e-mail o ID destinatario) e quale record mantenere.

**Suggerimento:** deduplicare sempre prima dell&#39;invio per assicurarsi che ogni persona riceva il messaggio una sola volta.

Ulteriori informazioni sull&#39;[attività Deduplication](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html){target="_blank"}

+++

+++ Come identificare ed eseguire il targeting degli abbonati a una newsletter?

Campaign tiene traccia automaticamente degli abbonamenti alle newsletter tramite i servizi di informazione. Per eseguire il targeting degli abbonati:

* Utilizza un&#39;attività **[!UICONTROL Query]** e filtra in base a **[!UICONTROL Subscriptions]** > seleziona il servizio newsletter
* Eseguire il targeting degli abbonati direttamente dalla consegna scegliendo **[!UICONTROL To > Subscribers of an information service]**
* Crea elenchi di sottoscrittori con l&#39;attività del flusso di lavoro **[!UICONTROL Subscription Services]**

Campaign tiene traccia della cronologia degli abbonamenti/annullamenti e gestisce automaticamente il consenso/diniego.

**Argomenti correlati:**

[Gestione sottoscrizioni](../start/subscriptions.md) | [Attività query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}

+++

+++ Qual è la best practice per escludere profili da una popolazione target?

Utilizza l&#39;attività **[!UICONTROL Exclusion]** in un flusso di lavoro per rimuovere i profili indesiderati dalla destinazione. Inseriscilo dopo le attività di targeting e definisci quale popolazione escludere.

Ulteriori informazioni sull&#39;[attività di esclusione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html){target="_blank"}

+++

+++ Posso utilizzare profili esterni senza importarli in Campaign?

Sì, Campaign v8 consente di lavorare con profili esterni memorizzati in un database esterno senza caricarli in Adobe Campaign. [Ulteriori informazioni](../audiences/external-profiles.md).

+++

## Progettazione messaggio {#design}

Scopri come progettare messaggi di marketing efficaci in Campaign v8, inclusi modelli e-mail, tecniche di personalizzazione e contenuti multilingue. Progetta i tuoi messaggi nella console client o utilizza il moderno **Invia e-mail a Designer** nell&#39;interfaccia utente di Campaign Web per un&#39;esperienza di modifica visiva migliorata.

+++ Quali sono le best practice per la progettazione delle e-mail in Campaign?

Linee guida chiave: assicurati che la progettazione sia reattiva per dispositivi mobili, usa codice compatibile HTML 4.0/XHTML con CSS in linea, ottimizza le immagini (sotto i 100 KB) con testo alt, utilizza campi unione di personalizzazione, testa i client e-mail prima dell’invio e includi una versione in testo normale. Per una consegna dei messaggi ottimale, è necessario impostare la dimensione totale dell&#39;e-mail su un valore inferiore a 500 KB.

**Argomenti correlati:**

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

+++ Come posso personalizzare le righe dell’oggetto dell’e-mail?

Le righe dell’oggetto personalizzate aumentano notevolmente i tassi di apertura. Campaign consente di inserire in modo dinamico i dati dei destinatari, applicare una logica condizionale e testare le varianti per ottimizzare il coinvolgimento.

**Tecniche Personalization:**

* **Campi di base** - Inserire nome, cognome, posizione: `"<%@ firstName %>, exclusive offer for you"`
* **Contenuto condizionale** - Argomenti diversi per segmento: `"<% if (recipient.gender == 'F') { %>Special offer just for you<% } else { %>Exclusive deal inside<% } %>"`
* **Dati dinamici** - Includi cronologia acquisti, punti fedeltà o informazioni account
* **Emojis** - Aggiungi impatto visivo (esegui prima il test tra client e-mail)

**Best practice:** Mantieni sotto i 50 caratteri, verifica i token di personalizzazione prima dell&#39;invio, utilizza i test A/B per ottimizzare, evitare parole trigger di posta indesiderata, includi proposta di valore o urgenza.

**Argomenti correlati:**

[Campi di personalizzazione](../send/personalization-fields.md) | [Contenuto condizionale](../send/conditions.md)

+++

+++ Posso inviare messaggi multilingue?

Sì. Campaign v8 offre funzionalità multilingue, con la **Interfaccia web di Campaign** che fornisce l’approccio più semplice. L’interfaccia utente web offre una distribuzione nativa multilingue con varianti di lingua: aggiungi varianti di lingua alla consegna e Campaign invia automaticamente la versione appropriata in base alla lingua preferita del destinatario. Disponibile per e-mail, notifiche push, SMS e messaggi transazionali.

Funzioni chiave: duplicazione automatica dei contenuti, invio automatico basato sulla lingua, fallback della lingua predefinito e gestione semplificata delle varianti.

La console client supporta anche contenuti multilingue utilizzando contenuti condizionali e flussi di lavoro, ma richiede una configurazione più manuale.

**Argomenti correlati:**

[Consegne multilingue (interfaccia Web)](https://experienceleague.adobe.com/en/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [Contenuto condizionale (console client)](../send/conditions.md)

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

**Argomenti correlati:**

[Panoramica dell&#39;Assistente AI](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [Casi di utilizzo dell&#39;Assistente IA](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [Allineamento marchio](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Verifica e invio dei messaggi {#send}

Scopri le best practice per testare, convalidare, inviare e tracciare i messaggi di marketing per garantire la corretta consegna della campagna.

+++ Come migliorare il recapito messaggi e-mail?

La capacità di recapito dei messaggi e-mail, un aspetto critico per il successo del programma di marketing di ogni mittente, è caratterizzata da criteri e regole in continua evoluzione. Per orientarsi nel mondo digitale e raggiungere al meglio i vari tipi di pubblico, è necessario ottimizzare regolarmente la strategia e-mail tenendo conto delle tendenze chiave di recapito messaggi.

Consulta questa guida per scoprire le [best practice per il recapito messaggi](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=it){target="_blank"}

Scopri come implementare la recapitabilità in Campaign [in questa guida](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=it){target="_blank"}

**Argomenti correlati:**

[Introduzione al recapito messaggi](../send/about-deliverability.md) | [Controllare il contenuto del messaggio](../send/control-message-content.md) | [Monitorare il recapito messaggi](../send/monitoring-deliverability.md) | [SpamAssassin](../send/spamassassin.md)

+++

+++ Come posso assicurarmi che la consegna venga inviata senza errori?

**Prima di inviare:** Esegui analisi consegna, invia bozze di test, controlla gli avvisi, verifica il conteggio delle destinazioni.

**Durante/dopo l&#39;invio:** monitora il dashboard di consegna (inviato, recapitato, mancati recapiti, errori), controlla i registri di consegna, tieni traccia delle percentuali di successo/mancato recapito, controlla gli indirizzi messi in quarantena.

**Best practice:** configura gli avvisi, utilizza ondate per volumi di grandi dimensioni, verifica prima i volumi di piccole dimensioni, pulisci regolarmente il database dei destinatari e monitora la reputazione del mittente.

**Argomenti correlati:**

[Tracciare e monitorare le consegne](../send/tracking.md) | [Best practice per la consegna](delivery-best-practices.md)

+++

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

Ulteriori informazioni sono disponibili nella [Guida agli indirizzi seed](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html){target="_blank"}

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

+++ Posso eseguire test A/B sulle consegne?

Sì! Campaign ti consente di eseguire test A/B (o test suddivisi) per ottimizzare oggetto, contenuto, nome del mittente, tempi di invio e altro ancora confrontando le prestazioni tra diverse varianti.

**Elementi che è possibile verificare:**

* **Righe oggetto** - Confronta i tassi di apertura tra soggetti diversi
* **Varianti di contenuto** - Testa layout, inviti all&#39;azione o immagini diversi
* **Informazioni mittente** - Verifica del nome del mittente o impatto sull&#39;indirizzo
* **Ora di invio** - Identifica intervalli di consegna ottimali
* **Strategie Personalization** - Confronto tra contenuti personalizzati e generici

**Funzionamento:**

1. Creare la consegna e definire le varianti di test (fino a 3)
2. Dividi il pubblico (in genere il 10-20% per i segmenti di test)
3. Campaign invia varianti per testare i segmenti e tenere traccia delle prestazioni
4. La variante vincente viene inviata automaticamente al pubblico rimanente (oppure selezioni manualmente il vincitore)

**Disponibile in:** sia l&#39;interfaccia utente Web di Campaign che la console client. L’interfaccia web offre una configurazione più semplice grazie al confronto visivo.

**Argomenti correlati:**

[Analisi della consegna](../send/delivery-analysis.md) | [Inviare e tenere traccia delle consegne](../send/send.md)

+++

+++ Cos’è una regola di tipologia?

Le regole di tipologia sono regole aziendali automatizzate applicate durante l’analisi della consegna per convalidare e ottimizzare l’invio dei messaggi. Garantiscono la conformità alle politiche di marketing, proteggono il recapito messaggi e prevengono l’affaticamento dei clienti.

**Tipi di regole principali:**

* **Regole di filtro** - Escludi destinatari (inseriti nell&#39;elenco Bloccati, non sottoscritti, in quarantena)
* **Regole di pressione** - Controlla la frequenza dei messaggi per evitare di sopraffare i destinatari
* **Regole di capacità** - Limita il volume dei messaggi per l&#39;elaborazione dei limiti di capacità o ISP
* **Regole di controllo** - Verifica la validità del messaggio (oggetto, collegamento per annullare l&#39;iscrizione, formato mittente)

Le regole sono raggruppate in tipologie e applicate durante l’analisi della consegna. Campaign può escludere i destinatari, bloccare la consegna o generare avvisi in base alle regole.

Ulteriori informazioni nella [Guida alle regole di tipologia](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=it){target="_blank"}

+++

+++ Come posso inviare le e-mail in modo graduale?

Sì. L’invio ondata suddivide la consegna in più batch inviati a intervalli pianificati. Questo è essenziale per le campagne su grandi volumi per bilanciare il carico del server, impedire la limitazione dell’ISP, creare la reputazione del mittente con i nuovi IP e gestire gli opt-out/bounce tra un’ondata e l’altra.

**Configurazione:**

Nelle proprietà di consegna, abilita l’invio delle onde e definisci il numero di onde (o dimensione batch), l’intervallo tra le onde e la distribuzione delle onde (percentuali lineari o personalizzate). Campaign divide automaticamente la popolazione target e invia ogni ondata secondo la pianificazione.

Utilizza le ondate per le campagne di grandi dimensioni, monitora le prestazioni della prima ondata prima di continuare e lascia un tempo sufficiente tra un’ondata e l’altra per elaborare i mancati recapiti e le rinunce.

Scopri come [configurare l&#39;invio ondata](../send/configure-and-send.md#sending-using-multiple-waves)

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

[Guida al tracciamento dei collegamenti](../send/tracking.md) | [Best practice per il tracciamento](../send/send.md)

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

[Monitoraggio della consegna](../send/send.md) | [Guida al tracciamento](../send/tracking.md)

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
* inserire nell&#39;elenco Bloccati **** - Destinatari che hanno rinunciato o richiesto di essere esclusi

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

+++ Che cos’è un flusso di lavoro?

Adobe Campaign include flussi di lavoro per orchestrare l’intera gamma di processi e attività tra i diversi moduli del server dell’applicazione. Questo ambiente grafico completo ti consente di progettare processi inclusi segmentazione, esecuzione di campagne, elaborazione di file, partecipazione di utenti, ecc. Il motore del flusso di lavoro esegue e traccia tali processi.

Ad esempio, puoi utilizzare un flusso di lavoro per scaricare un file da un server, decomprimerlo e quindi importare i record contenuti all’interno nel database di Adobe Campaign.

Un flusso di lavoro può inoltre coinvolgere uno o più operatori da avvisare o che possono effettuare scelte e approvare processi. In questo modo, è possibile creare un’azione di consegna, assegnare un’attività a uno o più operatori per lavorare sul contenuto, specificare dei target e approvare le prove prima di avviare la consegna.

[Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=it){target="_blank"} sui workflow. Puoi inoltre consultare le [best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=it){target="_blank"}.

**Argomenti correlati:**

[Introduzione ai flussi di lavoro](../config/workflows.md) | [Crea il tuo primo flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=it){target="_blank"} | [Casi di utilizzo del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [Monitorare l&#39;esecuzione del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

+++

+++ Posso monitorare l’esecuzione di un flusso di lavoro?

Sì. Campaign fornisce diversi strumenti di monitoraggio: dashboard del flusso di lavoro (stato in tempo reale ed errori), registri del flusso di lavoro (registri di esecuzione dettagliati), mappa di calore (visualizzazione dell’attività e dei colli di bottiglia), audit trail (tracciamento delle modifiche) e avvisi (notifiche degli errori).

Per monitorare, aprire il flusso di lavoro e fare clic sulla scheda **Registri**. Le attività non riuscite vengono visualizzate in rosso.

**Argomenti correlati:**

[Monitorare l&#39;esecuzione del flusso di lavoro](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} | [Best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}

+++

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

[Crea un flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=it){target="_blank"} | [Attività del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"} | [Best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"} | [Casi di utilizzo del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ Come posso automatizzare le campagne ricorrenti?

Utilizza i flussi di lavoro con l&#39;attività **Scheduler** per automatizzare le campagne che vengono eseguite secondo una pianificazione regolare, ovvero a intervalli giornalieri, settimanali, mensili o personalizzati. Perfetto per e-mail di benvenuto, messaggi di compleanno, invii di newsletter, promemoria del carrello abbandonati e reporting regolare.

**Schema di installazione:**

1. **Pianificazione** - Definisci la frequenza (ad esempio, &quot;Ogni lunedì alle 9&quot;)
2. **Query** - Seleziona il pubblico di destinazione con criteri dinamici
3. **Arricchimento** (facoltativo) - Aggiungi dati di personalizzazione
4. **Consegna** - Configura il messaggio (e-mail, SMS, push)
5. **Fine** - Il flusso di lavoro viene completato e attende la prossima esecuzione pianificata

**Campagne automatizzate comuni:**

* **Serie di benvenuto** - Flusso di lavoro giornaliero per inviare e-mail di onboarding ai nuovi abbonati
* **E-mail di compleanno** - Verifica giornaliera per i destinatari con compleanni, invia messaggio personalizzato
* **Nuovo coinvolgimento** - Targeting settimanale degli utenti inattivi con offerte di riconquista
* **Newsletter** - Distribuzione pianificata settimanale o mensile dei contenuti
* **Abbandono carrello** - Flusso di lavoro orario per identificare e inviare messaggi agli utenti che abbandonano il carrello

**Suggerimento:** utilizza il tipo **Recapito ricorrente** nei flussi di lavoro per tenere traccia di ogni esecuzione separatamente e gestire i report cronologici.

**Argomenti correlati:**

[Attività Scheduler](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/scheduler.html){target="_blank"} | [Consegne ricorrenti](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/sending-a-birthday-email.html){target="_blank"} | [Automazione campagna](https://experienceleague.adobe.com/docs/campaign/automation/home.html?lang=it){target="_blank"}

+++

+++ Come posso importare dati in Campaign?

**Metodi:** Importazione guidata (CSV/TXT una tantum), importazione basata su flusso di lavoro (**[!UICONTROL Data loading (file)]** attività per importazioni complesse/ricorrenti con trasformazioni), API REST (sincronizzazione programmatica/in tempo reale).

**Best practice:** verifica con campioni di piccole dimensioni, utilizza la codifica UTF-8, mappa correttamente i campi, applica la deduplicazione, pianifica importazioni di grandi dimensioni fuori picco.

**Argomenti correlati:**

[Best practice per l&#39;importazione](../start/import.md) | [Attività di caricamento dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"} | [Flusso di lavoro di importazione ricorrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"}

+++

+++ Come posso garantire la qualità dei dati durante le importazioni?

La qualità dei dati è fondamentale per la corretta esecuzione della campagna. La scarsità dei dati comporta errori di consegna, spreco di risorse e rischi di conformità. Campaign fornisce strumenti per convalidare, pulire e arricchire i dati durante il processo di importazione.

**Passaggi di convalida dei dati:**

1. **Convalida pre-importazione** - Verificare il formato del file, la codifica (UTF-8), la mappatura delle colonne, i campi obbligatori presenti
2. **Deduplicazione** - Utilizza l&#39;attività **[!UICONTROL Deduplication]** per identificare e gestire i duplicati tramite e-mail, ID o chiavi personalizzate
3. **Arricchimento dei dati** - Utilizza l&#39;attività **[!UICONTROL Enrichment]** per aggiungere dati mancanti dalle tabelle di Campaign esistenti
4. **Formattazione standardizzazione** - Normalizzazione di numeri di telefono, indirizzi e-mail, date, codici paese tramite JavaScript o arricchimento
5. **Regole di convalida** - Applica vincoli (formato e-mail valido, campi obbligatori, intervalli di valori)

**Problemi comuni e correzioni:**

* **Errori di codifica dei caratteri** → utilizzare sempre la codifica UTF-8
* **Mancata corrispondenza formato data** → Standardizzare al formato AAAA-MM-GG
* **Indirizzi e-mail non validi** → Utilizzare le regole di convalida o JavaScript per filtrare
* **Record duplicati** → Includi sempre l&#39;attività di deduplicazione prima degli aggiornamenti
* **Campi obbligatori mancanti** → Impostare valori predefiniti o rifiutare record incompleti

**Best practice:** crea un modello di flusso di lavoro riutilizzabile per la &quot;qualità dei dati&quot; con attività standard di convalida e pulizia che puoi applicare a tutte le importazioni.

**Argomenti correlati:**

[Guida alla qualità dei dati](../start/import.md) | [Attività di deduplicazione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html){target="_blank"} | [Attività di arricchimento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

+++

+++ Quali sono i casi d’uso comuni dei flussi di lavoro in Campaign?

I flussi di lavoro automatizzano i processi di marketing, tra cui:

**Gestione dati:** Importare/caricare dati, pulizia, arricchimento, gestione elenchi\
**Automazione campagna:** serie di benvenuto, campagne di compleanno, ricoinvolgimento, abbandono del carrello\
**Destinazione avanzata:** test A/B, segmentazione dinamica, punteggio lead, orchestrazione cross-channel\
**Monitoraggio:** Monitoraggio del flusso di lavoro/della consegna, avvisi, manutenzione del database\
**Integrazione:** sincronizzazione CRM, integrazioni API, flussi di lavoro attivati da eventi

**Argomenti correlati:**

[Libreria dei casi di utilizzo del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [Crea un flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=it){target="_blank"} | [Best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}

+++

+++ Come posso aggiornare i dati di Campaign con un flusso di lavoro?

Utilizza l&#39;attività **[!UICONTROL Update data]** per operazioni di database in blocco: Inserisci (aggiungi nuovi record), Aggiorna (modifica esistente), Inserisci o aggiorna (upsert), Elimina (rimuovi record corrispondenti).

**Utilizzi comuni:** aggiornare gli attributi del profilo, sincronizzarli con i sistemi esterni, gestire le appartenenze agli elenchi, pulire/deduplicare i dati, applicare modifiche di stato in blocco.

Configura le chiavi di riconciliazione per una corrispondenza precisa e scegli le opzioni di aggiornamento.

**Argomenti correlati:**

[Aggiorna attività dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"} | [Attività di gestione dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ Come posso sfruttare le funzionalità di gestione dati?

Le attività di gestione dei dati consentono operazioni sofisticate: arricchimento (aggiunta di dati da tabelle correlate), suddivisione (popolazioni di segmenti), deduplicazione (rimozione di duplicati), aggiornamento dei dati (operazioni in blocco), modifica della dimensione (dimensioni di targeting switch), intersezione/unione/esclusione (combinare/filtrare le popolazioni).

**Utilizzi comuni:** arricchisci con dati di acquisto/comportamento, segmenta i tipi di pubblico, rimuovi i duplicati, integra database esterni (FDA), crea query complesse a più tabelle.

**Argomenti correlati:**

[Attività di gestione dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"} | [Attività di arricchimento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

+++

+++ Posso automatizzare l’invio di messaggi personalizzati?

Sì. Creare flussi di lavoro automatizzati: Query (pubblico di destinazione) → Arricchimento (aggiunta di dati di personalizzazione) → Suddivisione (segmenti facoltativi) → Consegna (messaggi personalizzati) → Scheduler (esecuzione ricorrente).

**Personalization:** Utilizzare dati di profilo, dati comportamentali, contenuto condizionale e valori dinamici. Scenari comuni: campagne di compleanno, abbandono del carrello, programmi fedeltà, messaggi di riconquista e attivati da eventi.

**Argomenti correlati:**

[Guida di Personalization](../send/personalize.md) | [Casi di utilizzo del flusso di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=it){target="_blank"}

+++

+++ Come posso dividere un pubblico in sottoinsiemi con un flusso di lavoro?

Utilizza l&#39;attività **[!UICONTROL Split]** per dividere le popolazioni: condizioni di filtro (età, posizione, stato VIP), distribuzione percentuale (test A/B), record limite (primo N, primo X%), raggruppamento dati (un sottoinsieme per valore).

**Utilizzi comuni:** test A/B, routing delle preferenze del canale, rollout progressivo, messaggistica specifica per il segmento, bilanciamento del carico. Ogni sottoinsieme scorre verso una transizione separata per elaborazioni diverse.

**Argomenti correlati:**

[Attività divisa](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html){target="_blank"} | [Guida ai test A/B](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ Come posso aggiornare i dati sui destinatari da un file esterno?

Sì. Flusso di lavoro: caricamento dei dati (file) → arricchimento (facoltativo) → riconciliazione (chiavi di corrispondenza come e-mail/ID) → aggiornamento dei dati (aggiornamento dei record corrispondenti, inserimento di nuovi se non corrispondono).

**Utilizzi comuni:** aggiorna gli attributi del profilo da CRM, aggiorna gli stati di abbonamento, sincronizza i punti fedeltà, aggiorna le preferenze di consenso/rinuncia.

**Best practice:** utilizza identificatori univoci, convalida prima i dati, verifica con esempi, pianifica aggiornamenti regolari.

**Argomenti correlati:**

[Importa guida dati](../start/import.md) | [Attività di caricamento dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"} | [Aggiorna attività dati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"}

+++

+++ Come posso identificare ed eseguire il targeting dei nuovi destinatari?

Eseguire la query sul campo **[!UICONTROL Created date]** per selezionare i destinatari aggiunti entro un intervallo di tempo specifico.

**Flusso di lavoro di benvenuto automatizzato:** modulo di pianificazione (esecuzione giornaliera) → query (selezione di nuovi destinatari) → deduplicazione (facoltativa) → consegna (messaggio di benvenuto) → Aggiorna dati (contrassegna come &quot;benvenuto&quot;).

**Avanzate:** utilizza funzioni di aggregazione per identificare dinamicamente le aggiunte recenti.

**Argomenti correlati:**

[Attività query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"} | [Utilizzo di aggregati](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html){target="_blank"}

+++

+++ Come si utilizzano le attività del flusso di lavoro?

Quattro categorie di attività:

**Targeting:** Query, Split, Deduplication, Enrichment, Intersection, Union, Exclusion (definisci/perfeziona pubblico)\
**Controllo di flusso:** modulo di pianificazione, attesa, test, fork, AND-join, OR-join, Jump (gestione logica/tempistica)\
**Azione:** Consegna, Aggiorna dati, Caricamento/estrazione dati, Codice JavaScript (eseguire operazioni)\
**Evento:** segnale esterno, raccoglitore file, trasferimento HTTP (reagisce ai trigger)

Trascina dalla palette, fai doppio clic per configurare, connetti con le transizioni.

**Argomenti correlati:**

[Attività di targeting](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"} | [Controllo del flusso](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"} | [Attività azione](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html){target="_blank"}

+++

+++ Quali sono le best practice per i flussi di lavoro?

**Progettazione:** Cancella nomi, aggiungi etichette/descrizioni, raggruppa attività correlate, suddividi processi complessi in flussi di lavoro più piccoli\
**Prestazioni:** Limitare le dimensioni delle query, utilizzare tabelle temporanee, pianificare l&#39;esecuzione fuori picco, evitare cicli eccessivi\
**Gestione degli errori:** Aggiungere percorsi di errore, configurare avvisi, eseguire test con esempi, esaminare i registri\
**Manutenzione:** archiviazione di flussi di lavoro obsoleti, controllo della versione, complessità limitata (&lt;20 attività), utilizzo di modelli\
**Sicurezza:** Applica le autorizzazioni, pulisci i dati temporanei, usa le variabili senza valori hardcoded

**Argomenti correlati:**

[Guida alle best practice per i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"} | [Monitorare i flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

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

[Cambia lingua nell&#39;interfaccia utente di Campaign Web](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [Introduzione alla console client di Campaign](connect.md)

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

[Documentazione del Pannello di controllo Campaign](https://experienceleague.adobe.com/it/docs/control-panel/using/control-panel-home){target="_blank"} | [Video tutorial di Pannello di controllo Campaign](https://experienceleague.adobe.com/en/docs/control-panel-learn/tutorials/control-panel-overview){target="_blank"}

+++

+++ Qual è la procedura per la delega del dominio?

Un sottodominio è una divisione del dominio che può essere utilizzata per isolare i brand o vari tipi di traffico (messaggi transazionali, informazioni di marketing, ecc.).

>[!NOTE]
>
>In qualità di utente di Managed Cloud Services, contatta Adobe per delegare i sottodomini ad Adobe.

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

[Tracciare e monitorare le consegne](../send/tracking.md) | [Configurare i collegamenti tracciati](../send/tracked-links.md) | [Tracciamento dei test](../send/testing-tracking.md)

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

Campaign v8 supporta le connessioni Federated Data Access (FDA) ai principali sistemi di database aziendali (database cloud, database aziendali, data warehouse, piattaforme di big data).

Le versioni del database supportate e i requisiti di connessione variano. Controlla la [Matrice di compatibilità](compatibility-matrix.md) per la versione di Campaign v8 per confermare il supporto per database specifici e garantire la licenza corretta per i connettori FDA.

Vedi [Configurare le connessioni FDA](../connect/fda.md)

+++

+++ Adobe Campaign può integrarsi con i sistemi CRM?

Sì. Campaign fornisce connettori CRM nativi per la sincronizzazione bidirezionale con i principali sistemi CRM. Sincronizza dati di contatto, lead, account, registri di consegna, dati di tracciamento e metriche di coinvolgimento. Supporta modalità di sincronizzazione pianificate, manuali e in tempo reale (tramite API).

Utilizza l’assistente del connettore di gestione delle relazioni con i clienti di Campaign per mappare i campi, selezionare le tabelle e pianificare la sincronizzazione. Controllare [Matrice di compatibilità](compatibility-matrix.md) per le versioni di CRM supportate.

**Argomenti correlati:**

[Configurazione connettore CRM](../connect/crm.md) | [Attività CRM per flussi di lavoro](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html){target="_blank"}

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

Ulteriori informazioni in [Installare e configurare la console client](connect.md)

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

Campaign offre diverse opzioni di reporting in base alle tue esigenze e competenze tecniche: rapporti incorporati, analisi descrittive, rapporti personalizzati nella console client e cubi.

**Opzioni di reporting:**

* **Rapporti incorporati** - Rapporti di consegna, campagne e tracciamento pronti all&#39;uso accessibili dalla scheda **[!UICONTROL Reports]**
* **Analisi descrittiva** - Rapporti statistici rapidi su qualsiasi dato con un&#39;interfaccia guidata
* **Rapporti personalizzati** - Rapporti avanzati creati da utenti tecnici tramite l&#39;editor di rapporti
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

Utilizza la console client per creare rapporti personalizzati avanzati con funzionalità di analisi complesse.

Nella console client puoi effettuare le seguenti operazioni:

* Creare report complessi utilizzando query SQL e calcoli personalizzati
* Creare rapporti su più pagine con grafici, tabelle e tabelle pivot
* Progettare la formattazione condizionale e il contenuto dinamico
* Accedere al modello dati completo di Campaign e ai database esterni (FDA)

Scopri come [creare rapporti personalizzati (console client)](../reporting/custom-reports.md)

+++

+++ Cos’è un cubo e come posso utilizzarlo per il reporting?

I cubi sono strutture di dati multidimensionali che consentono agli utenti aziendali di esplorare e analizzare i dati di Campaign tramite tabelle pivot senza competenze tecniche. Considerali come modelli di dati preconfigurati che semplificano la generazione di rapporti complessi. Questo strumento di reporting è disponibile sia nella console client che nell’interfaccia utente web di Campaign.

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

**Analisi avanzata:**

* Accedere alle risposte al sondaggio dalla scheda **[!UICONTROL Responses]** ed esportare i dati
* Utilizza l&#39;attività **[!UICONTROL Survey responses]** nei flussi di lavoro per eseguire il targeting dei destinatari in base alle loro risposte
* Combina i dati dei sondaggi con altri dati di Campaign per la segmentazione e la personalizzazione
* Creare rapporti e cubi personalizzati per l’analisi di sondaggi multidimensionali

**Argomenti correlati:**

[Introduzione ai sondaggi](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [Report sondaggi](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ Come posso condividere l’accesso ai miei report?

Controlla la visibilità dei rapporti tramite le autorizzazioni per le cartelle e i diritti denominati in Campaign.

**Metodi di controllo degli accessi:**

* **Autorizzazioni cartella** - Posiziona i report in cartelle con accesso appropriato per i gruppi di utenti
* **Diritti denominati** - Assegna i diritti per visualizzare, creare o modificare i report
* **Contesto di visualizzazione** - Definisci dove vengono visualizzati i report (cartella dei report, schede della campagna, schermate di consegna)

**Configurazione:** Salvare il report in una cartella specifica → Configurare l&#39;accesso alla cartella per i gruppi di operatori → Definire le proprietà del report e il contesto di visualizzazione.

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

Il modello dati di Campaign è una struttura di database relazionale basata su schema costituita da tabelle integrate (destinatari, consegne, campagne) che possono essere estese in base alle esigenze aziendali.

**Concetti chiave:** schemi (definizioni XML), tabelle incorporate, collegamenti (relazioni), enumerazioni (elenchi di valori), estensioni (campi/tabelle personalizzati).

**Schemi principali:** destinatario (`nms:recipient`), consegna (`nms:delivery`), flusso di lavoro (`xtk:workflow`), campagna (`nms:operation`), registri di tracciamento.

Comprendere il modello dati è essenziale per flussi di lavoro, query, estensioni di schema e integrazioni.

**Argomenti correlati:**

[Modello dati campagna](../dev/datamodel.md) | [Best practice per i modelli di dati](../dev/datamodel-best-practices.md)

+++

+++ Come si utilizzano gli schemi di Campaign?

Gli schemi definiscono la struttura dati di Campaign in formato XML, specificando la struttura della tabella, le proprietà dei campi, le relazioni, gli indici e il controllo degli accessi.

**Utilizzo degli schemi:**

* **Visualizza:** Accesso tramite **[!UICONTROL Administration > Configuration > Data schemas]**
* **Estendi:** crea schemi di estensione (ad esempio, `cus:recipient`) per aggiungere campi personalizzati senza modificare gli schemi di base
* **Crea:** Crea nuove tabelle per dati specifici dell&#39;azienda
* **Aggiornamento:** Applica modifiche tramite **[!UICONTROL Tools > Advanced > Update database structure]**

**Utilizzi comuni:** aggiungere campi personalizzati alla tabella dei destinatari, creare tabelle personalizzate, definire relazioni e implementare modelli specifici per l&#39;azienda.

**Importante:** non modificare mai direttamente gli schemi incorporati. Utilizza sempre gli schemi di estensione per compatibilità con l’aggiornamento.

**Argomenti correlati:**

[Introduzione agli schemi](../dev/schemas.md) | [Estendere uno schema](../dev/extend-schema.md)

+++

+++ Come si utilizza una tabella dei destinatari personalizzata?

Utilizza una tabella dei destinatari personalizzata quando esegui il targeting di account B2B, dati di abbonati separati, sistemi esterni o architetture multi-brand invece della tabella dei destinatari standard.

**Implementazione:** crea uno schema personalizzato con campi obbligatori (e-mail, chiave primaria, esclusioni) → Configura le mappature di destinazione → Aggiorna i modelli di consegna → Adatta flussi di lavoro/query.

**Considerazioni chiave:** deve includere i campi di consegna richiesti, i flussi di lavoro/moduli devono essere adattati e i test critici prima della migrazione di produzione.

**Best practice:** estendere prima la tabella dei destinatari standard. Utilizza le tabelle personalizzate solo quando è veramente necessario a causa di una maggiore complessità.

**Argomenti correlati:**

[Tabella dei destinatari personalizzata](../dev/custom-recipient.md) | [Mappature di destinazione](../audiences/target-mappings.md)

+++

+++ Quali sono le best practice per definire le query in Campaign?

L’editor delle query di Campaign crea visivamente le query del database senza SQL, utilizzandole nelle attività del flusso di lavoro, nel targeting della consegna, negli elenchi, nei rapporti e nei filtri.

**Best practice:**

* Inizia semplice: genera in modo incrementale, verifica ogni passaggio
* Utilizzare dimensioni filtro: sfruttare le relazioni tra tabelle
* Ottimizza le prestazioni: indicizza i campi interrogati, evita calcoli complessi
* Riutilizzare i filtri predefiniti per coerenza
* Eseguire prima il test con campioni di piccole dimensioni
* Documenta query complesse

**Pattern comuni:** i messaggi di apertura della consegna di Target, i contatti inattivi, i segmenti per comportamento, escludono i destinatari precedenti.

**Accesso:** **[!UICONTROL Tools > Generic query editor]** per esplorazioni ad hoc.

**Argomenti correlati:**

[Editor query](../start/query-editor.md) | [Attività query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}

+++

+++ Come posso importare un pacchetto di dati?

Importa pacchetti tramite **[!UICONTROL Tools > Advanced > Import package]** nella console client. I pacchetti contengono configurazioni di Campaign (schemi, flussi di lavoro, tipologie) e dati per la distribuzione tra le istanze.

**Tipi di pacchetto:** pacchetto utente (configurazioni personalizzate), pacchetto piattaforma (fornito da Adobe), pacchetto dati (dati effettivi).

**Best practice:** Esegui prima il test in sviluppo, esegui un backup prima dell&#39;importazione ed esporta dalla stessa/precedente versione.

Ulteriori informazioni in [Utilizzare i pacchetti dati](../dev/packages.md)

+++

+++ Dove posso trovare l’elenco delle API di Campaign v8?

Campaign v8 fornisce API SOAP (operazioni della console client), API REST (integrazioni moderne) e API JavaScript (script del flusso di lavoro).

**Utilizzi comuni:** integrazione con CRM/ERP, automazione di campagne, sincronizzazione di dati, creazione di soluzioni di monitoraggio, creazione di interfacce esterne.

**Accesso:** [Documentazione API di Campaign v8](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=it){target="_blank"}

+++


+++ Come si monitorano i flussi di lavoro dall’API?

Le API di Campaign consentono di controllare in modo programmatico i flussi di lavoro: avvio, pausa/ripresa, arresto, stato della query, recupero dei registri, monitoraggio dell’avanzamento dell’attività.

**Endpoint API:** `POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

**Comandi:** `{"method":"start"}`, `{"method":"pause"}`, `{"method":"resume"}`, `{"method":"stop"}`

**Casi d&#39;uso:** creare dashboard di monitoraggio, implementare avvisi automatici, orchestrare da scheduler esterni, creare dipendenze tra istanze, generare report personalizzati.

**Best practice:** combina il monitoraggio API con l&#39;audit trail per una governance completa.

Vedi [Flussi di lavoro di controllo tramite API](../dev/api/controlling-a-workflow.md)

+++

+++ Come posso aggiornare la struttura del database?

Dopo aver modificato gli schemi (aggiunta di campi, creazione di tabelle, modifica dei tipi di dati), aggiornare la struttura del database fisico tramite **[!UICONTROL Tools > Advanced > Update database structure]** per applicare le modifiche.

**Se necessario:** aggiunta di campi, creazione/estensione di tabelle, modifica delle proprietà dei campi, aggiunta/rimozione di collegamenti, creazione di indici.

**Importante:** esegui prima il backup, verifica in fase di sviluppo, pianifica i tempi di inattività per modifiche di grandi dimensioni, coordinati con il supporto di Adobe (Managed Cloud Services). Tieni presente che alcune modifiche potrebbero causare la perdita di dati.


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

Campaign elimina automaticamente tutti i dati collegati a un interessato: il profilo del destinatario, i registri di consegna e di tracciamento, i dati personalizzati con relazioni di proprietà e la cronologia degli abbonamenti.

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
* **[Orario di lavoro della community di Campaign](https://experienceleague.adobe.com/){target="_blank"}** - Partecipa a sessioni live con esperti Adobe

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
* **[Domande frequenti su versioni e aggiornamenti](upgrades.md)** - Controlla la versione e scopri gli aggiornamenti

### Supporto e servizi

Chiedi aiuto al team di supporto di Adobe e gestisci la tua istanza.

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** - Registrazione dei casi di supporto e gestione degli utenti
* **[Assistenza clienti Adobe](https://helpx.adobe.com/it/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - Contatta il team di supporto
* **[Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it){target="_blank"}** - Gestisci le impostazioni dell&#39;istanza Campaign
* **[Stato del sistema](https://status.adobe.com/){target="_blank"}** - Verifica lo stato dei servizi Adobe

### Formazione e certificazione

Migliora le tue competenze con i programmi ufficiali di formazione e certificazione di Adobe.

* **[Guida di Experience League](https://experienceleague.adobe.com/en/browse/campaign/campaign-v8){target="_blank"}** - Risorse di aiuto per Campaign v8 (interfaccia utente Web e console CLient)
* **[Adobe Digital Learning Services](https://learning.adobe.com/){target="_blank"}** - Corsi ufficiali con istruttore e autoapprendimento
* **[Certificazione Adobe Campaign](https://experienceleague.adobe.com/docs/certification/program/overview.html){target="_blank"}** - Convalida la tua esperienza con la certificazione professionale
* **[Percorsi di apprendimento Experience League](https://experienceleague.adobe.com/?lang=en#dashboard/learning){target="_blank"}** - percorsi di apprendimento guidato

### Altre risorse utili

* **[Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=it){target="_blank"}** - Riferimento per utenti di Classic v7
* **[Documentazione dell&#39;interfaccia utente Web di Campaign](https://experienceleague.adobe.com/it/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - Nuova guida dell&#39;interfaccia Web
* **[Best practice per il recapito dei messaggi](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=it){target="_blank"}** - Ottimizzare la consegna dei messaggi e-mail

