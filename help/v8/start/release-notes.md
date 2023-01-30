---
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: e7f4982a9b13fe5413b6cce0a1cc58e2b3a6afa4
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 34%

---

# Ultima versione{#latest-release}

In questa pagina sono elencate nuove funzionalità, miglioramenti e correzioni introdotti con l’**ultima versione di Campaign v8**.

## Versione 8.4.3 {#release-8-4-3}

>[!CAUTION]
>
> L’aggiornamento della console client è obbligatorio. Scopri come aggiornare la console client in questa [pagina](../start/connect.md#download-ac-console).

_27 gennaio 2023_

**Miglioramenti**

* È stato risolto un problema di sincronizzazione dell’indicatore di consegna tra il server di marketing e il server di mid-sourcing . (NEO-50724) <!--OKKKK-->
* È stato risolto un problema che poteva causare un errore durante l’esportazione di un flusso di lavoro. (NEO-50555) <!--OKKKK-->
* È stato risolto un problema che si verificava durante l’estensione di uno schema precedentemente esteso. (NEO-49118) <!--OKKKK-->
* È stato risolto un problema che si verificava durante l’utilizzo di due attività di arricchimento con lo stesso identificatore nella definizione del collegamento. (NEO-48851)
* Sono stati risolti due problemi di preparazione della consegna. La preparazione della consegna potrebbe non riuscire quando il numero di offerte potenziali manipolate era troppo alto. Il secondo problema si verificava quando gli URL immagine venivano definiti come URL da monitorare in una consegna in formato testo. (NEO-48807) <!--OKKKK-->
* È stato risolto un problema che poteva causare un errore del flusso di lavoro a causa del quale un flusso di lavoro sovrascriveva il nome del warehouse definito nell&#39;account esterno per gli account non FFDA. (NEO-43209) <!--OKKKK-->
* Maggiore sicurezza sulle applicazioni web per prevenire attacchi DDoS. (NEO-50757) <!--OKKKK-->
* La gestione dei dati di tracciamento consolidati è stata migliorata nel **[!UICONTROL Consolidated tracking]** (nms:trackingStats) Tabella FFDA per evitare duplicati. (NEO-46409)
* È stato risolto un problema relativo all’operatore logico nelle query del flusso di lavoro quando si utilizza un `enableIf` in una condizione di operatore logico. La condizione logica precedente è stata sovrascritta. (NEO-45815)  <!--OKKKK-->
* La generazione di profili attivi è stata ottimizzata nel flusso di lavoro di fatturazione per migliorare le prestazioni. (NEO-47658) <!--OKKKK-->
* È stato risolto un problema relativo all’importazione di file HTML quando i nodi immagine (img) contenevano URL con campi di personalizzazione. (NEO-48396)
* È stato risolto un problema relativo al Snowflake (tutte le distribuzioni) quando si utilizzava il parametro di ordinamento in un **Divisione** attività del flusso di lavoro. (NEO-45899) <!--OKKKK-->
* È stato risolto un problema che causava un errore quando un utente con diritti di accesso in lettura nella cartella nmsDeliveryMapping tentava di eseguire una campagna o un flusso di lavoro. (NEO-48230)
* È stato risolto un problema di prestazioni nella scheda HTML di una consegna che poteva verificarsi in caso di un codice HTML di grandi dimensioni. (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* È stato risolto un problema che impediva agli utenti di utilizzare **Unisci righe selezionate** opzione del flusso di lavoro. (NEO-48488)
* È stato risolto un problema sul connettore FDA del Snowflake che causava la perdita dei record quando si utilizzava l’opzione &quot;0 o 1 cardinalità join semplice&quot; durante l’arricchimento. (NEO-48737)
* I riferimenti rimanenti alla libreria log4j sono stati rimossi dall’installazione di Campaign su Windows. (NEO-44851)
* È stato risolto un problema che poteva causare un errore durante l’aggiunta dell’indicatore **Destinatari che hanno aperto** (estimatedRecipientOpen) nei dati aggiuntivi di un’attività del flusso di lavoro **Query**. (NEO-46665)
* La gestione degli URL di tracciamento è stata migliorata nei flussi di lavoro con più consegne per migliorare le prestazioni. (NEO-50894) <!--OKKKK-->
* È stato risolto un problema che poteva impedire la replica degli schemi che utilizzano Xtkfolder. (NEO-46787) <!--OKKKK-->
* È stato risolto un problema che poteva causare l’eliminazione della colonna personalizzata &quot;lastModified&quot; nella tabella NmsSubscription. (NEO-48402)
