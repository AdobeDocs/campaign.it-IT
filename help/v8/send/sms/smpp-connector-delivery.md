---
title: Connettore SMPP nelle proprietà di consegna
description: Informazioni sulle impostazioni del connettore SMPP nelle consegne
feature: SMS
role: User
level: Beginner, Intermediate
exl-id: 704e151a-b863-46d0-b8a1-fca86abd88b9
source-git-commit: ea51863bdbc22489af35b2b3c81259b327380be4
workflow-type: tm+mt
source-wordcount: '1342'
ht-degree: 5%

---

# Descrizione del connettore SMPP {#smpp-connector-desc}

>[!AVAILABILITY]
>
>Questa funzionalità è disponibile per tutti gli ambienti FDA di Campaign. È **non** disponibile per le distribuzioni FFDA di Campaign. Questa documentazione si applica ad Adobe Campaign v8.7.2 e versioni successive. Per passare dalla versione precedente al nuovo connettore SMS, fai riferimento a questa [nota tecnica](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/sms-migration){target="_blank"}
>
>Per le versioni precedenti, leggere la [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

## Flusso di dati del connettore SMS {#sms-data-flow}

Questa sezione descrive come il processo SMS gestisce i dati.

Di seguito è riportato un diagramma a blocchi di alto livello che riepiloga il modo in cui il processo SMS interagisce con il relativo ambiente.

![](assets/smsv2_highlevel.png){zoomable="yes"}

Il processo SMS ospita 2 componenti importanti: il connettore SMPP che gestisce le comunicazioni con il provider SMPP e un’attività in background per la riconciliazione SR.

### Flusso di dati per gli account SMPP {#sms-data-flow-smpp-accounts}

Il processo SMS esegue il polling di nms:extAccount e genera nuove connessioni nel connettore SMPP, passando le impostazioni di ogni account. La frequenza di polling può essere regolata in serverConf nell&#39;impostazione *configRefreshMillis*.

Per ogni account SMPP attivo, il connettore SMPP cerca di mantenere sempre attive le connessioni. Si riconnette se la connessione viene persa.

### Flusso di dati durante l’invio di messaggi {#sms-data-flow-sending-msg}

* Il processo SMS seleziona le consegne attive eseguendo la scansione di nms:delivery. Una consegna è attiva quando:
   * Il suo stato implica che i messaggi possono essere inviati
   * Il suo periodo di validità non è scaduto
   * In realtà è una consegna (ad esempio non è un modello, non viene eliminato)
   * Il connettore SMPP poteva aprire almeno una connessione per l’account esterno collegato alla consegna
* Per ogni consegna, il processo SMS carica le parti di consegna. Se la parte di consegna è stata inviata parzialmente, il processo SMS controlla quali messaggi sono già stati inviati controllando il registro ampio.
* Il processo SMS espande il modello con i dati di personalizzazione della parte di consegna.
* Il connettore SMPP genera una PDU MT (SUBMIT_SM PDU) che corrisponde al contenuto e ad altre impostazioni.
* Il connettore SMPP invia il messaggio MT tramite una connessione del trasmettitore (o ricetrasmettitore).
* Il provider restituisce un ID per questo messaggio MT. È inserito in nms:providerMsgId.
* Il processo SMS aggiorna l’ampio registro allo stato inviato.
* In caso di errore finale, il processo SMS aggiorna di conseguenza l&#39;ampio registro e potrebbe creare un nuovo tipo di errore in nms:broadLogMsg.

### Flusso di dati durante la ricezione di messaggi SR {#sms-data-flow-sr}

* Il connettore SMPP riceve e decodifica l’SR (DELIVER_SM PDU). Utilizza i regex definiti nell’account esterno per ottenere l’ID e lo stato del messaggio.
* ID messaggio e stato inseriti in nms:providerMsgStatus
* Dopo essere stato inserito, il connettore SMPP risponde con una PDU DELIVER_SM_RESP.
* Se si è verificato un errore durante il processo, il connettore SMPP invia una PDU DELIVER_SM_RESP negativa e registra un messaggio.

### Flusso di dati durante la ricezione di un messaggio MO {#sms-data-flow-mo}

* Il connettore SMPP riceve e decodifica il MO (DELIVER_SM PDU).
* La parola chiave viene estratta dal messaggio. Se corrisponde a una qualsiasi parola chiave dichiarata, vengono eseguite le azioni corrispondenti. È possibile scrivere in nms:address per aggiornare la quarantena.
* Se vengono dichiarati valori TLV personalizzati, vengono decodificati in base alle rispettive impostazioni.
* Il MO completamente decodificato ed elaborato viene inserito nella tabella nms:inSms.
* Il connettore SMPP risponde con una PDU DELIVER_SM_RESP. Se viene rilevato un errore, verrà restituito un codice di errore al provider.

### Flusso di dati durante la riconciliazione di MT e SR {#sms-reconciling-mt-sr}

* Il componente di riconciliazione SR legge periodicamente nms:providerMsgId e nms:providerMsgStatus. I dati di entrambe le tabelle sono collegati in join.
* Per tutti i messaggi che hanno una voce in entrambe le tabelle, la voce corrispondente nms:broadLog viene aggiornata.
* È possibile aggiornare la tabella nms:broadLogMsg nel processo se viene rilevato un nuovo tipo di errore o per aggiornare i contatori per gli errori non qualificati manualmente.

## Voci MT, SR e broadlog corrispondenti {#sms-matching-entries}

Ecco un diagramma che descrive l’intero processo:

![](assets/message_processing.png){zoomable="yes"}

**Fase 1**

* Il messaggio viene scansionato, formattato e quindi trasmesso al connettore SMPP.
* Il connettore SMPP lo formatta come PDU MT SUBMIT_SM.
* Il messaggio MT viene inviato al provider SMPP.
* Il provider risponde con SUBMIT_SM_RESP. SUBMIT_SM e SUBMIT_SM_RESP corrispondono al rispettivo sequence_number.
* SUBMIT_SM_RESP fornisce un ID proveniente dal provider. Questo ID viene inserito insieme all&#39;ID di registro generale nella tabella nms:providerMsgId.

**Fase 2**

* Il provider invia una PDU DELIVER_SM SR.
* L’SR viene analizzato per estrarre l’ID del provider, lo stato e il codice di errore. Questo passaggio utilizza i regex di estrazione.
* L&#39;ID provider e lo stato corrispondente vengono inseriti in nms:providerMsgStatus.
* Quando tutti i dati vengono inseriti nel database in modo sicuro, il connettore SMPP risponde con DELIVER_SM_RESP. DELIVER_SM e DELIVER_SM_RESP hanno una corrispondenza con il loro sequence_number.

**Fase 3**

* Il componente di riconciliazione SR del processo SMS analizza periodicamente le tabelle nms:providerMsgId e nms:providerMsgStatus.
* Se una riga presenta ID provider corrispondenti in entrambe le tabelle, le due voci vengono unite insieme. Questo consente di associare l’ID di registro ampio (memorizzato in providerMsgId) allo stato (memorizzato in providerMsgStatus)
* Il registro esteso viene aggiornato con lo stato corrispondente.

## Affinità e connettore di processo dedicato {#sms-affinities}

Le affinità vengono ignorate dal connettore di processo dedicato e vengono eseguite all’interno del processo SMS.

## opzioni serverConf {#sms-serverconf-options}

Alcune impostazioni possono essere regolate in serverConf.xml. Come qualsiasi altra impostazione in questo file, deve essere specificato nel file config-instance.xml. Tutte le impostazioni si trovano nell&#39;elemento &lt; mta2 >.

In questa tabella vengono riepilogate tutte le impostazioni. I valori sensibili min/max forniscono un’idea approssimativa dell’intervallo da considerare nella maggior parte dei casi. Il valore di debug è il valore da scegliere quando si tenta di individuare problemi non correlati alle prestazioni.

| Impostazione | Descrizione | Predefinito | Valore minimo sensibile | Valore massimo sensibile | Valore di debug |
|:-:|:-:|:-:|:-:|:-:|:-:|
| batchUpdateSize | Dimensioni dei microbatch di aggiornamento | 5000 | 100: latenza molto bassa | maxWaitingMessages/updateThreads: andare oltre questo valore è inutile perché maxWaitingMessages limiterà comunque il buffering | 1: disabilitare la microbatch, aggiornare i messaggi uno alla volta |
| configRefreshMillis | Periodo di ricaricamento della configurazione in millisecondi | 10000 | pollPeriodMillis: latenza bassa | 600000: non ricaricare troppo velocemente per risparmiare risorse | 500: la bassa latenza consente di provare più rapidamente le nuove impostazioni |
| deliveryPartRetryCount | Numero massimo di tentativi o rinvii di un deliveryPart. Attenzione: il riavvio del processo di invio conta come un nuovo tentativo; anche gli arresti anomali possono essere conteggiati come un nuovo tentativo. | 20 | 1: Disattivare i nuovi tentativi | 50: rendere i messaggi più persistenti per aggirare i provider instabili | 1: disabilitare i nuovi tentativi. 1000: evitare lo scaricamento dei messaggi non riusciti. |
| deliveryPartRetryDelaySeconds | Ritardo minimo prima di un nuovo tentativi di un deliveryPart. Si tratta di cross-process e cross-container. Il ritardo è espresso in secondi. | 60 | 0: Nuovi tentativi immediati | 3600: tentativi molto lenti (1 ora tra un tentativo e l’altro) | 1: rende i nuovi tentativi facili da seguire nei registri occupati. |
| logOutput | Invia dati di monitoraggio e profilatura sull’output del registro principale. | true | false: può aumentare un po’ la velocità effettiva. Scoraggiato. | true: abilita la registrazione. | true |
| maxWaitingMessages | Numero massimo di messaggi elaborati in qualsiasi momento | 50000 | 256: sufficiente per una singola deliveryPart | 200000: limitata dalla lunghezza della query SQL (64 KB) | 1: Elaborare i messaggi uno alla volta |
| pollPeriodMillis | Frequenza di polling del database (in millisecondi) per verificare la presenza di nuovi messaggi | 2000 | 500: latenza molto bassa | 10000: batch più grandi | 500: la bassa latenza semplifica il debug. |
| prepareThreads | Numero di thread per la preparazione dei messaggi | 3 | 1: filettato singolo | Numero di CPU. Prestare attenzione all&#39;utilizzo della RAM. Un aumento superiore a 6 può richiedere l’aumento di maxSMSMemoryMb, maxProcessMemoryAlertMb e maxProcessMemoryWarningMb | 1: Il thread singolo genera registri più puliti. |
| profDeliveryStat | Registra varie statistiche aggregate sulle funzioni interne del processo SMS | true | false: può aumentare un po’ la velocità effettiva. Scoraggiato. | true: registro di livello di dettaglio basso | true |
| profLogPerMessage | Registra ogni passaggio di elaborazione per ogni messaggio | falso | false: riduce la gravità del registro. | true: registro di verbozza molto alto. **Da utilizzare solo se assolutamente necessario**. Grande impatto sulle prestazioni. **Disattivare questa impostazione non appena sono stati raccolti dati sufficienti**. | true |
| providerIdScanPeriod | Periodo in secondi tra le analisi per la ricerca di nuovi ID provider da riconciliare | 10 | 1: latenza bassa | 60: Batch più grandi per una maggiore velocità effettiva | 1: latenza bassa per facilitare il debug dell’elaborazione dei messaggi. |
| providerIdThreads | Numero di thread per la riconciliazione dell’ID fornitore. È sufficiente 1 thread per istanza. Imposta su 0 per disabilitare su questo contenitore. | 1 | 0: Disattiva su questo contenitore | 1 | 1 |
| sendingThreads | Numero di thread di invio | 1 | 1: filettato singolo | Numero di CPU. Troppi thread di solito compromettono le prestazioni. | 1: Il thread singolo genera registri più puliti. |
| updateThreads | Numero di thread per l&#39;aggiornamento del database | 1 | 1: filettato singolo | Numero di CPU. Ogni thread crea la propria connessione DB. | 1: Il thread singolo genera registri più puliti. |
| verifyMode | Simula l’invio di messaggi. I messaggi non vengono effettivamente inviati. Utile per il debug | falso | falso | true | false: esegue il sistema normalmente. true: verifica solo l&#39;accesso al database e la preparazione dei messaggi. |
