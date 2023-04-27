---
product: campaign
title: Pubblico di destinazione della campagna di marketing
description: Scopri come definire il pubblico delle campagne di marketing
feature: Campaigns, Audiences
exl-id: 70a63632-f66d-40f2-806d-bde89303936a
source-git-commit: a2518ea0c0ab23f50b3132b750a14e98b4ffad7d
workflow-type: tm+mt
source-wordcount: '1457'
ht-degree: 1%

---

# Selezionare il pubblico delle campagne {#marketing-campaign-deliveries}

In una campagna di marketing, per ogni consegna, puoi definire:

* Il pubblico di destinazione. Puoi inviare messaggi a un [elenco dei destinatari](#send-to-a-group) o creare un [pubblico in un flusso di lavoro](#build-the-main-target-in-a-workflow)
* Gruppo di controllo. È possibile [aggiungere un gruppo di controllo](#add-a-control-group) per monitorare il comportamento dei destinatari dopo la consegna dei messaggi
<!--
* Seed addresses - Learn more in [this section](../../delivery/using/about-seed-addresses.md).-->

Alcune di queste informazioni possono essere ereditate dal [modello di campagna](marketing-campaign-templates.md#campaign-templates).

<!--
To build the delivery target, you can define filtering criteria for the recipients in the database. This recipient selection mode is presented in [this section](../../delivery/using/steps-defining-the-target-population.md).
-->

## Invia a un gruppo{#send-to-a-group}

È possibile importare una popolazione in un elenco, quindi eseguire il targeting di tale elenco nelle consegne. A tale scopo, segui la procedura indicata di seguito:

1. Modifica la consegna e fai clic sul pulsante **[!UICONTROL To]** collegamento per modificare la popolazione target.
1. In **[!UICONTROL Main target]** seleziona la scheda **[!UICONTROL Defined via the database]** e fai clic su **[!UICONTROL Add]** per selezionare i destinatari.

   ![](assets/select-main-target.png)

1. Scegli **[!UICONTROL A list of recipients]**.

   ![](assets/target-a-list.png)


1. Fai clic su **[!UICONTROL Next]** per selezionare l’elenco.

   ![](assets/select-the-list.png)

   Puoi perfezionare la destinazione aggiungendo nuovi criteri di filtro.

1. Fai clic su **[!UICONTROL Finish]** una volta definiti tutti i criteri e salva il target principale.

## Creare il pubblico in un flusso di lavoro della campagna {#build-the-main-target-in-a-workflow}

Il target principale di una consegna può essere definito anche nel flusso di lavoro della campagna: questo ambiente grafico consente di creare un target utilizzando query, test e operatori: unione, deduplicazione, condivisione, ecc.

>[!IMPORTANT]
>
>Non devi aggiungere più di 28 flussi di lavoro in una campagna. Superato questo limite, nell’interfaccia non sono visibili flussi di lavoro aggiuntivi e possono generare errori.

### Creare il flusso di lavoro {#create-a-targeting-workflow}

Il targeting può essere creato tramite una combinazione di condizioni di filtro in una sequenza grafica in un flusso di lavoro. Puoi creare popolazioni e sottopopolazioni che saranno oggetto di targeting in base alle tue esigenze. Per visualizzare l’editor del flusso di lavoro, fai clic sul pulsante **[!UICONTROL Targeting and workflows]** nel dashboard della campagna.

![](assets/targeting-and-wf-tab.png)

La popolazione target viene estratta dal database Adobe Campaign tramite una o più query inserite in un flusso di lavoro. Scopri come creare una query in [questa sezione](../workflow/query.md).

Puoi avviare query e condividere popolazioni tramite caselle quali Unione, Intersezione, Condivisione, Esclusione, ecc.

Selezionare gli oggetti dagli elenchi a sinistra dell’area di lavoro e collegarli per creare la destinazione.

![](assets/campaign-wf.png)

Nel diagramma, collega le query di targeting e pianificazione necessarie per la costruzione del target nel diagramma. Puoi eseguire il targeting mentre la costruzione è in corso, al fine di controllare la popolazione estratta dal database.

>[!NOTE]
>
>Esempi e procedure per la definizione delle query sono descritti in [questa sezione](../workflow/query.md).

La sezione a sinistra dell’editor contiene una libreria di oggetti grafici che rappresentano le attività. La prima scheda contiene le attività di targeting e la seconda scheda contiene le attività di controllo del flusso, che vengono utilizzate occasionalmente per coordinare le attività di targeting.

Le funzioni di esecuzione e formattazione del flusso di lavoro di targeting sono accessibili tramite la barra degli strumenti dell’editor di diagrammi.

![](assets/wf-diagram.png)

>[!NOTE]
>
>Le attività disponibili per la creazione del diagramma, nonché tutte le funzioni di visualizzazione e layout sono descritte in [questa sezione](../workflow/about-workflows.md).

Puoi creare diversi flussi di lavoro di targeting per una singola campagna. Per aggiungere un flusso di lavoro:

1. Vai alla sezione in alto a sinistra della zona di creazione del flusso di lavoro, fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Add]**. È inoltre possibile utilizzare **[!UICONTROL New]** pulsante situato sopra questa zona.

   ![](assets/add-a-wf.png)

1. Seleziona la **[!UICONTROL New workflow]** modello e nome del flusso di lavoro.
1. Fai clic su **[!UICONTROL OK]** per confermare la creazione del flusso di lavoro, quindi creare il diagramma per questo flusso di lavoro.

### Eseguire il flusso di lavoro {#execute-a-workflow}

I flussi di lavoro di targeting possono essere avviati manualmente tramite **[!UICONTROL Start]** nella barra degli strumenti, purché si disponga dei diritti appropriati.

Il targeting può essere programmato per l’esecuzione automatica in base a una pianificazione (pianificazione) o a un evento (segnale esterno, importazione di file, ecc.).

Le azioni relative all’esecuzione del flusso di lavoro di targeting (avvio, arresto, pausa, ecc.) sono **asincrono** processi: il comando viene salvato e avrà effetto non appena il server sarà disponibile per applicarlo.

Le icone della barra degli strumenti consentono di intervenire sull’esecuzione del flusso di lavoro di targeting.

* Avvia o riavvia

   * La **[!UICONTROL Start]** consente di avviare il flusso di lavoro di targeting. Quando fai clic su questa icona, vengono attivate tutte le attività senza una transizione di input (eccetto i ponticelli di fine).

      ![](assets/start.png)

      Il server prende in considerazione la richiesta, come mostrato dal suo stato: **[!UICONTROL Start as soon as possible]**.

   * Puoi riavviare il flusso di lavoro di targeting tramite l’icona appropriata della barra degli strumenti. Questo comando può essere utile se **[!UICONTROL Start]** l’icona non è disponibile, ad esempio quando è in corso l’arresto del flusso di lavoro di targeting. In questo caso, fai clic sul pulsante **[!UICONTROL Restart]** per anticipare il riavvio. Il server prende in considerazione la richiesta, come mostra il suo stato: **[!UICONTROL Restart requested]**.

* Interrompi o interrompi

   * Le icone della barra degli strumenti consentono di interrompere o sospendere un flusso di lavoro di targeting in corso.

      Quando fai clic su **[!UICONTROL Pause]**, le operazioni in corso **[!UICONTROL are not]** sospesa, ma nessun&#39;altra attività viene avviata fino al prossimo riavvio.

      ![](assets/pause.png)

      Il server prende in considerazione il comando, come mostra il relativo stato: **[!UICONTROL Pause requested]**.

      Puoi anche mettere in pausa automaticamente un flusso di lavoro di targeting quando l’esecuzione raggiunge una particolare attività. A questo scopo, fai clic con il pulsante destro del mouse sull’attività da cui deve essere messo in pausa il flusso di lavoro di targeting e seleziona **[!UICONTROL Enable but do not execute]**.

      ![](assets/donotexecute.png)

      Questa configurazione viene visualizzata da un’icona speciale.

      ![](assets/pause_activity.png)

      >[!NOTE]
      >
      >Questa opzione è utile durante la progettazione avanzata della campagna di targeting e le fasi di test.

      Fai clic su **[!UICONTROL Start]** per riprendere l&#39;esecuzione.

   * Fai clic sul pulsante **[!UICONTROL Stop]** per interrompere l’esecuzione in corso.

      ![](assets/stop.png)

      Il server prende in considerazione il comando, come mostra il relativo stato: **[!UICONTROL Stop requested]**.
   Puoi anche interrompere automaticamente un flusso di lavoro di targeting quando l’esecuzione raggiunge un’attività . A questo scopo, fai clic con il pulsante destro del mouse sull’attività da cui verrà interrotto il flusso di lavoro di targeting e seleziona **[!UICONTROL Do not activate]**.

   ![](assets/donotactivate.png)

   Questa configurazione viene visualizzata da un’icona speciale.

   ![](assets/unactivation.png)


   >[!NOTE]
   >
   >Questa opzione è utile durante la progettazione avanzata della campagna di targeting e le fasi di test.

* Arresto incondizionato

   In Esplora risorse, seleziona **[!UICONTROL Administration > Production > Object created automatically > Campaign workflows]** per accedere e intervenire su ogni flusso di lavoro della campagna.

   Per interrompere incondizionatamente il flusso di lavoro, fai clic sul pulsante **[!UICONTROL Actions]** icona e selezione **[!UICONTROL Unconditional]** fermatevi. Questa azione interrompe il flusso di lavoro della campagna.

   ![](assets/stop_unconditional.png)

## Aggiungi un gruppo di controllo {#add-a-control-group}

Un gruppo di controllo è una popolazione che non riceverà la consegna; viene utilizzato per monitorare il comportamento dopo la consegna e l’impatto della campagna effettuando un confronto con il comportamento della popolazione target, che ha ricevuto la consegna.

Il gruppo di controllo può essere estratto dal target principale e/o provenire da un gruppo o query specifico.

### Attivare il gruppo di controllo per una campagna {#activate-the-control-group-for-a-campaign}

È possibile definire un gruppo di controllo a livello di campagna, nel qual caso il gruppo di controllo verrà applicato a ogni consegna della campagna interessata.

1. Modifica la campagna in questione e fai clic sul pulsante **[!UICONTROL Edit]** scheda .
1. Fai clic su **[!UICONTROL Advanced campaign parameters...]**.

   ![](assets/enable-control-group.png)

1. Seleziona la **[!UICONTROL Enable and edit control group configuration]** opzione .
1. Fai clic su **[!UICONTROL Edit...]** per configurare il gruppo di controllo.

   ![](assets/edit-control-group.png)

La procedura completa è descritta in [questa sezione](#extract-the-control-group-from-the-main-target). Ulteriori informazioni sui gruppi di controllo in [questa sezione](#add-a-population).

### Attiva il gruppo di controllo per una consegna {#activate-the-control-group-for-a-delivery}

È possibile definire un gruppo di controllo a livello di consegna, nel qual caso il gruppo di controllo verrà applicato a ogni consegna della campagna interessata.

Per impostazione predefinita, la configurazione del gruppo di controllo definita a livello di campagna si applica a ogni consegna della campagna. È tuttavia possibile adattare il gruppo di controllo per una singola consegna.

>[!NOTE]
>
>Se hai definito un gruppo di controllo per una campagna e lo configuri anche per una consegna collegata a questa campagna, verrà applicato solo il gruppo di controllo definito per la consegna.

1. Modifica la consegna in questione, quindi fai clic sul pulsante **[!UICONTROL To]** link.
1. Fai clic sul pulsante **[!UICONTROL Control group]** , quindi seleziona **[!UICONTROL Enable and edit control group configuration]**.

   ![](assets/enable-control-group-for-a-delivery.png)

1. Fai clic su **[!UICONTROL Edit...]** per configurare il gruppo di controllo.

La procedura completa è descritta in [questa sezione](#extract-the-control-group-from-the-main-target).

### Utilizzare un nuovo gruppo come gruppo di controllo {#add-a-population}

È possibile utilizzare una popolazione specifica per il gruppo di controllo. In tal caso, selezionare l’elenco da utilizzare come gruppo di controllo nel campo correlato.

Questa popolazione può provenire da un elenco di destinatari o può essere definita tramite una query specifica.

![](assets/new-population-as-control-group.png)

>[!NOTE]
>
>L’editor delle query Adobe Campaign è presentato in [questa sezione](../workflow/query.md).

### Estrarre il gruppo di controllo dal target principale {#extract-the-control-group-from-the-main-target}

Puoi anche estrarre i destinatari dal target principale della consegna. In questo caso, i destinatari verranno presi dal target delle azioni di consegna interessate da questa configurazione. Questa estrazione può essere casuale o essere il risultato dell’ordinamento dei destinatari.

![](assets/extract-control-group-from-target.png)

Per estrarre un gruppo di controllo, abilitare il gruppo di controllo per la campagna o la consegna e selezionare una delle opzioni seguenti: **[!UICONTROL Activate random sampling]** o **[!UICONTROL Keep only the first records after sorting]**.

* Utilizza la **[!UICONTROL Activate random sampling]** opzione per applicare il campionamento casuale ai destinatari nella popolazione principale. Se poi imposti la soglia su 100, il gruppo di controllo sarà composto da 100 destinatari selezionati in modo casuale dalla popolazione target. Il campionamento casuale dipende dal motore del database.
* Utilizza la **[!UICONTROL Keep only the first records after sorting]** possibilità di definire un limite basato su uno o più ordinamenti. Se selezioni la **[!UICONTROL Age]** come criterio di ordinamento e quindi definisci 100 come soglia, il gruppo di controllo sarà composto dai 100 destinatari più giovani. Ad esempio, potrebbe essere interessante definire un gruppo di controllo che includa i destinatari che effettuano pochi acquisti o i destinatari che effettuano acquisti frequenti e confrontare il loro comportamento con quello dei destinatari contattati.

Fai clic su **[!UICONTROL Next]** definire l’ordinamento (se necessario) e selezionare la modalità di limitazione del destinatario.

![](assets/limit-control-group.png)

Questa configurazione equivale a un **[!UICONTROL Split]** nel flusso di lavoro, che consente di suddividere il target in sottoinsiemi. Il gruppo di controllo è uno di questi sottoinsiemi.


### Video tutorial {#create-email-video}

Questo video spiega come aggiungere un gruppo di controllo a una campagna.

>[!VIDEO](https://video.tv.adobe.com/v/335606?quality=12)

Sono disponibili ulteriori video dimostrativi relativi a Campaign [qui](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.
