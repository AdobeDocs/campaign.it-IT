---
title: Utilizzare i dati del flusso di lavoro
description: Scopri come utilizzare i dati dei flussi di lavoro
feature: Workflows, Data Management
exl-id: 5014c2ed-2a74-4122-b7b9-d3703db7ab12
source-git-commit: 34af97ae01f7dba418fd0a8c950fc549dfbbd98b
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 9%

---

# Utilizzare i dati del flusso di lavoro{#how-to-use-workflow-data}

È possibile utilizzare le attività del flusso di lavoro per eseguire più attività. Di seguito sono riportati alcuni esempi di utilizzo per aggiornare il database creando elenchi, gestire gli abbonamenti, inviare messaggi tramite un flusso di lavoro o arricchire le consegne e i relativi tipi di pubblico.

Un set di casi di utilizzo del flusso di lavoro è disponibile in [questa sezione](workflow-use-cases.md).

## Ciclo di vita dei dati {#data-life-cycle}

### Tabella di lavoro temporanea del flusso di lavoro {#work-table}

Nei flussi di lavoro, i dati trasportati da un’attività all’altra vengono memorizzati in una tabella di lavoro temporanea.

Questi dati possono essere visualizzati e analizzati facendo clic con il pulsante destro del mouse sulla transizione appropriata.

![](assets/wf-right-click-analyze.png)

A questo scopo, seleziona il menu pertinente:

* **[!UICONTROL Display the target...]**

  Questo menu visualizza i dati disponibili sulla popolazione target.

  ![](assets/wf-right-click-display.png)

  È possibile accedere alla struttura della tabella di lavoro nel **[!UICONTROL Schema]** scheda.

  ![](assets/wf-right-click-schema.png)

  Per ulteriori informazioni al riguardo, consulta [questa sezione](monitor-workflow-execution.md#worktables-and-workflow-schema).

* **[!UICONTROL Analyze target...]**

  Questo menu consente di accedere alla procedura guidata di analisi descrittiva che consente di produrre statistiche e rapporti sui dati di transizione.

  Per ulteriori informazioni, consulta la [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/analyzing-populations/about-descriptive-analysis.html){target="_blank"}.

I dati di destinazione vengono eliminati durante l’esecuzione del flusso di lavoro. È accessibile solo l&#39;ultima tabella di lavoro. È possibile configurare il flusso di lavoro in modo che tutte le tabelle di lavoro rimangano accessibili: selezionare **[!UICONTROL Keep the result of interim populations between two executions]** nelle proprietà del flusso di lavoro.

![](assets/wf-purge-data-option.png)

>[!CAUTION]
>
>Questa opzione non deve **mai** essere selezionata in un flusso di lavoro di **produzione**. Viene utilizzata per analizzare i risultati ed è progettata solo a scopo di test e quindi deve essere utilizzata solo in ambienti di sviluppo o di staging.


### Sfruttare i dati target {#target-data}

I dati memorizzati nella tabella di lavoro temporanea del flusso di lavoro sono disponibili per le attività di personalizzazione. I dati possono essere utilizzati in [campi di personalizzazione](../../v8/send/personalization-fields.md).

Questo consente di utilizzare i dati raccolti tramite un elenco in una consegna, ad esempio. A tale scopo, utilizza la sintassi seguente:

```
%= targetData.FIELD %
```

**[!UICONTROL Target extension]** (targetData) Gli elementi di personalizzazione del tipo non sono disponibili per i flussi di lavoro di targeting. Il target della consegna deve essere integrato nel flusso di lavoro e specificato nella transizione in entrata della consegna.

Nell’esempio seguente, stai raccogliendo un elenco di informazioni sui clienti, da utilizzare in un’e-mail personalizzata. Applica i seguenti passaggi:

1. Crea un flusso di lavoro per raccogliere informazioni, riconciliarle con i dati già presenti nel database, quindi avvia una consegna.

   ![](assets/wf-targetdata-sample-1.png)

1. Nel nostro esempio, il contenuto del file è il seguente:

   ```
   Music,First name,Last name,Account,CD/DVD,Card
   Pop,David,BLAIR,4323,CD,0
   Rock,Daniel,ARCARI,3222,DVD,1
   Disco,Uma,ALTON,0488,DVD,0
   Jazz,Paul,BOLES,6475,CD,1
   Jazz,David,BOUKHARI,0841,DVD,1
   [...]
   ```

   Per caricare il file, configura **[!UICONTROL Data loading (file)]** attività come segue:

   ![](assets/wf-targetdata-sample-2.png)

1. Configurare **[!UICONTROL Enrichment]** per riconciliare i dati raccolti con quelli già presenti nel database di Adobe Campaign. In questo caso, la chiave di riconciliazione è il numero di account:

   ![](assets/wf-targetdata-sample-3.png)

1. Quindi configura il **[!UICONTROL Delivery]**: viene creato in base a un modello e i destinatari sono specificati dalla transizione in entrata.

   ![](assets/wf-targetdata-sample-4.png)

   >[!CAUTION]
   >
   >Per personalizzare la consegna è possibile utilizzare solo i dati contenuti nella transizione. **targetData** i campi di personalizzazione del tipo sono disponibili solo per la popolazione in entrata del **[!UICONTROL Delivery]** attività.

1. Nel modello di consegna, utilizza i campi raccolti nel flusso di lavoro.

   A tale scopo, inserire **[!UICONTROL Target extension]** digita i campi di personalizzazione.

   ![](assets/wf-targetdata-sample-5.png)

   In questo caso, si desidera inserire il genere musicale e il tipo di file multimediale (CD o DVD) preferiti dal cliente, come indicato nel file raccolto dal flusso di lavoro.

   In più, aggiungeremo un coupon per i titolari di carta fedeltà, ovvero i destinatari per i quali il valore &quot;Carta&quot; è uguale a 1.

   ![](assets/wf-targetdata-sample-6.png)

   **[!UICONTROL Target extension]** I dati di tipo (targetData) vengono inseriti nelle consegne utilizzando le stesse caratteristiche di tutti i campi di personalizzazione. Possono essere utilizzati anche nell’oggetto, nelle etichette di collegamento o nei collegamenti stessi.


## Aggiornare il database {#update-the-database}

Tutti i dati raccolti possono essere utilizzati per aggiornare il database o nelle consegne. Ad esempio, puoi arricchire le possibilità di personalizzazione del contenuto dei messaggi (includi il numero di contratti nel messaggio, specifica il carrello acquisti medio nell’ultimo anno, ecc.) o specificare il targeting della popolazione (inviare un messaggio ai co-titolari del contratto, indirizzare i 1,000 migliori abbonati ai servizi online, ecc.). Questi dati possono anche essere esportati o archiviati in un elenco.

### Aggiorna elenchi  {#list-updates}

I dati del database di Adobe Campaign e gli elenchi esistenti possono essere aggiornati utilizzando due attività dedicate:

* Il **[!UICONTROL List update]** attività consente di memorizzare le tabelle di lavoro in un datalist.

  È possibile selezionare un elenco esistente o crearlo. In questo caso, vengono calcolati il nome e, se possibile, la cartella dei record.

  ![](assets/s_user_create_list.png)

  Fai riferimento a [Aggiornamento elenco](list-update.md).

* Il **[!UICONTROL Update data]** l’attività esegue un aggiornamento di massa dei campi nel database.

  Per ulteriori informazioni, consulta [Aggiorna dati](update-data.md).

### Gestire le iscrizioni {#subscription-management}

Per informazioni sull’abbonamento e sull’annullamento dell’abbonamento dei destinatari a un servizio di informazioni tramite un flusso di lavoro, consulta [Subscription Services](subscription-services.md).
