---
product: campaign
title: Modelli di campagna di marketing
description: Modelli di campagna di marketing
feature: Campaigns, Templates
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 1bd8d3e7-aaa9-4e00-96bb-0d30614ab380
TQID: 'https://experienceleague.adobe.com/qmz-Sd1EJmACFfgozVirCHCaeiQN-lGKuxd9-VAPMHs'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: baf8e746-117b-5e73-b179-0a83edc0295f
    internal-label: Templates
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 8839c1717cb026a38987a745ffc080a79f344bce
workflow-type: tm+mt
source-wordcount: '1331'
ht-degree: 4%
---
# Creare e configurare modelli di campagna {#campaign-templates}

Tutte le campagne di marketing si basano su un modello, che memorizza le caratteristiche e le funzionalità principali. Campaign viene fornito con un modello integrato per la creazione di campagne. Questo modello presenta tutte le funzionalità abilitate: documenti, indirizzi seed, approvazioni, profili di consegna, ecc.

Le funzionalità disponibili dipendono dalle autorizzazioni, dai componenti aggiuntivi e dalla configurazione della piattaforma Adobe Campaign.


>[!NOTE]
>
>La struttura viene visualizzata quando si fa clic sull&#39;icona **[!UICONTROL Explorer]** nella home page.

Viene fornito un modello incorporato al fine di creare una campagna per la quale non è stata definita alcuna configurazione specifica. Puoi creare e configurare i modelli della campagna e quindi creare campagne a partire da questi modelli.

## Creare un modello di campagna {#create-a-campaign-template}

Per creare un modello per campagne, segui la procedura seguente:

1. Apri Campaign **Explorer** e passa a **Risorse > Modelli > Modelli campagna**.
1. Fai clic su **Nuovo** nella barra degli strumenti sopra l&#39;elenco dei modelli.

![Elenco modelli campagna in Risorse > Modelli, con il pulsante Nuovo evidenziato nella barra degli strumenti.](assets/campaign-template-node.png)

Puoi anche **duplicare** il modello incorporato per riutilizzarne e adattarne la configurazione. A tale scopo, fare clic con il pulsante destro del mouse sul modello e selezionare **Duplica**.

1. Immetti l’etichetta del nuovo modello di campagna.
1. Fai clic su **Salva** e riapri il modello.
1. Nella scheda **Modifica**, definisci le proprietà del modello.
1. Seleziona il collegamento **Parametri campagna avanzati...** per aggiungere un flusso di lavoro al modello della campagna.

   ![Scheda Modifica nuovo modello campagna con il collegamento Parametri campagna avanzati evidenziato.](assets/campaign-template-parameters.png)

1. Modifica il valore **Targeting e flussi di lavoro** in **Sì**. e conferma. Scopri come aggiungere funzionalità in [Tipologia di moduli](#typology-of-enabled-modules).
1. La scheda **Impostazione destinazione e flussi di lavoro** è stata aggiunta al modello. Fare clic su **Aggiungi flusso di lavoro...**, immettere un **Etichetta** e fare clic su **Ok**.
1. Crea il flusso di lavoro in base alle tue esigenze.

   ![Scheda Targeting e flussi di lavoro del modello con un flusso di lavoro contenente Query e Read list che porta alla consegna e-mail.](assets/campaign-template-create-wf.png)

1. Fai clic su **Salva**. Il modello è ora pronto per essere utilizzato per creare una nuova campagna.

Le varie schede e schede secondarie del modello della campagna consentono di accedere alle relative impostazioni, come descritto in [Configurazione generale](#general-configuration).

## Seleziona moduli {#select-modules}

Il collegamento **[!UICONTROL Advanced campaign parameters...]** consente di abilitare e disabilitare i processi per le campagne basate su questo modello. Seleziona le funzionalità che desideri abilitare nelle campagne create in base a questo modello.

![Scheda Configurazione impostazioni avanzate in cui sono elencate tutte le funzionalità con un valore Sì o No; spese e obiettivi sono No.](assets/campaign-template-select-modules.png)

Se non è selezionata una funzionalità, gli elementi relativi al processo (menu, icone, opzioni, schede, schede secondarie, ecc.) non vengono visualizzati nell’interfaccia del modello o nelle campagne basate su questo modello. Le schede a sinistra dei dettagli della campagna e le schede disponibili coincidono con le funzionalità selezionate nel modello. Ad esempio, la funzionalità **Spese e obiettivi** non è abilitata, la scheda **[!UICONTROL Budget]** corrispondente non viene visualizzata nelle campagne basate su questo modello.

Inoltre, al dashboard della campagna vengono aggiunte scelte rapide per le finestre di configurazione. Quando una funzionalità è abilitata, un collegamento diretto consente di accedervi dal dashboard della campagna.

### Esempi di configurazione

* Ad esempio, con le seguenti impostazioni:

  ![Impostazioni avanzate: gruppo di controllo, indirizzi seed e documenti impostati su Sì; approvazioni, targeting e flussi di lavoro impostati su No.](assets/campaign-template-select-functionalities.png)

  Il dashboard della campagna mostra:

  ![Dashboard di Campaign con solo le schede Dashboard e Modifica, Aggiungi una consegna e Aggiungi collegamenti a documenti.](assets/campaign-template-dashboard-sample-1.png)

  Manca la scheda **[!UICONTROL Targeting and workflows]**.

  Sono disponibili le seguenti funzionalità:

  ![Scheda Modifica della campagna con le sezioni Proprietà, Documenti e Audit e nessuna sezione Budget.](assets/campaign-template-edit-sample-1.png)

  Manca la scheda **[!UICONTROL Budget]**.

  Anche le impostazioni avanzate della campagna riflettono questa configurazione.

  ![Impostazioni avanzate della campagna con le schede Popolazione controllo e Indirizzi seed e Nessuna scheda Approvazioni.](assets/campaign-template-parameters-sample-1.png)

  La scheda **[!UICONTROL Approvals]** non è disponibile.

* Con questa configurazione:
  ![Impostazioni avanzate: approvazioni, targeting e flussi di lavoro, spese e obiettivi impostati su Sì; altre funzionalità No.](assets/campaign-template-dashboard-sample-2.png)

  Il dashboard della campagna mostra:

  ![Dashboard di Campaign con la scheda Targeting e flussi di lavoro e un collegamento Aggiungi consegna, ma nessun collegamento Aggiungi documento.](assets/campaign-template-select-functionalities-2.png)

  La scheda **[!UICONTROL Targeting and workflows]** è disponibile, ma manca il collegamento **Aggiungi documento**.

  Sono disponibili le seguenti funzionalità:

  ![Scheda Modifica con la sezione Budget aperta, che mostra le relative schede Budget, Obiettivi e Costi e Spese.](assets/campaign-template-edit-sample-2.png)

  La scheda **[!UICONTROL Budget]** è disponibile.

  Anche le impostazioni avanzate della campagna riflettono questa configurazione.

  ![Impostazioni avanzate con la scheda Approvazioni e le convalide dei processi e senza le schede Popolazione controllo o Indirizzi seed.](assets/campaign-template-parameters-sample-2.png)

  La scheda **[!UICONTROL Approvals]** è disponibile, ma le schede **[!UICONTROL Control population]** e **[!UICONTROL Seed addresses]** non sono abilitate.


## Tipologia dei moduli {#typology-of-enabled-modules}

* **Gruppo di controllo**

  Quando questo modulo è selezionato, viene aggiunta una scheda aggiuntiva alle impostazioni avanzate del modello e delle campagne basate su questo modello. La configurazione può essere definita tramite il modello o singolarmente per ogni campagna. Ulteriori informazioni sui gruppi di controllo in [Consegne di campagne di marketing](marketing-campaign-deliveries.md).

  ![Scheda Popolazione controllo impostazioni avanzate con l&#39;opzione Gruppo di controllo attivata e un collegamento Modifica per la relativa configurazione.](assets/template-activate-1.png)


* **Indirizzi di seed**

  Quando questo modulo è selezionato, viene aggiunta una scheda aggiuntiva alle impostazioni avanzate del modello e delle campagne basate su questo modello. La configurazione può essere definita tramite il modello o singolarmente per ogni campagna.

  ![Impostazioni avanzate Scheda Indirizzi seed con un collegamento Importa modelli seed e un elenco di indirizzi seed.](assets/template-activate-2.png)

* **Documenti**

  Quando questo modulo è selezionato, viene aggiunta una scheda aggiuntiva alla scheda **[!UICONTROL Edit]** del modello e delle campagne basate su questo modello. I documenti allegati possono essere aggiunti dal modello o singolarmente per ciascuna campagna. Ulteriori informazioni sui documenti in [Consegne di campagne di marketing](marketing-campaign-deliveries.md).

  ![Sezione Documenti della scheda Modifica in cui sono elencati i documenti allegati, con i pulsanti Aggiungi, Elimina e Dettagli.](assets/template-activate-3.png)

* **Profilo di consegna**

  Quando questo modulo è selezionato, alla scheda **[!UICONTROL Documents]** viene aggiunta una scheda secondaria **[!UICONTROL Delivery outlines]** per definire i profili di consegna per la campagna. Ulteriori informazioni sui profili di consegna in [Usa profili di consegna](marketing-campaign-assets.md#delivery-outlines).

  ![Scheda secondaria dei profili di consegna della sezione Documenti con un collegamento Aggiungi struttura di consegna.](assets/template-activate-4.png)

* **Impostazione destinazione e flussi di lavoro**

  Quando selezioni il modulo **[!UICONTROL Targeting and workflows]**, viene aggiunta una scheda che consente di creare uno o più flussi di lavoro per le campagne basate su questo modello. I flussi di lavoro possono anche essere configurati singolarmente per ogni campagna basata su questo modello.Ulteriori informazioni sui flussi di lavoro delle campagne in [Consegne di campagne di marketing](marketing-campaign-deliveries.md).

  ![Scheda Targeting e flussi di lavoro con un flusso di lavoro: Query e Leggi elenco, Deduplicazione, Consegna mobile.](assets/template-activate-5.png)

  Quando questo modulo è abilitato, viene aggiunta una scheda **[!UICONTROL Jobs]** alle impostazioni avanzate della campagna per definire la sequenza di esecuzione del processo.

* **Approvazioni**

  Se abiliti **[!UICONTROL Approvals]**, puoi selezionare i processi da approvare e gli operatori responsabili delle approvazioni. Ulteriori informazioni sulle approvazioni in [Seleziona revisori](marketing-campaign-approval.md#select-reviewers).

  ![Scheda Approvazioni impostazioni avanzate con approvazioni di contenuto, destinazione, budget ed estrazione abilitate e revisori assegnati.](assets/template-activate-6.png)

  È possibile scegliere se abilitare o meno l&#39;approvazione del processo tramite la scheda **[!UICONTROL Approvals]** della sezione delle impostazioni avanzate dei modelli.

* **Spese e obiettivi**

  Quando questo modulo è selezionato, viene aggiunta una scheda **[!UICONTROL Budget]** ai dettagli del modello e delle campagne basate su questo modello, in modo che sia possibile selezionare il budget associato.

  ![Sezione Budget della scheda Modifica con i campi di budget correlati, gli obiettivi e la scheda Costi con le righe di costo.](assets/template-activate-7.png)


## Proprietà modello {#template-properties}

![Scheda Modifica modello campagna con il menu a discesa Tipo di operazione aperto, che mostra Univoco, Ricorrente e Periodico.](assets/template-op-type.png)

Quando crei un modello di campagna, devi immettere le seguenti informazioni:

* Immetti l&#39;**etichetta** del modello: l&#39;etichetta è obbligatoria ed è l&#39;etichetta predefinita per tutte le campagne basate su questo modello.
* Seleziona la campagna **natura** dall&#39;elenco a discesa. I valori disponibili in questo elenco sono quelli salvati nell&#39;enumerazione **[!UICONTROL natureOp]**.

  Scopri come accedere e configurare le enumerazioni in [Gestione enumerazioni](../../v8/config/enumerations.md).

* Selezionare il tipo **di campagna**: univoco, ricorrente o periodico. Per impostazione predefinita, i modelli di campagna si applicano a campagne univoche. Le campagne ricorrenti e periodiche sono descritte in dettaglio in [Creare campagne ricorrenti e periodiche](recurring-periodic-campaigns.md).
* Specifica la durata della campagna, ovvero il numero di giorni durante i quali la campagna avrà luogo. Quando crei una campagna basata su questo modello, le date di inizio e di fine della campagna verranno compilate automaticamente.

  Se la campagna è ricorrente, devi specificare le date di inizio e di fine della campagna direttamente nel modello.

* Specifica il **programma correlato** del modello: le campagne basate su questo modello sono collegate al programma selezionato.

<!--
## Track campaign execution{#campaign-reverse-scheduling}

You can create a schedule for a campaign and track accomplishments, for instance to prepare an event schedule for a specific date. Campaign templates now let you calculate the start date of a task based on the end date of a campaign.


In the task configuration box, go to the **[!UICONTROL Implementation schedule]** area and check the **[!UICONTROL The start date is calculated based on the campaign end date]** box. (Here, "start date" is the task start date). Go to the **[!UICONTROL Start]** field and enter an interval: the task will start this long before the campaign end date. If you enter a period which is longer than the campaign is set to last, the task will begin before the campaign.

![](assets/mrm_task_in_template_start_date.png)

When you create a campaign using this template, the task start date will be calculated automatically. However, you can always change it later.
-->
