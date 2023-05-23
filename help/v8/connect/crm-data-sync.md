---
title: Sincronizzazione dei dati dei connettori CRM
description: Gestire i dati tra Campaign e il CRM
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 2a7ae88e-d47f-416b-84cd-986ab9be6aef
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 1%

---

# Sincronizzare i dati tra Campaign e il CRM {#data-synchronization}

La sincronizzazione dei dati tra Adobe Campaign e il sistema CRM è gestita dal **Connettore CRM** attività del flusso di lavoro.

Ad esempio, per importare i dati di Microsoft Dynamics in Adobe Campaign, crea il seguente tipo di flusso di lavoro:

![](assets/ms-dyn-wf.png)

Questo flusso di lavoro importa i contatti tramite Microsoft Dynamics, li sincronizza con i dati esistenti di Adobe Campaign, li elimina e aggiorna il database di Adobe Campaign.

Il **[!UICONTROL CRM Connector]** l&#39;attività deve essere configurata per sincronizzare i dati.

![](assets/crm-connector-ms-dyn.png)

Con questa attività è possibile:

* Importa dal CRM - [Ulteriori informazioni](#importing-from-the-crm)
* Esporta in CRM - [Ulteriori informazioni](#exporting-to-the-crm)
* Importa oggetti eliminati nel CRM - [Ulteriori informazioni](#importing-objects-deleted-in-the-crm)
* Elimina oggetti nel CRM - [Ulteriori informazioni](#deleting-objects-in-the-crm)

![](assets/crm-remote-op.png)

Seleziona l’account esterno che corrisponde al CRM con cui desideri configurare la sincronizzazione, quindi seleziona l’oggetto da sincronizzare: account, opportunità, lead, contatti, ecc.

![](assets/crm-remote-obj.png)

La configurazione di questa attività dipende dal processo da eseguire. Di seguito sono descritte diverse configurazioni.

## Importa dal CRM {#importing-from-the-crm}

Per importare i dati tramite il sistema di gestione delle relazioni con i clienti in Adobe Campaign, devi creare il seguente tipo di flusso di lavoro:

![](assets/crm-wf-import.png)

1. Seleziona un **[!UICONTROL Import from the CRM]** operazione.
1. In **[!UICONTROL Remote object]** selezionare l&#39;oggetto da importare. Questo oggetto corrisponde a una delle tabelle create in Adobe Campaign durante la configurazione del connettore.
1. In **[!UICONTROL Remote fields]** , immettere i campi da importare.

   Per aggiungere un campo, fai clic su **[!UICONTROL Add]** nella barra degli strumenti, quindi fare clic sul pulsante **[!UICONTROL Edit expression]** icona.

   Se necessario, modifica il formato dei dati utilizzando l’elenco a discesa del **[!UICONTROL Conversion]** colonne. I possibili tipi di conversione sono descritti in [questa sezione](#data-format).

   >[!CAUTION]
   >
   >L’identificatore del record nel CRM è obbligatorio per il collegamento di oggetti nel CRM e in Adobe Campaign. Viene aggiunto automaticamente quando la casella viene approvata.
   >
   >L’ultima data di modifica sul lato del sistema di gestione delle relazioni con i clienti è obbligatoria anche per le importazioni di dati incrementali.

1. Puoi filtrare i dati da importare in base alle tue esigenze. A questo scopo, fai clic su **[!UICONTROL Edit the filter...]** collegamento.

   Nell’esempio seguente, Adobe Campaign importa solo i contatti per i quali è stata registrata un’attività dal 1° novembre 2021.

   ![](assets/crm-task-import-filter.png)

   >[!CAUTION]
   >
   >Le limitazioni relative alle modalità di filtro dei dati sono descritte in dettaglio [questa sezione](#filtering-data).

1. Seleziona la **[!UICONTROL Use automatic index...]** opzione per gestire automaticamente la sincronizzazione incrementale degli oggetti tra il sistema CRM e Adobe Campaign, a seconda della data e dell’ultima modifica.

   Per ulteriori informazioni al riguardo, consulta [questa sezione](#variable-management).

### Gestisci variabili {#variable-management}

Attiva il **[!UICONTROL Automatic index]** per raccogliere solo gli oggetti modificati dopo l&#39;ultima importazione.

![](assets/use-auto-index.png)

Per impostazione predefinita, la data dell’ultima sincronizzazione viene memorizzata in un’opzione specificata nella finestra di configurazione: **LASTIMPORT_&lt;%=instance.internalName%>_&lt;%=activityName%>**.

>[!NOTE]
>
>Questa nota si applica solo al modello generico **[!UICONTROL CRM Connector]** attività. Per altre attività CRM, il processo è automatico.
>
>Questa opzione deve essere creata e compilata manualmente in **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**. Deve essere un’opzione di testo e il suo valore deve corrispondere al seguente formato: **aaaa/MM/gg hh:mm:ss**.
> 
>È necessario aggiornare manualmente questa opzione per ulteriori importazioni.

Puoi specificare il campo CRM remoto di cui tenere conto per identificare le modifiche più recenti.

Per impostazione predefinita, vengono utilizzati i campi seguenti (nell’ordine specificato):

* Per Microsoft Dynamics: **modifedon**,
* Per Salesforce.com: **LastModifiedDate**, **SystemModstamp**.

Attivazione di **[!UICONTROL Automatic index]** genera tre variabili che possono essere utilizzate nel flusso di lavoro di sincronizzazione tramite un **[!UICONTROL JavaScript code]** attività di tipo. Queste attività sono:

* **vars.crmOptionName**: nome dell’opzione che contiene la data dell’ultima importazione.
* **vars.crmStartImport**: data di inizio (inclusa) dell’ultima importazione di dati.
* **vars.crmEndDate**: data di fine (esclusa) dell’ultima importazione di dati.

   >[!NOTE]
   >
   >Queste date vengono visualizzate nel seguente formato: **aaaa/MM/gg hh:mm:ss**.

### Filtrare i dati {#filtering-data}

Per garantire un funzionamento efficiente con i vari CRM, i filtri devono essere creati utilizzando le seguenti regole:

* Ogni livello di filtro può utilizzare un solo tipo di operatore.
* Operatore AND NOT non supportato.
* I confronti possono riguardare solo valori nulli (tipo &quot;è vuoto&quot;/&quot;non è vuoto&quot;) o numeri. Ciò significa che il valore (colonna di destra) viene valutato e il risultato di questa valutazione deve essere un numero. I confronti tra tipi JOIN non sono pertanto supportati.
* Il valore contenuto nella colonna di destra viene valutato in JavaScript.
* I confronti JOIN non sono supportati.
* L&#39;espressione nella colonna di sinistra deve essere un campo. Non può essere una combinazione di diverse espressioni, un numero, ecc.

### Ordina per {#order-by}

In Microsoft Dynamics e Salesforce.com è possibile ordinare i campi remoti da importare in ordine crescente o decrescente.

A questo scopo, fai clic su **[!UICONTROL Order by]** e aggiungere le colonne all&#39;elenco.

L’ordine delle colonne nell’elenco è il seguente:

![](assets/crm-import-order.png)

### Identificazione del record {#record-identification}

Invece di importare gli elementi inclusi (e possibilmente filtrati) nel CRM, puoi utilizzare una popolazione calcolata in precedenza nel flusso di lavoro.

A questo scopo, seleziona la **[!UICONTROL Use the population calculated upstream]** e specificare il campo contenente l&#39;identificatore remoto.

Seleziona quindi i campi del gruppo in entrata da importare, come illustrato di seguito:

![](assets/use-population-calc-upstream.png)

## Esporta nel CRM {#exporting-to-the-crm}

Esporta i dati di Adobe Campaign nel tuo CRM per copiarne l’intero contenuto nel tuo database CRM.

Per esportare i dati nel CRM, crea il seguente tipo di flusso di lavoro:

![](assets/crm-export-diagram.png)

1. Seleziona un **[!UICONTROL Export to CRM]** operazione.
1. Vai a **[!UICONTROL Remote object]** e selezionare l&#39;oggetto da esportare. Questo oggetto corrisponde a una delle tabelle create in Adobe Campaign durante la configurazione del connettore.

   >[!CAUTION]
   >
   >La funzione di esportazione del **[!UICONTROL CRM Connector]** L’attività può inserire o aggiornare campi nel CRM. Per abilitare gli aggiornamenti dei campi nel CRM, specifica la chiave primaria della tabella remota. Se la chiave non è presente, i dati verranno inseriti invece di essere aggiornati.

1. Se devi eseguire esportazioni più veloci, controlla  **[!UICONTROL Export in Batches]** opzione.

   ![](assets/crm-export-batch.png)

1. In **[!UICONTROL Mapping]** , fare clic su **[!UICONTROL New]** per specificare i campi da esportare e la relativa mappatura nel CRM.

   Per aggiungere un campo, fai clic su **[!UICONTROL Add]** nella barra degli strumenti, quindi fare clic sul pulsante **[!UICONTROL Edit expression]** icona.

   >[!NOTE]
   >
   >Se non viene definita alcuna corrispondenza per un campo, i valori non possono essere aggiornati: vengono inseriti direttamente nel CRM.

   Se necessario, modifica il formato dei dati utilizzando l’elenco a discesa del **[!UICONTROL Conversion]** colonne. I possibili tipi di conversione sono descritti in [questa sezione](#data-format).

   >[!NOTE]
   >
   >L&#39;elenco dei record da esportare e il risultato dell&#39;esportazione vengono salvati in un file temporaneo che rimane accessibile fino al completamento o al riavvio del flusso di lavoro. Questo consente di avviare il processo in modo sicuro in caso di errori.

## Configurazioni aggiuntive {#additional-configurations}

### Formato dei dati {#data-format}

Puoi convertire al volo il formato dei dati quando li importi in o dal CRM.

A questo scopo, seleziona la conversione da applicare nella colonna corrispondente.

![](assets/crm-task-import.png)

Il **[!UICONTROL Default]** La modalità applica la conversione automatica dei dati, che nella maggior parte dei casi è uguale a una copia/incolla dei dati. Tuttavia, viene applicata la gestione del fuso orario.

Altre possibili conversioni sono:

* **[!UICONTROL Date only]**: elimina i campi di tipo Data + Ora.
* **[!UICONTROL Without time offset]**: annulla la gestione del fuso orario applicata nella modalità predefinita.
* **[!UICONTROL Copy/Paste]**: utilizza dati non elaborati, ad esempio stringhe (nessuna conversione).

### Elaborazione degli errori {#error-processing}

Nel quadro delle importazioni o delle esportazioni di dati, puoi applicare un processo specifico agli errori e ai rifiuti. A questo scopo, seleziona la **[!UICONTROL Keep the rejections in a file]** e **[!UICONTROL Process errors]** opzioni in **[!UICONTROL Behavior]** scheda.

![](assets/crm-export-options.png)

Queste opzioni aggiungono le relative transizioni di output.

![](assets/crm-export-transitions.png)

Quindi inserisci le attività rilevanti per elaborare i dati. Ad esempio, aggiungi un **Wait** l’attività e la pianificazione ripetono i tentativi per individuare eventuali errori.

Il **[!UICONTROL Reject]** la transizione di output consente di accedere allo schema di output contenente le colonne specifiche relative ai messaggi di errore e ai codici. Per Salesforce.com, questa colonna è **errorSymbol** (simbolo di errore, diverso dal codice di errore), **errorMessage** (descrizione del contesto dell’errore).

## Importa oggetti eliminati nel CRM {#importing-objects-deleted-in-the-crm}

Puoi importare in Adobe Campaign gli oggetti eliminati dal CRM.

1. Seleziona un **[!UICONTROL Import objects deleted in the CRM]** operazione.
1. Vai a **[!UICONTROL Remote object]** e selezionare l&#39;oggetto interessato dal processo. Questo oggetto corrisponde a una delle tabelle create in Adobe Campaign durante la configurazione del connettore.
1. Specifica il periodo di eliminazione da considerare nella **[!UICONTROL Start date]** e **[!UICONTROL End date]** campi (sono incluse le date).

   >[!CAUTION]
   >
   >Il periodo di eliminazione deve coincidere con le limitazioni specifiche del sistema CRM. Ad esempio, per Salesforce.com, non è possibile recuperare gli elementi eliminati più di 30 giorni fa.

## Elimina oggetti nel CRM {#deleting-objects-in-the-crm}

Per eliminare oggetti nel CRM, specifica la chiave primaria degli elementi remoti da eliminare.

Il **[!UICONTROL Behavior]** Questa scheda consente di abilitare l’elaborazione dei rifiuti. Questa opzione genera una seconda transizione di output per **[!UICONTROL CRM connector]** attività. Per ulteriori informazioni, consulta [Errore di elaborazione](#error-processing).
