---
title: Utilizzare Campaign e i database esterni (FDA)
description: Scopri come utilizzare Campaign e i database esterni
feature: Federated Data Access
role: Admin
level: Beginner, Intermediate
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 1%

---

# Federated Data Access (FDA){#gs-fda}

Usa il connettore FDA (Federated Data Access) per collegare Campaign a uno o più **database esterni** e elabora le informazioni archiviate senza influire sui dati del database di Campaign Cloud. Puoi quindi accedere ai dati esterni senza modificare la struttura dei dati di Adobe Campaign.

![](../assets/do-not-localize/speech.png)   Come utente di Cloud Services gestiti, [Adobe di contatto](../start/campaign-faq.md#support) per collegare i database esterni con Campaign.


>[!NOTE]
>
>* I database compatibili per Federated Data Access sono elencati in [Matrice di compatibilità](../start/compatibility-matrix.md).
>
>* Nel contesto di un [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), è disponibile un account esterno specifico per gestire la comunicazione tra il database locale di Campaign e il database cloud di Snowflake. Questo account esterno è configurato per te per Adobe e **non deve** essere modificati.
>



## Best practice e limitazioni

L’opzione FDA è soggetta alle limitazioni del sistema di database di terze parti utilizzato.

Inoltre, tieni presente le limitazioni e le best practice seguenti:

* L’opzione FDA viene eseguita per manipolare i dati in database esterni in modalità batch nei flussi di lavoro. Per evitare problemi di prestazioni, si sconsiglia di utilizzare il modulo FDA nel contesto di operazioni unitarie, ad esempio: personalizzazione, interazione, messaggistica in tempo reale, ecc.

* Evita le operazioni che devono utilizzare il più possibile sia Adobe Campaign che il database esterno. A questo scopo, puoi:

   * Esporta il database Adobe Campaign nel database esterno ed esegui le operazioni solo dal database esterno prima di reimportare i risultati in Adobe Campaign.

   * Raccogli i dati dal database Adobe Campaign esterno ed esegui le operazioni localmente.
   Se desideri eseguire la personalizzazione nelle consegne utilizzando i dati del database esterno, raccogli i dati da utilizzare in un flusso di lavoro per renderli disponibili in una tabella temporanea. Quindi utilizza i dati della tabella temporanea per personalizzare la consegna. Per eseguire questa operazione, preelabora la personalizzazione dei messaggi in un flusso di lavoro dedicato utilizzando **[!UICONTROL Prepare the personalization data with a workflow]** disponibile nella **[!UICONTROL Analysis]** scheda delle proprietà di consegna. Durante l’analisi della consegna, questa opzione crea ed esegue automaticamente un flusso di lavoro che memorizza in una tabella temporanea tutti i dati collegati alla destinazione, inclusi i dati provenienti da tabelle collegate in un database esterno.

   >[!CAUTION]
   >
   >Questa opzione migliora notevolmente le prestazioni durante l’esecuzione del passaggio di personalizzazione.


## Utilizzare dati esterni in un flusso di lavoro

Campaign viene fornito con diverse attività del flusso di lavoro che puoi utilizzare per interagire con i dati provenienti da database esterni:

* **Filtrare dati esterni** - Utilizzare **[!UICONTROL Query]** attività per aggiungere dati esterni e utilizzarli nelle configurazioni di filtro definite.

* **Creare sottoinsiemi** - Utilizzare **[!UICONTROL Split]** attività per creare sottoinsiemi. Puoi utilizzare dati esterni per definire i criteri di filtro da utilizzare.

* **Carica database esterno** - Utilizzare i dati esterni nel **[!UICONTROL Data loading (RDBMS)]** attività.

* **Aggiunta di informazioni e collegamenti** - Utilizzare **[!UICONTROL Enrichment]** attività per aggiungere dati aggiuntivi alla tabella di lavoro del flusso di lavoro e collegamenti a una tabella esterna. In questo contesto, può utilizzare dati provenienti da un database esterno.

Puoi anche definire direttamente una connessione a un database esterno da tutte le attività del flusso di lavoro elencate in precedenza, per un utilizzo temporaneo. In questo caso, si trova in un database esterno locale, da utilizzare solo all’interno del flusso di lavoro corrente.

>[!CAUTION]
>
>Questo tipo di configurazione deve essere utilizzato solo temporaneamente per raccogliere i dati. La configurazione dell’account esterno deve essere preferita per qualsiasi altro utilizzo.

Ad esempio, nella **[!UICONTROL Query]** attività, puoi definire una connessione temporanea a un database esterno come segue:

1. Apri l’attività e fai clic su **[!UICONTROL Add data...]**
1. Seleziona la **[!UICONTROL External data]** options
1. Seleziona la **[!UICONTROL Locally defining the data source]** opzione
1. Selezionare il motore di database di destinazione nell&#39;elenco a discesa. Immetti il nome del server e fornisci i parametri di autenticazione. Specifica anche il nome del database esterno.
1. Selezionare la tabella in cui sono memorizzati i dati. È possibile immettere il nome della tabella direttamente nel campo corrispondente oppure fare clic sull&#39;icona di modifica per accedere all&#39;elenco delle tabelle del database.
1. Fai clic sul pulsante **[!UICONTROL Add]** per definire uno o più campi di riconciliazione tra i dati del database esterno e i dati del database Adobe Campaign. La **[!UICONTROL Edit expression]** icone **[!UICONTROL Remote field]** e **[!UICONTROL Local field]** consente di accedere all’elenco dei campi di ciascuna tabella.
1. Se necessario, specifica una condizione di filtro e la modalità di ordinamento dei dati.
1. Selezionare i dati aggiuntivi da raccogliere nel database esterno. A questo scopo, fai doppio clic sui campi che desideri aggiungere per visualizzarli nel **[!UICONTROL Output columns]**.
1. Fai clic su **[!UICONTROL Finish]** per confermare questa configurazione.
