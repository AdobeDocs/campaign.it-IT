---
title: Convalida di una connessione SMPP
description: Scopri come convalidare una connessione SMPP
feature: SMS
role: User
level: Intermediate
exl-id: eda6934a-e48a-4932-8c88-588f661005d6
source-git-commit: 6f29a7f157c167cae6d304f5d972e2e958a56ec8
workflow-type: tm+mt
source-wordcount: '4437'
ht-degree: 0%

---

# Convalida di una connessione SMPP {#validate-smpp-connection}

Di seguito sono riportati alcuni controlli per verificare che la connessione SMPP sia corretta.

## Aspetti da verificare prima di andare in diretta {#check-go-live}

Prima di andare &quot;live&quot;, assicurati che la configurazione di SMPP sia corretta, con l’elenco di controlli riportato di seguito.

>[!IMPORTANT]
>
>Questo elenco di controllo non è esaustivo. Più controlli si effettuano, meglio è.

>[!NOTE]
>
>Abilita le tracce SMPP dettagliate durante i controlli; ti aiuterà, insieme al team di supporto, a comprendere le soluzioni ai problemi.

### Verifica la presenza di conflitti di account esterni {#sms-external-accounts-check}

Verifica di non disporre di account esterni SMS rimanenti. Elimina gli account di test per eliminare potenziali conflitti.

Verifica che nessun’altra istanza si connetta all’account esterno. In particolare, accertati che l’ambiente di pre-produzione non si connetta all’account esterno di produzione.

Se hai bisogno di avere più account sulla stessa istanza di Campaign che si connettono allo stesso provider, contatta il provider per assicurarti che distinguano effettivamente le connessioni tra questi account. Avere più account con lo stesso accesso richiede una configurazione aggiuntiva.

Verifica che in tutti gli account esterni SMS abilitati sia abilitata l’impostazione di processo dedicato. Non è possibile combinare i due tipi di account (con e senza processo dedicato) nella stessa istanza.

### Eseguire un test reale {#real-test}

Prova a inviare alcuni SMS su dispositivi mobili diversi.

**Invia SMS con tutti i tipi di caratteri**

Se devi inviare un SMS con caratteri non GSM o non ASCII, prova a inviare alcuni messaggi con i caratteri più diversi possibili. Se imposti una tabella di mappatura caratteri personalizzata, invia almeno un SMS per tutti i possibili valori data_coding.

**Verifica che i messaggi SR siano elaborati correttamente**

L’SMS deve essere contrassegnato come ricevuto nel registro di consegna. Il registro di consegna deve essere corretto e avere un aspetto simile al seguente: &quot;*SR yourProvider stat=DELIVRD err=000|#MESSAGE#*&quot;.

Verificare di aver impostato correttamente il campo &quot;*Nome implementazione SMSC*&quot;: il registro di consegna non deve mai contenere &quot;*SR Generic*&quot; negli ambienti di produzione.

**Verifica che MO siano elaborati**

Invia alcuni SMS per tutte le parole chiave di risposta automatica e verifica che la risposta sia rapida (non più di pochi secondi).

Verificare che i messaggi MO siano inseriti nel database *nms:inSms*. Se disponi di TLV personalizzati, accertati che siano anche inseriti correttamente e correttamente formattati.

Controlla nel registro che Campaign risponde con un *DELIVER_SM_RESP (command_status=0)* riuscito.

**Esegui un test di carico**

Ciò è particolarmente importante se invii molti messaggi o se utilizzi la messaggistica in tempo reale.

Eseguire un test per caricare la connessione al 100% per almeno 5 secondi. Dovrai inviare messaggi reali se il provider non dispone di un modo per connettersi a un account falso per i test. Un modo per farlo è monitorare da vicino la prima consegna abbastanza grande con messaggi SMPP dettagliati abilitati.

Il numero minimo di messaggi da inviare può essere calcolato come segue:

*Velocità effettiva MT massima * Numero totale di connessioni trasmettitore/ricetrasmettitore * 5*

Al termine della consegna, verifica quanto segue:

* Verifica che tutti i messaggi siano stati inviati (non necessariamente ricevuti)
* Deve essere presente una PDU assolutamente pari a zero con command_status diverso da 0x00000000, a meno che il provider non lo indichi esplicitamente come funzionamento normale
* Le connessioni devono rimanere assolutamente stabili (nessuna PDU BIND) durante l’intero processo di consegna.
* Verificare che tutti i messaggi abbiano un messaggio SR e che sia stato elaborato correttamente (vedere [Verificare che il messaggio SR sia stato elaborato correttamente](#real-test)). Se una piccola percentuale presenta errori, verifica che si tratti di errori SR effettivi che restituiscono errori, non di errori durante l’invio o l’elaborazione sul lato Campagna.
* Se non si è sicuri delle prestazioni, verificare che la latenza sia ragionevole, in particolare tra una PDU e la corrispondente RESP, una latenza superiore a 500 ms può rappresentare un problema per l&#39;elevata velocità di trasmissione. Utilizza questa latenza per controllare la formula della finestra di invio (consulta l’impostazione della finestra di invio per ulteriori dettagli)

### Controllare le PDU {#pdu}

Verificare che le PDU siano formattate correttamente.

>[!IMPORTANT]
>
>Questo passaggio è vivamente consigliato per la connessione a un provider che in precedenza non era connesso a Campaign.

**ASSOCIA**

Verificare che le PDU BIND_* siano inviate correttamente. La cosa più importante da verificare è che il provider restituisca sempre PDU BIND_*_RESP riuscite (command_status = 0).

Verificare che non siano presenti troppe PDU BIND_*. Se ne sono presenti troppi, potrebbe indicare che la connessione è instabile. Per ulteriori informazioni, consulta la sezione Risoluzione dei problemi di connessioni instabili di seguito.

**INQUIRE_LINK**

Verificare che le PDU INQUIRE_LINK vengano scambiate regolarmente quando la connessione è inattiva.

**SUBMIT_SM / DELIVER_SM**

Invia un messaggio, quindi cerca nei registri le PDU SUBMIT_SM, SUBMIT_SM_RESP, DELIVER_SM e DELIVER_SM_RESP corrispondenti.

Con la PDU *SUBMIT_SM*:

* Verifica che data_coding sia corretto (0 per impostazione predefinita).
* Verifica che short_message sia codificato correttamente: prova a decodificarlo utilizzando un convertitore esadecimale che supporta più codifiche (alcune sono disponibili online).
* Se utilizzi message_payload per i messaggi lunghi, verifica che il contenuto sia presente nel campo facoltativo e non nel campo short_message.

Con la PDU *SUBMIT_SM_RESP*:

* Verifica che sia stato eseguito correttamente (command_status = 0).
* Verifica che il corpo della stringa contenga un ID formattato correttamente seguito da un byte &quot;0&quot;.

Con la PDU *DELIVER_SM*:

* Decodificare il campo esadecimale short_message (sono disponibili strumenti online per questo scopo).
* Con uno strumento di controllo regex, verifica che il regex definito in Extraction regex dell’ID nell’SR restituisca esattamente un gruppo di acquisizione e che acquisisca l’intero ID nel messaggio.
* Verifica che l’ID estratto corrisponda a quello in SUBMIT_SM_RESP.
* Verifica che il regex definito in Regex di estrazione dello stato nell’SR restituisca il contenuto del campo stat.
* Verificare che il regex definito in Regex di estrazione dell&#39;errore nell&#39;SR restituisca il contenuto del campo di errore.

Con la PDU *DELIVER_SM_RESP*:

* Verifica che sia stato inviato rapidamente dopo la ricezione della PDU DELIVER_SM (in genere meno di 1 secondo).
* Verifica che sia stato eseguito correttamente (command_status = 0).

### Test live con il provider {#sms-live-test}

Una best practice prima di andare in diretta è quella di eseguire un test in tempo reale con il provider, in cui entrambe le parti esaminano i registri durante l’esecuzione.

>[!IMPORTANT]
>
>Questo passaggio è vivamente consigliato per la connessione a un provider mai connesso a Campaign in precedenza.

### Disattiva tracce SMPP dettagliate {#sms-disable-smpp}

Una volta completati tutti i controlli, l’ultima azione da eseguire è disabilitare le tracce SMPP dettagliate in modo che non generino troppi registri.

## Risoluzione dei problemi SMS {#sms-troubleshooting}

### Procedura generale di risoluzione dei problemi {#sms-general-troubleshooting}

Il connettore SMS coinvolge 3 entità: il provider SMPP, Adobe e te.
Il principale esperto SMS è il provider SMPP, pertanto devono essere coinvolti in tutti i problemi relativi al traffico SMS (problemi di connessione, messaggi persi, problemi di codifica, regole specifiche per paese, ecc.).

#### Abilita processo dedicato {#sms-dedicated-process}

>[!IMPORTANT]
>
>Assicurarsi che **[!UICONTROL Send messages through a dedicated process]** sia abilitato in tutti gli account SMS attivi.

In caso di problemi con il connettore precedente (basato su MTA) (processo dedicato disabilitato), valuta la possibilità di migrare al connettore di processo dedicato. Funziona molto meglio, è più stabile e fornisce un feedback molto migliore nei suoi registri.

#### Conflitto tra diversi account esterni {#sms-conflict-external-accounts}

Se l’istanza dispone di più account esterni SMS, verifica che i problemi non siano causati da un conflitto tra account.

Per isolare l’account esterno che causa problemi:

1. Disattiva tutti gli account esterni
1. Abilita un account esterno
1. Prova a riprodurre il problema
1. Se il problema non viene visualizzato con l&#39;account singolo, disattivarlo e riavviare il sistema al passaggio 2 dell&#39;account successivo. Dopo aver controllato ogni singolo account, sono possibili due scenari:

**Il problema è apparso su uno o più account**

In questo caso, puoi applicare altre procedure di risoluzione dei problemi su ogni singolo account. È consigliabile disabilitare altri account durante la diagnosi di un account, al fine di ridurre il traffico di rete e la quantità di registri.

**Il problema non è stato visualizzato quando è attivo un solo account alla volta**

Si è verificato un conflitto tra gli account. Adobe Campaign tratta gli account singolarmente, ma il provider può trattarli come un singolo account.

*Stai utilizzando combinazioni di login/password diverse tra tutti i tuoi account*
Contattare il provider per diagnosticare potenziali conflitti.

*Alcuni account esterni condividono la stessa combinazione di account di accesso e password*
Il provider non ha modo di sapere da quale account esterno proviene la PDU BIND, quindi tratta tutte le connessioni da più account come un unico account, quindi probabilmente indirizzano MO e SR in modo casuale sui 2 account, causando problemi apparentemente casuali.

Se il provider supporta più codici brevi per la stessa combinazione di login/password, dovrai chiedere loro dove inserire tale codice breve nella PDU BIND. Si noti che questa informazione deve essere inserita nella PDU BIND e non in SUBMIT_SM, perché la PDU BIND è l&#39;unica posizione che consente il routing corretto dei MO.

Consulta la sezione [Informazioni in ogni tipo di PDU](#pdu) per sapere quali campi sono disponibili nella PDU BIND. In genere il codice breve viene inserito in *address_range*, ma questo richiede un supporto speciale da parte del provider. Contattali per sapere in che modo si aspettano di instradare più codici brevi in modo indipendente.

Adobe Campaign supporta la gestione di più codici brevi sullo stesso account esterno in modo corretto, quindi spesso l’utilizzo di un singolo account per tutto il traffico funziona correttamente.

#### Un account esterno non funziona più {#sms-external-account-not-working}

In generale, le connessioni SMPP tendono a essere molto stabili nel tempo e, una volta configurate correttamente, dovrebbero continuare a funzionare.

* Verifica se il connettore è stato modificato di recente e da chi (controlla Account esterni come gruppo).
* Verificare se il sistema è stato aggiornato e quando.
* Verifica se eventuali pacchetti che influiscono sugli SMS potrebbero essere stati aggiornati di recente.

Se nessuno di questi controlli determina una causa principale, contatta il provider. A volte, quando i provider aggiornano le piattaforme, il connettore si comporta in modo leggermente diverso. Questo potrebbe interrompere le impostazioni ottimizzate e introdurre regressioni.

Si consiglia di tenersi in contatto con il provider, che spesso comunica in anticipo modifiche importanti.

#### Problema con il mid-sourcing (in hosting)  {#sms-issue-hosted}

* Se il problema si verifica in un ambiente di mid-sourcing, accertati che i registri di consegna e di broadcast siano creati e aggiornati correttamente sul server di mid-sourcing. In caso contrario, il problema non è un problema SMS.
* Assicurati che il nome dell’operatore mid sia rigorosamente minuscolo, altrimenti la consegna rimarrà nello stato In sospeso.
* Se tutto funziona sul server mid e gli SMS vengono inviati correttamente, ma l’istanza di marketing non viene aggiornata correttamente, si verifica un problema di sincronizzazione mid.

#### Problema durante la connessione al provider {#sms-issue-connection}

* Se la PDU BIND restituisce un codice *command_status* diverso da zero (ovvero se si verifica un errore) o se non è presente alcuna PDU BIND_RESP, chiedere al provider perché ciò si verifichi.
* Verificare che la rete sia configurata correttamente in modo da consentire la connessione TCP al provider.
* Chiedi al provider di verificare che gli indirizzi IP dell’istanza di Adobe Campaign siano consentiti correttamente (la maggior parte dei provider lo richiede).
* Controlla le impostazioni dell’account esterno. Chiedi al provider in caso di dubbi sul valore di alcuni campi.
* Se la connessione è riuscita ma instabile, controllare [Problemi con connessioni instabili](#unstable-connections). sezione successiva.
* Se i problemi di connessione sono difficili da diagnosticare, un&#39;acquisizione di rete porterà molte informazioni. Assicurarsi che l&#39;acquisizione di rete venga eseguita contemporaneamente mentre il problema si verifica, in modo da poterlo analizzare in modo efficiente. È inoltre necessario notare l&#39;ora esatta in cui il problema si verifica, in modo che sia più facile individuarlo nelle acquisizioni di rete.

#### Problemi con connessioni instabili {#unstable-connections}

**Diagnosi connessioni instabili:**

Una connessione è considerata instabile se si verifica una di queste situazioni:

* La connessione dura meno di 1 ora.
* Il riavvio del processo SMS comporterà una &quot;correzione&quot; temporanea. Probabilmente significa che una connessione instabile attiva la limitazione, il riavvio del processo SMS cancella la limitazione, quindi accade di nuovo finché non viene trovata la causa principale.
* Il provider invia PDU UNBIND. Il provider non deve mai inviare PDU UNBIND in condizioni di funzionamento normali.
* *inquire_link* va in timeout, sul lato Campaign o sul lato provider. In tal caso, è possibile che INQUIRE_LINK_RESP sia visualizzato o meno con un codice di errore diverso da zero.
* Ci sono molte PDU BIND. Non dovrebbero essercene più di alcuni in un giorno (dipende dal numero di connessioni). Deve essere inviato un avviso a più di 1 PDU BIND all&#39;ora e per connessione.

**Come risolvere i problemi di stabilità della connessione:**

* Le connessioni instabili sono raramente la causa principale, spesso è il risultato di un altro problema che attiva una disconnessione in un modo o nell&#39;altro. Trovare la causa principale è la priorità.
* Abilita tracce SMPP dettagliate. Avrai bisogno che visualizzino cosa accade al riavvio della connessione.
* Se il provider invia PDU UNBIND, probabilmente commette un errore. Chiedi loro perché hanno inviato UNBIND e probabilmente porterà alla causa principale.
* L&#39;acquisizione di una rete a volte è l&#39;unico modo per vedere come viene chiusa la connessione.
* Se il provider chiude le connessioni (inviando un pacchetto TCP FIN o TCP RST), chiedere loro perché lo fanno. Questo dovrebbe dirvi la causa principale del problema.
* Se il provider chiude la connessione dopo aver inviato un errore corretto (ad esempio DELIVER_SM_RESP con un codice di errore), deve correggere il connettore perché impedisce la trasmissione di altri tipi di messaggi e attiverà la limitazione dell’MTA. Ciò è particolarmente importante nella modalità ricetrasmettitore, dove la chiusura della connessione influisce sia su MT che su SR.
* In presenza di timeout (BIND timeout, SUBMIT_SM timeout), è possibile che Campaign invii messaggi troppo rapidamente per tale provider. Prova ad abbassare l&#39;impostazione *velocità effettiva MT massima* e a vedere se risolve il problema.

#### Problema durante l’invio di un messaggio MT (SMS regolare inviato a un utente finale)

* Verifica che la connessione sia stabile: una connessione SMPP deve rimanere attiva per almeno 1 ora di seguito. Consulta la sezione &quot;Problema con connessioni instabili&quot; di cui sopra.
* Se il riavvio del processo SMS fa funzionare di nuovo il messaggio MT per un piccolo periodo di tempo, probabilmente hai dei limiti a causa di una connessione instabile. Consulta la sezione &quot;Problema con connessioni instabili&quot; di cui sopra.
* Verificare che l&#39;ampio registro sia presente e che lo stato sia corretto con le date corrette. In caso contrario, non si tratta di un problema SMS, ma di un problema di consegna o di una questione di preparazione della consegna (che non rientra nell’ambito di questo documento).
* Verifica che il connettore SMS sia effettivamente associato all’apparecchiatura del provider. Chiedere al provider di fornire un feedback per verificare che tutti i sistemi comunichino correttamente. Per informazioni sul processo di associazione, vedere PDU BIND_TRANSMITTER e BIND_TRANSCEIVER. Per una corretta risoluzione dei problemi, potrebbe essere necessario abilitare le tracce SMPP.
* Con le tracce SMPP abilitate, verifica che la PDU SUBMIT_SM contenga le informazioni corrette (consulta la documentazione precedente).
* Verificare che il provider risponda con una PDU SUBMIT_SM_RESP con un valore &quot;OK&quot; (codice 0). Assicurati che la PDU arrivi con un ritardo ragionevole: qualsiasi elemento che superi 1 secondo è sospetto e deve essere discusso con il provider, in genere arriva in meno di 100 ms.
* Se tutti questi passaggi funzionano, si può essere certi che il problema è sul lato del fornitore. Dovranno risolvere i problemi sulla loro piattaforma.
* Se funziona ma la velocità effettiva non è coerente, prova a regolare la finestra di invio e ad abbassare la velocità effettiva di MT. Per regolare l’impostazione, dovrai collaborare con il provider. Campaign può inviare messaggi molto rapidamente in modo che possano verificarsi problemi di prestazioni sull’apparecchiatura del provider.

#### MT sono duplicati (lo stesso SMS viene inviato più volte di fila)

I duplicati sono spesso causati da nuovi tentativi. È normale disporre di duplicati quando si ritenta il messaggio, pertanto è necessario concentrare gli sforzi sull’eliminazione della causa principale dei nuovi tentativi.

* Se vedi duplicati inviati a distanza di esattamente 60 secondi (o qualsiasi altro periodo sospettosamente &quot;regolare&quot;), è probabile che si tratti di un problema dal lato del provider, che non inviano un SUBMIT_SM_RESP abbastanza veloce.
* Se sono presenti molti BIND/UNBIND, la connessione è instabile: vedere la sezione [Problemi con connessioni instabili](#unstable-connections) per le soluzioni prima di tentare di risolvere i problemi relativi ai messaggi duplicati.
* Verificare che tutte le PDU SUBMIT_SM corrispondano a SUBMIT_SM_RESP poco dopo. Se non lo fanno o SUBMIT_SM_RESP sono troppo lenti, il problema è sul lato del provider.

Attenuazione della quantità di duplicati in caso di un nuovo tentativo:

* Abbassa la *finestra di invio*. La finestra di invio deve essere sufficientemente grande da coprire la latenza SUBMIT_SM_RESP, ma non troppo grande. Il valore rappresenta il numero massimo di messaggi che è possibile duplicare se si verifica un errore mentre la finestra è piena.

#### Problema durante l’elaborazione di SR (conferme di consegna)

* Per eseguire qualsiasi tipo di risoluzione dei problemi SR, è necessario abilitare le tracce SMPP.
* Verificare che la PDU DELIVER_SM provenga dal provider e che sia ben formata.
* Controlla che Campaign risponda con una PDU DELIVER_SM_RESP riuscita in modo tempestivo. Questo garantisce che l’SR sia stato inserito nella tabella providerMsgStatus per l’elaborazione differita dal processo SMS.

Se la PDU DELIVER_SM non viene riconosciuta correttamente, è necessario controllare alcuni elementi:

* Controlla la regex relativa all’estrazione degli ID e all’elaborazione degli errori nell’account esterno. Potrebbe essere necessario convalidarli in base al contenuto della PDU DELIVER_SM.
* Verifica che nella tabella broadLogMsg sia stato eseguito correttamente il provisioning degli errori (per ulteriori informazioni, consulta la documentazione di Campaign).

Se la PDU DELIVER_SM è stata confermata dal connettore SMPP esteso ACC ma il broadLog non viene aggiornato correttamente, controlla il processo di riconciliazione degli ID descritto nella sezione Precedente Corrispondenza tra le voci MT, SR e broadlog.

Se hai corretto tutto ma alcuni SR non validi si trovano ancora nei buffer del provider, puoi saltarli utilizzando l’opzione &quot;Conteggio conferme ID non valido&quot;. Questo deve essere usato con cautela e azzerato a 0 il più rapidamente possibile dopo la pulizia dei buffer.

Se l’elaborazione SR è lenta, prova a qualificare i messaggi di stato più comuni nella tabella BroadLogMsg.

Se vengono ricevuti solo alcuni messaggi SR ma non tutti, verificare che nessun altro sistema si connetta all&#39;account del provider, ad esempio un sistema di test. SR può essere indirizzato su qualsiasi connessione, quindi alcuni di essi possono essere indirizzati a questo altro sistema. Il provider potrebbe aiutarti a individuare la posizione di questo altro sistema che si connette all’account.

#### Problema durante l’elaborazione di MO (e quarantena/risposta automatica)

* Abilita le tracce SMPP durante i test. Se non si abilita TLS, è sempre meglio eseguire un&#39;acquisizione di rete durante la risoluzione dei problemi di MO per verificare che le PDU contengano le informazioni corrette e siano formattate correttamente.
* Quando acquisisci il traffico di rete o analizzi le tracce SMPP, assicurati di acquisire l’intera conversazione con il MO e il relativo messaggio MT di risposta (se è configurata una risposta).
* Se il MO (DELIVER_SM PDU) non viene visualizzato nelle tracce, è possibile essere certi che il problema si verifichi sul lato del provider. Dovranno risolvere i problemi sulla loro piattaforma.
* Se viene visualizzata la PDU DELIVER_SM, verifica che sia confermata da Campaign con una PDU DELIVER_SM_RESP riuscita (codice 0). Questo RESP garantisce che tutta la logica di elaborazione sia stata applicata da Campaign (risposta automatica e quarantena). In caso contrario, cerca un messaggio di errore nei registri di processo SMS.
* Se sono abilitate le risposte automatiche, verificare che SUBMIT_SM sia stato inviato al provider. In caso contrario, troverai sicuramente un messaggio di errore nei registri di processo degli SMS.
* Se la PDU SUBMIT_SM MT contenente la risposta si trova nelle tracce ma l’SMS non arriva al telefono cellulare, dovrai contattare il provider per assistenza sulla risoluzione dei problemi, perché il problema è probabilmente dalla loro parte.

#### Problema durante la preparazione della consegna che non esclude i destinatari in quarantena (messi in quarantena dalla funzione di risposta automatica)

* Verifica che il formato del numero di telefono sia esattamente lo stesso nella tabella di quarantena e nel registro di consegna. In caso contrario, vedere l&#39;impostazione &quot;Send full phone number&quot; (Invia numero di telefono completo) in alto se si verificano problemi con il prefisso più del formato del numero di telefono internazionale.
* Controlla codici brevi: si verificano delle esclusioni se il codice breve del destinatario è lo stesso definito nell’account esterno o se è vuoto (vuoto = qualsiasi codice breve). Se per l’intera istanza di Campaign viene utilizzato un solo codice breve, è più semplice lasciare vuoti tutti i campi &quot;codice breve&quot;.

#### Problemi di codifica  {#sms-encoding-issues}

I problemi di codifica sono frequenti negli SMS. Ecco alcuni passaggi di base.

**Passaggio 1: Contatta il provider**

Il provider è l’esperto che sa come funziona l’SMS. Contattali e vedi con loro cosa non va. Dovrebbero essere in grado di dirti se il problema è dalla loro parte o in Campaign. Se il problema è in Campaign, dovrebbero essere in grado di dirti esattamente quale campo non è corretto, il che aiuta enormemente.

**Passaggio 2: scopri cosa contiene il messaggio**

Dovrai sapere cosa c&#39;è nel tuo messaggio. Quella frase può sembrare facile, però non lo è. Unicode consente un numero talmente elevato di varianti per caratteri simili che Campaign non è in grado di gestirli tutti.

La causa più comune di problemi è il copia-incolla da un elaboratore di testi, che cambia i caratteri usuali in versioni corrette tipograficamente: spazi modificati in spazi unificatori, virgolette doppie modificate in virgolette di apertura e chiusura, meno segni modificati in vari tipi di trattini ...

Non copiare e incollare il messaggio durante il test, digitalo sempre direttamente nell’interfaccia.

**Non lasciarti intimidire da valori esadecimali**. Esadecimale sembra strano e innaturale, ma ha una qualità molto distinta: si può distinguere la differenza tra caratteri simili. Una L minuscola, una I maiuscola, O, 0, tutti i diversi tipi di virgolette, codifiche non latine o anche diversi tipi di spazi possono tutti avere lo stesso aspetto (o anche non essere visualizzati affatto). Esadecimale mostra tutto e aiuta a confrontare le cose.

Per convertire Unicode in esadecimale, è possibile utilizzare gli strumenti in linea.

**All&#39;apertura dei ticket** sui problemi di codifica, sia con il provider che con il supporto Campaign, **includi una versione esadecimale** di ciò che digiti e di ciò che visualizzi.

**Passaggio 3: sapere cosa inviare**

Determina la codifica che prevedi di utilizzare e cerca online la tabella dei caratteri corrispondente. Verifica che i caratteri che intendi inviare siano effettivamente disponibili nella tabella codici di destinazione. Verifica che il campo data_coding sia corretto e corrisponda a quello previsto da te e dal provider.

**Passaggio 4: scopri cosa hai effettivamente inviato**

Per visualizzare esattamente i byte inviati al provider, è necessario l&#39;output di debug del connettore. I problemi di codifica vengono visualizzati nelle PDU SUBMIT_SM, quindi assicurati di acquisirli. Invia messaggi molto distinti e facili da trovare nel registro.

Non esitare a inviare diversi tipi di caratteri speciali durante il test. Ad esempio, la codifica GSM7 dispone di caratteri estesi molto distinti nella loro forma esadecimale, che sono quindi facili da individuare perché non compaiono in nessun’altra codifica.

#### Problemi relativi alle prestazioni {#sms-performance-issues}

>[!NOTE]
>
>Le prestazioni sono un argomento molto ampio. Questa sezione fornisce alcuni controlli di base da eseguire prima di tentare di ridimensionare o eseguire altri grandi progetti.

**Problemi di prestazioni durante l&#39;invio di messaggi MT**

* Verifica che tutte le impostazioni nella sezione Throughput e ritardi dell’account esterno siano corrette e che corrispondano alle impostazioni consentite dal provider.
* Verifica che non siano presenti nuovi tentativi.
* Verificare che l&#39;infrastruttura del provider non sia saturata. Verificare la presenza di errori RMSGQFUL o RTHROTTLED nelle PDU RESP.
* Verificare le impostazioni di serverConf. Iniziare con i valori predefiniti e aumentare i parametri lentamente e uno alla volta.
* Controlla che il processo SMS non venga riavviato sempre quando è sotto carico. In caso contrario, potrebbe essere necessario aumentare *maxSMSMemoryMb*, *maxProcessMemoryAlertMb* e *maxProcessMemoryWarningMb* nel file serverConf.

**Problemi di prestazioni durante la ricezione di SR**

Se il provider lamenta un sovraccarico del buffer sul lato, è possibile che Campaign non riceva l’SR abbastanza velocemente.

* Verificare che il database dell&#39;istanza non sia sovraccarico. L&#39;elaborazione SR dipende molto dalle prestazioni del database.
* Chiedere al provider di aumentare la finestra di invio per DELIVER_SM. Idealmente dovrebbe essere grande quanto l&#39;impostazione *batchUpdateSize* in serverConf.

### Elementi da includere durante la comunicazione relativa a un problema SMS

Ogni volta che chiedi assistenza su un problema relativo agli SMS (che si tratti dell’apertura di un ticket di supporto ad Adobe Campaign, al provider SMS o di qualsiasi tipo di comunicazione sul problema), dovrai includere almeno le seguenti informazioni per assicurarti che sia adeguatamente qualificato. I problemi correttamente qualificati sono fondamentali per risolverli più rapidamente, pertanto dedicare un po’ più di tempo a comprendere la situazione e fornire informazioni significative porterà a un enorme salto in efficienza.

* Abilita i messaggi SMPP dettagliati quando viene visualizzato il problema. La maggior parte dei problemi relativi agli SMS sono praticamente impossibili da risolvere senza questo.
* Se il problema è relativo al traffico SMS, contatta prima il provider. Sono i più esperti e la loro piattaforma è solitamente adatta per una diagnosi efficiente dei problemi di traffico SMS in tempo reale.
* Includere una breve descrizione del problema.
* Includi una descrizione del risultato previsto.
* Includi tutti i feedback del provider.
* Includere registri e/o acquisizioni di rete pertinenti. Quando esegui le acquisizioni, assicurati di riprodurre il problema durante l’acquisizione, altrimenti sarà inutile.
* Se si includono registri, tracce o acquisizioni, individuare la posizione esatta nel file quando viene visualizzato il problema, nonché la posizione esatta di un esempio di lavoro, se presente. Le acquisizioni o le tracce possono essere grandi e noiose da esaminare, quindi è utile qualsiasi cosa aiuti a trovare informazioni al loro interno.
* Se fai riferimento a messaggi, PDU o registri, indica chiaramente il loro timestamp in modo che siano facili da trovare per gli altri.
* Prova a riprodurre il problema in un ambiente di test. Se non sei sicuro di un’impostazione, prova nell’ambiente di test e verifica il risultato con le tracce SMPP. In genere è meglio segnalare i problemi replicati negli ambienti di test piuttosto che segnalare direttamente i problemi negli ambienti di produzione.
* Includi eventuali modifiche apportate alla piattaforma: anche una piccola modifica può avere un impatto enorme. Inoltre, includi eventuali modifiche apportate dal provider al proprio lato.

#### Quando è utile l&#39;acquisizione di una rete?

L&#39;acquisizione di rete non è sempre necessaria. Molto spesso, i messaggi SMPP dettagliati sono sufficienti. Di seguito sono riportate alcune linee guida che consentono di determinare se un&#39;acquisizione di rete merita lo sforzo:

* Problemi di connessione, ma i messaggi dettagliati non mostrano alcuna PDU BIND_RESP.
* Disconnessioni inspiegabili senza messaggio di errore (questo è il comportamento del connettore quando rileva un errore di protocollo di basso livello).
* Il provider si lamenta del processo di separazione/disconnessione.
* Si sono verificati problemi di codifica nei campi TLV facoltativi.
* Si sospetta che il traffico sia misto tra connessioni diverse.

In tutte le altre situazioni, prova ad analizzare prima i messaggi SMPP dettagliati e a richiedere un’acquisizione di rete solo se è chiaro che mancano informazioni nei registri dettagliati.

#### Quando è inutile l&#39;acquisizione di una rete?

In alcuni casi, catturare il traffico di rete è inutile o semplicemente una perdita di tempo. Di seguito sono elencate le situazioni più comuni:

* TLS abilitato: per definizione, il traffico TLS è crittografato e non può essere acquisito.
* Problemi di prestazioni: i registri contengono tutte le informazioni necessarie per tracciare i problemi di prestazioni.
* Problemi di tempistica (tempo tentativi, periodo enquire_link, limite velocità effettiva, ecc.)
* Analisi ed elaborazione SR: i registri dettagliati forniscono molto più contesto e una presentazione migliore.
* Elaborazione MO (risposte automatiche, quarantena).
* Errori che non coinvolgono il traffico SMPP effettivo: preparazione della consegna, problemi API del Centro messaggi, problemi del flusso di lavoro, ...
