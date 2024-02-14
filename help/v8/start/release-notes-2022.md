---
title: Note sulla versione di Campaign v8 2022
description: Elenco delle funzioni e dei miglioramenti introdotti con le versioni di Campaign v8 2022
feature: Release Notes
role: User
level: Beginner
exl-id: 76473fa5-48ba-42cf-8664-0dd197833a86
source-git-commit: 43994eb29af2b85272de0ce4dc34cc66aba2e04a
workflow-type: tm+mt
source-wordcount: '1919'
ht-degree: 91%

---

# Note sulla versione 2022{#2022-rn}

In questa pagina sono elencate le nuove funzionalità, i miglioramenti e le correzioni introdotte con le **versioni di Campaign v8 2022**.

## Versione 8.4.2 {#release-8-4-2}

_28 ottobre 2022_

**Correzioni**

* È stato risolto un problema che impediva l’aggiornamento corretto dell’indicatore di consegna riuscita quando si utilizzava l’MTA avanzato di Adobe Campaign. (NEO-50462)

## Versione 8.4.1 {#release-8-4-1}

_30 settembre 2022_

**Novità**

<table> 
<thead>
<tr> 
<th> <strong>Integrazione di Adobe Campaign con Adobe Experience Platform</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>Sono ora disponibili nuovi connettori di destinazione e origine per consentire un’integrazione fluida tra Adobe Campaign e Adobe Experience Platform:</p>
<ul><li>Utilizza il connettore di destinazione di Adobe Campaign Managed Cloud Services per inviare i segmenti di Experience Platform ad Adobe Campaign per l’attivazione.</li>
<li>Utilizza il connettore di origine di Adobe Campaign Managed Cloud Service per inviare i registri di consegna e tracciamento di Adobe Campaign ad Adobe Experience Platform.</li>
</ul>
<p>Per ulteriori informazioni, consulta la <a href="../connect/ac-aep.md">documentazione dettagliata</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Disponibilità del canale X (precedentemente noto come Twitter)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Il <a href="../send/twitter.md">Canale social X</a> è ora disponibile con Campaign v8. Puoi eseguire le seguenti azioni:</p>
<ul> 
<li><p>Inviare messaggi su X (precedentemente noto come Twitter): Adobe Campaign consente di inviare messaggi direttamente al tuo account X. Puoi anche inviare messaggi diretti a tutti i tuoi follower.
</p></li>
<li><p>Raccogliere nuovi contatti: Adobe Campaign può ripristinare automaticamente i dati del profilo, consentendo di eseguire campagne di targeting e implementare strategie cross-channel.
</p></li>
</ul>
<p>Scopri come collegare Campaign e X nel <a href="../connect/ac-tw.md">documentazione dettagliata</a>.</p>
<p>Scopri come creare post e inviare messaggi diretti con Campaign in <a href="../connect/ac-tw.md">questa pagina</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Miglioramento della sicurezza**

Per ottimizzare la sicurezza, i token di sicurezza sono stati rimossi dagli URL generati da Campaign:

* Questa modifica si applica solo agli URL delle richieste GET. Altri tipi, inclusi gli URL delle richieste POST, non subiscono modifiche.
* Se utilizzi un codice personalizzato, i token di sicurezza non vengono più recuperati dal parametro di protezione URL delle richieste GET. Devi generare un nuovo token di sicurezza utilizzando il seguente codice JSSP:

  ```getNewSecurityToken(jsspContext.getSessionToken(), jsspContext.getSecurityToken(), true);```

  Puoi anche utilizzare l’API di accesso per recuperare i token di sicurezza.
* Non vi è alcuna modifica nella gestione dei token di sessione.

**Miglioramenti**

* Dopo la fine del ciclo di vita di Internet Explorer 11, il motore di rendering HTML nella console utilizza ora **Microsoft Edge Chromium**. Inoltre, **Microsoft Edge WebView2 Runtime** è ora necessario per tute le installazioni della console client.
* È stata migliorata l’esecuzione dei flussi di lavoro con elevata disponibilità, che consente di eseguire flussi di lavoro simultanei tra contenitori diversi per evitare sia la perdita del servizio del flusso di lavoro sia i relativi errori di esecuzione. **Nota**: questa nuova funzionalità viene rilasciata solo in Disponibilità limitata a un set di clienti.
* Le richieste di privacy vengono ora eseguite in batch per uno specifico spazio dei nomi di privacy. Questo miglioramento aumenta il tempo di esecuzione per le richieste di eliminazione di dati relativi a GDPR e privacy.

**Aggiornamenti della compatibilità**

* L’SDK di Campaign v8 supporta ora iOS 16 per le notifiche push.

Consulta la [Matrice di compatibilità di Campaign](compatibility-matrix.md).

**Correzioni**

* È stato risolto un problema che interessava gli aggiornamenti dello stato del registro di consegna sull’istanza MID quando l’opzione FeatureFlag_GZIP_Compression era abilitata. (NEO-49183)
* È stato risolto un problema che avrebbe potuto bloccare le consegne sullo stato **In sospeso** anche se era stata raggiunta la data di contatto. (NEO-48079)
* È stato risolto un problema nei flussi di lavoro che poteva impedire l’aggiornamento dei file sul server quando si utilizzava l’attività **Caricamento dati (file)**. Il processo si è interrotto al 100% ma non è mai terminato. (NEO-47269)
* È stato risolto un problema durante il post-aggiornamento in ambienti giapponesi. (NEO-46640)
* È stato risolto un problema che poteva verificarsi se una consegna raggiungeva una dimensione precisa durante il processo MTA. (NEO-46097)
* È stato risolto un problema che impediva ai registri di tracciamento di restituire i dati relativi al browser del destinatario. (NEO-46612)
* È stato risolto un problema che causava problemi di personalizzazione durante l’invio di messaggi SMS utilizzando una modalità di consegna esterna. (NEO-46415)
* È stato risolto un problema che poteva generare duplicati nei registri di tracciamento. (NEO-46409)
* È stato risolto un problema che impediva al flusso di lavoro tecnico **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) di venire interrotto anche se si verificava un errore durante la relativa esecuzione. (NEO-46280)
* Per evitare rallentamenti durante l’invio di una bozza agli indirizzi seed, tutte le repliche consecutive dei membri di seed ora sono raggruppate in un’unica richiesta di replica. (NEO-44844)
* È stato risolto un problema che causava la visualizzazione di un errore durante il tentativo di visualizzare l’anteprima di una consegna negli eventi archiviati del Centro messaggi . (NEO-43620)
* È stato risolto un problema che si verificava durante l’inserimento di dati nel database cloud di Snowflake con un’attività **Query** e un’attività **Change Data Source** (Cambia origine dati) di Campaign: il processo non riusciva se nei dati era presente il carattere barra inversa. Alla stringa di origine non veniva applicato l’escape e i dati non venivano elaborati correttamente in Snowflake. (NEO-45549)
* È stato risolto un problema che si verificava se si utilizzava l’attività di **Query** e si aplicava un filtro a una tabella. Quando un nome di colonna conteneva la parola &quot;Update&quot;, si verificava un errore di compilazione con un identificatore non valido e un messaggio di tipo: &quot;numero di righe aggiornate&quot;. (NEO-46485)
* Il flusso di lavoro tecnico per la **pulizia del database** ora gestisce anche gli schemi di staging personalizzati. (NEO-48974)
* È stato risolto un problema che poteva rallentare l’analisi della consegna, durante il passaggio di esclusione dei destinatari inseriti nell’elenco Bloccati, se si eseguiva il targeting di volumi elevati di destinatari. (NEO-48019)
* È stata migliorata la stabilità durante la gestione di stringhe XML non valide durante le chiamate SOAP. (NEO-48027)
* È stato risolto un problema che causava la creazione di DeliveryParts non necessarie quando la consegna utilizzava le modalità calendario e suddivisione. (NEO-48634)
* È stato risolto un problema di prestazioni che si verificava durante l’utilizzo di scaglioni basati su calendario. (NEO-48451)
* È stato risolto un problema che poteva causare un messaggio di errore nella schermata dell’elenco di consegna dopo la creazione di una nuova mappatura di destinazione in uno schema personalizzato. (NEO-49237)
* È stato risolto un problema che poteva causare la perdita di dati in caso di errore del flusso di lavoro di staging e periodo di conservazione completamente passato. (NEO-48975)

## Versione 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> aggiornamento della console client obbligatorio. Scopri come aggiornare la console client in questo [pagina](../start/connect.md#download-ac-console).

_7 ottobre 2022_

**Correzioni**

* È stato risolto un problema che interessava gli aggiornamenti dello stato del registro di consegna sull’istanza MID quando l’opzione FeatureFlag_GZIP_Compression era abilitata. (NEO-49183)
* Il flusso di lavoro tecnico per la **pulizia del database** ora gestisce anche gli schemi di staging personalizzati. (NEO-48974)
* È stato risolto un problema che poteva bloccare le consegne sullo stato **In sospeso** anche se era stata raggiunta la data di contatto. (NEO-48079, NEO-48251)
* È stata migliorata la stabilità durante la gestione di stringhe XML non valide durante le chiamate SOAP. (NEO-48027)
* È stato risolto un problema che poteva rallentare l’analisi della consegna, durante il passaggio di esclusione dei destinatari inseriti nell’elenco Bloccati, se si eseguiva il targeting di volumi elevati di destinatari. (NEO-48019)
* Per evitare rallentamenti durante l’invio di una bozza agli indirizzi seed, tutte le repliche consecutive dei membri di seed ora sono raggruppate in un’unica richiesta di replica. (NEO-44844)
* È stato risolto un problema che causava problemi di personalizzazione durante l’invio di messaggi SMS utilizzando una modalità di consegna esterna. (NEO-46415)
* È stato risolto un problema che causava la visualizzazione di un errore durante il tentativo di visualizzare l’anteprima di una consegna negli eventi archiviati del Centro messaggi . (NEO-43620)
* È stato risolto un problema nei flussi di lavoro che poteva impedire l’aggiornamento dei file sul server quando si utilizzava l’attività **Caricamento dati (file)**. Il processo si è interrotto al 100% ma non è mai terminato. (NEO-47269)
* È stato risolto un problema che causava la creazione di DeliveryParts non necessarie quando la consegna utilizzava le modalità calendario e suddivisione. (NEO-48634)
* È stato risolto un problema di prestazioni che si verificava durante l’utilizzo di scaglioni basati su calendario. (NEO-48451)
* È stato risolto un problema che poteva causare un messaggio di errore nella schermata dell’elenco di consegna dopo la creazione di una nuova mappatura di destinazione in uno schema personalizzato. (NEO-49237)
* È stato risolto un problema che poteva verificarsi se una consegna raggiungeva una specifica dimensione durante il processo MTA. (NEO-46097)
* È stato risolto un problema che impediva ai registri di tracciamento di restituire i dati relativi al browser del destinatario. (NEO-46612)
* È stato risolto un problema durante il post-aggiornamento in ambienti giapponesi. (NEO-46640)
* È stato risolto un problema che si verificava se si utilizzava l’attività **Query** e si aplicava un filtro a una tabella. Quando un nome di colonna conteneva la parola &quot;Update&quot;, si verificava un errore di compilazione con un identificatore non valido e un messaggio di tipo: &quot;numero di righe aggiornate&quot;. (NEO-46485)
* È stato risolto un problema che impediva al flusso di lavoro tecnico **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) di venire interrotto anche se si verificava un errore durante la relativa esecuzione. (NEO-46280)
* È stato risolto un problema che poteva causare la perdita di dati in caso di errore del flusso di lavoro di staging e periodo di conservazione completamente passato. (NEO-48975)
* È stato risolto un problema che si verificava durante l’inserimento di dati nel database cloud di Snowflake con un’attività **Query** e un’attività **Change Data Source** (Cambia origine dati) di Campaign: il processo non riusciva se nei dati era presente il carattere barra inversa. Alla stringa di origine non veniva applicato l’escape e i dati non venivano elaborati correttamente in Snowflake. (NEO-45549)

## Versione 8.3.8 {#release-8-3-8}

_18 maggio 2022_

**Novità**

<table> 
<thead>
<tr> 
<th> <strong>Notifiche sensibili al tempo</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Con iOS 15, Apple ha aggiunto il concetto di “notifiche urgenti” che permette allo sviluppatore dell’app di ignorare la modalità di attivazione quando una notifica è considerata urgente e deve quindi raggiungere l’utente in tempo reale.</p>
<p>Per ulteriori informazioni, consulta la <a href="../send/push.md#send-notifications-on-ios">documentazione dettagliata</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Integrazione core Privacy Service</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Campaign v8 ora si integra con Adobe Privacy Core Service. Le richieste di accesso a dati personali inviate dal servizio core per la privacy a tutte le soluzioni Experience Cloud vengono gestite automaticamente da Campaign tramite un flusso di lavoro dedicato.</p>
<p>Per ulteriori informazioni, consulta la <a href="privacy.md">documentazione dettagliata</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table>
<thead>
<tr>
<th><strong>Gestione della risposta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Gestione della risposta di Campaign consente di misurare il successo e il ROI delle campagne di marketing o delle proposte di offerta su tutti i canali: e-mail, dispositivi mobili, direct mailing, ecc.</p>
<p>Per ulteriori informazioni, consulta la <a href="../start/campaigns.md#response-manager-add-on">documentazione dettagliata</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Marketing distribuito</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Marketing distribuito di Campaign consente di implementare campagne di collaborazione tra entità centrali (sedi centrali, dipartimenti di marketing, ecc.) e gli enti locali (punti vendita, agenzie regionali, ecc.). Tramite un’area di lavoro condivisa (pacchetti di campagne), puoi creare modelli di campagna e proporli alle entità locali.</p>
<p>Per ulteriori informazioni, consulta la <a href="../start/campaigns.md#distributed-marketing-add-on">documentazione dettagliata</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Aggiornamenti della compatibilità**

* L’SDK di Campaign v8 supporta ora Android 12 e iOS 15 per le notifiche push.
* Campaign v8 è ora compatibile con Windows 11.

Consulta la [Matrice di compatibilità di Campaign](compatibility-matrix.md).

**Miglioramenti**

* L’autenticazione di Microsoft Exchange Online OAuth 2.0 per POP3 è ora supportata in Campaign. [Maggiori informazioni](../config/external-accounts.md#bounce-mails-external-account)
* Sono state applicate correzioni critiche relative all’API web di Microsoft Dynamics Connector.
* È stato aggiunto il nuovo diritto di scrittura dello schema di operatore e gruppo (operatorWrite) denominato per consentire agli utenti di inserire, aggiornare ed eliminare gli schemi Operatori (xtk:operator) e Gruppi di operatori (xtk:group).
  <!--* You can now enable the Email BCC (blind carbon copy) capability to store emails sent by Campaign at the delivery level, through the dedicated option in the delivery properties. [Read more](../config/email-settings.md#email-bcc)-->
  <!--* To ensure better performances, a new "Split" option is now activated by default in the Routing external account. This option allows messages to be automatically split across your mid-sourcing instances in order to be delivered faster to the recipients.-->
* È ora possibile configurare più account attivi LINE su un singolo mid-sourcing.
* Il numero di connessioni predefinite per il processo web è stato aumentato da 50 a 150.
* Campaign viene fornito con un set di nuovi guardrail per impedire l’inserimento di chiavi duplicate nel database di Snowflake. [Maggiori informazioni](../architecture/keys.md)

**Correzioni**

* È stato risolto un problema che si verificava durante l’utilizzo di seed e gruppi di controllo nella stessa consegna ricorrente. (NEO-41197)
* È stato risolto un problema su FFDA che causava il blocco dell’invio di e-mail per tutti i destinatari appartenenti alla stessa deliveryPart durante il processo di invio (fino a 256) quando i blocchi di personalizzazione contenevano uno dei seguenti caratteri: `' & < > "`. Questi caratteri ora sono supportati nei blocchi di personalizzazione (ad esempio: nome=“Brian O&#39;Neil”). (NEO-43184)
* È stato risolto un problema che poteva causare un errore nel flusso di lavoro di tracciamento quando si utilizzava uno schema personalizzato come mappatura di destinazione. Ora assicuriamo che il tipo di collegamento esterno a uno schema di targeting personalizzato sia corretto durante la generazione dello schema broadLog tramite la procedura guidata di mappatura di destinazione. (NEO-43506)
* È stato risolto un problema che poteva causare il mancato funzionamento dei flussi di lavoro di distribuzione FFDA per lingue diverse dall’inglese. (NEO-44561)

## Versione 8.2.10 {#release-8-2-10}

_2 febbraio 2022_

**Correzioni**

* È stato risolto un problema che causava un errore nella preparazione della consegna se veniva raggiunto il numero massimo di messaggi, definito nella regola di tipologia.
* È stato risolto un problema che si verificava durante la configurazione del connettore Adobe Analytics se l’indirizzo e-mail conteneva un carattere “s”.
* È stato risolto un problema che si verificava durante il post aggiornamento e poteva causare la perdita di dati della tabella deliveryMapping da una mappatura di consegna personalizzata.
* È stato risolto un problema a causa del quale i destinatari potevano ricevere lo stesso messaggio più volte per la stessa consegna se l’indirizzo e-mail conteneva una virgoletta singola (&#39;). Questo carattere ora viene preceduto da un carattere di escape. (NEO-41198)
* È stato risolto un problema di generazione ID che si verificava durante l’invio di bozze con indirizzi seed o sostitutivi. (NEO-42637)
* È stato risolto un problema che poteva impedire l’invio di bozze utilizzando il metodo di sostituzione dell’indirizzo. (NEO-40417)
* È stato risolto un problema che impediva l’installazione del pacchetto LINE. (NEO-42503)
