---
title: Note sulla versione v8 di Adobe Campaign
description: Early Campaign versione v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e873e945f7101c5c54b4b18a128951e08d329b87
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Note preliminari sulla versione {#e-new-release}

Questa pagina descrive miglioramenti e correzioni inclusi nella prossima versione di Campaign v8. Questo contenuto è soggetto a modifiche senza preavviso fino alla data di rilascio. Le note ufficiali sulla versione sono disponibili in questo [page](../start/release-notes.md).

## Versione 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> L’aggiornamento della console client è obbligatorio. Scopri come aggiornare la console client in questo [page](../start/connect.md#download-ac-console).

_7 ottobre 2022_

**Miglioramenti**

* È stato risolto un problema che influenzava gli aggiornamenti dello stato del registro di consegna sull’istanza MID, quando l’opzione FeatureFlag_GZIP_Compression era abilitata. (NEO-49183)
* La **Pulizia del database** il flusso di lavoro tecnico ora gestisce anche gli schemi di staging personalizzati. (NEO-48974)
* È stato risolto un problema che poteva causare il blocco delle consegne in **In sospeso** stato anche se è stata raggiunta la data di contatto. (NEO-48079, NEO-48251)
* È stata migliorata la stabilità durante la gestione di stringhe XML non valide durante le chiamate SOAP. (NEO-48027)
* È stato risolto un problema che poteva rallentare l’analisi della consegna, durante l’esclusione del passaggio dei destinatari inserita nell&#39;elenco Bloccati, quando si eseguiva il targeting di grandi volumi di destinatari. (NEO-48019)
* Per evitare la lentezza durante l’invio di prove agli indirizzi di seed, tutte le repliche consecutive dei membri di seed ora sono raggruppate in un’unica richiesta di replica. (NEO-44844)
* È stato risolto un problema che causava problemi di personalizzazione durante l’invio di messaggi SMS utilizzando una modalità di consegna esterna. (NEO-46415)
* È stato risolto un problema che causava la visualizzazione di un errore durante il tentativo di visualizzare l’anteprima di una consegna in qualsiasi evento archiviato del Centro messaggi . (NEO-43620)
* È stato risolto un problema nei flussi di lavoro che poteva impedire l’aggiornamento dei file sul server quando si utilizzava **Caricamento dati (file)** attività. Il processo si è interrotto al 100% ma non è mai terminato. (NEO-47269)
* È stato risolto un problema che causava la creazione di DeliveryParts non necessarie quando la consegna utilizzava il calendario e le modalità di suddivisione. (NEO-48634)
* È stato risolto un problema di prestazioni che si verificava durante l’utilizzo di ondate basate su calendario. (NEO-48451)
* È stato risolto un problema che poteva causare un messaggio di errore nella schermata dell’elenco di consegna dopo la creazione di una nuova mappatura di destinazione in uno schema personalizzato. (NEO-49237)
* È stato risolto un problema che poteva verificarsi se una consegna raggiungeva una dimensione specifica durante il processo MTA. (NEO-46097)
* È stato risolto un problema che impediva ai registri di tracciamento di restituire i dati relativi al browser del destinatario. (NEO-46612)
* È stato risolto un problema durante l’aggiornamento successivo negli ambienti giapponesi. (NEO-46640)
* È stato risolto un problema che si verificava con l’utilizzo di **Query** attività e filtraggio di una tabella. Quando un nome di colonna conteneva la parola &quot;Update&quot;, si è verificato un errore di compilazione con un identificatore non valido e il seguente messaggio: &quot;numero di righe aggiornate&quot;. (NEO-46485)
* È stato risolto un problema che impediva la **[!UICONTROL Replicate Staging data]** Il flusso di lavoro tecnico (ffdaReplicateStagingData) non viene interrotto anche quando si è verificato un errore durante la relativa esecuzione. (NEO-46280)
* È stato risolto un problema che poteva causare la perdita di dati se il flusso di lavoro di staging era in errore e il periodo di conservazione era completamente passato. (NEO-48975)
* È stato risolto un problema che si verificava durante l’inserimento di dati nel database cloud di Snowflake con una campagna **Query** attività e **Cambia origine dati** attività: il processo non riusciva quando nei dati è presente un carattere barra rovesciata. La stringa di origine non è preceduta dall&#39;escape e i dati non sono stati elaborati correttamente sul Snowflake. (NEO-45549)
