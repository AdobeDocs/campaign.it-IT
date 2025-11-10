---
title: Passaggio al nuovo connettore SMS v2
description: Scopri come passare al nuovo connettore SMS v2
feature: Technote
role: Admin
hide: true
hidefromtoc: true
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
source-git-commit: 784c74aaff23dbf1f35c6e8153f90610048e1c07
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 0%

---

# Passaggio al nuovo connettore SMS v2

Questo documento illustra la procedura e le considerazioni chiave per la migrazione dal connettore SMS basato su MTA al nuovo **connettore di elaborazione SMS dedicato** in Adobe Campaign v8.

## Perché passare al connettore v2

Il processo SMS dedicato introduce il supporto per la modalità ricetrasmettitore SMPP, riducendo il conteggio delle connessioni e migliorando l’efficienza delle risorse, supportando al tempo stesso le configurazioni del trasmettitore/ricevitore se necessario. Offre una maggiore stabilità, con un ripristino più rapido dagli errori, connessioni persistenti e nessuna dipendenza dai file locali o dalla comunicazione tra processi. Anche le prestazioni sono migliorate, con latenza inferiore, throughput più elevato e microbatch intelligente per bilanciare velocità e affidabilità. Inoltre, l’isolamento del processo SMS semplifica la risoluzione dei problemi e riduce al minimo l’impatto su più canali. Questi miglioramenti rendono il connettore dedicato una soluzione più solida e scalabile per la consegna di SMS.

## Differenze tra i connettori v1 e v2

Il connettore SMS dedicato in Adobe Campaign v8 introduce diverse modifiche architetturali rispetto al connettore basato su MTA. Una differenza chiave è l’utilizzo predefinito della modalità ricetrasmettitore SMPP, che riduce il numero di connessioni combinando le funzioni di invio e ricezione. Se il provider non supporta questa modalità, è comunque possibile utilizzare connessioni separate del trasmettitore e del ricevitore. A differenza del connettore MTA, l’abilitazione delle risposte automatiche non ha alcun effetto sul conteggio delle connessioni e tutte le connessioni del ricevitore possono gestire qualsiasi tipo di messaggio in ingresso.

Il conteggio delle connessioni viene ora calcolato utilizzando una formula diversa:

```
Total connections = SMS sending threads * Number of MTA child connections. 
```

Il parametro sendingThreads, definito in serverConf, ha come valore predefinito 1 e in genere deve rimanere invariato a meno che non venga specificamente ottimizzato per ottenere prestazioni elevate. Poiché un singolo processo gestisce tutto il traffico SMS, la gestione del parallelismo attraverso questi parametri diventa fondamentale per controllare il carico e il comportamento del sistema.

La finestra di invio si comporta in modo simile al connettore MTA, ma ha un impatto ancora maggiore sulle prestazioni nella modalità dedicata. Le finestre di invio più grandi riducono le operazioni di I/O al database e migliorano la velocità effettiva. Campaign può gestire in modo efficiente finestre con oltre 1000 messaggi, purché il provider lo supporti e il caso d’uso consenta un piccolo margine di perdita di messaggi o duplicazione in caso di problemi di connessione. Dal lato del fornitore, anche la configurazione di una finestra di invio SR più grande può migliorare in modo significativo la velocità effettiva dei rapporti di consegna.

Infine, anche se la gestione dei messaggi MO (Originati da dispositivi mobili) rimane funzionalmente invariata, il codice sottostante è stato aggiornato. Il throughput per connessione è ancora limitato allo stesso modo, ma il connettore dedicato consente un invio burst molto più veloce. Tuttavia, senza limiti di velocità effettiva, l’invio ad alta velocità potrebbe sopraffare le risorse del provider o del sistema, rendendo consigliabile impostare limiti di velocità effettiva MT espliciti nella configurazione dell’account esterno.

## Procedura di commutazione

Per garantire un passaggio fluido al processo SMS dedicato, è meglio eseguire l’operazione durante un traffico SMS basso o assente. Alcuni messaggi nel buffer potrebbero andare persi o rimanere in uno stato non valido se i buffer MTA non sono completamente scaricati. È inoltre normale perdere alcuni SR per una settimana dopo il passaggio, a causa di tempi SR imprevedibili. Il mancato rispetto di queste precauzioni può causare la perdita o la duplicazione dei messaggi, nonostante le protezioni integrate.

Entrambi i connettori SMS utilizzano formati diversi per l’elaborazione SR (Status Report, Rapporto di stato). Sebbene entrambi si basino sulla tabella `NmsProviderMsgId`, interagiscono in modo diverso con essa. Pertanto, il passaggio a un altro connettore richiede la cancellazione dell’intera tabella per evitare conflitti o dati orfani. Esistono diversi modi per eseguire questa pulizia. Di seguito sono riportate le query SQL che è possibile utilizzare:

```
TRUNCATE TABLE NmsProviderMsgId;
TRUNCATE TABLE NmsProviderMsgStatus;
```

### Passaggi

1. Rivedi le impostazioni di `serverConf` (`sms > mta2`).
1. Sospendi il flusso di lavoro di preparazione dei messaggi in tempo reale (se applicabile).
1. Metti in pausa tutte le consegne SMS.
1. Disattiva l’account esterno SMS.
1. Arresta e riavvia i processi MTA e SMS.
1. Verifica che non siano attive connessioni SMPP. Se presente, assicurati che tutte le consegne siano sospese.
1. Cancellare il contenuto delle tabelle `NmsProviderMsgId` e `NmsProviderMsgStatus` nel database.
1. Nell’account esterno:
   * Abilita la casella di controllo &quot;Processo dedicato&quot;
   * Regola altre impostazioni: connessioni secondarie MTA, velocità effettiva MT, finestra di invio
1. Riattiva l’account esterno e salva.
1. Riprendere le consegne SMS.
1. Verifica che i servizi SMS funzionino normalmente.

>[!NOTE]
>
>Monitora i registri SMS, MTA e MTA secondari per individuare eventuali errori o problemi.
>
>Salva le impostazioni dell’account esterno precedenti a scopo di rollback.

### Procedura di ripristino

È possibile tornare al connettore MTA seguendo gli stessi passaggi utilizzati durante l’interruttore iniziale, nello stesso ordine. Ciò include l’interruzione o la sospensione di tutte le consegne SMS e il ripristino della configurazione dell’account esterno originale.

1. Se l’istanza utilizza consegne in tempo reale, sospendi il flusso di lavoro tecnico responsabile della preparazione di tali messaggi.
1. Metti in pausa tutte le consegne SMS.
1. Disattiva l’account esterno SMS.
1. Arresta e riavvia i processi MTA e SMS.
1. Assicurati che nessuna connessione SMPP rimanga attiva; in caso affermativo, verifica che tutte le consegne siano correttamente sospese.
1. Cancellare le tabelle `NmsProviderMsgId` e `NmsProviderMsgStatus` nel database.
1. Nell’account esterno:
   * Deseleziona l’opzione &quot;Processo dedicato&quot; nell’account esterno.
   * Ripristina tutte le impostazioni account esterne precedenti: connessioni MTA secondarie, velocità effettiva MT, finestra di invio
1. Riattiva e salva l’account esterno.
1. Riprendi tutte le consegne SMS.
1. Infine, conferma che i servizi SMS funzionino normalmente.
