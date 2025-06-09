---
title: Impostazioni account esterno SMPP
description: Scopri come configurare l’account esterno SMPP
feature: SMS
role: User
level: Intermediate
exl-id: 1f941b35-c7e0-4e8c-b6e5-a1a3e5354483
source-git-commit: 3ac2976839f084761ba56647b282062d8d457ff2
workflow-type: tm+mt
source-wordcount: '3650'
ht-degree: 3%

---

# Impostazioni account esterno SMPP {#smpp-external-account}

Adobe Campaign utilizza il protocollo SMPP per inviare SMS a un provider di servizi.

Il connettore SMS in Adobe Campaign offre molte opzioni per adattarne il comportamento e renderlo compatibile con la maggior parte dei provider SMPP, che tendono a deviare di un po’ dalle specifiche ufficiali.

>[!IMPORTANT]
>
>* Adobe Campaign supporta la versione 3.4 del protocollo SMPP.
>
>* L&#39;impostazione di una connessione a un nuovo provider può richiedere alcune competenze tecniche, la conoscenza di TCP, binarie, rappresentazioni esadecimali e codifiche di testo. Sarà inoltre necessaria una cooperazione attiva con il fornitore.

L’apparecchiatura di rete sul lato del fornitore di servizi SMS è spesso denominata SMSC.

## Impostazioni della connessione {#smpp-connection-settings}

![](assets/smpp_connection_settings.png){zoomable="yes"}

Di seguito sono riportati i parametri e il loro ruolo necessari per impostare la connessione:

* **Nome implementazione SMSC**: imposta il nome dell&#39;implementazione SMSC. Deve essere impostato sul nome del provider. Il ruolo di questo campo è descritto nella sezione Gestione degli errori SMPP.
* **Server**: nome DNS o indirizzo IP del server a cui connettersi.
* **Porta**: la porta TCP a cui connettersi.
* **Account**: account di accesso della connessione. Passato nel campo system_id della PDU BIND.
* **Password**: password della connessione SMPP. Passato nel campo password della PDU BIND.
* **Tipo di sistema**: valore passato nel campo system_type della PDU BIND. Alcuni provider necessitano di un valore specifico.
* **Numero di connessioni MTA secondarie**: definisce il numero di connessioni aperte per thread di invio.
Il numero totale di connessioni può essere calcolato utilizzando questa formula:
  *Totale connessioni = Numero di processi SMS * Numero di thread di invio * Numero di connessioni MTA secondarie*

   * Il numero di processi SMS è normalmente 1. In alcune istanze con prestazioni molto elevate, è possibile avviare più processi SMS in parallelo.
   * Il numero di thread di invio è impostato in serverConf (impostazione sendingThreads). Il valore predefinito è 1.
   * Il numero di connessioni MTA secondarie corrisponde a questa impostazione nell’account esterno.

  Con i valori predefiniti, questa impostazione imposta direttamente il numero di connessioni.

In **modalità ricetrasmettitore**, indica il numero totale di connessioni.

In **modalità trasmettitore+ricevitore**, definisce il numero di coppie trasmettitore+ricevitore (una coppia = un trasmettitore + un ricevitore).
Non è possibile cambiare l&#39;equilibrio tra trasmettitori e ricevitori.

* **Inviare messaggi tramite un processo dedicato**:
Per Adobe Campaign v8.7.2 e versioni successive, questa opzione deve essere sempre abilitata. Questo influisce notevolmente sul modo in cui vengono elaborati i messaggi.
* **Modalità di connessione SMPP**:
Impostare la connessione in modalità ricetrasmettitore o in modalità trasmettitore+ricevitore separati.
   * Trasmettitore+ricevitore (o TX+RX): due connessioni TCP separate vengono utilizzate per trasmettere e ricevere i messaggi.
   * Ricetrasmettitore (o TRX): una singola connessione TCP viene utilizzata per trasmettere e ricevere i messaggi.
* **Utilizzare parametri diversi per il destinatario**:
Disponibile solo in modalità trasmettitore+ricevitore.
Se la casella non è selezionata, le stesse impostazioni vengono utilizzate per il trasmettitore e il ricevitore. Quando la casella è selezionata, le impostazioni standard si applicano solo al trasmettitore, mentre le impostazioni del ricevitore si applicano solo al ricevitore.
* **Server di ricezione, porta, account, password, tipo di sistema**
Queste impostazioni si applicano al ricevitore in modalità trasmettitore+ricevitore. Funzionano come la parte trasmettitore. Per [ulteriori dettagli](#smpp-connection-settings), vedere sopra.
* **Abilita tracce SMPP dettagliate nel file di registro**
Quando questa opzione è attivata, i registri aggiuntivi verranno inviati al file di registro. Questa funzione è molto utile per la risoluzione dei problemi, ma deve essere mantenuta disabilitata nelle istanze con throughput elevato se non è richiesta alcuna risoluzione dei problemi.

## Impostazioni canale SMPP {#smpp-channel-settings}

![](assets/smpp_channel_settings.png){zoomable="yes"}

### Autorizza la traslitterazione di caratteri {#smpp-transliteration}

La traslitterazione è il processo di ricerca di caratteri equivalenti a quelli mancanti. Ad esempio, il carattere francese &quot;ê&quot; (con accento circonflesso) non è presente nella codifica GSM, ma può essere sostituito da &quot;e&quot; senza compromettere troppo la leggibilità.

Se questa casella non è selezionata, la codifica del testo avrà esito negativo se non è in grado di codificare la stringa esattamente come è.

Se questa casella è selezionata, la codifica del testo tenterà di convertire la stringa in una versione approssimativa anziché non riuscire. Se alcuni caratteri non hanno un equivalente nella codifica di destinazione, la codifica del testo avrà esito negativo.

Per una spiegazione più generale del processo di codifica, vedere [Definire una mappatura specifica delle impostazioni di codifica](#mapping-encodings).

### Numero di origine

Definisce l&#39;indirizzo di origine predefinito per i messaggi. Questa impostazione si applica solo se il numero di origine è stato lasciato vuoto nella consegna. Per impostazione predefinita, il campo del numero di origine non viene passato, pertanto il provider lo sostituirà con il codice breve.

In questo modo viene abilitata la funzione di sostituzione indirizzo mittente/ADC.

### Source TON/NPI, TON di destinazione/NPI

TON (tipo di numero) e NPI (indicatore del piano di numerazione) (descritti nella sezione 5.2.5 delle specifiche SMPP 3.4). Questi valori devono essere impostati in base alle esigenze del provider.

Vengono trasmessi così come sono nei campi source_addr_ton, source_addr_npi, dest_addr_ton e dest_addr_npi della PDU SUBMIT_SM.

### Tipo di servizio

Questo campo viene trasmesso così come è nel campo service_type della PDU SUBMIT_SM. Imposta l&#39;elemento in base alle esigenze del provider.

## Velocità effettiva e ritardi {#smpp-delays}

![](assets/smpp_throughput.png){zoomable="yes"}

Queste impostazioni controllano tutti gli aspetti relativi alla temporizzazione del canale SMPP. Alcuni provider richiedono un controllo molto preciso della frequenza dei messaggi, della finestra e degli intervalli dei nuovi tentativi, pertanto queste impostazioni devono essere impostate su valori che corrispondano alla capacità del provider e alle condizioni indicate nel relativo contratto.

### Finestra di invio

La finestra è il numero di PDU SUBMIT_SM che possono essere inviate senza attendere un SUBMIT_SM_RESP corrispondente.

Esempio di trasmissione con una finestra massima di 4:

![](assets/sms_sending_window.png){zoomable="yes"}

La finestra consente di aumentare il throughput quando il collegamento di rete ha una latenza elevata. Il valore della finestra deve essere almeno il numero di SMS/s moltiplicato per la latenza del collegamento (in secondi), in modo che il connettore non attenda mai un SUBMIT_SM_RESP prima di inviare il messaggio successivo.

Se la finestra è troppo grande, puoi inviare più messaggi duplicati in caso di problemi di connessione (casi rari). Inoltre, la maggior parte dei provider ha un limite molto rigoroso per la finestra e rifiuta i messaggi che superano tale limite.

Come calcolare la formula ottimale della finestra di invio:

Misura la latenza massima tra SUBMIT_SM e SUBMIT_SM_RESP.
Moltiplica questo valore (in secondi) per il throughput MT massimo: questo fornirà il valore ottimale della finestra di invio.
Esempio: se hai impostato 300 SMS/s nella velocità effettiva massima in MT ed è presente in media una latenza di 100 ms tra SUBMIT_SM e SUBMIT_SM_RESP, il valore ottimale è 300×0.1 = 30.

In caso di dubbi, preferisci una finestra più grande per evitare problemi di prestazioni.

### Velocità effettiva MT massima

Numero massimo di MT al secondo e per connessione. Questa impostazione è rigorosamente applicata, l’MTA non invierà mai i messaggi più rapidamente di questo limite. È utile per i provider che richiedono una limitazione precisa.

Per conoscere il limite di velocità effettiva totale, moltiplica questo numero per il numero totale di connessioni (vedi la formula precedente).

0 significa nessun limite, l’MTA invierà MT il più rapidamente possibile.

In genere si raccomanda di mantenere questa impostazione al di sotto di 1000, in quanto è impossibile garantire un throughput preciso al di sopra di tale numero, a meno che non sia opportunamente analizzato sull’architettura finale e non sia stato specificamente richiesto al fornitore di SMPP. Potrebbe essere meglio aumentare il numero di connessioni per superare i 1000 MT/s.

### Tempo prima della riconnessione

Quando la connessione TCP viene persa, il connettore attenderà questo numero di secondi prima di tentare di stabilire una connessione.

### Periodo di scadenza del MT

Timeout tra SUBMIT_SM e il corrispondente SUBMIT_SM_RESP. Se il RESP non viene ricevuto in tempo, il messaggio verrà considerato come non riuscito e verranno applicati i criteri globali per i nuovi tentativi dell’MTA.

### Timeout di associazione

Timeout tra il tentativo di connessione TCP e la risposta BIND_*_RESP. Quando si verifica un timeout, la connessione viene chiusa dal connettore Campaign e si attende il tempo necessario per riconnettersi prima di riprovare.

### Periodo enquire_link

inquire_link è un tipo speciale di PDU inviata per mantenere attiva la connessione. Questo periodo è in secondi. Il connettore campaign invia inquire_link solo quando la connessione è inattiva per risparmiare larghezza di banda. Se non viene ricevuto alcun RESP dopo il doppio di questo periodo, la connessione verrà considerata inattiva e verrà attivato un processo di riconnessione.

## Mappatura delle codifiche {#mapping-encodings}

Per informazioni dettagliate sulla codifica del testo, vedere la [sezione relativa alla codifica del testo SMS](sms-channel.md#sms-text-encoding).

Questa impostazione consente di definire una mappatura di codifica personalizzata, diversa dalle specifiche. Potrai dichiarare un elenco di codifiche e il relativo valore data_coding. L’MTA tenterà di codificare utilizzando la prima codifica dell’elenco; se questa non riesce, tenterà di utilizzare la codifica successiva nell’elenco, ecc. Se non è possibile utilizzare alcuna codifica per codificare il messaggio, si verifica un errore. Una volta trovata la codifica, l’MTA crea la PDU SUBMIT_SM con il testo codificato e il campo data_coding impostato con il valore specificato nella tabella.

L’ordine degli elementi nella tabella è importante: le codifiche vengono tentate dall’alto verso il basso. La codifica più economica o quella più consigliata si trova in cima all&#39;elenco, seguita da codifiche sempre più costose (o meno auspicabili).

UCS-2 non avrà mai esito negativo in quanto può codificare tutti i caratteri supportati in Campaign. La lunghezza massima di un SMS UCS-2 è molto inferiore (solo 70 caratteri).

Puoi inoltre utilizzare questa impostazione per forzare l’utilizzo di una codifica specifica dichiarando solo 1 riga nella tabella di mappatura.

La mappatura predefinita utilizzata quando la casella di controllo non è selezionata equivale alla tabella seguente:

| data_coding | Codifica |
|:-:|:-:|
| 0 | GSM |
| 8 | UCS-2 |

Ciò significa che l’MTA tenterà di codificare il messaggio in GSM, se riesce, lo invia con data_coding impostato su 0.

Se il messaggio non può essere codificato in GSM, verrà codificato in UCS-2 e data_coding verrà impostato su 8.

## Specificità SMSC {#smsc-specificities}

![](assets/smsc_specificities.png){zoomable="yes"}

### Attiva message_payload

Se questa opzione è deselezionata, gli SMS lunghi verranno suddivisi dall’MTA e inviati in più PDU SUBMIT_SM con UDH. Il messaggio verrà ricomposto dal telefono cellulare dopo i dati UDH.

Se questa opzione è selezionata, gli SMS lunghi vengono inviati in una PDU SUBMIT_SM, inserendo il testo nel campo facoltativo message_payload (per informazioni dettagliate, consulta le specifiche SMPP).

Se questa funzione è abilitata, Campaign non sarà in grado di contare le parti SMS singolarmente: tutti i messaggi verranno conteggiati come inviati in una sola parte.

### Invia il numero di telefono completo

Se questa casella di controllo non è selezionata, solo le cifre del numero di telefono vengono inviate al provider (campo destination_addr del campo SUBMIT_SM). Questo è il comportamento predefinito perché l’indicatore del numero internazionale (in genere un prefisso +) viene sostituito dai campi TON e NPI in SMPP.

Quando la casella di controllo è selezionata, il numero di telefono viene inviato così com’è, senza pre-elaborazione (e spazi potenziali, + prefisso o cancelletto/hash/asterisco).

Questa funzione influisce anche sul comportamento della funzione di quarantena di risposta automatica: quando la casella di controllo non è selezionata, ai numeri di telefono inseriti nella tabella di quarantena viene aggiunto un prefisso + per compensare la rimozione del prefisso + dal numero di telefono da parte del protocollo SMPP stesso.

### Associa TON/NPI

TON (tipo di numero) e NPI (indicatore del piano di numerazione) (descritti nella sezione 5.2.5 delle specifiche SMPP 3.4). Questi valori devono essere impostati in base alle esigenze del provider.

Vengono trasmessi così come sono nei campi addr_ton e addr_npi della PDU BIND.

### Intervallo di indirizzi

Inviato così com’è nel campo address_range della PDU BIND. Questo valore deve essere impostato in base alle esigenze del provider.

### Conteggio ID conferma non valido

Limita il numero di &quot;ID messaggio non valido&quot; DELIVER_SM_RESP che possono essere inviati per un singolo messaggio SR. **Utilizzare questa opzione solo per la risoluzione dei problemi come soluzione alternativa** e impostarla su 0 in condizioni normali.

Spiegazione dettagliata: supponiamo che questa impostazione sia impostata su 2:

* Il provider invia un messaggio SR (DELIVER_SM) con ID &quot;1234&quot;
* Impossibile trovare l&#39;ID &quot;1234&quot; nel database
* Il connettore conta 1 errore &quot;ID non valido&quot; per tale ID, pertanto invia DELIVER_SM_RESP con il codice di errore &quot;ID messaggio non valido&quot; (comportamento normale).
* Il provider ritenta lo stesso messaggio SR con ID &quot;1234&quot;
* Impossibile trovare l’ID &quot;1234&quot; nel database
* Il connettore conta 2 errori &quot;ID non valido&quot; per tale ID, pertanto invia DELIVER_SM_RESP &quot;OK&quot;, anche se non è stato elaborato correttamente.

Questa funzione ha lo scopo di effettuare il flushing dei buffer SR sul lato provider quando messaggi SR non validi bloccano messaggi legittimi che non possono essere elaborati.

Impostando questo campo su 0 si disabilita il meccanismo in modo che venga sempre restituito &quot;ID messaggio non valido&quot;. Si tratta di un comportamento normale.

Impostando questo campo su 1, il connettore risponde sempre &quot;OK&quot;, anche se l’ID non è valido. Questo valore deve essere impostato su 1 utilizzato solo sotto supervisione per la risoluzione dei problemi e per il tempo minimo, ad esempio per il ripristino da un problema lato provider.

### Regex di estrazione dell’ID nell’SR

Il formato SR non è strettamente imposto dalla specifica del protocollo SMPP. Si tratta solo di una raccomandazione descritta nell’appendice B delle specifiche. Per questo motivo, alcuni implementatori SMPP formattano questo campo in modo diverso, pertanto Campaign ha bisogno di un modo per estrarre il campo corretto.

Per impostazione predefinita, acquisisce fino a 10 caratteri alfanumerici dopo &quot;id:&quot;.

Il regex deve avere esattamente un gruppo di acquisizione (una parte racchiusa tra parentesi). Le parentesi devono circondare la parte corrispondente all&#39;ID. Il formato regex è PCRE.

Quando regoli questa impostazione, accertati di includere il maggior contesto possibile per evitare falsi attivatori. Se esistono prefissi specifici (come &quot;id:&quot; nello standard), includili nel regex. Utilizzare inoltre i delimitatori di parola (\b) il più possibile per evitare di acquisire il testo al centro di una parola.

Non includere abbastanza contesto nel codice regex può introdurre un piccolo difetto di sicurezza: il contenuto effettivo del messaggio può essere incluso nel messaggio SR, quindi se abbini solo un formato ID specifico senza contesto (ad esempio, un UUID), potrebbe essere l’analisi del contenuto di testo effettivo (ad esempio, un UUID incorporato nel campo di testo) invece dell’ID.

### Regex di estrazione dello stato nell’SR

Questo regex acquisisce lo stato dal campo di testo dei messaggi SR.

Per impostazione predefinita, acquisisce tra 5 e 15 caratteri dopo &quot;stat:&quot;.

Il regex deve avere **esattamente un gruppo di acquisizione** (una parte racchiusa tra parentesi). Le parentesi devono circondare la parte corrispondente allo stato. Il formato regex è PCRE.

### Regex applicato per determinare lo stato Riuscito

Questo regex viene applicato al risultato del precedente regex (&quot;Regex di estrazione dello stato&quot;). Se il regex corrisponde, il messaggio viene considerato di successo.

Per impostazione predefinita, corrisponde a tutto ciò che inizia con &quot;DELIV&quot;. Corrisponde al valore standard &quot;DELIVRD&quot;.

### Regex applicato per determinare lo stato Errore

Questo regex viene applicato al risultato del precedente regex (&quot;Regex di estrazione dello stato&quot;). Se il regex corrisponde, il messaggio viene considerato errato.

Per impostazione predefinita, corrisponde a tutti i vari stati di errore descritti nelle specifiche.

### Regex di estrazione del codice di errore nell’SR

Questo codice regex acquisisce il codice di errore dal campo di testo dei messaggi SR.

I codici di errore possono essere qualificati nella qualifica del registro di consegna.

Per impostazione predefinita, acquisisce 3 caratteri dopo &quot;err:&quot;.

### Formato ID nella conferma MT

Indica il formato dell’ID restituito nel campo message_id della PDU SUBMIT_SM_RESP.

* **Non modificare**: l&#39;ID viene archiviato così com&#39;è nel database, come testo con codifica ASCII. Non si verificano pre-elaborazione né filtri.
* **Numero decimale**: l&#39;ID deve essere un numero decimale in formato ASCII. Gli spazi iniziali e finali e gli zeri iniziali vengono rimossi quando si utilizza questa impostazione.
* **Numero esadecimale**: l&#39;ID deve essere un numero esadecimale in formato ASCII, senza 0x iniziale né h finale. L’ID viene quindi convertito in un numero decimale prima di essere memorizzato nel database.
* **Stringa esadecimale**: l&#39;ID deve essere un testo con codifica ASCII, a sua volta una stringa di byte con codifica esadecimale. Ad esempio, nella PDU si trova 0x34 0x31 0x34 0x32 0x34 0x33, che si traduce in ASCII &quot;414243&quot;; quindi questa stringa viene decodificata come stringa esadecimale di byte e si ottiene &quot;ABC&quot; come risultato: si memorizza l&#39;ID &quot;ABC&quot; nel database.

### Formato ID nell’SR

Indica il formato dell’ID acquisito dal regex di estrazione dell’ID nell’SR. I valori hanno lo stesso significato e lo stesso comportamento del formato in MT qui sopra.

### ID SR o codice di errore in campo opzionale

Se questa opzione è selezionata, il contenuto dei campi facoltativi verrà aggiunto al testo elaborato dai regex di cui sopra. Il testo avrà il formato &quot; 0xTAG:VALUE&quot;, dove 0xTAG è il valore esadecimale a 4 cifre del tag in lettere maiuscole (ad esempio 0x002E).

Ad esempio, potrebbe essere utile acquisire l&#39;ID nel campo receivted_message_id. Per questo, abilita questa casella di controllo e il seguente testo verrà aggiunto allo stato:

0x001E:05e3299e-8d37-49d0-97c6-8e4fe60c7739

In questo esempio, 0x001E è il tag del campo facoltativo e l’UUID è il valore del campo.

Per acquisire questo valore, ora puoi impostare il seguente regex nel regex di estrazione dell’ID nel campo SR:

\b0x001E:([0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12})\b

>[!IMPORTANT]
>
>È possibile acquisire solo campi facoltativi con valori di testo a 8 bit (ASCII/UTF-8). In particolare, i campi binari non possono essere acquisiti in modo affidabile con il sistema regex corrente.

### ID SR o codice di errore in campo di testo

Se questa opzione è selezionata, durante l’elaborazione del testo di stato dell’SR verrà mantenuto il campo Testo:. Questa opzione è utile se il provider inserisce dati importanti in questo campo, ad esempio l’ID o lo stato. Di solito questo campo può essere eliminato in modo sicuro perché può contenere testo con una codifica non ASCII e interrompere l’elaborazione regex.

L’abilitazione di questa opzione può introdurre un difetto di sicurezza molto piccolo se il regex di estrazione dell’ID nel campo SR non è abbastanza specifico: il contenuto del campo Text può essere analizzato come un ID e un utente malintenzionato può utilizzarlo per inserire ID falsi, il che può portare a una situazione di rifiuto parziale del servizio.

### Tag ID servizio

Consente di aggiungere un valore TLV personalizzato. Questo campo imposta il tag, passato come valore esadecimale nel formato **0x1234**.

Il valore del valore TLV personalizzato deve essere impostato nella consegna nel campo &quot;Service or program ID&quot; (ID servizio o programma) nei parametri avanzati della consegna. Il valore viene inviato come testo con codifica UTF-8.

Questa impostazione consente di aggiungere solo un’opzione TLV per messaggio.

>[!NOTE]
>
>Questa opzione è sostituita dall&#39;impostazione molto più potente **Parametri SMPP opzionali (TLV)** nei parametri di consegna. Queste funzioni si escludono a vicenda e non possono essere utilizzate contemporaneamente.

### Abilita TLS su SMPP

Se abilitate, tutte le connessioni a SMSC verranno crittografate utilizzando TLS.

### Verifica dei certificati

* **Verifica completa del certificato**: controlla il certificato TLS e il nome host remoto durante la connessione. Questo valore offre il massimo livello di sicurezza.
* **Ignora la verifica del nome host**: controllare il certificato TLS remoto, ma non verificare se il nome host remoto corrisponde. Diminuisce leggermente la sicurezza.
* **Ignora la verifica del certificato**: non controllare il certificato TLS. La connessione è ancora crittografata, ma è vulnerabile agli attacchi man-in-the-middle. Diminuisce molto la sicurezza.

## Traffico in entrata {#incoming-traffic}

![](assets/incoming_traffic.png){zoomable="yes"}

### Parametri SMPP (TLV) opzionali in MO

Campaign consente di ricevere 3 campi aggiuntivi in MO (tabella nms:inSms): SMS collegato, alias e account di grandi dimensioni. Con il connettore SMPP, questi campi possono essere compilati con dati provenienti da qualsiasi parametro SMPP (TLV) opzionale, con qualsiasi formato comune.

Per ogni campo, puoi impostare il tag associato e il relativo formato. Chiedi al provider di servizi SMPP di disporre di queste informazioni.

* Tag: il valore del tag, in formato decimale (ad esempio 12345) o esadecimale con prefisso 0x (ad esempio 0x12ab). I tag possono essere compresi tra 0 e 65535.
* Formato: il formato utilizzato per il valore. I valori binari sono tutti valori binari con segno big-endian. Per i campi di testo, scegli la codifica utilizzata dal provider SMPP.

### Risposta automatica inviata al MO

Questa funzione consente di rispondere rapidamente al testo in formato MO e di gestire blacklist per codici di scelta rapida.

Le colonne *Parola chiave* e *Codice breve* definiscono le condizioni per attivare la risposta automatica: se entrambi i campi corrispondono, viene inviato il messaggio MO e viene attivata l&#39;azione aggiuntiva. Per specificare un carattere jolly, lascia vuoto il campo. La parola chiave corrisponde alla prima parola alfanumerica nel testo MO, ignorando la punteggiatura e gli spazi iniziali. Ciò significa che il campo Parola chiave non può contenere spazi e deve essere una singola parola.

Inoltre, l&#39;impostazione *Parola chiave* è un prefisso. Ad esempio, se specifichi &quot;AD&quot;, corrisponderà a &quot;AD&quot;, &quot;ADAPT&quot; e &quot;ADOBE&quot;. Se disponi di più parole chiave con un prefisso comune, fai attenzione all’ordine, le parole chiave vengono elaborate dall’alto verso il basso.

La colonna *Rispondi* è il testo da rispondere. In questo campo non è disponibile alcuna personalizzazione, il testo della risposta è sempre lo stesso. Se lasci questo campo vuoto, non verrà risposto alcun messaggio, ma l’azione aggiuntiva verrà attivata comunque.

La colonna dell&#39;azione *Aggiuntivo* fornisce un&#39;azione aggiuntiva da eseguire quando la parola chiave e il codice breve corrispondono (il codice breve vuoto corrisponde a tutti i codici brevi). Attualmente, puoi mettere in quarantena o rimuoverlo dalla quarantena. Se specifichi un’azione aggiuntiva ma lasci vuoto il campo di risposta, l’azione verrà eseguita ma non verrà inviata alcuna risposta. La quarantena viene applicata solo per il codice breve specificato o per tutti i codici brevi se il campo viene lasciato vuoto.

Tutte le voci della tabella vengono elaborate nell&#39;ordine specificato, fino a quando non viene trovata una corrispondenza per una regola. Se più regole corrispondono a un MO, verrà applicata solo la regola più in alto.

>[!NOTE]
>
>L&#39;impostazione **invia numero di telefono completo** ha un impatto sul comportamento del meccanismo di quarantena automatica delle risposte: se l&#39;opzione invia numero di telefono completo non è selezionata, il numero di telefono messo in quarantena verrà preceduto da un segno più (&quot;+&quot;) per renderlo compatibile con il formato del numero di telefono internazionale.

>[!NOTE]
>
>In un’architettura di mid-sourcing, l’applicazione della risposta automatica per il connettore SMPP esteso richiede di aggiungere l’accesso in scrittura per l’operatore mid nella cartella dell’account esterno.

>[!IMPORTANT]
>
>Presta attenzione alle codifiche nelle risposte automatiche, soprattutto quando si copia e incolla. Il software di elaborazione testi tende ad aggiungere ulteriore formattazione, ad esempio aggiungendo spazi unificatori o cambiando le virgolette agli apostrofi.
