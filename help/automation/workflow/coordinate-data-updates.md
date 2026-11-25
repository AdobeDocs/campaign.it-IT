---
product: campaign
title: Coordinare gli aggiornamenti dei dati
description: Coordinare gli aggiornamenti dei dati
feature: Workflows, Data Management
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 9faf7ee7-07c1-415b-b234-a945994792c7
TQID: 'https://experienceleague.adobe.com/DmafsXGIr-CWPruj9mDR-XmcnWHeMk75-Sm-70-aCk4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 3%
---
# Coordinare gli aggiornamenti dei dati{#coordinating-data-updates}



Questo caso d’uso descrive la creazione di un flusso di lavoro che consente di gestire gli aggiornamenti concomitanti quando si utilizzano diverse esecuzioni di un flusso di lavoro.

Lo scopo è verificare che il processo di aggiornamento sia terminato prima di eseguire un&#39;altra operazione di aggiornamento. A questo scopo, verrà impostata una variabile di istanza e verrà eseguito un test del flusso di lavoro se l’istanza è in esecuzione per decidere se continuare l’esecuzione del flusso di lavoro ed eseguire l’aggiornamento.

![Flusso di lavoro: modulo di pianificazione, in esecuzione? test che termina alla fine il giorno Sì oppure Query, Aggiorna dati e fine 2 il giorno No.](assets/uc_dataupdate_wkf.png)

Questo flusso di lavoro è costituito da:

* un&#39;attività **Scheduler**, che esegue il flusso di lavoro su una frequenza specifica.
* un&#39;attività **Test** che controlla se il flusso di lavoro è già in esecuzione.
* **Query** e **Aggiorna dati** attività nel caso in cui il flusso di lavoro non sia già in esecuzione, seguite da un&#39;attività **End** che reinizializza la variabile dell&#39;istanza del flusso di lavoro su false.
* Attività **End** se il flusso di lavoro è già in esecuzione.

Per creare il flusso di lavoro, effettua le seguenti operazioni:

1. Aggiungi un&#39;attività **Scheduler**, quindi configurane la frequenza in base alle tue esigenze.
1. Aggiungi un&#39;attività **Test** per verificare se il flusso di lavoro è già in esecuzione, quindi configurala come segue.

   >[!NOTE]
   >
   >&quot;isRunning&quot; è il nome della variabile di istanza scelto per questo esempio. Questa non è una variabile incorporata.

   ![È in esecuzione? attività di test con la condizione Yes instance.vars.isRunning e il ramo predefinito etichettato No.](assets/uc_dataupdate_test.png)

1. Aggiungi un&#39;attività **End** al fork **No**. In questo modo, non viene eseguito nulla se il flusso di lavoro è già in esecuzione.
1. Aggiungi le attività desiderate al fork **Yes**. Nel nostro caso, **Attività Query** e **Aggiorna dati**.
1. Apri la prima attività, quindi aggiungi il comando **instance.vars.isRunning = true** nella scheda **[!UICONTROL Advanced]**. In questo modo, la variabile di istanza viene impostata come in esecuzione.

   ![Scheda Avanzate dell&#39;attività Query con istanza dello script di inizializzazione.vars.isRunning = true.](assets/uc_dataupdate_query.png)

1. Aggiungi un&#39;attività **End** alla fine del fork **[!UICONTROL Yes]**, quindi aggiungi il comando **instance.vars.isRunning = false** nella scheda **[!UICONTROL Advanced]**.

   In questo modo, non verrà eseguita alcuna azione durante l’esecuzione del flusso di lavoro.

   ![Scheda Avanzate dell&#39;attività Fine 2 con istanza dello script di inizializzazione.vars.isRunning = false.](assets/uc_dataupdate_end.png)

**Argomenti correlati:**

* [Impedire esecuzioni simultanee multiple](monitor-workflow-execution.md#preventing-simultaneous-multiple-executions)
* [Attività Aggiorna dati](update-data.md)
