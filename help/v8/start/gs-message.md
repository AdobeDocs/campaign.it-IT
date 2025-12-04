---
title: Introduzione ai messaggi
description: Introduzione ai messaggi
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: a523e76d-776c-47d3-9c15-34241cee1092
source-git-commit: 3453820bb0eca7847ec55d7e6ea15766a57ab94e
workflow-type: tm+mt
source-wordcount: '998'
ht-degree: 74%

---

# Introduzione ai messaggi {#gs-ac-msg}

Con Adobe Campaign, puoi inviare campagne cross-channel tra cui e-mail, SMS, notifiche push e direct mail; inoltre, puoi misurarne l’efficacia utilizzando diversi rapporti dedicati. Questi messaggi sono progettati e inviati tramite consegna e possono essere personalizzati per ogni destinatario.

Le funzionalità di base includono il targeting, la definizione e la personalizzazione dei messaggi, l’esecuzione di comunicazioni e i relativi rapporti operativi.

## Casi d’uso {#gs-ac-delivery}

Per inviare messaggi, devi creare una consegna. La modalità di creazione della consegna dipende dal caso d’uso.

>[!NOTE]
>
>Durante la creazione di una consegna, devi selezionare un modello. Per ogni canale sono disponibili modelli predefiniti. Ulteriori informazioni sui modelli di consegna sono disponibili in [questa pagina](../send/create-templates.md).

1. **Messaggi una tantum** - Puoi inviare messaggi una tantum a un pubblico. Scopri come inviare il primo messaggio in [questa sezione](create-message.md).

   ![](assets/send-email.png)

1. **Messaggi in una campagna di marketing** - Puoi inviare messaggi nel contesto di una [campagna di marketing](campaigns.md), definire un processo di approvazione, inviarli e tracciarli in un dashboard consolidato. Scopri come in [questa sezione](../../automation/campaigns/marketing-campaign-deliveries.md).

   ![](assets/deliveries-in-a-campaign.png)

1. **Messaggi in un flusso di lavoro** - Puoi inviare messaggi tramite un [flusso di lavoro](../config/workflows.md) e automatizzare le consegne. Scopri come in [questa pagina](../../automation/workflow/delivery.md).

   ![](assets/send-in-a-wf.png)

1. **Messaggi attivati** - È possibile [Attivare i messaggi](../send/transactional.md) da un evento. La messaggistica transazionale (Message Center) è il modulo di Campaign progettato per la gestione dei messaggi di attivazione. Scopri come configurare e inviare messaggi transazionali in [questa pagina](../send/transactional.md)

## Canali di comunicazione {#gs-channel}

Adobe Campaign v8 viene fornito con i canali di consegna elencati di seguito. I canali disponibili nel tuo ambiente dipendono dal contratto. Controlla il contratto di licenza.

* **Canale e-mail**: le consegne e-mail ti consentono di inviare e-mail personalizzate alla popolazione target. [Ulteriori informazioni](../send/email.md)

* **Canali mobili**: le consegne sui canali mobili ti consentono di inviare messaggi personalizzati ai dispositivi della popolazione target. Puoi inviare [SMS](../send/sms/sms.md) e [LINE](../send/line/line.md) messaggi su dispositivi mobili.

* **Canale app mobile**: puoi utilizzare Adobe Campaign per inviare [notifiche push personalizzate e segmentate](../send/push.md) su dispositivi mobili iOS e Android tramite app dedicate. Una volta eseguiti i passaggi di configurazione e integrazione, le consegne iOS e Android possono essere create e inviate tramite Adobe Campaign. Puoi anche progettare e inviare notifiche avanzate ai dispositivi Android con immagini o video.

* **Canale direct mailing**: [Direct mailing](../send/direct-mail.md) è un canale offline che consente di creare, personalizzare e generare un file esterno da condividere con i provider di direct mailing. Utilizza questo canale per orchestrare canali online e offline nei percorsi cliente.

  Quando prepari una consegna di direct mail, Adobe Campaign genera un file contenente tutti i profili target e le informazioni del contatto selezionato, ad esempio l’indirizzo postale. Puoi quindi inviare questo file al provider di direct mail, che si occuperà dell’invio effettivo.


* **Altri canali**: Adobe Campaign include anche un modello di consegna telefonica, utilizzato per creare consegne esterne. L’utilizzo di questo canale implica l’implementazione di metodologie dedicate per l’elaborazione dei file di output. I passaggi di configurazione sono gli stessi del [Canale direct mail](../send/direct-mail.md).

  >[!NOTE]
  >
  >Il canale Telefono non è un canale incorporato. L’implementazione richiede il coinvolgimento del team di consulenza o di un partner di Adobe. Per maggiori informazioni, contatta il tuo rappresentante Adobe.

  Le consegne di tipo “Altro” utilizzano un modello tecnico specifico che non esegue un processo: questo consente di gestire le azioni di marketing eseguite al di fuori della piattaforma Adobe Campaign.

  Questo canale non dispone di un meccanismo specifico. Si tratta di un canale generico con una propria opzione di indirizzamento dell’account esterno, un tipo di modello di consegna e un’attività del flusso di lavoro della campagna, come qualsiasi altro canale di comunicazione disponibile in Adobe Campaign. Questo canale è progettato solo a scopo descrittivo, ad esempio per definire consegne per le quali desideri tenere traccia del target di una campagna eseguita in uno strumento diverso da Adobe Campaign.

## Tipi di consegna {#types-of-deliveries}

In Campaign sono disponibili tre tipi di oggetti di consegna:

### Consegna unica {#single-delivery}

Una **consegna** è un oggetto di consegna autonoma che viene eseguito una volta. Può essere duplicato, preparato di nuovo, ma finché è nel suo stato finale (annullato, interrotto, completato), non può essere riutilizzato.

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

## Funzionalità di Personalization {#personalization}

I messaggi consegnati da Adobe Campaign possono essere personalizzati in vari modi. [Ulteriori informazioni sulle funzionalità di personalizzazione](../send/personalize.md)

È possibile eseguire le seguenti operazioni:

* Inserire campi di personalizzazione dinamici. [Ulteriori informazioni](../send/personalization-fields.md)
* Inserire blocchi di personalizzazione predefiniti. [Ulteriori informazioni](../send/personalization-blocks.md)
* Creare contenuto condizionale. [Ulteriori informazioni](../send/conditions.md)


## Tracciamento e monitoraggio {#gs-tracking-logs}

Il monitoraggio delle consegne dopo l’invio è un passaggio fondamentale per garantire l’efficienza delle campagne di marketing e l’effettivo raggiungimento dei clienti. Puoi monitorare una consegna, oltre a capire come vengono gestiti errori e quarantene.

Scopri come [tenere traccia e monitorare le consegne](../send/tracking.md)
