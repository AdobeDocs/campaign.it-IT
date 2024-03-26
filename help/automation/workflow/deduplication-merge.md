---
title: Utilizzare la funzionalità di unione dell’attività Deduplicazione
description: Scopri come utilizzare la funzionalità di unione dell’attività Deduplicazione
feature: Workflows, Data Management
role: User
exl-id: ee201cfd-a351-41d8-a5ad-2f2e538dc643
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 4%

---

# Utilizzare la funzionalità di unione dell’attività Deduplicazione {#deduplication-merge}



## Informazioni su questo caso d’uso {#about-this-use-case}

Questo caso d’uso descrive come utilizzare **[!UICONTROL Merge]** funzionalità in **[!UICONTROL Deduplication]** attività.

Per ulteriori informazioni su questa funzionalità, consulta [questa sezione](deduplication.md#merging-fields-into-single-record).

Il **[!UICONTROL Deduplication]** L’attività viene utilizzata per rimuovere le righe duplicate da un set di dati. In questo caso d’uso, i dati mostrati di seguito vengono duplicati in base al campo E-mail.

| Data ultima modifica | Nome | Cognome | E-mail | Telefono cellulare | Telefono |
|-----|------------|-----------|-------|--------------|------|
| 5/19/2020 | Robert | Tisner | bob@mycompany.com | 444-444-444 | 777 77 77 777 |
| 7/22/2020 | Bobby | Tisner | bob@mycompany.com | | 777 77 77 777 |
| 10/03/2020 | Bob |  | bob@mycompany.com | | 888 88 88 888 |

Con l’attività Deduplicazione di **[!UICONTROL Merge]** funzionalità, puoi configurare un set di regole per la deduplicazione per definire un gruppo di campi da unire in un singolo record di dati risultante. Ad esempio, con un set di record duplicati, è possibile scegliere di mantenere il numero di telefono meno recente o il nome più recente.

## Attivazione della funzionalità di unione {#activating-merge}


Per abilitare la funzionalità di unione, devi innanzitutto configurare **[!UICONTROL Deduplication]** attività. Per farlo, segui questi passaggi:

1. Apri l’attività, quindi fai clic su **[Modifica configurazione]** collegamento.

1. Seleziona il campo di riconciliazione da utilizzare per la deduplicazione, quindi fai clic su **[!UICONTROL Next]**. In questo esempio, vogliamo deduplicare in base al campo e-mail.

   ![](assets/uc_merge_edit.png)

1. Fai clic su **[!UICONTROL Advanced parameters]** , quindi attiva il **[!UICONTROL Merge records]** e **[!UICONTROL Use several record merging criteria]** opzioni.

   ![](assets/uc_merge_advanced_parameters.png)

1. Il **[!UICONTROL Merge]** viene aggiunta alla scheda **[!UICONTROL Deduplication]** schermata di configurazione. Questa scheda consente di specificare i dati da unire durante l’esecuzione della deduplicazione.

## Configurazione dei campi da unire {#configuring-rules}

Di seguito sono elencate le regole che desideri utilizzare per unire i dati in un singolo record:

* Mantieni il nome più recente (campi nome e cognome).
* Mantieni il telefono cellulare più recente,
* Mantieni il numero di telefono meno recente,
* Tutti i campi di un gruppo devono essere non nulli per essere idonei per il record finale.

Per configurare queste regole, effettua le seguenti operazioni:

1. Apri **[!UICONTROL Merge]** , quindi fare clic sulla scheda **[!UICONTROL Add]** pulsante.

   ![](assets/uc_merge_add.png)

1. Specifica l’identificatore e l’etichetta del gruppo di campi da unire.

   ![](assets/uc_merge_identifier.png)

1. Indicare le condizioni per la selezione dei record da prendere in considerazione.

   ![](assets/uc_merge_filter.png)

1. Ordina in base all’ultima data di modifica per selezionare il nome più recente.

   ![](assets/uc_merge_sort.png)

1. Selezionare i campi da unire. In questo esempio, è necessario mantenere i campi Nome e Cognome.

   ![](assets/uc_merge_keep.png)

1. I campi vengono aggiunti al set di dati da unire e un nuovo elemento viene aggiunto allo schema del flusso di lavoro.

   Ripeti questi passaggi per configurare i campi relativi al telefono cellulare e al telefono.

   ![](assets/dedup8.png)

   ![](assets/dedup9.png)

## Risultati {#results}

Dopo aver configurato queste regole, i seguenti dati vengono ricevuti alla fine del **[!UICONTROL Deduplication]** attività.

| Data di modifica | Nome | Cognome | E-mail | Telefono cellulare | Telefono |
|-----|------------|-----------|-------|--------------|------|
| 5/19/2020 | Robert | Tisner | bob@mycompany.com | 444-444-444 | 777 77 77 777 |
| 7/22/2020 | Bobby | Tisner | bob@mycompany.com | | 777 77 77 777 |
| 10/03/2020 | Bob |  | bob@mycompany.com | | 888 88 88 888 |

Il risultato viene unito dai tre record in base alle regole configurate in precedenza. Dopo il confronto, si conclude che vengono utilizzati il nome e il telefono cellulare più recenti, insieme al numero di telefono originale.

| Nome | Cognome | E-mail | Telefono cellulare | Telefono |
|------------|-----------|-------|--------------|------|
| Bobby | Tisner | bob@mycompany.com | 444 44 44 444 | 888 88 88 888 |

>[!NOTE]
>
> Il nome che è stato unito è &quot;Bobby&quot;, perché abbiamo configurato una regola &quot;Name&quot; composta sia dal nome che dal cognome.
>
>Di conseguenza, &quot;Bob&quot; (il nome più recente) non poteva essere preso in considerazione perché il relativo campo del cognome associato era vuoto. La combinazione più recente di nome e cognome è stata unita nel record finale.
