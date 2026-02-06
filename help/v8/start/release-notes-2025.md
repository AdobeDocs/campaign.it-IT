---
title: Note sulla versione di Campaign v8 (console) 2025
description: Elenco di funzioni e miglioramenti introdotti con le versioni di Campaign v8 2025
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: 981fa2029528cac5806da7c39aec3a2e6de0bf56
workflow-type: tm+mt
source-wordcount: '3472'
ht-degree: 33%

---

# Note sulle versioni 2025 {#2025-rn}

In questa pagina sono elencate le nuove funzionalità, i miglioramenti e le correzioni inclusi nelle **versioni di Campaign v8 2025**. Per la versione più recente, consulta [questa pagina](release-notes.md).

Per qualsiasi nuova implementazione o aggiornamento a un ambiente esistente, installa [la versione più recente](release-notes.md).

>[!BEGINSHADEBOX]

**In questa pagina**

* [Versione 8.8.2](#release-8-8-2)
* [Versione 8.6.5](#release-8-6-5)
* [Versione 8.6.4](#release-8-6-4)
* [Versione 8.7.4](#release-8-7-4)
* [Versione 8.7.3](#release-8-7-3)


>[!ENDSHADEBOX]

## Versione 8.8.2 {#release-8-8-2}

_9 ottobre 2025_

>[!AVAILABILITY]
>
>Questa versione è in **disponibilità limitata** (LA).

### Nuove funzioni {#features-8-8-2}

Il **nuovo connettore di invio SMS** è ora disponibile per [distribuzioni FFDA di Campaign](../architecture/enterprise-deployment.md). Consulta la [documentazione dettagliata](../send/sms/sms.md).

Questa versione include anche una serie di funzionalità disponibili con l’interfaccia utente web di Campaign:

* [Arricchimento del profilo nei messaggi transazionali](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Funzionalità multilingue per messaggi transazionali, notifiche push e SMS](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}

Consulta le [note sulla versione](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=it){target="_blank"} dell’interfaccia utente di Campaign Web

### Correzioni {#fixes-8-8-2}

<!--
* Fixed an issue which prevented dynamic reporting from being available for transactional messages.
-->
* È stato risolto un problema che poteva causare un errore nel flusso di lavoro di pulizia del database. (NEO-87949)
* È stato risolto un problema in Marketing distribuito a causa del quale i dati di tracciamento non venivano registrati per le consegne di campagne collaborative. (NEO-86836)
<!--
* Issue SMS2.0 with FFDA Continuous Deliveries (NEO-88785)
-->
* È stato risolto un problema che poteva impedire il corretto funzionamento della personalizzazione nei frammenti. (NEO-88161)
* È stato risolto un problema, dopo la migrazione al nuovo connettore ODBC Redshift, che poteva causare un errore dell’attività Split workflow con errori SQL. (NEO-87466)
* È stato risolto un problema che poteva causare conteggi di esclusione non accurati nei flussi di lavoro. (NEO-89207)
* È stato risolto un problema che poteva causare indicatori di clic imprecisi per le notifiche push. (NEO-89503)
* È stato risolto un problema a causa del quale i registri di consegna SMS non venivano aggiornati correttamente, impedendo la creazione di rapporti di stato precisi in Adobe Campaign. (NEO-88479)
* È stato risolto un problema a causa del quale le virgolette francesi non venivano convertite correttamente in virgolette inglesi nel contenuto della consegna. (NEO-89631)
* È stato risolto un problema a causa del quale Real-Time Server restituiva un codice di risposta errato per token IMS non validi. (NEO-87428)
* È stato risolto un problema a causa del quale le statistiche di consegna per E-mail e SMS non venivano ricalcolate completamente, causando indicatori di successo imprecisi. (NEO-88106)
* È stato risolto un problema relativo al nuovo connettore di invio SMS a causa del quale i registri di consegna non assegnavano correttamente lo stato di consegna per un piccolo sottoinsieme di messaggi. (NEO-89581)
* È stato risolto un problema relativo al nuovo connettore di invio SMS a causa del quale le consegne delle metriche di successo non venivano aggiornate correttamente sui server marketing e mid. (NEO-89850)
* È stato risolto un problema di sincronizzazione tra le istanze Real-Time e Marketing che causava registri di tracciamento mancanti e rapporti errati. (NEO-90247)
* È stato risolto un problema di arricchimento del flusso di lavoro che poteva causare errori durante la selezione dei campi tra due collegamenti 1-N consecutivi negli schemi personalizzati. (NEO-87682)

## Versione 8.8.1 {#release-8-8-1}

_giovedì 9 luglio 2025_

### Nuove funzioni {#features-8-8-1}

Precedentemente rilasciata per un piccolo gruppo di clienti, la seguente funzionalità è ora disponibile per tutti gli ambienti FDA di Campaign:

* **Nuovo connettore di invio SMS** - Il connettore di invio SMS è stato modernizzato e migliorato per abilitare le connessioni SMPP in modalità ricetrasmettitore, abilitare le connessioni SMPP permanenti e garantire una migliore compatibilità. È ora disponibile un nuovo account esterno SMS per tutte le nuove implementazioni SMS. Le implementazioni esistenti sono ancora supportate, tuttavia si consiglia di passare a questo nuovo connettore moderno ed esteso. Contatta Adobe per passare al nuovo connettore. [Ulteriori informazioni](../send/sms/sms.md)

  >[!NOTE]
  >
  >Questa funzionalità è **non** disponibile per [distribuzioni FFDA di Campaign](../architecture/enterprise-deployment.md).

<!-- (from ACC rn, aleady in the product, to remove?) -->

<!-- * **Enrichment in transactional messages** (to remove?) -->

<!--
* **Multilingual delivery creation** in the Web UI - You can now send multiple email deliveries in different languages in Adobe Campaign Web User Interface. The Multilingual delivery feature allows you to choose the default language of your delivery as well as the different languages in which the delivery can be sent. You can also preview these deliveries in the languages you have chosen. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html)

ACC - Multilingual deliveries - Starting Campaign Web User interface April release, you will be able to send multiple email deliveries in different languages, and access the related dynamic reports. This capability will only be available in Adobe Campaign Web User Interface at the end of April, and require a server update to Campaign v8.7.4.
-->

<!--
*  **Visual fragments** in the Web UI - You can now create, use and archive content fragments. Visual fragments are pre-defined visual blocks that you can reuse across multiple email deliveries, or in content templates. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/content/manage-reusable-content/fragments/fragments.html){target="_blank"}

(already available in console and web, to remove?) 
web - * Visual fragments - You can now archive visual content fragments. Learn more
-->

<!--
* **Delivery alerting** in the Web UI - The Delivery alerting feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html){target="_blank"}
-->

<!--
* **Landing pages improvements**  in the Web UI- The following improvements to landing pages are now available:

    * You can now reference a default subscription/unsubscription landing page when configuring a service. When designing an email, if you define a link to that landing page, users submitting the landing page form are automatically subscribed to or unsubscribed from this service. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/audiences/work-with-services/manage-services.html#create-service){target="_blank"}
    * A new option in the landing page configuration allows anonymous visitors to access the landing page. If you unselect this option, only identified users can access and submit the form. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#create-landing-page){target="_blank"}
    * A new option in the landing page configuration allows to store additional internal data when the landing page is being submitted. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#create-landing-page){target="_blank"}
    * A new option enables to use a landing page for several services, making it dynamic. When adding a link to an email, if you select a dynamic landing page, you can select any service. If you select a landing page that has a specific service associated, this service will be automatically used (you cannot select another one). [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#define-actions-on-form-submission){target="_blank"}
    * Conditional content is now supported in landing pages. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html){target="_blank"}
    * You can link a landing page to a service, and send a confirmation message when users validate it. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html#lp-message){target="_blank"}
    * You can add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#captcha){target="_blank"}

web - * **Subscriptions with Landing pages** - You can now link a landing page to a service, and send a confirmation message when users validate it. [Learn more](../landing-pages/lp-content.md#lp-message){target="_blank"}.
Web - * **Captcha in landing pages** - You can now add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](../landing-pages/create-lp.md#captcha)
-->

<!--
* (from ACC rn, already in product, to remove?) **Rich Push Notification (GA)** - You can now send rich push notifications. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. With this version, a set of templates for rich push notifications are now available for your iOS and Android apps. [Read more](../send/rich-push-android.md). 
ACC * Rich Push Notification templates - You can now send rich push notifications via Android. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. Read more.
-->

Precedentemente rilasciata in Disponibilità limitata, la seguente funzionalità è ora disponibile **su richiesta**:

<!--
* **Dynamic Reporting** - You can now access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Dynamic reporting is also available for multilingual email deliveries and transactional messages. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html){target="_blank"}

ACC **Dynamic Reporting for Transactional messages** - You can now monitor your transactional messages in the Dynamic Reporting user interface. These reports provide the ability to the marketer to view the all the reporting metrics and dimensions of transactional messages, breakdown of deliveries sent through a template in real time. [Read more](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}
ACC - Dynamic Reporting - As a Campaign Standard migrated user, you can access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Read more
* **Dynamic Reporting for Multilingual** - Dynamic reporting is now available for multilingual email deliveries. For more information, refer to the [detailed documentation](../reporting/global-reports.md).
-->

* **API REST** - È ora possibile utilizzare le API REST per creare integrazioni per Adobe Campaign e creare il proprio ecosistema interfacciando Adobe Campaign con il pannello di tecnologie utilizzato. L’API REST per la messaggistica transazionale è disponibile anche per il canale SMS. Quando nel payload sono presenti sia e-mail che telefono cellulare, puoi utilizzare il campo “wishedChannel” per specificare il canale. Se non viene fornito, l’e-mail verrà utilizzata per impostazione predefinita a meno che wishedChannel non richieda esplicitamente l’invio di SMS. Per le e-mail sono disponibili anche API transazionali basate su eventi. [Ulteriori informazioni](../dev/api/get-started-apis.md)

  >[!NOTE]
  >
  >Questa funzionalità è **non** disponibile per [distribuzioni FFDA di Campaign](../architecture/enterprise-deployment.md).

* **Annullamento iscrizione a mailing list con un solo clic** - Con i principali ISP che richiedono ai mittenti di consentire ai destinatari di rinunciare istantaneamente con un solo clic, ora puoi abilitare l&#39;intestazione Annullamento iscrizione a mailing list con un solo clic nell&#39;interfaccia utente, direttamente dal modello e-mail o dalle proprietà di consegna. Questa opzione è attivata per impostazione predefinita. [Ulteriori informazioni](../send/email-parameters.md#one-click-list-unsubscribe)

<!--
ACC - Rest APIs - As a Campaign Standard migrated user, you can use Rest APIs to create integrations for Adobe Campaign and build your own ecosystem by interfacing Adobe Campaign with the panel of technologies that you use. Read more
* **SMS REST API support (LA)** - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS. For more information, refer to the [detailed documentation](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target=_blank}.
ACC - SMS REST API support - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS.
ACC * **Transactional messaging REST APIs** - Event-based Transactional APIs are now available for Emails. [Read more](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}
-->

Oltre alle funzioni elencate in precedenza, questa versione include anche una serie di funzionalità disponibili con l’interfaccia utente web di Campaign:

* [Creazione consegna multilingue](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html#multilingual-delivery){target="_blank"}
* [Avvisi di consegna](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html){target="_blank"}
* [Miglioramenti alle pagine di destinazione](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/get-started-lp.html){target="_blank"}
* [Reporting dinamico](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"} (su richiesta)
* [Branding centralizzato](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html){target="_blank"} (su richiesta, nuove implementazioni)

Consulta le [note sulla versione](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=it){target="_blank"} dell’interfaccia utente di Campaign Web

### Miglioramenti generali {#improvements-8-8-1}

* Microsoft Fabrics è ora supportato come database esterno con Federated Data Access (FDA) di Adobe Campaign. [Ulteriori informazioni](../config/external-accounts.md#transfer-data-external-accounts)
* Campaign v8 ora supporta Android 15 e iOS 18 per le notifiche push. [Ulteriori informazioni](../start/compatibility-matrix.md#MobileSDK)
* I database cloud sono ora supportati in aggiunta ai database locali per il tunneling Secure Virtual Private Network. [Ulteriori informazioni](../config/enhanced-security.md#vpn-databases)
* Nella sezione &quot;Traffico in ingresso&quot; del connettore SMS 2.0 è stato aggiunto un nuovo set di campi &quot;ID provider&quot;. [Ulteriori informazioni](../send/sms/smpp-external-account.md#incoming-traffic)
* I destinatari per i quali è stata annullata l’iscrizione tramite il metodo &quot;mailto&quot; List-Unsubscribe non vengono più messi in quarantena. Se per la consegna non è stato definito alcun servizio, viene annullato l’abbonamento al servizio associato alla consegna oppure viene inviato al inserisco nell&#39;elenco Bloccati di consegna del profilo (sezione &quot;Non contattare più&quot; del profilo). [Ulteriori informazioni](../send/quarantines.md)
* Una versione rinnovata del rapporto di rendering della casella in entrata è ora disponibile nella console client di Adobe Campaign.
* Il file `setup-client.exe` è stato sostituito con un file `ac-client.msi`, che fornisce agli amministratori un metodo più semplice per eseguire aggiornamenti di massa senza richiedere l&#39;intervento dell&#39;utente.

### Correzioni {#fixes-8-8-1}

* È stato risolto un problema che impediva la ricezione delle risposte automatiche a causa di un periodo di validità non valido in SMS 2.0. Questo garantisce il corretto recapito dei messaggi dopo la migrazione. (NEO-88088)
* È stato risolto un problema in SMS 2.0 a causa del quale alcuni campi della tabella `inSms` non venivano aggiornati correttamente, garantendo l&#39;inserimento accurato dei dati per le funzionalità SMS. (NEO-87906)
<!--
* NOOOO Addressed delivery preparation failures for IndiGo Aviation after upgrading to v7.4.2. This fix resolves personalization and deduplication-related errors, enabling smooth delivery workflows. (NEO-87693)
* NOOOO Corrected Redshift database function definitions in version 8.6.4, ensuring proper execution of functions like `AddDays`, `AddHours`, `AddMinutes`, and `AddSeconds`. (NEO-87305)
* Provided a silent installation mechanism for the client console to facilitate mass upgrades without user intervention. This resolves challenges with manual installations. (NEO-69772)
-->
* Sono stati corretti gli errori del flusso di lavoro di pulizia del database a causa di riferimenti di colonna mancanti o errati nelle query SQL. In questo modo i registri e i dati dei visitatori verranno eliminati correttamente. (NEO-86813)
* È stato risolto un problema che causava l’assenza di date evento nei registri di consegna. Questa correzione assicura una popolazione precisa delle date degli eventi, fondamentale per i trigger e i flussi di lavoro pianificati. (NEO-86708)
* Sono stati risolti i problemi di inserimento del registro di consegna SMS in SMS 2.0, garantendo la registrazione corretta nella tabella `nmsBroadLogMid`. (NEO-86556)
* Sono stati risolti i problemi di estrazione dei file con la modalità di consegna esterna nei modelli di Direct Mail, garantendo compatibilità e funzionalità. (NEO-86520)
* Sono stati risolti i problemi di elaborazione delle consegne che coinvolgevano il routing diviso tra più istanze MID, garantendo aggiornamenti accurati dello stato di consegna e la velocità effettiva. (NEO-86500)
* Sono stati corretti i dati di tracciamento mancanti nei report dinamici post-migrazione da Campaign Standard a Campaign v8, garantendo una generazione accurata di rapporti per i registri di tracciamento della consegna. (NEO-86419)
* Sono stati risolti i problemi di attivazione dei flussi di lavoro che venivano eseguiti due volte, causando violazioni di chiave duplicate. Questa correzione garantisce la corretta gestione ed esecuzione degli eventi. (NEO-86154)
* Sono stati risolti i problemi di compatibilità con le funzioni SQL OOTB Redshift dopo la distribuzione, garantendo la corretta esecuzione di funzioni come `GetDate()` nei flussi di lavoro. (NEO-85834)
* Sono stati risolti i problemi di rendering nelle build e-mail in cui le immagini scomparivano quando gli URL venivano allegati. Questa correzione assicura la corretta visualizzazione delle immagini nelle anteprime della casella in entrata. (NEO-85716)
* È stato corretto il rendering delle virgolette chiuse in WebUI, per garantire una visualizzazione accurata dei caratteri nelle consegne e-mail. (NEO-85687)
* È stata corretta la funzionalità di collegamento alla pagina speculare, che garantiva la corretta navigazione tra le varianti di lingua all’interno delle pagine specchiate. (NEO-85625)
* Risoluzione dei problemi relativi al formato della data nei selettori di date dell&#39;app Web, garantendo la compatibilità con i formati di data giapponesi (`yyyy-mm-dd`). (NEO-85234)
* Sono stati risolti i problemi del flusso di lavoro di post-elaborazione con impostazioni di routing alternative nel midsourcing, garantendo la corretta esecuzione del flusso di lavoro. (NEO-85111)
* È stata migliorata la velocità effettiva di consegna di Android durante l’utilizzo delle ondate, garantendo che i componenti di consegna vengano elaborati nell’ordine corretto in base alla pianificazione. (NEO-84324)
* Sono stati corretti gli errori di preparazione della consegna a causa di errori di elaborazione nulli nella funzione `to_varchar`, garantendo la fluidità dei lanci delle campagne. (NEO-84108)
* Risoluzione dei problemi di connessione SFTP causati dalle versioni obsolete di `libcurl` e `libssh2`, per garantire la compatibilità con i server SFTP ospitati da Azure. (NEO-84038)
* Sono stati risolti i problemi del connettore FDA di Snowflake che interessavano errori di autenticazione della coppia di chiavi, garantendo il successo delle connessioni al database. (NEO-84024)
* Sono stati risolti i problemi di funzionalità delle regole di tipologia, garantendo la corretta applicazione delle regole di pressione nelle consegne PUSH. (NEO-84010)
* Sono stati risolti gli errori di query BigQuery causati da confronti di date e marche temporali non corrispondenti dopo l’aggiornamento, garantendo la compatibilità con le condizioni di filtro. (NEO-83826)
* È stato risolto un problema che causava un errore nelle attività di consegna durante la ripresa delle consegne in pausa a causa di errori di personalizzazione. Questa correzione garantisce flussi di lavoro di consegna più fluidi e impedisce errori relativi alle attività in pausa. (NEO-83809)
* È stato risolto un problema in FFDA, quando si utilizzava l’opzione &quot;target record load query&quot; (query di caricamento record target). È stato aggiunto il supporto per le clausole &quot;ordina per&quot; e &quot;dove&quot;. (NEO-83793)
* Sono stati risolti errori di consegna ricorrenti causati dalla scrittura di valori Null in colonne non nullable nella tabella broadLogRcp. Questa correzione migliora l’affidabilità della consegna e impedisce gli errori durante le campagne live. (NEO-83729)
* È stato risolto un problema a causa del quale gli indirizzi di seed venivano duplicati durante la preparazione della consegna, causando discrepanze nel conteggio dei messaggi. Questa correzione assicura un targeting accurato e impedisce errori di duplicazione. (NEO-83703)
* È stato risolto un problema critico a causa del quale le consegne di produzione venivano inviate dopo il periodo di validità, causando potenzialmente problemi legali. Le consegne ora rispettano rigorosamente i periodi di validità definiti. (NEO-83350)
* È stato risolto un problema di spazio che si verificava durante il caricamento di volumi di dati di grandi dimensioni nelle tabelle di Teradata. Questa correzione ottimizza l’elaborazione dei dati e risolve gli errori intermittenti negli ambienti di produzione. (NEO-83252)
* È stato risolto un errore del flusso di lavoro tecnico relativo agli errori SendMetricsToNewRelic che causava ritardi nell’elaborazione degli eventi RT. Questa correzione garantisce un’esecuzione più fluida del flusso di lavoro e impedisce i backlog di eventi. (NEO-83143)
* È stato risolto un errore del flusso di lavoro di pulizia del database causato da problemi di conversione da ID a UUID nelle istanze di interazione FFDA. Questo aggiornamento garantisce le operazioni di pulizia corrette e riduce il carico del sistema. (NEO-83138)
* Sono stati risolti gli errori di consegna causati da vincoli sulle lunghezze dei nomi interni dei membri seed. Questa correzione consente di usare nomi interni più lunghi senza influire sulla personalizzazione della consegna. (NEO-83044)
* È stato risolto un problema che causava il blocco delle consegne nella personalizzazione in sospeso a causa di errori casuali. Questo aggiornamento garantisce processi di personalizzazione più fluidi e un’esecuzione affidabile della consegna. (NEO-82781)
* È stato risolto un problema che impediva la revisione delle proposte di offerta nella console a causa di errori API e lentezza. Questa correzione migliora i tempi di risposta dell’interfaccia utente e garantisce la funzionalità corretta delle offerte. (NEO-82742)
* Sono stati risolti gli arresti anomali intermittenti nella console Adobe Campaign quando si utilizzano oggetti di consegna personalizzati. Questa correzione assicura stabilità e affidabilità durante l’utilizzo di flussi di lavoro personalizzati. (NEO-82675)
* Sono stati risolti gli errori di elaborazione e flusso di lavoro lenti segnalati dopo la migrazione da v7 a v8. Questo aggiornamento ottimizza i flussi di lavoro delle campagne e assicura un’esecuzione tempestiva. (NEO-82665)

<!--
* Resolved an issue where sysfilters were generating incorrect SQL queries after upgrading to v8.6.3. This fix ensures proper query generation and restores sysfilter functionality. (NEO-82591)
-->

* È stato risolto un problema critico a causa del quale i processi secondari MTA si bloccavano, bloccando le consegne Push e WhatsApp. Questo aggiornamento garantisce flussi di lavoro di comunicazione più fluidi e impedisce colli di bottiglia nella consegna. (NEO-82351)
* È stato risolto un problema di migrazione dei dati a causa del quale i campi stringa delle tabelle GCP causavano errori durante gli aggiornamenti a Teradata. Questa correzione elimina la necessità di soluzioni alternative e migliora l’efficienza del flusso di lavoro. (NEO-82260)
* È stata aggiornata la logica di pulizia del database per tenere conto dei database primari nelle istanze FFDA, evitando inutili tentativi di eliminare le tabelle inesistenti. Questa correzione ottimizza le operazioni di pulizia. (NEO-81879)
* Risoluzione degli arresti anomali della console causati dall’utilizzo di flussi di lavoro secondari in combinazione con campi enum. Questa correzione assicura stabilità quando si lavora con flussi di lavoro arricchiti. (NEO-81864)
* È stato risolto un problema a causa del quale i campi di sub-affinità nelle mappature di destinazione venivano modificati in modo errato dopo la duplicazione della consegna, causando errori del flusso di lavoro. Questo aggiornamento garantisce la coerenza dei valori di sub-affinità. (NEO-81809)
* È stato aggiunto il supporto per i caratteri jolly nelle attività di trasferimento file in Adobe Campaign Classic v8, consentendo agli utenti di caricare file con nomi dinamici (ad esempio, `abc_*`) nei flussi di lavoro. (NEO-81758)
* È stata introdotta un&#39;opzione per abilitare il flag `content-available` nelle notifiche push di iOS per Adobe Campaign Classic v8. Questo miglioramento consente alle app mobili di memorizzare le notifiche nella casella in entrata e supporta gli aggiornamenti in background, affrontando i problemi di eliminazione della consegna causati dalle limitazioni APNS. (NEO-81721)

<!--
* Updated the Campaign 7.4.1 release upgrade process to require manual installation of dependencies. Documentation has been provided to guide users on installing required libraries such as `epel-release`, `java-11-openjdk-headless`, and others. (NEO-81433)
-->

* È stata aggiunta l’opzione di configurazione timeout per le connessioni BigQuery in Adobe Campaign Classic v8. Questo miglioramento consente agli utenti di regolare il periodo di timeout per le query, risolvendo i problemi con errori di query dovuti a limiti di timeout predefiniti. (NEO-81222)
* È stato risolto un problema intermittente a causa del quale gli URL della pagina speculare non riuscivano per le consegne inviate tramite account esterni di routing Split e Alternate dopo la migrazione v8. Le parti di consegna sottostanti sono ora copiate correttamente in `mirrorPageInfo`. (NEO-81105)

<!--
* Resolved an authentication failure issue with inMail caused by token expiration. Restarting the `nlserver` process now resolves the error. (NEO-80683)
-->

* È stato corretto il pulsante &quot;Accedi alla nuova interfaccia Web&quot; nella console client per puntare all&#39;URL corretto (`https://experience.adobe.com`) per le istanze di produzione. In questo modo vengono risolti i problemi relativi agli URL non validi negli ambienti di produzione. (NEO-80673)
* È stato risolto un problema nell’attività Split a causa del quale l’utilizzo di Ordinamento e Dimensione (come percentuale del segmento) causava errori SQL. La funzionalità ora funziona correttamente. (NEO-80432)
* È stato risolto un problema di arresto anomalo nei flussi di lavoro che utilizzavano `CCurlAzureBlobStorage::UploadStream`. I flussi di lavoro ora vengono eseguiti senza errori di segmentazione durante i caricamenti di Azure Blob Storage. (NEO-79598)
* È stato risolto un problema che impediva la visualizzazione delle pagine mirror dalla console client negli ambienti di produzione. I collegamenti alle pagine mirror ora funzionano correttamente sia nella vista e-mail che nella vista della console. (NEO-78946)
* È stato risolto un problema relativo al registro di consegna a causa del quale alcuni registri venivano erroneamente contrassegnati come &quot;Consegna annullata&quot; nonostante la consegna del messaggio. È stata risolta la causa principale relativa alle discrepanze tra data di contatto e data evento. (NEO-78933)
* Aggiornamento della libreria `com.google.code.gson:gson` per migliorare la sicurezza. (NEO-78299)
* Sono stati risolti gli errori di vincolo della chiave duplicata nei registri di connessione FDA (`nmsconnectionlogs`) che causavano errori del flusso di lavoro. La logica di inserimento è stata regolata per evitare ID duplicati. (NEO-78050)
* È stato risolto un problema a causa del quale gli indirizzi e-mail in quarantena venivano erroneamente contrassegnati come mobili nella tabella degli indirizzi, causando errori di analisi della consegna. La logica di riconciliazione tra gli oggetti di consegna è stata corretta. (NEO-76986)
* È stato risolto un errore di preparazione della consegna durante l’utilizzo di gruppi di controllo con un database di Oracle. La generazione della query SQL è stata corretta per garantire la compatibilità con i database Oracle. (NEO-76947)
* Sono stati risolti gli errori di consegna causati dalla creazione simultanea di cartelle durante le transizioni dei nuovi mesi. La logica di creazione della cartella di consegna è stata regolata per evitare violazioni di chiavi duplicate. (NEO-76824)
* Sono stati risolti problemi di conversione del fuso orario incoerenti negli account esterni di Teradata. Le marche temporali visualizzate ora sono allineate correttamente alle impostazioni del fuso orario configurato. (NEO-76716)
* Sono stati migliorati i flussi di lavoro di pulizia del database per gestire in modo efficiente set di dati di grandi dimensioni. È stato implementato un nuovo approccio che utilizza gli ID di riga e le variabili di binding per ottimizzare le prestazioni di eliminazione. (NEO-76439)
* È stato risolto un problema a causa del quale le consegne esterne con il canale &quot;Altro&quot; non generavano file di output. Le proprietà di consegna ora includono correttamente il percorso dei file generati. (NEO-75962)
* Sono stati corretti gli errori nel flusso di lavoro `ffdaReplicateStagingData` causati da aggiornamenti di dati di grandi dimensioni. Le impostazioni di timeout e la gestione delle dimensioni della tabella sono state ottimizzate per evitare errori del flusso di lavoro. (NEO-75643)
* È stato risolto un problema a causa del quale l’anteprima dei file di output della direct mailing causava la visualizzazione di dashboard vuoti. La dashboard ora viene visualizzata correttamente dopo le anteprime dei file. (NEO-75359)
* Sono stati migliorati gli indicatori di tracciamento per le notifiche push, in modo da includere clic e aperture. Indicatori come `@recipientClick`, `@personClick` e `@totalRecipientClick` ora tengono conto dei clic di notifica mobile. (NEO-75240)
* Sono stati corretti gli errori nei flussi di lavoro di pulizia per le consegne con stato di annullamento in sospeso esterno. La logica di recupero dei record del database è stata corretta. (NEO-74833)
* È stato risolto un problema di discrepanza di fuso orario in Russia (UTC+3:00 Mosca) dove `nlserver` tempi di output non erano corretti. La logica di sincronizzazione dell&#39;ora è stata aggiornata. (NEO-74754)
* Sono stati corretti gli errori nel flusso di lavoro `defaultMidSourcingDlvStat` causati da una sintassi SQL errata per i database MSSQL. La logica di generazione della query è stata regolata per compatibilità. (NEO-74156)
* Sono stati risolti diversi arresti anomali nel processo web. (NEO-73174)
* È stato risolto un problema che impediva il corretto funzionamento delle query BigQuery in presenza di apostrofi nelle condizioni. La logica di gestione delle query è stata aggiornata per interpretare correttamente i caratteri speciali. (NEO-72547)
* È stato risolto un problema che impediva il corretto funzionamento delle regole di tipologia con filtri di esclusione. La generazione della query SQL per la preparazione della consegna è stata corretta. (NEO-72292)
* Sono state risolte le discrepanze nelle date dell’evento e delle date di contatto per la gestione delle e-mail non consegnate. È stata migliorata la logica di gestione del fuso orario. (NEO-72277)
* Gestione migliorata dei caratteri UTF-8 convertiti in modo errato nelle consegne di direct mailing. I caratteri nascosti vengono ora elaborati correttamente per evitare errori di consegna. (NEO-72148)
* Sono stati risolti degli errori nell’attività SMS in entrata in cui i filtri causavano problemi di salvataggio. Il flusso di lavoro ora viene salvato correttamente senza generare errori. (NEO-70427)
* È stata corretta la generazione di query SQL per i criteri di idoneità raggruppati negli spazi dell’offerta. Sono state aggiunte parentesi mancanti nelle condizioni SQL per garantire un filtro corretto. (NEO-70425)

<!--
* Updated the public documentation link in the `ffdaUnicity` workflow email template to point to the correct page for key management in v8. (NEO-67996)
-->

* Sono stati corretti alcuni errori intermittenti nei flussi di lavoro di caricamento dati BigQuery causati da contenuti HTTP o da problemi di codifica dei trasferimenti. È stata migliorata la logica di gestione della connessione. (NEO-66989)

## Versione 8.6.5 {#release-8-6-5}

_sabato 25 aprile 2025_

>[!AVAILABILITY]
>
>Questa versione è in **disponibilità limitata** (LA).

### Nuove funzioni {#features-8-6-5}

**Nuovo connettore di invio SMS** - Il connettore di invio SMS è stato modernizzato e migliorato per abilitare le connessioni SMPP in modalità ricetrasmettitore, abilitare le connessioni SMPP permanenti e garantire una migliore compatibilità per gli ambienti in transizione da Adobe Campaign Standard. È ora disponibile un nuovo account esterno SMS per tutte le nuove implementazioni SMS. L’implementazione esistente è ancora supportata, tuttavia si consiglia di passare a questo nuovo connettore moderno ed esteso. [Ulteriori informazioni](../send/sms/sms.md).

### Miglioramenti generali {#improvements-8-6-5}

* Le prestazioni globali dell’applicazione sono state migliorate, nel contesto di una distribuzione Enterprise (FFDA), inclusi l’invio di bozze di consegna e la pulizia del database.

* Per aumentare la sicurezza su tutte le comunicazioni tra applicazioni, mTLS è ora supportato per le chiamate API esterne.

* Mail Transfer Agent (MTA): è stato risolto elemento secondario MTA orfano bloccato nello stato **[!UICONTROL Start pending]**.

### Correzioni {#fixes-8-6-5}

In questa versione sono stati risolti anche i seguenti problemi:

NEO-67620, NEO-71534, NEO-80245, NEO-81105, NEO-81758, NEO-81908, NEO-82351, NEO-82742, NEO-83044, NEO-83138, NEO-83350, NEO-83729, NEO-83793, NEO-83809, NEO-84038, NEO-84108, NEO-85269, NEO-86121, NEO-86556, NEO-86739

## Versione 8.7.4 {#release-8-7-4}

_venerdì 10 aprile 2025_

>[!AVAILABILITY]
>
>Questa versione è in **Disponibilità limitata** (LA). È limitata ai clienti che eseguono la migrazione **da Adobe Campaign Standard ad Adobe Campaign v8** e non possono essere distribuiti in nessun altro ambiente.
>
>In qualità di utente Campaign Standard che passa a Campaign v8, scopri di più su questa transizione nella [documentazione sull’interfaccia utente web di Campaign v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuove funzioni {#features-8-7-4}

* **Supporto API REST SMS**: l’API REST per la messaggistica transazionale è ora disponibile per il canale SMS. Quando nel payload sono presenti sia e-mail che telefono cellulare, puoi utilizzare il campo “wishedChannel” per specificare il canale. Se non viene fornito, per impostazione predefinita verrà utilizzata l’e-mail, a meno che wishedChannel non richieda esplicitamente l’SMS.

* **Consegne multilingue**: a partire dalla versione di aprile dell’interfaccia utente di Campaign Web, sarà possibile inviare più consegne e-mail in lingue diverse e accedere ai rapporti dinamici correlati. Questa funzionalità sarà disponibile nell’interfaccia utente di Adobe Campaign Web solo alla fine di aprile e richiederà un aggiornamento del server a Campaign v8.7.4.

### Correzioni {#fixes-8-7-4}

In questa versione sono stati risolti i seguenti problemi:

NEO-80245, NEO-83559

## Versione 8.7.3 {#release-8-7-3}

_14 febbraio 2025_

>[!AVAILABILITY]
>
>Questa versione è in **Disponibilità limitata** (LA). È limitata ai clienti che eseguono la migrazione **da Adobe Campaign Standard ad Adobe Campaign v8** e non possono essere distribuiti in nessun altro ambiente.
>
>In qualità di utente Campaign Standard che passa a Campaign v8, scopri di più su questa transizione nella [documentazione sull’interfaccia utente web di Campaign v8](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuove funzioni {#features-8-7-3}

* **Reporting dinamico per messaggi transazionali**: ora puoi monitorare i messaggi transazionali nell’interfaccia utente del reporting dinamico. Questi rapporti forniscono al marketer la possibilità di visualizzare in tempo reale tutte le metriche e le dimensioni del reporting dei messaggi transazionali, con l’analisi delle consegne inviate tramite un modello. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"}

* **API REST per la messaggistica transazionale**: le API transazionali basate su eventi sono ora disponibili per le e-mail. [Ulteriori informazioni](../dev/api/get-started-apis.md)

### Correzioni {#fixes-8-7-3}

In questa versione sono stati risolti i seguenti problemi:

NEO-79373, NEO-81908, NEO-83081

## Versione 8.6.4 {#release-8-6-4}

_15 gennaio 2025_

### Miglioramenti generali {#improvements-8-6-4}

* La stabilità dell’applicazione Campaign è stata migliorata durante l’analisi della consegna nel contesto di una [distribuzione Enterprise (FFDA)](../../v8/architecture/enterprise-deployment.md).
* Questa versione include meccanismi dell’architettura FFDA migliorati e rafforzati, tra cui gestione delle chiavi, staging e replica dei dati.
* Sono stati introdotti nuovi flussi di lavoro tecnici per la [distribuzione Enterprise (FFDA)](../../v8/architecture/enterprise-deployment.md). Questi flussi di lavoro replicano la consegna e i dati correlati centralizzando le richieste di replica parallela sulle tabelle corrispondenti. Il flusso di lavoro inizia con `Replicate nms`. [Ulteriori informazioni](../architecture/replication.md)
* Nelle proprietà del flusso di lavoro è ora disponibile una nuova opzione **Abilita il supervisore watchdog per mantenere il flusso di lavoro in esecuzione permanente**. Quando questa opzione è abilitata, i flussi di lavoro si riavviano automaticamente dopo che si è verificato un errore. Per impostazione predefinita, il riavvio si verifica ogni 30 secondi se il flusso di lavoro presenta ancora un errore. Per modificare questo intervallo, puoi creare una nuova opzione `XtkWorkflow_WatchdogRestartTimerTimeout` e impostare un tipo di dati interi per specificare il nuovo ritardo. Questa opzione deve essere abilitata solo nei flussi di lavoro tecnici. [Ulteriori informazioni](../../automation/workflow/workflow-properties.md#execution)

### Miglioramenti di sicurezza {#security-8-6-4}

È stata migliorata l’elaborazione delle richieste HTTP nel modulo web Apache per rafforzare la sicurezza e prevenire potenziali vulnerabilità nella gestione delle richieste. (NEO-85824)

La connessione con le soluzioni e le app Adobe tramite l’account esterno di **[!UICONTROL Adobe Experience Cloud]** è stata aggiornata per rafforzare la sicurezza.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Aggiornamenti della compatibilità {#comp-8-6-4}

Sono stati aggiunti i seguenti connettori FDA. Consulta [questa pagina](compatibility-matrix.md#FederatedDataAccessFDA).

* Databricks è ora supportato come database esterno con il Federated Data Access (FDA) di Adobe Campaign.

* È ora disponibile un nuovo connettore Amazon Redshift FDA ODBC. Offre connettività migliorata, manutenzione semplificata e compatibilità avanzata. Questa nuova versione include i seguenti miglioramenti:

   * Il nuovo connettore si basa sull’interfaccia ODBC che si allinea ai connettori FDA più recenti. Questo garantisce un supporto a lungo termine.
   * Inoltre, introduce un nuovo meccanismo di caricamento dei dati utilizzando bucket S3, che migliora in modo significativo le prestazioni.

  È comunque possibile utilizzare il connettore legacy. Se desideri provare quello nuovo, contatta il tuo rappresentante Adobe.

### Correzioni {#fixes-8-6-4}

In questa versione sono stati risolti i seguenti problemi:

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-81127, NEO-81209, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592, NEO-82640, NEO-82665, NEO-82781, NEO-82920, NEO-83081, NEO-83096, NEO-83137, NEO-83143.

