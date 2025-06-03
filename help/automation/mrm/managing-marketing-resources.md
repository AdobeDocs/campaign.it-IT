---
product: campaign
title: Gestire le risorse di marketing
description: Scopri come gestire le risorse di marketing
feature: Campaigns, Resource Management
role: User
exl-id: 4d91fb7d-f846-4644-b83d-5a6a988ae297
source-git-commit: 4f9183c7f1d12feb255a0050da423647f0fce85e
workflow-type: tm+mt
source-wordcount: '1111'
ht-degree: 1%

---

# Gestire le risorse di marketing{#managing-marketing-resources}

Utilizza Adobe Campaign per gestire e tenere traccia delle risorse di marketing coinvolte nel ciclo di vita della campagna. Queste risorse di marketing possono essere un white paper, un file di dati, un logo o qualsiasi altra risorsa correlata a una campagna.

Per ogni risorsa marketing gestita tramite Adobe Campaign, puoi tracciarne lo stato e la cronologia in qualsiasi momento e visualizzare la versione corrente.

Per impostazione predefinita, le risorse di marketing sono archiviate nella cartella **[!UICONTROL MRM > Marketing resources]** di Campaign Explorer.

## Aggiungere una risorsa di marketing {#adding-a-marketing-resource}

Per aggiungere una risorsa di marketing, effettua le seguenti operazioni:

1. Passare alla scheda **[!UICONTROL Campaigns]** e selezionare **[!UICONTROL Marketing resouces]**.

1. Fai clic sul pulsante **[!UICONTROL Create]**.
   ![](assets/add-a-mkt-resource.png)
1. Trascina e rilascia il file nella finestra delle risorse Marketing per caricarlo sul server Campaign. È inoltre possibile utilizzare il collegamento **[!UICONTROL Upload file to server...]**.
   ![](assets/mkt-resource-creation.png)

Al termine del caricamento, la risorsa viene aggiunta all’elenco delle risorse disponibili.

## Gestire le risorse di marketing {#manage-marketing-resources}

Una volta caricata, la risorsa marketing è disponibile per tutti gli operatori Adobe Campaign. Possono visualizzarlo, crearne una copia per modificarlo o aggiornare il file sul server.

![](assets/open-a-marketing-resource.png)

Utilizzare l&#39;elenco a discesa **[!UICONTROL Assigned to]** nella scheda **[!UICONTROL Edit]** per selezionare l&#39;operatore responsabile della risorsa.

![](assets/assign-a-mkt-resource.png)

Puoi anche selezionare gli operatori o i gruppi di operatori responsabili della convalida delle risorse e della pubblicazione delle risorse. Per accedere a queste opzioni, fare clic sul collegamento **[!UICONTROL Advanced parameters]**.

Questi operatori ricevono una notifica tramite e-mail all’avvio del processo di convalida delle risorse.

Se non è selezionato alcun revisore, la risorsa **[!UICONTROL cannot be]** è soggetta ad approvazione.

Utilizzare la scheda **[!UICONTROL Audit]** per aggiungere un lettore di bozze e definire una data di disponibilità per la risorsa. Oltre questa data, verrà visualizzato con lo stato **[!UICONTROL Late]**.

>[!NOTE]
>
>La scheda **[!UICONTROL History]** contiene il registro di download e aggiornamento per la risorsa. Il pulsante **[!UICONTROL Details]** consente di visualizzare la versione selezionata.
>
>La scheda **[!UICONTROL Audit]** consente di monitorare tutte le azioni eseguite sulla risorsa: approvazioni, rifiuti di approvazione, commenti correlati o pubblicazioni.

### Blocco/sblocco di una risorsa {#locking-unlocking-a-resource}

Una volta create, le risorse sono disponibili nel dashboard delle risorse di marketing e gli operatori possono modificarle.

Quando un operatore inizia a lavorare su una risorsa, si consiglia di bloccarla per impedire ad altri operatori di modificarla contemporaneamente. La risorsa viene quindi riservata: rimane accessibile, ma non può essere pubblicata o aggiornata sul server da un altro operatore.

Una risorsa marketing può essere bloccata solo se non è stata approvata.

Per bloccare una risorsa, è necessario fare clic sul pulsante **[!UICONTROL Lock]** nel dashboard delle risorse.

![](assets/lock-a-resource.png)


Una volta aggiornata la risorsa, fare clic sul pulsante **[!UICONTROL Lock]** nel dashboard delle risorse per renderla nuovamente disponibile a tutti gli operatori.

Un messaggio speciale avvisa gli operatori che tentano di accedervi:

![](assets/mkt-resource-locked.png)

La scheda **[!UICONTROL Tracking]** indica il nome dell&#39;operatore che ha bloccato la risorsa.

![](assets/mkt-resource-audit-tab.png)


>[!NOTE]
>
>Solo l&#39;operatore che ha bloccato la risorsa e gli operatori con diritti di amministratore sono autorizzati a sbloccare una risorsa.

### Forum di discussione {#discussion-forums}

Per ogni risorsa, la scheda **[!UICONTROL Forum]** consente ai partecipanti di condividere le informazioni.

![](assets/mkt-resource-forum.png)

Ulteriori informazioni sono disponibili nella sezione [Forum di discussione](discussion-forums.md).

### Processo di approvazione {#approval-process}

La data di disponibilità prevista viene visualizzata nei dettagli della risorsa, se specificata nella scheda **[!UICONTROL Tracking]**. Una volta raggiunta questa data, è possibile eseguire il processo di approvazione utilizzando il pulsante **[!UICONTROL Submit for approval]** nel dashboard delle risorse. Lo stato della risorsa cambia quindi in **[!UICONTROL Approval in progress]**.

Per approvare una risorsa, fare clic sul pulsante **[!UICONTROL Approve the resource]** nel relativo dashboard.

![](assets/mkt-resouce-approve.png)

Gli operatori autorizzati possono quindi accettare o rifiutare l’approvazione. Questa azione è possibile tramite il messaggio e-mail inviato (facendo clic sul collegamento nel messaggio di notifica) o tramite la console client (facendo clic sul pulsante **[!UICONTROL Approve]** ).

La finestra di approvazione consente di inserire un commento.

![](assets/mkt-resource-approval-confirmation.png)

Passare alla scheda **[!UICONTROL Tracking]** per verificare le approvazioni.

>[!NOTE]
>
>Oltre al revisore specificato per ogni risorsa di marketing, gli operatori con diritti di amministratore e il responsabile risorse sono autorizzati ad approvare una risorsa di marketing.

### Pubblicare una risorsa {#publishing-a-resource}

Una volta approvata, la risorsa marketing deve essere pubblicata. Il processo di pubblicazione deve essere soggetto a un&#39;implementazione specifica in base ai requisiti aziendali. Ciò significa che le risorse possono essere pubblicate su una extranet o su qualsiasi altro server, che è possibile inviare informazioni specifiche a un fornitore di servizi esterno e così via.

Per pubblicare una risorsa, fai clic sul pulsante **[!UICONTROL Publish]** nell&#39;area di modifica del dashboard delle risorse di marketing.

![](assets/mkt-resource-publish.png)

Puoi anche automatizzare la pubblicazione di una risorsa tramite un flusso di lavoro.

Pubblicare una risorsa significa renderla disponibile per l’uso (ad esempio, da un’altra attività). La pubblicazione varia a seconda della natura della risorsa: per un volantino, la pubblicazione può significare l&#39;invio del file a una stampante, per un&#39;agenzia web, può significare la pubblicazione su un sito web, ecc.

Per pubblicare Adobe Campaign, devi creare un flusso di lavoro adeguato e collegarlo alla risorsa. A questo scopo, apri la casella **[!UICONTROL Advanced settings...]** della risorsa, quindi seleziona il flusso di lavoro desiderato nel campo **[!UICONTROL Post-processing]**.

![](assets/mkt-resource-post-processing-wf.png)

Il flusso di lavoro viene eseguito:

* Quando il revisore fa clic sul collegamento **[!UICONTROL Publish resource]** o, se non è stato definito alcun revisore, la persona responsabile della risorsa.
* Se la risorsa è gestita tramite un&#39;attività di creazione di risorse di marketing, verrà eseguita quando l&#39;attività è impostata su **[!UICONTROL Finished]**, purché la casella **[!UICONTROL Publish the marketing resource]** sia selezionata nell&#39;attività. [Ulteriori informazioni](creating-and-managing-tasks.md#marketing-resource-creation-task))

Se un flusso di lavoro non viene avviato immediatamente (ad esempio se viene interrotto), lo stato della risorsa cambia in **[!UICONTROL Pending publication]**. Una volta avviato il flusso di lavoro, lo stato della risorsa cambia in **[!UICONTROL Published]**. Questo stato non tiene conto di possibili errori nel processo di pubblicazione. Controlla lo stato del flusso di lavoro per assicurarti che sia eseguito correttamente.

## Collegare una risorsa a una campagna {#linking-a-resource-to-a-campaign}

### Fare riferimento a una risorsa di marketing {#referencing-a-marketing-resource}

Le risorse di marketing possono essere associate alle campagne, purché questa funzione sia stata selezionata nel [modello campagna](../campaigns/marketing-campaign-templates.md).

Passa alla scheda **[!UICONTROL Edit > Documents > Resources]** nel dashboard della campagna, quindi fai clic su **[!UICONTROL Add]** per selezionare la risorsa interessata.

![](assets/link-a-mkt-resource-to-a-campaign.png)

Puoi filtrare le risorse per stato, natura o tipo, oppure applicare un filtro personalizzato.

Utilizza il pulsante **[!UICONTROL Details]** per modificare e visualizzare in anteprima la risorsa.

### Aggiungere una risorsa marketing a una struttura di consegna {#adding-a-marketing-resource-to-a-delivery-outline}

Le risorse di marketing possono essere associate alle consegne tramite i profili di consegna.

Ulteriori informazioni sui profili di consegna in [questa sezione](../campaigns/marketing-campaign-deliveries.md).

A questo scopo, fai clic con il pulsante destro del mouse su una struttura di consegna e seleziona **Nuovo > Risorsa**.

![](assets/mkt-resource-add-in-del-outline.png)

Immetti il nome della risorsa e selezionala dall&#39;elenco a discesa **Risorsa marketing**.

![](assets/mkt-resource-select-in-del-outline.png)


## Gestione delle scorte {#stock-management}

È possibile associare una risorsa marketing a uno o più titoli per gestire le forniture e visualizzare un avviso nel dashboard in caso di scorte insufficienti.


Per associare una risorsa marketing a un magazzino, effettuare le seguenti operazioni:

1. Modificate un materiale grezzo o createne uno nuovo. Ulteriori informazioni sulle scorte in [questa sezione](../campaigns/providers-stocks-and-budgets.md#stock-management).

1. Aggiungere una linea magazzino e selezionare la risorsa marketing corrispondente.

   ![](assets/mkt-resource-in-a-stock-line.png)

   È possibile modificare la risorsa selezionata tramite l&#39;icona **[!UICONTROL Edit the link]** situata a destra della risorsa dopo averla selezionata.

1. Specificare il materiale iniziale e il materiale di allerta, quindi salvare.

Le scorte sono indicate nella scheda della risorsa marketing **Scorte**.
