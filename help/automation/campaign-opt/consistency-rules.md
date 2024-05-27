---
product: campaign
title: Regole di coerenza
description: Regole di coerenza
feature: Typology Rules
exl-id: dcb4ffcf-71e5-48a2-b0f7-42915a599652
source-git-commit: 7f6c394f56d517c0a675e0fd2341bb6ef98044f0
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 4%

---

# Regole di coerenza{#consistency-rules}

Adobe Campaign garantisce comunicazioni coerenti grazie a un set di regole contenute nelle tipologie di campagne. Il loro obiettivo è controllare le consegne inviate ai destinatari, ad esempio volume, natura, pertinenza e così via.

**Capacità** le regole, ad esempio, possono evitare di sovraccaricare la piattaforma interessata dalla consegna dei messaggi. Ad esempio, le offerte speciali che contengono un collegamento di download non devono essere inviate a troppe persone contemporaneamente, per evitare di saturare il server; le campagne telefoniche non devono superare la capacità di elaborazione dei call center, ecc.

## Capacità di controllo {#control-capacity}

Prima di consegnare i messaggi, è necessario assicurarsi che l’organizzazione abbia la capacità (infrastruttura fisica) di elaborare la consegna, le risposte che la consegna può generare (messaggi in entrata) e il numero di chiamate da effettuare per contattare gli abbonati (capacità di elaborazione del call center), ad esempio.

Per eseguire questa operazione, crea **[!UICONTROL Capacity]** regole di tipologia.

Nell’esempio seguente, creiamo una regola di tipologia per una campagna fedeltà telefonicamente. Limitiamo il numero di messaggi a 20 al giorno, ovvero la capacità di elaborazione giornaliera di un call center. Una volta applicata la regola a due consegne, possiamo monitorare il consumo tramite i registri.

Per progettare una nuova regola di capacità, effettuare le seguenti operazioni:

1. Sotto **[!UICONTROL Administration > Campaign management > Typology management > Typology rules]** cartella, fai clic su **[!UICONTROL New]**.
1. Seleziona un **[!UICONTROL Capacity]** tipo di regola.

   ![](assets/campaign_opt_create_capacity_01.png)

1. In **[!UICONTROL Capacity]** crea le righe relative alla disponibilità: nel nostro esempio, si tratta dei periodi di tempo durante i quali è possibile effettuare chiamate. Selezionare un periodo di 24 ore e immettere 150 nella quantità iniziale, il che significa che il call center è in grado di gestire 150 chiamate al giorno.

   ![](assets/campaign_opt_create_capacity_02.png)

   >[!NOTE]
   >
   >Le linee di disponibilità sono solo a scopo informativo. Se devi escludere i messaggi quando viene raggiunto il limite di capacità, consulta [questa sezione](#exclude-messages-when-capacity-limit-reached).

1. Associa questa regola a una tipologia e fai riferimento a essa nella consegna per applicare questa regola di capacità. Per ulteriori informazioni al riguardo, consulta [questa sezione](apply-rules.md#apply-a-typology-to-a-delivery).
1. Puoi monitorare il consumo dalla regola **[!UICONTROL Consumptions]** e **[!UICONTROL Capacity]** schede.

   Quando una regola viene utilizzata in una consegna, il **[!UICONTROL Consumed]** e **[!UICONTROL Remaining]** Le colonne forniscono informazioni sul caricamento, come illustrato di seguito:

   ![](assets/campaign_opt_create_capacity_03.png)

   Per ulteriori informazioni al riguardo, consulta [questa sezione](#monitor-consumption).

## Definire il carico massimo {#define-the-maximum-load}

Per definire il carico massimo, è necessario definire le linee di disponibilità. A questo scopo, sono disponibili due opzioni: puoi eseguire manualmente [creare una o più righe di disponibilità](#add-availability-lines-one-by-one) o creare intervalli di disponibilità. La frequenza di questi periodi di tempo può essere automatizzata. [Ulteriori informazioni](#add-a-set-of-availability-lines).

### Aggiungere righe di disponibilità una alla volta {#add-availability-lines-one-by-one}

Per creare una riga di disponibilità, fare clic su **[!UICONTROL Add]** e seleziona **[!UICONTROL Add an availability line]**. Inserire il periodo di disponibilità e il carico disponibile.

![](assets/campaign_opt_create_capacity_02.png)

Aggiungi tutte le righe necessarie per adattarle alla capacità di elaborazione.

### Aggiungere un set di righe di disponibilità {#add-a-set-of-availability-lines}

Per definire i periodi di disponibilità per un determinato periodo di tempo, fare clic sul pulsante **[!UICONTROL Add]** e selezionare il pulsante **[!UICONTROL Add a set of availability lines]** opzione. Indica una durata per ogni periodo di tempo e il numero di periodi da creare.

Per automatizzare la frequenza di creazione della pagina, fai clic sul pulsante **[!UICONTROL Change]** e definire la programmazione dei periodi di tempo.

![](assets/campaign_opt_create_capacity_07.png)

Ad esempio, definiamo una pianificazione per creare periodi di disponibilità per tutti i giorni lavorativi a una velocità di 10 chiamate all’ora tra le 9 e le 17. A questo scopo, esegui i seguenti passaggi:

1. Selezionare il tipo di periodicità e i giorni e le ore di validità:

   ![](assets/campaign_opt_create_capacity_08.png)

1. Indicare le date di validità:

   ![](assets/campaign_opt_create_capacity_09.png)

1. Controlla la pianificazione prima di approvarla:

   ![](assets/campaign_opt_create_capacity_10.png)

Il **[!UICONTROL Forecasting]** workflow crea automaticamente tutte le righe corrispondenti.

![](assets/campaign_opt_create_capacity_12.png)

>[!NOTE]
>
>È consigliabile creare righe di disponibilità tramite importazioni di file. Questa scheda consente di visualizzare e controllare le linee di consumo.

## Escludi messaggi al raggiungimento del limite di capacità {#exclude-messages-when-capacity-limit-reached}

Le righe di disponibilità sono solo a scopo informativo. Per escludere i messaggi in eccesso, selezionare la casella di controllo **[!UICONTROL Exclude from the target messages in excess of capacity]** opzione. Questo impedisce il superamento della capacità. Per la stessa popolazione dell&#39;esempio precedente, il consumo e la capacità rimanente non possono superare la quantità iniziale:

![](assets/campaign_opt_create_capacity_04.png)

Il numero massimo di messaggi che possono essere elaborati viene suddiviso in modo uniforme nell’intervallo di disponibilità definito. Ciò è particolarmente importante per i call center, poiché il loro numero massimo di chiamate al giorno è limitato. In caso di consegne e-mail, il **[!UICONTROL Do not limit instantaneous delivery capacity]** consente di ignorare questo intervallo di disponibilità e di inviare le e-mail contemporaneamente.

![](assets/campaign_opt_create_capacity_05.png)

>[!NOTE]
>
>In caso di sovraccarico, i messaggi salvati vengono selezionati in base alla formula definita nelle proprietà di consegna.

![](assets/campaign_opt_create_capacity_06.png)

## Consumo monitor {#monitoring-consumption}

Per impostazione predefinita, le regole di capacità sono solo a scopo indicativo. Seleziona la **[!UICONTROL Exclude messages in excess of capacity from the target]** per evitare il superamento del carico definito. In questo caso, i messaggi in eccesso verranno automaticamente esclusi dalle consegne utilizzando questa regola di tipologia.

Per monitorare i consumi, visualizza i valori visualizzati nella **[!UICONTROL Consumed]** colonna del **[!UICONTROL Capacity]** nella regola di tipologia.

![](assets/campaign_opt_create_capacity_04.png)

Per visualizzare le linee di consumo, fare clic su **[!UICONTROL Consumptions]** nella regola.
