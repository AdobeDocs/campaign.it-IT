---
product: campaign
title: Configurare le regole di filtro
description: Scopri come configurare le regole di filtro
feature: Typology Rules
exl-id: 17507cdf-211f-4fa2-abb9-33d4f6dc47bb
source-git-commit: 1fb93efac4fee4965213f8b42f518f2c10638e20
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 1%

---

# Regole di filtro{#filtering-rules}

Utilizza le regole di filtro per selezionare i messaggi da escludere in base ai criteri definiti in una query. Queste regole sono collegate a una dimensione di targeting.

Le regole di filtro possono essere collegate ad altri tipi di regole (controllo, pressione, ecc.) nelle tipologie o raggruppate in una tipologia **Filtro** dedicata. [Ulteriori informazioni](#create-and-use-a-filtering-typology).

## Creare una regola di filtro {#create-a-filtering-rule}

Ad esempio, puoi filtrare gli abbonati alle newsletter per evitare che le comunicazioni vengano inviate a destinatari minorenni.

Per definire questo filtro, effettua le seguenti operazioni:

1. Individua la cartella **[!UICONTROL Administration > Campaign management > Typology management > Typology rules]** di Campaign Exporer e fai clic sull&#39;icona **Nuovo** per creare una regola di tipologia.
1. Creare una regola di tipologia **[!UICONTROL Filtering]** applicabile a tutti i canali.

   ![](assets/campaign_opt_create_filter_01.png)

1. Dalla scheda **Filtro**, modifica la dimensione di targeting predefinita in **Sottoscrizioni** (**nms:subscription**).

   ![](assets/campaign_opt_create_filter_02.png)

1. Creare il filtro utilizzando il collegamento **[!UICONTROL Edit the query from the targeting dimension...]**.

   ![](assets/campaign_opt_create_filter_03.png)

1. Filtra in base all’età del destinatario e salva la condizione di filtro.

   ![](assets/campaign_opt_create_filter_03b.png)

1. Dalla scheda **Tipologie**, collega questa regola a una tipologia di campagna e salvala.

   ![](assets/campaign_opt_create_filter_04.png)

Quando questa regola viene utilizzata in una consegna, gli abbonati minorenni vengono esclusi automaticamente. Un messaggio specifico indica quando viene applicata la regola:

![](assets/campaign_opt_create_filter_05.png)

## Condizione di una regola di filtro {#condition-a-filtering-rule}

Puoi limitare il campo dell’applicazione della regola di filtro in base alla consegna o alla struttura della consegna collegata.

A questo scopo, vai alla scheda **[!UICONTROL General]** della regola di tipologia, seleziona il tipo di restrizione da applicare e crea il filtro.
<!--
![](assets/campaign_opt_create_filter_06.png)
-->


In questo caso, anche se la regola è collegata a tutte le consegne, verrà applicata solo a quelle che corrispondono ai criteri del filtro definito.

>[!NOTE]
>
>Le tipologie e le regole di filtro possono essere utilizzate in un flusso di lavoro, nell&#39;attività **[!UICONTROL Delivery outline]**. [Ulteriori informazioni](../workflow/delivery-outline.md).

## Creare e utilizzare una tipologia di filtro {#create-and-use-a-filtering-typology}

È possibile creare **[!UICONTROL Filtering]** tipologie: contengono solo regole di filtro.

![](assets/campaign_opt_create_typo_filtering.png)

Queste tipologie specifiche possono essere collegate a una consegna quando la destinazione è selezionata: nella procedura guidata di consegna, fai clic sul collegamento **[!UICONTROL To]**, quindi sulla scheda **[!UICONTROL Exclusions]**.

![](assets/campaign_opt_apply_typo_filtering.png)

Quindi seleziona la tipologia di filtro da applicare alla consegna. A tale scopo, fare clic sul pulsante **[!UICONTROL Add]** e selezionare le tipologie da applicare.

Puoi anche collegare le regole di filtro direttamente tramite questa scheda, senza raggrupparle in una tipologia. A tale scopo, utilizzare la sezione inferiore della finestra.

![](assets/campaign_opt_select_typo_filtering.png)

>[!NOTE]
>
>Nella finestra di selezione sono disponibili solo le tipologie e le regole di filtro.
>
>Queste configurazioni possono essere definite nel modello di consegna e applicate automaticamente a tutte le nuove consegne create utilizzando il modello.
>

## Regole di esclusione del recapito messaggi predefinite {#default-deliverability-exclusion-rules}

Per impostazione predefinita sono disponibili due regole di filtro: **[!UICONTROL Exclude addresses]** ( **[!UICONTROL addressExclusions]** ) e **[!UICONTROL Exclude domains]** ( **[!UICONTROL domainExclusions]** ). Durante l’analisi e-mail, queste regole confrontano gli indirizzi e-mail dei destinatari con gli indirizzi o i nomi di dominio non consentiti contenuti in un elenco di soppressione globale crittografato gestito nell’istanza di recapito messaggi. In caso di corrispondenza, il messaggio non viene inviato al destinatario.

Questo per evitare di essere aggiunti al inserisco nell&#39;elenco Bloccati di a causa di attività dannose, in particolare l’utilizzo di uno Spamtrap. Ad esempio, se utilizzi uno Spamtrap per abbonarti tramite uno dei tuoi moduli web, un’e-mail di conferma viene inviata automaticamente a quello Spamtrap, e il tuo indirizzo viene aggiunto automaticamente al inserisco nell&#39;elenco Bloccati di.

>[!NOTE]
>
>Gli indirizzi e i nomi di dominio contenuti nell’elenco di soppressione globale sono nascosti. Nei registri di analisi della consegna è indicato solo il numero di destinatari esclusi.
