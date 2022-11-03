---
product: campaign
title: Modelli di campagna di marketing
description: Modelli di campagna di marketing
feature: Campaigns, Templates
exl-id: 1bd8d3e7-aaa9-4e00-96bb-0d30614ab380
source-git-commit: 60db4c2e8cd280845ddd0176bd10dc1b7edbb767
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 5%

---

# Creare e configurare modelli di campagna {#campaign-templates}

Tutte le campagne di marketing si basano su un modello, che memorizza le caratteristiche e le funzionalità principali. Campaign viene fornito con un modello integrato per la creazione di campagne. Questo modello ha tutte le funzionalità abilitate: Documenti, indirizzi di seed, approvazioni, linee di consegna, ecc.

Le funzionalità disponibili dipendono dalle autorizzazioni, dai componenti aggiuntivi e dalla configurazione della piattaforma Adobe Campaign.


>[!NOTE]
>
>La struttura ad albero viene visualizzata quando si fa clic sul pulsante **[!UICONTROL Explorer]** nella home page.

Viene fornito un modello integrato al fine di creare una campagna per la quale non è stata definita alcuna configurazione specifica. Puoi creare e configurare i modelli della campagna e quindi creare campagne a partire da questi modelli.

## Creare un modello di campagna {#create-a-campaign-template}

Per creare un modello di campagna, segui i passaggi seguenti:

1. Apri campagna **Esplora risorse**, e sfogliare per **Risorse > Modelli > Modelli di campagna**.
1. Fai clic su **Nuovo** nella barra degli strumenti sopra l’elenco dei modelli.

![](assets/campaign-template-node.png)

È inoltre possibile **duplicato** il modello incorporato per riutilizzare e adattare la sua configurazione. A questo scopo, fai clic con il pulsante destro del mouse sul modello e seleziona **Duplica**.

1. Inserisci l’etichetta del nuovo modello di campagna.
1. Fai clic su **Salva** e riapri il modello.
1. In **Modifica** definisci le proprietà del modello.
1. Seleziona **Parametri della campagna avanzati...** per aggiungere un flusso di lavoro al modello della campagna.

   ![](assets/campaign-template-parameters.png)

1. Modificare la **Targeting e flussi di lavoro** valore a **Sì** e conferma. Scopri come aggiungere funzionalità in [questa sezione](#typology-of-enabled-modules).
1. La **Targeting e flussi di lavoro** viene aggiunta al modello. Fai clic su **Aggiungi un flusso di lavoro...**, immetti un **Etichetta** e fai clic su **Ok**.
1. Crea il flusso di lavoro in base alle tue esigenze.

   ![](assets/campaign-template-create-wf.png)

1. Fai clic su **Salva**. Il modello è ora pronto per essere utilizzato per creare una nuova campagna.

Le varie schede e schede secondarie del modello della campagna consentono di accedere alle relative impostazioni, descritte in [Configurazione generale](#general-configuration).

## Seleziona moduli {#select-modules}

La **[!UICONTROL Advanced campaign parameters...]** link ti consente di abilitare e disabilitare i lavori per le campagne basate su questo modello. Seleziona le funzionalità da abilitare nelle campagne create in base a questo modello.

![](assets/campaign-template-select-modules.png)

Se una funzionalità non è selezionata, gli elementi relativi al processo (menu, icone, opzioni, schede, schede secondarie, ecc.) non vengono visualizzate nell’interfaccia del modello o nelle campagne basate su questo modello. Le schede a sinistra dei dettagli della campagna e le schede disponibili coincidono con le funzionalità selezionate nel modello. Ad esempio, il **Spese e obiettivi** funzionalità non abilitata, corrispondente **[!UICONTROL Budget]** non vengono visualizzate nelle campagne basate su questo modello.

Inoltre, i collegamenti alle finestre di configurazione vengono aggiunti al dashboard della campagna. Quando una funzionalità è abilitata, un collegamento diretto vi permette di accedervi dal dashboard della campagna.

### Esempi di configurazione

* Ad esempio, con le seguenti impostazioni:

   ![](assets/campaign-template-select-functionalities.png)

   Il dashboard della campagna mostra:

   ![](assets/campaign-template-dashboard-sample-1.png)

   Tieni presente che **[!UICONTROL Targeting and workflows]** scheda mancante.

   Sono disponibili le seguenti funzionalità:

   ![](assets/campaign-template-edit-sample-1.png)

   Tieni presente che **[!UICONTROL Budget]** scheda mancante.

   Anche le impostazioni avanzate della campagna riflettono questa configurazione.

   ![](assets/campaign-template-parameters-sample-1.png)

   Tieni presente che **[!UICONTROL Approvals]** scheda non disponibile.

* Con questa configurazione:
   ![](assets/campaign-template-dashboard-sample-2.png)

   Il dashboard della campagna mostra:

   ![](assets/campaign-template-select-functionalities-2.png)

   Tieni presente che **[!UICONTROL Targeting and workflows]** è disponibile ma la **Aggiungi un documento** link mancante.

   Sono disponibili le seguenti funzionalità:

   ![](assets/campaign-template-edit-sample-2.png)

   Tieni presente che **[!UICONTROL Budget]** è disponibile la scheda .

   Anche le impostazioni avanzate della campagna riflettono questa configurazione.

   ![](assets/campaign-template-parameters-sample-2.png)

   Tieni presente che **[!UICONTROL Approvals]** è disponibile ma la **[!UICONTROL Control population]** e **[!UICONTROL Seed addresses]** le schede non sono abilitate.


## Tipologia dei moduli {#typology-of-enabled-modules}

* **Gruppo di controllo**

   Quando questo modulo è selezionato, viene aggiunta una scheda aggiuntiva alle impostazioni avanzate del modello e alle campagne basate su questo modello. La configurazione può essere definita tramite il modello o singolarmente per ogni campagna. Ulteriori informazioni sui gruppi di controllo in [questa sezione](marketing-campaign-deliveries.md#defining-a-control-group).

   ![](assets/template-activate-1.png)


* **Indirizzi di seed**

   Quando questo modulo è selezionato, viene aggiunta una scheda aggiuntiva alle impostazioni avanzate del modello e alle campagne basate su questo modello. La configurazione può essere definita tramite il modello o singolarmente per ogni campagna.

   ![](assets/template-activate-2.png)

* **Documenti**

   Quando questo modulo è selezionato, viene aggiunta una scheda aggiuntiva al **[!UICONTROL Edit]** scheda del modello e delle campagne basate su questo modello. I documenti allegati possono essere aggiunti dal modello o singolarmente per ogni campagna. Ulteriori informazioni sui documenti in [questa sezione](marketing-campaign-deliveries.md#manage-associated-documents).

   ![](assets/template-activate-3.png)

* **Profilo di consegna**

   Quando questo modulo è selezionato, un **[!UICONTROL Delivery outlines]** la sottoscheda viene aggiunta al **[!UICONTROL Documents]** per definire i contorni di consegna per la campagna. Ulteriori informazioni sui profili di consegna in [questa sezione](marketing-campaign-assets.md#delivery-outlines).

   ![](assets/template-activate-4.png)

* **Targeting e flussi di lavoro**

   Quando selezioni la **[!UICONTROL Targeting and workflows]** modulo , viene aggiunta una scheda per consentire la creazione di uno o più flussi di lavoro per campagne basate su questo modello. I flussi di lavoro possono anche essere configurati singolarmente per ogni campagna basata su questo modello.Ulteriori informazioni sui flussi di lavoro delle campagne in [questa sezione](marketing-campaign-deliveries.md#build-the-main-target-in-a-workflow).

   ![](assets/template-activate-5.png)

   Quando questo modulo è abilitato, un **[!UICONTROL Jobs]** viene aggiunta una scheda alle impostazioni avanzate della campagna per definire la sequenza di esecuzione del processo.

* **Approvazioni**

   Se si abilita **[!UICONTROL Approvals]**, puoi selezionare i processi da approvare e gli operatori responsabili delle approvazioni. Ulteriori informazioni sulle approvazioni in [questa sezione](marketing-campaign-approval.md#select-reviewers).

   ![](assets/template-activate-6.png)

   Puoi scegliere se abilitare o meno l&#39;approvazione del processo tramite la **[!UICONTROL Approvals]** scheda della sezione delle impostazioni avanzate dei modelli.

* **Spese e obiettivi**

   Quando questo modulo è selezionato, un **[!UICONTROL Budget]** viene aggiunta una scheda ai dettagli del modello e delle campagne basate su questo modello in modo che sia possibile selezionare il budget associato.

   ![](assets/template-activate-7.png)


## Proprietà del modello {#template-properties}

![](assets/template-op-type.png)

Quando crei un modello di campagna, devi immettere le seguenti informazioni:

* Inserisci il **etichetta** del modello: l’etichetta è obbligatoria ed è l’etichetta predefinita per tutte le campagne basate su questo modello.
* Seleziona la campagna **natura** dall’elenco a discesa. I valori disponibili in questo elenco sono quelli salvati in **[!UICONTROL natureOp]** enumerazione.

Scopri come accedere e configurare le enumerazioni in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/managing-enumerations.html){target=&quot;_blank&quot;}.


* Seleziona la **tipo di campagna**: unico, ricorrente o periodico. Per impostazione predefinita, i modelli di campagna si applicano a campagne univoche. Le campagne ricorrenti e periodiche sono descritte in [questa sezione](recurring-periodic-campaigns.md).
* Specifica la durata della campagna, ovvero il numero di giorni in cui avrà luogo la campagna. Quando crei una campagna basata su questo modello, le date di inizio e di fine della campagna verranno compilate automaticamente.

   Se la campagna è ricorrente, devi specificare le date di inizio e fine della campagna direttamente nel modello.

* Specifica la **programma correlato** del modello: le campagne basate su questo modello sono collegate al programma selezionato.

<!--
## Track campaign execution{#campaign-reverse-scheduling}

You can create a schedule for a campaign and track accomplishments, for instance to prepare an event schedule for a specific date. Campaign templates now let you calculate the start date of a task based on the end date of a campaign.


In the task configuration box, go to the **[!UICONTROL Implementation schedule]** area and check the **[!UICONTROL The start date is calculated based on the campaign end date]** box. (Here, "start date" is the task start date). Go to the **[!UICONTROL Start]** field and enter an interval: the task will start this long before the campaign end date. If you enter a period which is longer than the campaign is set to last, the task will begin before the campaign.

![](assets/mrm_task_in_template_start_date.png)

When you create a campaign using this template, the task start date will be calculated automatically. However, you can always change it later.-->
