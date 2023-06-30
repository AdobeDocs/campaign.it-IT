---
title: Utilizzare Campaign e i database esterni (FDA)
description: Scopri come utilizzare Campaign e i database esterni
feature: Federated Data Access
role: Admin
level: Beginner, Intermediate
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 1%

---

# Federated Data Access (FDA){#gs-fda}

Utilizza il connettore FDA (Federated Data Access) per collegare Campaign a uno o più **database esterni** ed elabora le informazioni in essi memorizzate senza influire sui dati del database cloud di Campaign. Puoi quindi accedere ai dati esterni senza modificare la struttura dei dati di Adobe Campaign.

![](../assets/do-not-localize/speech.png) In qualità di utente di Managed Cloud Services, [Adobe di contatto](../start/campaign-faq.md#support) per collegare i database esterni a Campaign.


>[!NOTE]
>
>* I database compatibili per Federated Data Access sono elencati nella [Matrice di compatibilità](../start/compatibility-matrix.md).
>
>* Nell&#39;ambito di una [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), è disponibile un account esterno specifico per gestire la comunicazione tra il database locale di Campaign e il database cloud di Snowflake. Questo account esterno è configurato per te da Adobe e **non deve** essere modificata.
>


## Best practice e limitazioni

L’opzione FDA è soggetta alle limitazioni del sistema di database di terze parti utilizzato.

Inoltre, tieni presente le seguenti limitazioni e best practice:

* L’opzione FDA consente di manipolare i dati in database esterni in modalità batch nei flussi di lavoro. Per evitare problemi di prestazioni, si sconsiglia di utilizzare il modulo FDA nel contesto di operazioni unitarie, come: personalizzazione, interazione, messaggistica in tempo reale, ecc.

* Evita le operazioni che devono utilizzare il più possibile sia Adobe Campaign che il database esterno. A questo scopo, puoi:

   * Esporta il database di Adobe Campaign nel database esterno ed esegui le operazioni solo dal database esterno prima di reimportare i risultati in Adobe Campaign.

   * Raccogli i dati dal database esterno di Adobe Campaign ed esegui le operazioni localmente.

  Se desideri eseguire la personalizzazione nelle consegne utilizzando i dati del database esterno, raccogli i dati da utilizzare in un flusso di lavoro per renderli disponibili in una tabella temporanea. Quindi utilizza i dati della tabella temporanea per personalizzare la consegna. Per eseguire questa operazione, pre-elabora la personalizzazione dei messaggi in un flusso di lavoro dedicato utilizzando **[!UICONTROL Prepare the personalization data with a workflow]** , disponibile nella **[!UICONTROL Analysis]** delle proprietà di consegna. Durante l’analisi della consegna, questa opzione crea ed esegue automaticamente un flusso di lavoro che memorizza tutti i dati collegati alla destinazione in una tabella temporanea, inclusi i dati di tabelle collegate in un database esterno.

  >[!CAUTION]
  >
  >Questa opzione migliora notevolmente le prestazioni durante l’esecuzione del passaggio di personalizzazione.


## Utilizzare dati esterni in un flusso di lavoro

Campaign viene fornito con diverse attività del flusso di lavoro che puoi utilizzare per interagire con i dati dei tuoi database esterni:

* **Filtrare in base a dati esterni** - Utilizza il **[!UICONTROL Query]** attività per aggiungere dati esterni e utilizzarli nelle configurazioni dei filtri definite.

* **Crea sottoinsiemi** - Utilizza il **[!UICONTROL Split]** attività per creare sottoinsiemi. Puoi utilizzare dati esterni per definire i criteri di filtro da utilizzare.

* **Carica database esterno** : utilizza i dati esterni nelle **[!UICONTROL Data loading (RDBMS)]** attività.

* **Aggiunta di informazioni e collegamenti** - Utilizza il **[!UICONTROL Enrichment]** attività per aggiungere dati aggiuntivi alla tabella di lavoro del flusso di lavoro e collegamenti a una tabella esterna. In questo contesto, può utilizzare dati provenienti da un database esterno.

Puoi anche definire direttamente una connessione a un database esterno da tutte le attività del flusso di lavoro elencate in precedenza, per un utilizzo temporaneo. In questo caso, si troverà in un database esterno locale, da utilizzare solo all’interno del flusso di lavoro corrente.

>[!CAUTION]
>
>Questo tipo di configurazione deve essere utilizzato solo temporaneamente per raccogliere dati. La configurazione dell’account esterno deve essere preferita per qualsiasi altro utilizzo.

Ad esempio, nel **[!UICONTROL Query]** attività, è possibile definire una connessione temporanea a un database esterno nel modo seguente:

1. Apri l’attività e fai clic su **[!UICONTROL Add data...]**
1. Seleziona la **[!UICONTROL External data]** opzioni
1. Seleziona la **[!UICONTROL Locally defining the data source]** opzione
1. Selezionare il motore di database di destinazione nell&#39;elenco a discesa. Immettere il nome del server e fornire i parametri di autenticazione. Specificare inoltre il nome del database esterno.
1. Selezionare la tabella in cui vengono memorizzati i dati. È possibile immettere il nome della tabella direttamente nel campo corrispondente oppure fare clic sull&#39;icona di modifica per accedere all&#39;elenco delle tabelle del database.
1. Fai clic su **[!UICONTROL Add]** per definire uno o più campi di riconciliazione tra i dati del database esterno e i dati nel database di Adobe Campaign. Il **[!UICONTROL Edit expression]** icone del **[!UICONTROL Remote field]** e **[!UICONTROL Local field]** consente di accedere all&#39;elenco dei campi di ciascuna tabella.
1. Se necessario, specifica una condizione di filtro e la modalità di ordinamento dei dati.
1. Selezionare i dati aggiuntivi da raccogliere nel database esterno. A questo scopo, fai doppio clic sui campi che desideri aggiungere per visualizzarli nel **[!UICONTROL Output columns]**.
1. Clic **[!UICONTROL Finish]** per confermare questa configurazione.
