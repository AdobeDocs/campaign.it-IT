---
title: Note preliminari sulla versione di Campaign v8
description: Versione preliminare di Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e873e945f7101c5c54b4b18a128951e08d329b87
workflow-type: ht
source-wordcount: '472'
ht-degree: 100%

---

# Note preliminari sulla versione {#e-new-release}

Questa pagina descrive i miglioramenti e le correzioni inclusi nella prossima versione di Campaign v8. Questo contenuto è soggetto a modifiche senza preavviso fino alla data di rilascio. Le note ufficiali sulla versione sono disponibili in questa [pagina](../start/release-notes.md).

## Versione 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> L’aggiornamento della console client è obbligatorio. Scopri come aggiornare la Console client in questa [pagina](../start/connect.md#download-ac-console).

_7 ottobre 2022_

**Miglioramenti**

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
* È stato risolto un problema che si verificava se si utilizzava l’attività **Query** e si aplicava un filtro a una tabella. Se un nome di colonna conteneva la parola “Update”, si verificava un errore di compilazione con un identificatore non valido e un messaggio di tipo: “numero di righe aggiornate”. (NEO-46485)
* È stato risolto un problema che impediva al flusso di lavoro tecnico **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) di venire interrotto anche se si verificava un errore durante la relativa esecuzione. (NEO-46280)
* È stato risolto un problema che poteva causare la perdita di dati in caso di errore del flusso di lavoro di staging e periodo di conservazione completamente passato. (NEO-48975)
* È stato risolto un problema che si verificava durante l’inserimento di dati nel database cloud di Snowflake con un’attività **Query** e un’attività **Change Data Source** (Cambia origine dati) di Campaign: il processo non riusciva se nei dati era presente il carattere barra inversa. Alla stringa di origine non veniva applicato l’escape e i dati non venivano elaborati correttamente in Snowflake. (NEO-45549)
