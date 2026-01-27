---
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 6693bb8a62c0d126b871dc24a75b76de71b86f8d
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 21%

---

# Versioni più recenti {#latest-release}

In questa pagina sono elencate le nuove funzionalità, i miglioramenti e le correzioni introdotte con le **versioni più recenti** di Campaign v8 (console). Ulteriori informazioni sulle versioni e gli aggiornamenti di Campaign sono disponibili in [questa pagina](upgrades.md). Altre versioni sono elencate nella sezione Versioni precedenti di questa documentazione.

## Versione 8.9.1 {#release-8-9-1}

_27 gennaio 2026_

>[!CAUTION]
>
> L’aggiornamento della console client è obbligatorio. Scopri come aggiornare la console client in questa [pagina](../start/connect.md#upgrade-ac-console).

### Nuove funzioni {#new-8-9-1}

Il **nuovo connettore di invio SMS** è ora disponibile per tutti i clienti (GA). Consulta la [documentazione dettagliata](../send/sms/sms.md).

Questa versione include una serie di funzionalità disponibili con l’interfaccia utente di Campaign Web:

* [Funzionalità di consegna multilingue (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}
* [Arricchimento profilo nei messaggi transazionali (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Adobe Experience Manager Live e copie per lingua](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html){target="_blank"}
* [Esperimenti di contenuto - Test A/B](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html)
* [Attività di consegna continua](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html)
* [Gestione approvazione campagna](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html)

Consulta le [note sulla versione](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=it){target="_blank"} dell’interfaccia utente di Campaign Web

### Miglioramenti di sicurezza {#security-8-9-1}

* Gli account esterni di Snowflake ora supportano l’autenticazione OAuth2, fornendo metodi di autenticazione moderni e sicuri per le connessioni federate di accesso ai dati. (NEO-87013)
* Sono state corrette le vulnerabilità di accesso ai file del flusso di lavoro limitando le operazioni alle directory autorizzate, impedendo l’accesso non autorizzato e la potenziale esecuzione di codice remoto. (NEO-88460)
* È stato aggiunto l’URL FTP, che consente di inserire nell&#39;elenco Consentiti controlli alle attività del codice JavaScript del flusso di lavoro, limitando le connessioni FTP in uscita solo agli indirizzi autorizzati. (NEO-89083)

### Altre modifiche {#changes-8-9-1}

* È stata migliorata la gestione della memoria contenitore implementando la limitazione automatica del flusso di lavoro in condizioni di memoria elevata, con funzionalità di riavvio intelligente del flusso di lavoro e guardrail di memoria per i processi non critici. (NEO-89041)
* È stato aggiunto il supporto per funzioni di crittografia e decrittografia asimmetriche nei flussi di lavoro di Campaign. (NEO-80257)
* Prestazioni migliorate dell’agente di replica e resilienza della memoria per caricamenti di dati di grandi dimensioni nelle implementazioni FFDA. (NEO-88430)


### Correzioni {#fixes-8-9-1}

* È stato risolto un problema che causava la visualizzazione di conteggi errati nei report dinamici in caso di raggruppamento per determinate colonne. (NEO-86898)
* Sono state risolte le discrepanze di dati tra i rapporti dinamici e i dati effettivi della campagna. (NEO-88068)
* Sono stati risolti dei problemi di concatenazione con i tipi di campo &quot;char&quot; PostgreSQL che causavano risultati imprevisti nelle query. (NEO-87769)
* È stato corretto un problema a causa del quale il comando logInfo di JavaScript non gestiva correttamente alcuni parametri. (NEO-88263)
* Risoluzione dei problemi di blocco della sincronizzazione nell&#39;elaborazione degli eventi in tempo reale del Centro messaggi. (NEO-88330)
* È stato risolto un problema che causava la riformattazione automatica del contenuto HTML da parte dell’Editor visivo, con conseguenti modifiche al layout. (NEO-88409)
* È stato corretto un problema a causa del quale l’attività Deduplication non funzionava correttamente con gli schemi temporanei. (NEO-88577)
* È stato risolto un problema che impediva la generazione di indirizzi seed durante l’invio delle bozze. (NEO-88720)
* Sono state migliorate le prestazioni delle query PostgreSQL ottimizzando la gestione delle colonne di partizione. (NEO-88771)
* È stato risolto un problema a causa del quale le attività di trasferimento file non gestivano correttamente i caratteri di continuazione riga. (NEO-88812)
* Ottimizzazione delle query PostgreSQL migliorata per prestazioni migliori in set di dati di grandi dimensioni. (NEO-88885)
* È stato corretto un errore di tipo &quot;Autorizzazione negata&quot; che impediva l’apertura di campagne ibride. (NEO-88955)
* Supporto esteso della funzione codice a barre per gestire stringhe di testo più lunghe. (NEO-88958)
* È stato corretto un errore nei registri della campagna che si verificava durante l’utilizzo di bozze con consegne ricorrenti. (NEO-88976)
* È stato risolto un problema che, in alcuni scenari, interessava le operazioni di invio di e-mail. (NEO-89019)
* È stato risolto un problema che causava la modifica imprevista della modalità di avvio del flusso di lavoro da Immediata a Normale. (NEO-89025)
* Sono stati corretti gli errori che si verificavano durante l’esecuzione dell’attività Update Data in condizioni specifiche. (NEO-89031)
* È stato risolto un problema che causava la perdita di metadati dello schema personalizzato da parte dell’attività Update Data (Aggiorna dati). (NEO-89056)
* È stato corretto un errore di convalida che si verificava durante la preparazione della consegna. (NEO-89063)
* È stata risolta la generazione di istruzioni SQL non valide quando le query contenevano filtri sulle relazioni di collegamento 1-1. (NEO-89065)
* È stato risolto un problema a causa del quale l’attività Incremental Query non rispettava il limite di dimensioni configurato. (NEO-89066)
* Sono state migliorate le prestazioni del flusso di lavoro nelle implementazioni FFDA per le operazioni su larga scala. (NEO-89098)
* Gestione della memoria e stabilità migliorate per i processi di workflow. (NEO-89105)
* È stata abilitata la convalida rigorosa delle colonne per i moduli web per evitare incoerenze nei dati. (NEO-89111)
* Sono stati risolti i problemi di sincronizzazione del Centro messaggi che causavano ritardi di elaborazione. (NEO-89138)
* Sono stati corretti degli errori nel flusso di lavoro &quot;Aggiorna per il recapito messaggi&quot; che impedivano la corretta esecuzione. (NEO-89160)
* Sono stati corretti gli errori che si verificavano durante l’esecuzione di attività di codice JavaScript nei flussi di lavoro. (NEO-89169)
* Sono state rimosse le configurazioni di warehouse Snowflake hardcoded per consentire le impostazioni account esterne corrette. (NEO-89201)
* Sono stati corretti 403 errori di tipo Non consentito che si verificavano durante le operazioni di trasferimento dei file del flusso di lavoro. (NEO-89226)
* Sono state ottimizzate le query lente nella tabella dei destinatari nelle distribuzioni FFDA. (NEO-89268)
* È stato risolto un problema a causa del quale le attività di query incrementali ignoravano le pianificazioni configurate. (NEO-89317)
* Sono stati risolti gli errori di accesso che si verificavano all’apertura delle campagne in ambienti ibridi. (NEO-89320)
