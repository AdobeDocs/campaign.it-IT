---
title: Opzioni della campagna
description: Scopri le opzioni di Campaign, dove sono memorizzate e come utilizzare le opzioni documentate per Campaign v8
feature: Architecture
role: Admin, Developer
level: Intermediate
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
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 92bab89570eca3eb13d6010db0deec74e7860c91
workflow-type: tm+mt
source-wordcount: '2849'
ht-degree: 3%
---
# Opzioni della campagna {#campaign-options}

Le opzioni sono parametri che controllano il comportamento dell’istanza Campaign, ad esempio il limite di dimensione predefinito delle immagini nelle e-mail, il numero di flussi di lavoro eseguiti contemporaneamente o il provider di indirizzamento predefinito dei modelli di consegna. Alcune opzioni sono integrate e altre vengono create quando necessario. Le opzioni disponibili dipendono dai pacchetti installati nell’istanza. Ulteriori informazioni sono disponibili in [Pacchetti incorporati](built-in-packages.md).

>[!CAUTION]
>
>Modifica solo le opzioni documentate nella documentazione di Campaign e solo come descritto. Le opzioni non documentate sono interne e non devono essere modificate. La modifica delle opzioni è riservata agli utenti esperti.

## Dove sono memorizzate le opzioni {#where-options-are-stored}

Le opzioni sono memorizzate nel database di Campaign, nella tabella **xtkOption** (schema **xtk:option**). In Campaign Explorer sono disponibili in **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**. Nell&#39;interfaccia utente di Campaign Web, sono disponibili in **[!UICONTROL Administration]** > **[!UICONTROL Options]**. Entrambi gli elenchi sono identici. Ulteriori informazioni in [Configurare le opzioni di Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options){target="_blank"}.

## Utilizzare le opzioni {#use-options}

1. In Esplora campagne, passa a **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**.
1. Seleziona l’opzione, quindi aggiornane il valore. Se l’opzione non esiste, creala con il nome esatto fornito nella documentazione.
1. Imposta un valore del tipo previsto dalla documentazione. Ad esempio, un’opzione di testo per la data di sincronizzazione del sistema di gestione delle relazioni con i clienti o un’opzione intera per il ritardo di riavvio del flusso di lavoro.

Puoi anche creare opzioni personalizzate, ad esempio per memorizzare i dati intermedi di un flusso di lavoro. Immettere un nome, selezionare il tipo di dati e impostare il valore. Ulteriori informazioni in [Configurare le opzioni di Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options#create){target="_blank"}.

Alcune opzioni contengono le credenziali. Crittografa i segreti con la funzione `cryptString`, come descritto in [Utilizzare le pagine di destinazione di Campaign e Adobe Experience Platform](../connect/ac-aep-landing-pages.md). Quando ruotate le credenziali, ruotate anche quelle memorizzate nelle opzioni. Ulteriori informazioni nella [guida alla rotazione delle credenziali](../../technotes/security/credential-rotation-guide.md#ac-options-credentials).

## Utilizzare le opzioni nei flussi di lavoro e nella personalizzazione {#use-options-in-processes}

Puoi leggere e scrivere i valori delle opzioni dal codice JavaScript, dalla personalizzazione e dalle query.

* **Codice JavaScript**, ad esempio un&#39;attività del flusso di lavoro del codice JavaScript: `getOption('OptionName')` restituisce il valore di un&#39;opzione e `setOption('OptionName', value, 'description')` lo imposta. Ad esempio, `getOption('IMS_ORG_ID')`. Ulteriori informazioni in [getOption](../../campaign-api/f-getoption.md) e [setOption](../../campaign-api/f-setoption.md).
* **Personalizzazione consegna**: `<%@ include option='OptionName' %>` inserisce il valore di un&#39;opzione. Ad esempio, `<%@ include option='NmsServer_URL' %>` include l&#39;URL del server in un collegamento a un&#39;app Web in un messaggio LINE. Ulteriori informazioni in [Inviare messaggi DIRECT LINE con Adobe Campaign](../send/line/line.md).
* **Editor query**: digitare `$(options:OPTION_NAME)` nel campo **Valore** per utilizzare il valore di un&#39;opzione. Ulteriori informazioni in [Query di progettazione](../start/design-queries.md).

## Opzioni disponibili {#available-options}

Le tabelle seguenti elencano le opzioni disponibili in Campaign v8, raggruppate per area. Quando un’altra pagina della documentazione descrive un’opzione, la tabella vi si collega. Alcune voci sono opzioni informative o di manutenzione. Elencare un’opzione non significa che sia sicuro modificarla.

### Consegne {#delivery-options}

Queste opzioni controllano il modo in cui le consegne vengono preparate e inviate. Coprono i limiti di immagine e allegati, il provider di routing predefinito, la soglia di suddivisione di mid-sourcing, lo script di tracciamento aperto, l’URL pubblico del server, la validità della consegna, la gestione di duplicati e consegne ritardate e codici a barre. Ulteriori informazioni sono disponibili in [Allegamento di file](../send/attaching-files.md), [Parametri e-mail](../send/email-parameters.md), [Best practice per le consegne](../start/delivery-best-practices.md), [Introduzione all&#39;architettura di Campaign](architecture.md#split), [Guida relativa ai pixel di tracciamento delle e-mail](../start/cnil-pixel-tracking.md) e [Invio di messaggi DIRECT LINE](../send/line/line.md).

| Opzione | Descrizione |
|---|---|
| NmsDelivery_MaxDownloadedImageSize | Dimensione massima, in byte, di un’immagine scaricata da un URL personalizzato e allegata a un messaggio e-mail. Il valore predefinito è 100.000 byte (100 KB). [Ulteriori informazioni](../send/attaching-files.md) |
| NmsDelivery_MaxRecommendedAttachments | Numero massimo di allegati in un messaggio e-mail o in un modello e-mail transazionale prima della visualizzazione di un avviso. Il valore predefinito è 1. [Ulteriori informazioni](../send/attaching-files.md) |
| NmsEmail_DefaultErrorAddress | Indirizzo e-mail di errore predefinito dell’istanza, utilizzato quando la consegna lascia vuoto l’indirizzo di errore. [Ulteriori informazioni](../send/email-parameters.md) |
| XtkEmail_Characters | Caratteri validi per un indirizzo e-mail. [Ulteriori informazioni](../start/delivery-best-practices.md) |
| NmsBroadcast_DefaultProvider | Provider di indirizzamento predefinito per i nuovi modelli di consegna. Per impostazione predefinita, impostalo sul nome di un account esterno frazionato per utilizzare la consegna frazionata. [Ulteriori informazioni](architecture.md#split) |
| NmsDelivery_MultiMidSplitThreshold | Dimensione da cui viene suddivisa una consegna tra più istanze di mid-sourcing. Il valore predefinito è 100K. [Ulteriori informazioni](architecture.md#split) |
| NmsTracking_OpenFormula | Script che calcola l’URL di tracciamento aperto. Definite un&#39;opzione per ogni scopo di pixel. [Ulteriori informazioni](../start/cnil-pixel-tracking.md) |
| NmsServer_URL | URL di base del server dell’applicazione web pubblica. Utilizzato, ad esempio, per includere un collegamento a un’app web in un messaggio LINE. [Ulteriori informazioni](../send/line/line.md) |
| NmsBroadcast_MsgValidityDuration | Periodo di validità predefinito di una consegna, in secondi. |
| NmsBroadcast_RemoveDuplicatesRecipients | Impostalo su 1 per ignorare automaticamente i destinatari duplicati. |
| NmsDelivery_ImageServerTimeout | Timeout, in secondi, per ottenere una risposta dal server durante il recupero di un’immagine scaricata da un URL personalizzato e allegata a un’e-mail. Se il timeout viene superato, il messaggio non può essere inviato. Il valore predefinito è 60 secondi. |
| NmsDeliveryWizard_ShowDeliveryWeight | Visualizza il peso del messaggio nell’assistente alla consegna. |
| NmsMTA_Alert_Delay | Ritardo, in minuti, dopo il quale una consegna viene considerata ritardata. Il valore predefinito è 30 minuti. |
| NmsServer_MirrorPageUrl | URL del server della pagina speculare. Si tratta del valore predefinito delle consegne e-mail quando la definizione di indirizzamento non specifica un URL. Per impostazione predefinita, è identico all’URL del server di tracciamento. |
| XtkBarcode_SpecialChar | Attiva o disattiva il supporto di caratteri speciali per i codici a barre Code128. |
| NMS_ActivateOwnerConfirmation | Impostalo su 1 in modo che l’operatore responsabile della consegna possa confermare l’invio, quando un operatore o un gruppo specifico è designato per avviare la consegna. Impostalo su 0 per disattivarlo: solo l’operatore o il gruppo designato, o un amministratore, può quindi confermare l’invio. |
| NmsDelivery_senderAddressMask | Elenco separato da virgole degli indirizzi del mittente consentiti nel campo Da e-mail delle consegne e-mail. Quando l’opzione ha un valore, il campo diventa un elenco a discesa. La restrizione è globale: si applica a ogni marchio e modello di consegna e supporta solo indirizzi statici. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options#restrict-sender-address){target="_blank"} |

### Campagne e flussi di lavoro {#campaign-workflow-options}

Queste opzioni controllano il modo in cui vengono eseguiti le campagne e i flussi di lavoro. Includono la conferma del proprietario di un invio, il numero di processi elaborati contemporaneamente e il controllo e il riavvio automatico dei flussi di lavoro. Includono inoltre la protezione delle attività SQL, la validità predefinita della campagna e il logo dei rapporti esportati. Ulteriori informazioni sono disponibili in [Consegne di campagne di marketing](../../automation/campaigns/marketing-campaign-deliveries.md), [Best practice per i flussi di lavoro](../../automation/workflow/workflow-best-practices.md), [Monitorare l&#39;esecuzione dei flussi di lavoro](../../automation/workflow/monitor-workflow-execution.md), [Proprietà dei flussi di lavoro](../../automation/workflow/workflow-properties.md) e [Codice SQL e Codice JavaScript](../../automation/workflow/sql-code-and-javascript-code.md#important-notes).

| Opzione | Descrizione |
|---|---|
| NmsCampaign_Activate_OwnerConfirmation | Crealo e impostalo su 1 in modo che il proprietario della campagna possa confermare l’invio, anche se sono definiti dei revisori. Impostatelo su 0 per disattivarlo. [Ulteriori informazioni](../../automation/campaigns/marketing-campaign-deliveries.md) |
| NmsOperation_LimitConcurrency | Numero massimo di processi di consegna, flusso di lavoro, ipotesi e simulazione che una campagna elabora contemporaneamente. Il valore predefinito è 10. [Ulteriori informazioni](../../automation/workflow/workflow-best-practices.md) |
| NmsServer_PausedWorkflowPeriod | Numero di giorni tra due controlli per i flussi di lavoro in pausa. [Ulteriori informazioni](../../automation/workflow/monitor-workflow-execution.md) |
| XtkWorkflow_WatchdogRestartTimerTimeout | Creala come opzione numero intero per modificare l’intervallo di 30 secondi in base al quale i flussi di lavoro vengono controllati e riavviati automaticamente. [Ulteriori informazioni](../../automation/workflow/workflow-properties.md) |
| XtkSecurity_FeatureFlag_SqlSensitive | Impostarlo su 0 per disattivare la protezione delle attività del codice SQL dai metodi SQL bloccati. [Ulteriori informazioni](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| XtkSecurity_SqlSensitive_Methods | Elenco dei metodi SQL di cui le attività SQL bloccano o segnalano l&#39;avviso. [Ulteriori informazioni](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| NmsOperation_Duration | Periodo di validità predefinito di una campagna, in secondi. |
| NmsOperation_TimeRange | Periodo di tempo per le condizioni di targeting ed estrazione in modalità pianificata. |
| NmsOperation_OperationMgtDebug | Impostatelo su 1 per registrare le informazioni di esecuzione del flusso di lavoro tecnico operationMgt nei registri di audit del flusso di lavoro. |
| NmsOperation_DeliveryPreparationWindow | Numero di giorni oltre i quali le consegne con stato incoerente sono escluse dal conteggio delle consegne in esecuzione dal flusso di lavoro tecnico operationMgt. Il valore predefinito è 7. |
| Workflow_AnalysisThreshold | Numero di record interessati dopo i quali le statistiche della tabella vengono ricalcolate automaticamente. |
| XtkReport_Logo | Logo visualizzato nell’angolo in alto a destra dei rapporti esportati. |

### Impostazioni predefinite e-mail {#email-default-options}

Queste opzioni definiscono il mittente predefinito e gli indirizzi e le etichette di risposta delle e-mail. Campaign li utilizza quando una consegna lascia vuoto il campo corrispondente. Ulteriori informazioni sono disponibili in [Parametri e-mail](../send/email-parameters.md) e [Utilizzare i modelli di consegna](../send/create-templates.md).

| Opzione | Descrizione |
|---|---|
| NmsEmail_DefaultFromAddress | Indirizzo mittente predefinito dell’istanza, utilizzato quando la consegna la lascia vuota. |
| NmsEmail_FromName | Etichetta From predefinita dell’istanza, utilizzata quando la consegna la lascia vuota. |
| NmsEmail_DefaultReplyToAddress | Indirizzo predefinito di risposta dell’istanza, utilizzato quando la consegna lascia vuoto. |
| NmsEmail_ReplyToName | Etichetta di risposta predefinita dell’istanza, utilizzata quando la consegna la lascia vuota. |
| NmsEmail_DefaultErrorAddress | Indirizzo di errore predefinito dell’istanza, utilizzato quando la consegna la lascia vuota. [Ulteriori informazioni](../send/email-parameters.md) |
| NmsDelivery_FromAddressMasks | Sintassi dell&#39;indirizzo mittente utilizzato per l&#39;invio di un messaggio. |
| NmsDelivery_ErrorAddressMasks | Sintassi dell’indirizzo di errore utilizzato durante la risposta a un messaggio. |
| NmsEmail_ExpOrganization | Nome comune dell’organizzazione, utilizzato in alcuni messaggi di avviso visualizzati ai destinatari. |

### Errori morbidi e quarantena {#error-options}

Queste opzioni definiscono quando un destinatario viene messo in quarantena dopo errori soft, che sono errori di consegna temporanei. Ulteriori informazioni su [Gestione della quarantena in Campaign](../send/quarantines.md#soft-error-management) e [Errori di consegna in Campaign](../send/delivery-failures.md#retries).

| Opzione | Descrizione |
|---|---|
| NmsNPAI_EmailMaxError | Numero massimo di errori software accettati sul canale e-mail prima che il destinatario venga messo in quarantena. |
| NmsNPAI_EmailSignificantErrorDelay | Tempo minimo che deve trascorrere dopo il precedente errore soft sul canale e-mail prima che venga preso in considerazione un nuovo errore soft. |
| NmsNPAI_MobileMaxError | Numero massimo di errori software accettati sul canale mobile prima che il destinatario venga messo in quarantena. |
| NmsNPAI_MobileSignificantErrorDelay | Tempo minimo che deve trascorrere dopo il precedente errore soft sul canale mobile prima che venga preso in considerazione un nuovo errore soft. |

### Canali {#channel-options}

Queste opzioni definiscono l’indirizzo del mittente della direct mailing, le impostazioni dei canali LINE e SMS e gli indirizzi di inoltro consentiti delle e-mail in entrata. Ulteriori informazioni in [Inviare direct mailing con Adobe Campaign](../send/direct-mail.md), [Inviare direct line messaggi con Adobe Campaign](../send/line/line.md) e [Inviare SMS con Adobe Campaign](../send/sms/sms.md).

| Opzione | Descrizione |
|---|---|
| NmsPaper_SenderLine1, NmsPaper_SenderLine3, NmsPaper_SenderLine4, NmsPaper_SenderLine6, NmsPaper_SenderLine7 | Righe 1, 3, 4, 6 e 7 dell’indirizzo del mittente delle consegne di direct mailing. |
| NmsLine_AESKey | Chiave AES utilizzata dal servlet lineImage per codificare gli URL nel canale LINE. |
| NmsLine_MessageCenterURL | URL del server del Centro messaggi utilizzato per inviare messaggi di benvenuto nel canale LINE. |
| NmsSMS_Priority | Priorità dei messaggi SMS inviati, trasmessi al gateway SMS. |
| NmsInmail_AllowlistEmail | Indirizzi e-mail di inoltro autorizzati del modulo di elaborazione della posta in entrata, separati da virgole. Utilizza * per consentire tutti gli indirizzi. |

### Soglie del Centro messaggi {#message-center-options}

Queste opzioni definiscono le soglie che generano un avviso o un avviso quando l’elaborazione di eventi in tempo reale, che attivano i messaggi transazionali, si deteriora. Ogni metrica ha una soglia di avvertenza e una soglia di avviso. Il nome dell&#39;opzione termina con Warning o Alert, ad esempio MC_RtEventErrorWarning e MC_RtEventErrorAlert. Ulteriori informazioni sono disponibili in [Impostazioni messaggistica transazionale di Campaign](../send/transactional.md) e [Impostazioni messaggistica transazionale di Campaign](../config/transactional-msg-settings.md).

| Prefisso nome opzione | Metrica |
|---|---|
| MC_RtEventAvgDeliveryTime | Tempo medio di invio di eventi in tempo reale. |
| MC_RtEventAvgProcessTime | Tempo medio di elaborazione degli eventi in tempo reale. |
| MC_RtEventAvgQueueTime | Tempo medio di attesa degli eventi in tempo reale. |
| MC_RtEventAvgQueue | Numero medio di eventi in tempo reale messi in coda. |
| MC_RtEventMaxQueue | Numero massimo di eventi in tempo reale messi in coda. |
| MC_RtEventMinQueue | Numero minimo di eventi in tempo reale messi in coda. |
| MC_RtEventQueue | Coda di eventi in tempo reale in sospeso. La soglia di avviso è la condizione critica. |
| MC_RtEventError | Errori di elaborazione degli eventi in tempo reale. |
| MC_RtEventThroughput | Throughput degli eventi in tempo reale. |

### Conservazione dei dati e database {#database-options}

Il flusso di lavoro di pulizia elimina i vecchi record per impedire la crescita del database. Queste opzioni definiscono per quanto tempo Campaign conserva ogni tipo di dati. Quando si modifica il ritardo nell&#39;interfaccia, viene creata automaticamente un&#39;opzione di rimozione ritardata. Se lo modifichi dall’elenco delle opzioni, esprime il valore in secondi. Ulteriori informazioni sono disponibili in [Architettura generale](general-architecture.md) e [Linee guida sulla sicurezza](../config/security.md#consent).

Solo gli amministratori possono modificare le opzioni di ritardo di eliminazione. I valori appropriati dipendono dall’ambiente in uso, pertanto verifica il valore corrente nell’istanza e non assumere un valore universale predefinito.

| Opzione | Descrizione |
|---|---|
| NmsCleanup_BroadLogPurgeDelay | Ritardo dopo il quale i registri di consegna (broadLog) vengono cancellati. |
| NmsCleanup_TrackingLogPurgeDelay | Ritardo dopo il quale i registri di tracciamento vengono cancellati. |
| NmsCleanup_TrackingStatePurgeDelay | Ritardo dopo il quale le statistiche di tracciamento vengono cancellate. |
| NmsCleanup_EventPurgeDelay | Ritardo dopo il quale gli eventi vengono cancellati. |
| NmsCleanup_EventHistoPurgeDelay | Ritardo dopo il quale la cronologia degli eventi viene cancellata. |
| NmsCleanup_EventStatPurgeDelay | Ritardo dopo il quale le statistiche degli eventi vengono cancellate. |
| NmsCleanup_PropositionPurgeDelay | Ritardo dopo il quale le proposte vengono cancellate. |
| NmsCleanup_QuarantineMailboxFull | Ritardo dopo il quale le quarantene vengono cancellate. |
| NmsCleanup_RecycledDeliveryPurgeDelay | Ritardo dopo il quale le consegne riciclate vengono cancellate. |
| NmsCleanup_RejectsPurgeDelay | Ritardo dopo il quale i rifiuti vengono cancellati. |
| NmsCleanup_VisitorPurgeDelay | Ritardo dopo il quale i visitatori vengono cancellati. |
| NmsCleanup_WorkflowResultPurgeDelay | Ritardo dopo il quale i risultati del flusso di lavoro vengono cancellati. |
| WdbcKillSessionPolicy | Comportamento dell’arresto incondizionato dei flussi di lavoro su PostgreSQL. 0 (impostazione predefinita): interrompe il processo del flusso di lavoro senza alcun impatto sul database. 1: interrompe il processo e annulla la query (pg_cancel_backend). 2: interrompe il processo e termina la query (pg_terminate_backend). |
| XtkSequence_AutoGeneration | Si applica agli schemi personalizzati creati dopo l’impostazione di questa opzione, con autopk=&quot;true&quot; e nessun attributo pkSequence: Campaign genera la sequenza automaticamente. |

### Personalizzazione del Centro messaggi {#message-center-customization}

Queste opzioni consentono di personalizzare il modo in cui Campaign arricchisce e instrada gli eventi in tempo reale e batch. Ulteriori informazioni sono disponibili in [Impostazioni messaggistica transazionale di Campaign](../send/transactional.md) e [Impostazioni messaggistica transazionale di Campaign](../config/transactional-msg-settings.md).

| Opzione | Descrizione |
|---|---|
| MC_EnrichmentCustomJs | Libreria JavaScript che arricchisce gli eventi. Deve implementare enrichRtEvents(aiEventId) per gli eventi in tempo reale e enrichBatchEvents(aiEventId) per gli eventi batch. Entrambe le funzioni arricchiscono gli eventi e li salvano nel database. |
| MC_RoutingCustomJs | Libreria JavaScript che instrada gli eventi. Deve implementare dispatchRtEvent(iEventId) e dispatchBatchEvent(iEventId), che restituiscono il nome interno del messaggio transazionale selezionato per l’evento in tempo reale o batch. |
| NmsMessageCenter_RoutingBatchSize | Dimensione dei gruppi utilizzati per il routing degli eventi. |
| NmsTracking_RT_ClickFormula, NmsTracking_RT_OpenFormula | Formule utilizzate per il tracciamento dei clic e delle aperture delle consegne in tempo reale (RT) quando viene attivato il branding. Sono configurate nell’istanza di controllo RT. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/branding/branding-configure){target="_blank"} |
| Branding_RT_ListXtkOptions_toPublish | Elenco delle opzioni, separate da virgole, che contengono le formule di tracciamento personalizzate, in modo che le consegne RT possano essere applicate. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/branding/branding-configure){target="_blank"} |

### Interazione (gestione delle offerte) {#interaction-options}

Queste opzioni si applicano all’interazione con Campaign, il modulo di gestione delle offerte. Controllano il modo in cui vengono scritte le proposte e come vengono sincronizzate le istanze di controllo ed esecuzione. Ulteriori informazioni sono disponibili in [Interazione campagna - Gestione delle offerte](../interaction/interaction.md) e nelle [opzioni di manutenzione](../interaction/interaction-architecture.md#maintenance-options) dell&#39;architettura di interazione.

| Opzione | Descrizione |
|---|---|
| NmsInteraction_UseDaemon | Impostatelo su 1 per abilitare la scrittura asincrona delle proposte, o su 0 per disabilitarla. |
| NmsInteraction_MapWorkflowId | Elenco di tutti i flussi di lavoro di sincronizzazione generati. Opzione di manutenzione informativa dell’istanza di controllo: non modificarla. |
| NmsExecutionInstanceId | Identificatore dell’istanza di esecuzione. Opzione informativa disponibile sulle istanze di esecuzione: non modificarla. |

Le seguenti opzioni sono anche opzioni di manutenzione dell’istanza di controllo:

* **`NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>`**: ultima data in cui un ambiente è stato sincronizzato in una determinata istanza.
* **`NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>`**: ultima data in cui le proposte di uno schema sono state sincronizzate da un&#39;istanza all&#39;altra.

>[!CAUTION]
>
>Utilizza le opzioni di manutenzione solo per casi di manutenzione specifici.

Le seguenti opzioni si applicano ai coupon, che non sono disponibili nelle distribuzioni Enterprise (FFDA). Ulteriori informazioni in [Coupon personalizzati](../send/personalized-coupons.md).

| Opzione | Descrizione |
|---|---|
| NmsModule_CouponsEnabled | Abilita i coupon. |
| NmsCoupons_MaxPerTransac | Numero di coupon aggiornati per transazione SQL. |

### Richieste di accesso a dati personali {#privacy-options}

Queste opzioni controllano il modo in cui Campaign elabora le richieste di accesso a dati personali, ad esempio la conferma delle eliminazioni, il numero di errori consentiti e la durata di conservazione dei dati della richiesta. Ulteriori informazioni in [Gestire le richieste di accesso a dati personali in Campaign](../start/privacy.md).

| Opzione | Descrizione |
|---|---|
| Privacy_Request_ConfirmDeletePending | Impostalo su 1 per confermare manualmente ogni eliminazione nell’interfaccia in un secondo passaggio. In caso contrario, i dati vengono eliminati senza conferma. |
| Privacy_Request_ConfirmDeletePendingDelay | Ritardo dopo il quale viene annullata una richiesta in attesa di conferma dell’eliminazione. |
| Privacy_Request_MaxErrorAllowed | Numero massimo di errori consentiti durante l’elaborazione o l’eliminazione di una richiesta di accesso a dati personali. |
| Privacy_Request_PurgeDelay | Ritardo tra la creazione di una richiesta nella coda e l’eliminazione dei relativi dati. |
| realtimeReporting_collectPII | Scelta dell’accordo PII (personally identifiable information) per il reporting dinamico. Il valore 1 corrisponde a Chiedi più tardi, 2 a Rifiuta e 3 ad Accetta. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reporting/dynamic-reporting/pii-agreement){target="_blank"} |

### Audit trail {#audit-trail-options}

L’audit trail registra le modifiche apportate alle entità Campaign. Utilizzare queste opzioni per attivarla o disattivarla per un&#39;entità, ad esempio per risparmiare spazio nel database. Imposta il valore su 1 per abilitare l’audit trail e su 0 per disabilitarlo. Ulteriori informazioni in [Audit trail](../reporting/audit-trail.md#enable-disable-audit-trail).

| Opzione | Entità sottoposta ad audit |
|---|---|
| XtkAudit_Workflows | Flussi di lavoro |
| XtkAudit_DataSchema | Schemi |
| XtkAudit_Option | Opzioni |
| XtkAudit_Delivery | Consegne |
| XtkAudit_ExtAccount | Account esterni |
| XtkAudit_DeliveryMapping | Mappature di consegna |
| XtkAudit_WebApp | Applicazioni web |
| XtkAudit_Offer | Offerte |
| XtkAudit_Operator | Operatori |
| XtkAudit_Enable_All | Tutte le entità |

### Integrazioni e sondaggi {#integration-options}

Queste opzioni memorizzano le impostazioni delle integrazioni e dei sondaggi: le credenziali di Adobe Developer Console per le pagine di destinazione, l’ultima data di sincronizzazione dell’attività del connettore di gestione delle relazioni con i clienti e il backup predefinito delle risposte ai sondaggi. Ulteriori informazioni in [Aggiornare i profili Adobe Experience Platform dalle pagine di destinazione di Adobe Campaign](../connect/ac-aep-landing-pages.md), [Sincronizzazione dati dei connettori CRM](../connect/crm-data-sync.md) e [Gestire le risposte](../dev/surveys/managing-answers.md).

| Opzione | Descrizione |
|---|---|
| IMS_CLIENT_ID, IMS_CLIENT_SECRET, IMS_ORG_ID, IMS_CLIENT_API_KEY | Credenziali Adobe Developer Console utilizzate per le pagine di destinazione con Adobe Experience Platform. [Ulteriori informazioni](../connect/ac-aep-landing-pages.md) |
| LASTIMPORT_ seguito dal nome interno dell’istanza e dal nome dell’attività | Data dell’ultima sincronizzazione dell’attività del connettore CRM generico. Crearlo manualmente come opzione di testo, nel formato `yyyy/MM/dd hh:mm:ss`. [Ulteriori informazioni](../connect/crm-data-sync.md) |
| NmsWebApp_XmlBackup | Crealo e impostalo su 1 per salvare una copia delle risposte non elaborate per impostazione predefinita per tutti i sondaggi. [Ulteriori informazioni](../dev/surveys/managing-answers.md) |
| AEMResourceTypeFilter | Tipi di risorse Adobe Experience Manager utilizzabili in Campaign, separate da virgole. [Ulteriori informazioni](../connect/ac-aem.md) |
| nmsPipeline_config | Configurazione dei trigger di Adobe Experience Cloud, in formato JSON. Crea come opzione testo lungo. [Ulteriori informazioni](../connect/ac-triggers.md) |
| TNT_EdgeServer | Server Adobe Target utilizzato per l’integrazione, impostato per impostazione predefinita. Si tratta del server di dominio Adobe Target seguito da /m2, ad esempio tt.omtrdc.net/m2. [Ulteriori informazioni](../connect/ac-at.md) |
| TNT_TenantName | Nome dell’organizzazione Adobe Target (client). [Ulteriori informazioni](../connect/ac-at.md) |
| AAM_DataSourceId, AAM_DestinationId | Identificatori utilizzati dall’integrazione con Adobe Audience Manager. [Ulteriori informazioni](../start/shared-audiences.md) |
| WdbcCapabilities_AzureDw | Opzioni del connettore Azure Synapse (Azure SQL Data Warehouse). [Ulteriori informazioni](../connect/fda.md) |

## Argomenti correlati {#related-topics}

* [Pacchetti integrati](built-in-packages.md)
* [Principi globali](general-architecture.md)
* [Guida alla rotazione delle credenziali](../../technotes/security/credential-rotation-guide.md)
