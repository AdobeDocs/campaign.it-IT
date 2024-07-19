---
title: Introduzione ai messaggi
description: Introduzione ai messaggi
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 7f6c394f56d517c0a675e0fd2341bb6ef98044f0
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 100%

---

# Introduzione ai messaggi {#gs-ac-audiences}

## Canali di consegna {#gs-ac-channels}

Con Adobe Campaign, puoi inviare campagne cross-channel tra cui e-mail, SMS, notifiche push e direct mail; inoltre, puoi misurarne l’efficacia utilizzando diversi rapporti dedicati. Questi messaggi sono progettati e inviati tramite consegna e possono essere personalizzati per ogni destinatario.

Le funzionalità di base includono il targeting, la definizione e la personalizzazione dei messaggi, l’esecuzione delle comunicazioni e i relativi rapporti operativi. Il punto di accesso funzionale principale è l’assistente alla consegna. Permette di sfruttare diverse funzionalità incluse in Adobe Campaign.

Adobe Campaign v8 è dotato dei canali di consegna seguenti:

* **Canale e-mail**: le consegne e-mail ti consentono di inviare e-mail personalizzate alla popolazione target. [Ulteriori informazioni](#gs-channel-email)

* **Canali mobili**: le consegne sui canali mobili ti consentono di inviare messaggi personalizzati ai dispositivi della popolazione target. [Ulteriori informazioni](#gs-channel-sms)

* **Canale applicazione mobile**: le consegne tramite app mobile ti consentono di inviare notifiche ai dispositivi iOS e Android. [Ulteriori informazioni](#gs-channel-push)

* **Canale direct mail**: le consegne tramite direct mail ti consentono di generare un file di estrazione che contiene dati sulla popolazione target. [Ulteriori informazioni](#gs-channel-direct)


  Altri canali sono descritti in [questa sezione](#other-channels).

  >[!NOTE]
  >
  >Il numero di canali disponibili dipende dal contratto. Controlla il contratto di licenza.

## Scegliere il proprio canale {#gs-channel}

### Canale e-mail {#gs-channel-email}

Il [canale e-mail](../send/direct-mail.md) è uno dei canali principali di Adobe Campaign e ti consente di pianificare e inviare e-mail personalizzate a target specifici.

Puoi inviare diversi tipi di e-mail:

* E-mail singole: e-mail che puoi inviare una volta a un target definito. Vengono solitamente utilizzate per promuovere un contenuto specifico che viene preparato e inviato una sola volta (newsletter, e-mail promozionale, ecc.).
* E-mail ricorrenti: in una campagna, invia regolarmente la stessa e-mail e aggrega ogni invio e i relativi rapporti su base periodica. Viene inviata la stessa e-mail, ma in genere a un target diverso, in base a quello idoneo per il giorno dell’invio. Un esempio comune è un’e-mail di compleanno. Per ulteriori informazioni, consulta [Consegne ricorrenti](../../automation/workflow/recurring-delivery.md).
* E-mail transazionali: e-mail unitarie che vengono attivate in base al comportamento della clientela. Consulta [Messaggistica transazionale](../send/transactional.md).

Per informazioni sull’utilizzo e i consigli per la consegna, consulta le [best practice per la consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=it#sending-messages){target="_blank"} di Adobe Campaign Classic.

Per ulteriori informazioni sui diversi tipi di consegna, consulta [questa sezione](#types-of-deliveries).

### Canale mobile {#gs-channel-sms}

Adobe Campaign consente di consegnare messaggi [SMS](../send/sms.md) e [LINE](../send/line.md) su dispositivi mobili.

Per i messaggi SMS, puoi creare, modificare e personalizzare i messaggi solo in formato testo. Puoi anche visualizzare in anteprima i messaggi SMS prima che vengano inviati.

Per i messaggi LINE, puoi inviare testo o immagini e collegamenti.

Per consegnare messaggi SMS o LINE a un telefono cellulare, è necessario:

* Un account esterno configurato sul canale **[!UICONTROL Mobile (SMS)]** o **[!UICONTROL LINE]**.
* Un modello di consegna SMS o LINE correttamente collegato a tale account esterno.


### Canale di notifica push {#gs-channel-push}

Puoi utilizzare Adobe Campaign per inviare [notifiche push](../send/push.md) personalizzate e segmentate a dispositivi mobili iOS e Android, tramite app dedicate. Una volta eseguiti i passaggi di configurazione e integrazione, le consegne iOS e Android possono essere create e inviate tramite Adobe Campaign. Puoi anche progettare e inviare notifiche avanzate ai dispositivi Android con immagini o video.

### Canale direct mail {#gs-channel-direct}

[Direct mail](../send/direct-mail.md) è un canale offline che ti consente di creare, personalizzare e generare il file esterno da condividere con i provider di direct mail. Utilizza questo canale per orchestrare canali online e offline nei percorsi cliente.

Quando prepari una consegna di direct mail, Adobe Campaign genera un file contenente tutti i profili target e le informazioni del contatto selezionato, ad esempio l’indirizzo postale. Puoi quindi inviare questo file al provider di direct mail, che si occuperà dell’invio effettivo.


### Altri canali {#other-channels}

Adobe Campaign viene fornito anche con un modello di consegna telefonica, utilizzato per creare consegne esterne. L’utilizzo di questo canale implica l’implementazione di metodologie dedicate per l’elaborazione dei file di output. I passaggi di configurazione sono gli stessi del [Canale direct mail](../send/direct-mail.md).

>[!NOTE]
>
>Il Canale telefonico non è un canale integrato. L’implementazione richiede il coinvolgimento del team di consulenza o di un partner di Adobe. Per maggiori informazioni, contatta il tuo rappresentante Adobe.

Le consegne di tipo “Altro” utilizzano un modello tecnico specifico che non esegue un processo: questo consente di gestire le azioni di marketing eseguite al di fuori della piattaforma Adobe Campaign.

Questo canale non dispone di un meccanismo specifico. Si tratta di un canale generico con una propria opzione di indirizzamento dell’account esterno, un tipo di modello di consegna e un’attività del flusso di lavoro della campagna, come qualsiasi altro canale di comunicazione disponibile in Adobe Campaign. Questo canale è progettato solo a scopo descrittivo, ad esempio per definire consegne per le quali desideri tenere traccia del target di una campagna eseguita in uno strumento diverso da Adobe Campaign.

## Scegliere il tipo di consegna {#types-of-deliveries}

In Campaign sono disponibili tre tipi di oggetti di consegna:

### Consegna unica {#single-delivery}

Una **consegna** è un oggetto di consegna autonoma che viene eseguito una volta. Può essere duplicato, preparato di nuovo, ma finché è nel suo stato finale (annullato, interrotto, finito), non può essere riutilizzato.

Le consegne possono essere create dall’elenco delle consegne o all’interno di un flusso di lavoro tramite un’attività di [Consegna](../../automation/workflow/delivery.md).

I flussi di lavoro forniscono anche attività di consegna specifiche in base al tipo di canale che desideri utilizzare. Per ulteriori informazioni su tali attività, consulta [questa sezione](../../automation/workflow/cross-channel-deliveries.md).

### Consegna ricorrente {#recurring-delivery}

Una **consegna ricorrente** è disponibile nel contesto di un flusso di lavoro. Consente di creare una nuova consegna ogni volta che l’attività viene eseguita. In questo modo si evita di dover creare una nuova consegna per attività ricorrenti. Ad esempio, se esegui questo tipo di attività una volta al mese, dopo un anno ti ritroverai 12 consegne.

Le consegne ricorrenti vengono create all’interno dei flussi di lavoro tramite l’[attività Consegna ricorrente](../../automation/workflow/recurring-delivery.md). Un esempio di questa attività in uso è presentato in questa sezione: [Creazione di una consegna ricorrente in un flusso di lavoro di targeting](../../automation/workflow/send-a-birthday-email.md).

### Consegna continua {#continuous-delivery}

Una **consegna continua** è disponibile nel contesto di un flusso di lavoro. Consente di aggiungere nuovi destinatari a una consegna esistente, evitando di dover crearne una nuova ogni volta che viene eseguita.

Se un’informazione nella consegna cambia (contenuto, nome, ecc.), nell’esecuzione della consegna viene creato un nuovo oggetto di consegna. Se non è stata modificata alcuna informazione, viene riutilizzato lo stesso oggetto di consegna e i registri di consegna e di tracciamento vengono aggiunti nello stesso oggetto.

Ad esempio, se esegui questo tipo di attività una volta al mese, ti ritroverai una singola consegna dopo un anno (purché non sia stata apportata alcuna modifica alla consegna).

Le consegne continue vengono create all’interno dei flussi di lavoro tramite l’[attività Consegna continua](../../automation/workflow/continuous-delivery.md).


## Scegli come inviare i messaggi{#gs-send-msg}

Dopo aver creato il messaggio e averne progettato e testato il relativo contenuto, puoi scegliere come inviarlo. Campaign offre una serie di funzionalità per:

* Inviare messaggi manualmente al target principale

  ![](assets/send-email.png)

  Scopri come inviare messaggi in [questa sezione](../send/send.md)

* Inviare messaggi associati a una [campagna di marketing](campaigns.md)

  ![](assets/deliveries-in-a-campaign.png)

  Per scoprire come inviare messaggi nel contesto di una campagna, consulta [questa sezione](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=it){target="_blank"}

* Inviare messaggi tramite un [flusso di lavoro](../config/workflows.md)

  ![](assets/send-in-a-wf.png)

  Per scoprire come automatizzare le consegne di e-mail, consulta [questa pagina](../../automation/workflow/delivery.md).

* [Attivare i messaggi](../send/transactional.md) da un evento

  La messaggistica transazionale (Message Center) è il modulo di Campaign progettato per la gestione dei messaggi di attivazione.

  Ulteriori informazioni sulle funzionalità per messaggi transazionali in [questa sezione](../architecture/architecture.md#transac-msg-archi)

  Scopri come configurare e inviare messaggi transazionali in [questa pagina](../send/transactional.md)

* Pianificare i messaggi

  ![](assets/schedule-send.png)

  Scopri come pianificare l’invio delle consegne in [questa pagina](../send/configure-and-send.md)

  Consulta anche questo [Caso d’uso: scopri come pianificare e inviare un’e-mail di compleanno](../../automation/workflow/send-a-birthday-email.md)


## Aggiungere la personalizzazione{#personalization}

I messaggi consegnati da Adobe Campaign possono essere personalizzati in vari modi. [Ulteriori informazioni sulle funzionalità di personalizzazione](../send/personalize.md)

È possibile eseguire le seguenti operazioni:

* Inserire campi di personalizzazione dinamici. [Ulteriori informazioni](../send/personalization-fields.md)
* Inserire blocchi di personalizzazione predefiniti. [Ulteriori informazioni](../send/personalization-blocks.md)
* Creare contenuto condizionale. [Ulteriori informazioni](../send/conditions.md)


## Registri di consegna e di tracciamento{#gs-tracking-logs}

Il monitoraggio delle consegne dopo l’invio è un passaggio fondamentale per garantire l’efficienza delle campagne di marketing e l’effettivo raggiungimento dei clienti. Puoi monitorare una consegna, oltre a capire come vengono gestiti errori e quarantene.

Scopri come monitorare le consegne nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=it#sending-messages){target="_blank"}

