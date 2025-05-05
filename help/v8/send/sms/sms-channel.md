---
title: Caratteristiche del canale SMS
description: Scopri le caratteristiche del canale SMS
feature: SMS
role: User
level: Intermediate
badge: label="Disponibilità limitata" type="Informative"
source-git-commit: 36bb1e2c9e2391065360c3cd2ad97612373ec0c2
workflow-type: tm+mt
source-wordcount: '1365'
ht-degree: 1%

---


# Caratteristiche del canale SMS {#sms-channel}

>[!IMPORTANT]
>
>Questa documentazione è per Adobe Campaign v8.7.2 e versioni successive.
>
>Per le versioni precedenti, leggere la documentazione di [Campaign Classic v7](https://experienceleague.adobe.com/it/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol).


## Tipi di SMS {#sms-types}

Quando invii SMS tramite un provider SMS, incontrerai 3 diversi tipi di SMS:

* **SMS MT (Mobile Terminated)**: si tratta di un SMS emesso da Adobe Campaign nei confronti di telefoni cellulari tramite il provider SMPP.
* **SMS MO (Originato da dispositivo mobile)**: si tratta di un SMS inviato da un dispositivo mobile ad Adobe Campaign tramite il provider SMPP.
* **SMS SR (Status Report) o DR o DLR (Delivery Receipt)**: si tratta di una ricevuta di ritorno inviata dal dispositivo mobile ad Adobe Campaign tramite il provider SMPP che indica che l&#39;SMS è stato ricevuto correttamente. Adobe Campaign può anche ricevere messaggi SR che indicano che il messaggio non può essere consegnato, spesso con una descrizione dell’errore.

È necessario distinguere tra conferme (PDU RESP, parte del protocollo SMPP) e SR. Un messaggio SR è una sorta di SMS inviato tramite la rete end-to-end, mentre un riconoscimento è solo una conferma del successo di un trasferimento.

Sia le conferme che l’SR possono attivare gli errori, distinguendo tra i due sarà utile per la risoluzione dei problemi.

### Informazioni trasmesse da un SMS  {#sms-info}

Un SMS trasporta più informazioni che testo. Di seguito un elenco di ciò che puoi aspettarti di trovare in un SMS:

* Il testo, che è limitato a 140 byte, che significa tra 70 e 160 caratteri a seconda della codifica. Consulta [Codifica testo SMS](#sms-text-encoding) di seguito per dettagli e limitazioni.
* Un indirizzo del destinatario, talvolta denominato ADC o MSISDN (il nome tecnico per &quot;numero di telefono&quot;). Questo è il numero del cellulare che riceverà l&#39;SMS.
* Un indirizzo del mittente, che può essere chiamato oADC o talvolta ID mittente. Può essere un numero di telefono (nell’uso quotidiano), un codice breve (quando inviato tramite un provider) o un nome (questa è una funzione facoltativa, in tal caso non è possibile rispondere all’SMS).
* Un flag per indicare se il messaggio è un messaggio flash (un messaggio flash è un pop-up non memorizzato)
* Un flag per indicare se è previsto o meno un messaggio SR.
* Una data di validità, dopo la quale nessuna apparecchiatura di rete può riprovare (non sempre presente o rispettata).
* Campo data_coding, che indica la codifica del testo.

## Codifica testo SMS {#sms-text-encoding}

>[!IMPORTANT]
>
>La codifica degli SMS è un argomento vasto e complesso con molte trappole e implementazioni non conformi!

La prima regola è **contatta sempre il provider SMPP in caso di problemi di codifica**. Solo loro hanno una conoscenza precisa della codifica supportata e regole speciali che possono essere applicate a causa di limitazioni nella piattaforma tecnica. Assicurati che verifichino ciò che gli invii e ciò che ti inviano, poiché è l’unica strada per un’interconnessione stabile e di successo.

I messaggi SMS utilizzano una speciale codifica a 7 bit, spesso denominata codifica GSM7.  Wikipedia ha [un buon articolo su di esso (GSM 03.38 in inglese)](https://en.wikipedia.org/wiki/GSM_03.38).

Nel protocollo SMPP, il testo GSM7 verrà espanso a 8 bit per carattere per facilitare la risoluzione dei problemi. SMSC lo impacchetterà in 7 bit per carattere prima di inviarlo al dispositivo mobile. Ciò significa che il campo short_message dell’SMS può avere una lunghezza massima di 160 byte nel frame SMPP, mentre è limitato a 140 byte quando viene inviato sulla rete mobile (il bit più significativo viene semplicemente scartato).

In caso di problemi di codifica, ecco alcuni aspetti importanti da verificare:
* Innanzitutto, assicurati di sapere quali caratteri appartengono a quale codifica. GSM7 è tristemente noto per il suo parziale supporto dei segni diacritici (accenti). Soprattutto in francese, dove è ed è fanno parte del GSM7, ma ê, â o ï non lo sono. Lo stesso vale per lo spagnolo.
* La C con cediglia (ç) è presente solo in maiuscolo nell’alfabeto GSM7, ma alcuni telefoni la rendono in minuscolo o con caratteri &quot;intelligenti&quot;: il consiglio generale è di evitarla completamente e rimuovere la cediglia (è ancora molto leggibile in francese) o passare a UCS-2.
* **Non utilizzare ASCII negli SMS.** a meno che non sia esplicitamente richiesto dal provider SMPP: questa codifica spreca spazio perché contiene caratteri a 8 bit e una copertura inferiore rispetto a GSM7. Questa codifica può essere richiesta per le reti CDMA (utilizzate in Nord America).
* Latin-1 non è sempre supportato. Verifica la compatibilità con il provider SMPP prima di tentare di utilizzare Latin-1.
* Le tabelle di cambio della lingua nazionale non sono supportate dal connettore Adobe Campaign. Al suo posto, utilizza UCS-2 o un altro codice_dati.
* Le unità UCS-2 e UTF-16 sono spesso combinate dai telefoni. Questo è un problema per le persone che inviano emoji e altri caratteri raramente utilizzati non presenti in UCS-2.
* Gli unici telefoni meno recenti non dispongono di glifi font per tutti i caratteri UCS-2. Gli smartphone più recenti tendono a essere in grado di mostrare caratteri rari piuttosto facilmente, gli smartphone più vecchi spesso mancano di molte emoji, e i telefoni con caratteristiche molto vecchie in genere hanno un supporto limitato a ciò che è utile nella lingua nativa del paese in cui sono stati acquistati. Se desideri utilizzare emoji o ASCII-art di qualche tipo, testalo su un&#39;ampia varietà di telefoni prima di inviarlo. L’anteprima della campagna non simula i glifi mancanti e mostra tutti i simboli disponibili sul browser web per l’anteprima.

Il campo *data_coding* indica la codifica utilizzata. Un problema importante è che il valore 0 indica *la codifica SMSC predefinita* nella specifica, in generale significa GSM7, ma non sempre è così. Rivolgiti al provider SMPP per sapere quale codifica è associata a data_coding = 0. Altri valori data_coding tendono a seguire le specifiche, ma l’unico modo per essere sicuri è quello di verificare con il provider SMPP.

La dimensione massima di un messaggio dipende dalla relativa codifica. Questa tabella riassume tutte le informazioni pertinenti:

| Codifica | Data_coding abituale | Dimensione del messaggio (caratteri) | Dimensione parte per SMS in più parti | Caratteri disponibili |
|:-:|:-:|:-:|:-:|:-:|  
| GSM7 | 0 | 160 | 152 | Set di caratteri di base GSM7 + estensione (i caratteri estesi contengono 2 caratteri) |
| Latin-1 | 3 | 140 | 134 | ISO-8859-1 |
| UCS-2 UTF-16 | 8 | 70 | 67 | Unicode (varia da telefono a telefono) |

## SMS multipart (SMS lunghi) {#multipart-sms}

Gli SMS multipart (spesso denominati SMS lunghi) sono SMS inviati in più parti. A causa di limitazioni tecniche nel protocollo di rete mobile, un SMS non può avere dimensioni superiori a 140 byte (consulta la sezione seguente relativa alla codifica del testo SMS per il numero di caratteri che possono rientrare in un SMS), pertanto è necessario dividere i messaggi più lunghi.

Ogni parte di un messaggio lungo è un singolo SMS. Questi componenti viaggiano in modo indipendente sulla rete e sono assemblati dal telefono cellulare ricevente. Per gestire in modo corretto i nuovi tentativi e i problemi di connettività, Campaign invia le parti in ordine inverso e richiede un SR solo sulla prima parte del messaggio (quella inviata per ultima); poiché il telefono cellulare visualizza un messaggio solo quando ha ricevuto la prima parte, i nuovi tentativi su parti aggiuntive non produrranno duplicati sul telefono cellulare.

È possibile impostare il numero massimo di SMS per messaggio per consegna utilizzando l’impostazione Numero massimo di SMS per messaggio nel modello di consegna. I messaggi che superano questo limite non riusciranno durante l’invio con un SMS che presenta un motivo di errore troppo lungo.

Sono disponibili 2 modi per inviare SMS lunghi:

* UDH
* message_payload

L’UDH è il metodo predefinito e consigliato per l’invio di messaggi lunghi. In questa modalità, il connettore divide il messaggio in più PDU SUBMIT_SM contenenti informazioni UDH. Questo protocollo è quello utilizzato dagli stessi telefoni cellulari, il che significa che Campaign ha il maggiore controllo sulla generazione dei messaggi, rendendola in grado di calcolare esattamente quante parti sono state inviate e come sono state divise.

*message_payload* è un modo per inviare l&#39;intero messaggio lungo in una singola PDU SUBMIT_SM. Il provider dovrà suddividerlo, il che significa che per Campaign è impossibile sapere esattamente quante parti sono state inviate. Alcuni provider richiedono questa modalità, ma la utilizzano solo se non supportano l&#39;UDH.

Per ulteriori dettagli sul protocollo e sui formati, consulta la descrizione dei campi esm_class, short_message e message_payload della PDU SUBMIT_SM riportata sopra.

>[!NOTE]
>
>Adobe Campaign supporta sia UDH che message_payload per l’invio, ma supporta solo message_payload per gli SMS in arrivo (MO).