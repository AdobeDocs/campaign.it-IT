---
title: Utilizzare Campaign e i database esterni (FDA)
description: Scopri come utilizzare Campaign e i database esterni
feature: Federated Data Access
role: Admin
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 631c4986d24daeff870412566318adb170ce040f
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 1%

---

# Federated Data Access (FDA){#gs-fda}

Utilizza il connettore FDA (Federated Data Access) per collegare Campaign a uno o più **database esterni** ed elaborare le informazioni in essi memorizzate senza influire sui dati del database cloud di Campaign. Puoi quindi accedere ai dati esterni senza modificare la struttura dei dati di Adobe Campaign.

>[!NOTE]
>
>* I database compatibili per Federated Data Access sono elencati nella [Matrice di compatibilità](../start/compatibility-matrix.md).
>
>* Nel contesto di una distribuzione [Enterprise (FFDA)](../../v8/architecture/enterprise-deployment.md), è disponibile un account esterno specifico per gestire la comunicazione tra il database locale di Campaign e il database cloud di Snowflake. Questo account esterno è configurato per te da Adobe e **non deve** essere modificato.
>
>* In qualità di utente di Managed Cloud Services, [contatta Adobe](../start/campaign-faq.md#support) per collegare i tuoi database esterni con Campaign.


## Best practice e limitazioni

L’opzione FDA è soggetta alle limitazioni del sistema di database di terze parti utilizzato.

Inoltre, tieni presente le seguenti limitazioni e best practice:

* L’opzione FDA consente di manipolare i dati in database esterni in modalità batch nei flussi di lavoro. Per evitare problemi di prestazioni, si sconsiglia di utilizzare il modulo FDA nel contesto di operazioni unitarie, come: personalizzazione, interazione, messaggistica in tempo reale, ecc.

* Evita le operazioni che devono utilizzare il più possibile sia Adobe Campaign che il database esterno. A questo scopo, puoi:

   * Esporta il database di Adobe Campaign nel database esterno ed esegui le operazioni solo dal database esterno prima di reimportare i risultati in Adobe Campaign.

   * Raccogli i dati dal database esterno di Adobe Campaign ed esegui le operazioni localmente.

  Se desideri eseguire la personalizzazione nelle consegne utilizzando i dati del database esterno, raccogli i dati da utilizzare in un flusso di lavoro per renderli disponibili in una tabella temporanea. Quindi utilizza i dati della tabella temporanea per personalizzare la consegna. Per eseguire questa operazione, pre-elabora la personalizzazione dei messaggi in un flusso di lavoro dedicato utilizzando l&#39;opzione **[!UICONTROL Prepare the personalization data with a workflow]**, disponibile nella scheda **[!UICONTROL Analysis]** delle proprietà di consegna. Durante l’analisi della consegna, questa opzione crea ed esegue automaticamente un flusso di lavoro che memorizza tutti i dati collegati alla destinazione in una tabella temporanea, inclusi i dati di tabelle collegate in un database esterno.

  >[!CAUTION]
  >
  >Questa opzione migliora notevolmente le prestazioni durante l’esecuzione del passaggio di personalizzazione.


## Utilizzare dati esterni in un flusso di lavoro

Campaign viene fornito con diverse attività del flusso di lavoro che puoi utilizzare per interagire con i dati dei tuoi database esterni:

* **Filtro su dati esterni**. Utilizzare l&#39;attività **[!UICONTROL Query]** per aggiungere dati esterni e utilizzarli nelle configurazioni di filtro definite.

* **Crea sottoinsiemi**. Utilizzare l&#39;attività **[!UICONTROL Split]** per creare sottoinsiemi. Puoi utilizzare dati esterni per definire i criteri di filtro da utilizzare.

* **Carica database esterno**. Utilizzare i dati esterni nell&#39;attività **[!UICONTROL Data loading (RDBMS)]**.

* **Aggiunta di informazioni e collegamenti** - Utilizzare l&#39;attività **[!UICONTROL Enrichment]** per aggiungere dati aggiuntivi alla tabella di lavoro del flusso di lavoro e collegamenti a una tabella esterna. In questo contesto, può utilizzare dati provenienti da un database esterno.

Puoi anche definire direttamente una connessione a un database esterno da tutte le attività del flusso di lavoro elencate in precedenza, per un utilizzo temporaneo. In questo caso, si troverà in un database esterno locale, da utilizzare solo all’interno del flusso di lavoro corrente.

>[!CAUTION]
>
>Questo tipo di configurazione deve essere utilizzato solo temporaneamente per raccogliere dati. La configurazione dell’account esterno deve essere preferita per qualsiasi altro utilizzo.

Nell&#39;attività **[!UICONTROL Query]**, ad esempio, è possibile definire una connessione temporanea a un database esterno nel modo seguente:

1. Apri l&#39;attività e fai clic su **[!UICONTROL Add data...]**
1. Seleziona le opzioni **[!UICONTROL External data]**
1. Seleziona l&#39;opzione **[!UICONTROL Locally defining the data source]**
1. Selezionare il motore di database di destinazione nell&#39;elenco a discesa. Immettere il nome del server e fornire i parametri di autenticazione. Specificare inoltre il nome del database esterno.
1. Selezionare la tabella in cui vengono memorizzati i dati. È possibile immettere il nome della tabella direttamente nel campo corrispondente oppure fare clic sull&#39;icona di modifica per accedere all&#39;elenco delle tabelle del database.
1. Fare clic sul pulsante **[!UICONTROL Add]** per definire uno o più campi di riconciliazione tra i dati del database esterno e i dati del database Adobe Campaign. Le icone **[!UICONTROL Edit expression]** di **[!UICONTROL Remote field]** e **[!UICONTROL Local field]** consentono di accedere all&#39;elenco dei campi di ciascuna tabella.
1. Se necessario, specifica una condizione di filtro e la modalità di ordinamento dei dati.
1. Selezionare i dati aggiuntivi da raccogliere nel database esterno. A tale scopo, fare doppio clic sui campi da aggiungere per visualizzarli in **[!UICONTROL Output columns]**.
1. Fare clic su **[!UICONTROL Finish]** per confermare questa configurazione.
