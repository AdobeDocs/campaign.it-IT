---
title: Creazione di un cubo in Adobe Campaign
description: Scopri come creare i cubi
feature: Reporting
role: Data Engineer
level: Beginner
exl-id: 03a6816b-e51a-4eaf-ab76-02d24f97ba46
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 3%

---

# Creare un cubo{#create-a-cube}

## Area di lavoro del cubo {#cube-workspace}

Per accedere ai cubi, passa a **[!UICONTROL Administration > Configuration > Cubes]** da Campaign explorer.

![](assets/cube-node.png)

Con i cubi è possibile:

* Esportare i dati direttamente in un rapporto, progettato in **[!UICONTROL Reports]** della piattaforma Adobe Campaign.

   A questo scopo, crea un nuovo rapporto e seleziona il cubo da utilizzare.

   ![](assets/create-new-cube.png)

   I cubi vengono visualizzati come modelli in base ai rapporti creati. Dopo aver scelto un modello, fai clic su **[!UICONTROL Create]** per configurare e visualizzare il nuovo rapporto.

   Puoi adattare le misure, modificare la modalità di visualizzazione o configurare la tabella, quindi visualizzare il rapporto utilizzando il pulsante principale.

   ![](assets/display-cube-table.png)

* Fare riferimento a un cubo nel **[!UICONTROL Query]** di una relazione per utilizzare i propri indicatori, come illustrato di seguito:

   ![](assets/cube-report-query.png)

* Inserire una tabella pivot basata su un cubo in una pagina qualsiasi di un report. A questo scopo, fai riferimento al cubo da utilizzare nel **[!UICONTROL Data]** della tabella pivot sulla pagina interessata.

   ![](assets/cube-in-a-report.png)

   Per ulteriori informazioni, consulta [Esplorare i dati in un rapporto](cube-tables.md#explore-the-data-in-a-report).


>[!CAUTION]
>
>Per creare i cubi sono necessarie le autorizzazioni di amministratore.

## Creare un cubo{#cube-create}

Prima di iniziare a creare un report cubo, identificare le dimensioni e le misure rilevanti e crearle nel cubo.

Per creare un cubo, attenersi alla procedura descritta di seguito.

1. Selezionare la tabella di lavoro. [Ulteriori informazioni](#select-the-work-table).
1. Definite le quote. [Ulteriori informazioni](#define-dimensions).
1. Definire le misure. [Ulteriori informazioni](#build-indicators).
1. Creare aggregati (facoltativo). [Ulteriori informazioni](customize-cubes.md#calculate-and-use-aggregates).

Nell’esempio seguente, scopri come creare rapidamente un cubo semplice in un rapporto per esportare le relative misure.

### Seleziona la tabella di lavoro {#select-the-work-table}

Per creare un cubo, effettuare le seguenti operazioni:

1. Fai clic su **[!UICONTROL New]** sopra l&#39;elenco dei cubi.

   ![](assets/create-a-cube.png)

1. Seleziona lo schema contenente gli elementi da esplorare (noto anche come &quot;schema dei fatti&quot;). In questo esempio, seleziona il valore predefinito **Destinatario** tabella.
1. Clic **[!UICONTROL Save]** per creare il cubo: viene aggiunto all&#39;elenco di cubi. Ora puoi utilizzare le schede per configurarlo.

1. Fai clic su **[!UICONTROL Filter the source data...]** collegamento per applicare i calcoli del cubo ai dati del database.

   ![](assets/cube-filter-source.png)

### Definire le dimensioni {#define-dimensions}

Una volta creato il cubo, definirne le dimensioni. I Dimension sono gli assi di analisi definiti per ciascun cubo in base al relativo schema fact. Queste sono le dimensioni analizzate nell’analisi, come il tempo (anno, mese, data), una classificazione di prodotti o contratti (famiglia, riferimento, ecc.), un segmento di popolazione (per città, fascia di età, stato, ecc.).

Per creare le quote, effettuate le seguenti operazioni:

1. Accedi a **[!UICONTROL Dimension]** del cubo e fare clic sul pulsante **[!UICONTROL Add]** per creare una nuova dimensione.
1. In **[!UICONTROL Expression field]**, fare clic su **[!UICONTROL Edit expression]** per selezionare il campo che contiene i dati interessati.

   ![](assets/cube-add-dimension.png)

1. In questo esempio, stiamo selezionando il destinatario **Età**. Per questo campo, puoi definire il binning per raggruppare le pagine e semplificare la lettura delle informazioni. È consigliabile utilizzare il binning quando è probabile che siano presenti più valori separati.

A questo scopo, seleziona la **[!UICONTROL Enable binning]** opzione. [Ulteriori informazioni](customize-cubes.md#data-binning).

1. Aggiungi un **Data** dimensione del tipo. In questo caso, vogliamo visualizzare le date di creazione del profilo del destinatario. A questo scopo, fai clic su **[!UICONTROL Add]** e seleziona la **[!UICONTROL Creation date]** nella tabella dei destinatari.
Puoi personalizzare la modalità di visualizzazione della data. A questo scopo, seleziona la gerarchia da utilizzare e i livelli da generare:

![](assets/cube-date-dimension.png)

Nel nostro esempio, vogliamo visualizzare solo anni, mesi e giorni. Tieni presente che non è possibile lavorare contemporaneamente con settimane e semestri/mesi: questi livelli non sono compatibili.

1. Crea un’altra dimensione per analizzare i dati relativi alla città del destinatario. A questo scopo, aggiungi una nuova dimensione e seleziona la città nel **[!UICONTROL Location]** nodo dello schema del destinatario.

È possibile abilitare il binning per semplificare la lettura delle informazioni e collegare i valori a un&#39;enumerazione.

Seleziona l’enumerazione dall’elenco a discesa. Questa enumerazione deve essere definita come **[!UICONTROL Reserved for binning]**.

![](assets/cube-dimension-with-enum.png)

Verranno visualizzati solo i valori nell’enumerazione. Gli altri saranno raggruppati sotto l’etichetta definita nella **[!UICONTROL Label of the other values]** campo.

Per ulteriori informazioni al riguardo, consulta [questa sezione](customize-cubes.md#dynamically-manage-bins).

### Creare indicatori {#build-indicators}

Una volta definite le dimensioni, specificate una modalità di calcolo per i valori da visualizzare nelle celle.

A questo scopo, crea gli indicatori nel **[!UICONTROL Measures]** scheda. Crea tutte le misure presenti nelle colonne da visualizzare nei rapporti basati su questo cubo.

Per creare gli indicatori, effettua le seguenti operazioni:

1. Accedi a **[!UICONTROL Measures]** e fai clic sul pulsante **[!UICONTROL Add]** pulsante.
1. Selezionare il tipo di misura e la formula da applicare. In questo esempio, stiamo contando il numero di donne tra i destinatari. La nostra misura si basa sullo schema dei fatti e utilizza **[!UICONTROL Count]** operatore.

   ![](assets/cube-new-measure.png)

   Utilizza il **[!UICONTROL Filter the measure data...]** collegamento per selezionare solo donne. [Ulteriori informazioni](customize-cubes.md#define-measures).

   ![](assets/cube-filter-measure-data.png)

1. Immettere l&#39;etichetta della misura e salvarla.

   ![](assets/cube-save-measure.png)

1. Salvare il cubo.


È ora possibile creare un report basato su questo cubo. [Ulteriori informazioni](cube-tables.md).
