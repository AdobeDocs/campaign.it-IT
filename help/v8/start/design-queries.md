---
title: Progettare le query in Campaign v8
description: Scopri come creare query nella console client di Campaign
feature: Query Editor, Data Management
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: edd495a377559007dad7158c9ab4a4917d89ae73
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 2%

---

# Query database Campaign

Le query vengono create utilizzando i campi della tabella selezionata o utilizzando una formula.

I passaggi per la creazione di una query in Adobe Campaign sono i seguenti:

1. [Selezionare la tabella di lavoro](#step-1---choose-a-table).
1. [Selezionare i dati da estrarre](#step-2---choose-data-to-extract).
1. [Definire la modalità di ordinamento dei dati](#step-3---sort-data).
1. [Definire le opzioni di filtro dei dati](#step-4---filter-data).
1. [Configura la formattazione dei dati](#step-5---format-data).
1. [Anteprima dei risultati della query](#step-6---preview-data).

Tutti questi passaggi sono disponibili nell&#39;[editor di query generico](query-editor.md). Quando una query viene creata in un altro contesto, alcuni passaggi possono mancare. Per ulteriori informazioni sulle query, consulta anche la [documentazione sull&#39;attività Query del flusso di lavoro](../../automation/workflow/query.md).


## Passaggio 1: scegliere una tabella {#step-1---choose-a-table}

Per eseguire una query sul database di Campaign, aprire l&#39;**[editor di query generico](query-editor.md)** e selezionare la tabella contenente i dati che si desidera eseguire nella finestra **[!UICONTROL Document type]**.

![](assets/query_editor_nveau_21.png)

Se necessario, filtrare i dati utilizzando il campo filtro o il pulsante **[!UICONTROL Filters]**.

## Passaggio 2: scegliere i dati da estrarre {#step-2---choose-data-to-extract}

Nella schermata **[!UICONTROL Data to extract]** scegliere i campi che si desidera includere nell&#39;output. Questi campi definiscono le colonne visualizzate nei risultati.

È possibile ad esempio selezionare **[!UICONTROL Age]**, **[!UICONTROL Primary key]**, **[!UICONTROL Email domain]** e **[!UICONTROL City]**. L’output sarà strutturato in base a questa selezione. Per regolare l&#39;ordine delle colonne, utilizzare le frecce blu sul lato destro della finestra.

![](assets/query_editor_nveau_01.png)

È possibile modificare un&#39;espressione aggiungendo una formula o applicando un processo a una funzione di aggregazione. Per modificare un&#39;espressione, fare clic sul campo colonna **[!UICONTROL Expression]**, quindi selezionare **[!UICONTROL Edit expression]**.

![](assets/query_editor_nveau_97.png)

È possibile raggruppare i dati visualizzati nelle colonne di output. A tale scopo, selezionare **[!UICONTROL Yes]** nella colonna **[!UICONTROL Group]** della finestra **[!UICONTROL Data to extract]**. I risultati verranno quindi aggregati in base all&#39;asse di raggruppamento selezionato. Per un esempio di query con raggruppamento, vedere [questa sezione](../../automation/workflow/query-delivery-info.md).

![](assets/query_editor_nveau_56.png)

* L&#39;opzione **[!UICONTROL Handle groupings (GROUP BY + HAVING)]** consente di raggruppare i risultati e di applicare condizioni a tali gruppi. Si applica a tutti i campi nelle colonne di output. Ad esempio, puoi utilizzarlo per raggruppare i valori di una colonna di output e quindi filtrare i risultati in modo da recuperare solo informazioni specifiche, ad esempio i destinatari di età compresa tra 35 e 50 anni.

  Per ulteriori informazioni al riguardo, consulta [questa sezione](../../automation/workflow/query-grouping-management.md).

L&#39;opzione **[!UICONTROL Remove duplicate rows (DISTINCT)]** elimina righe identiche dall&#39;output (deduplicazione). Ad esempio, se selezioni **Cognome**, **Nome** e **E-mail** come colonne di output, tutti i record con gli stessi valori in tutti e tre i campi verranno considerati duplicati. Nei risultati verrà mantenuta solo un’istanza, garantendo che ogni contatto venga visualizzato una sola volta.

## Passaggio 3: ordinare i dati {#step-3---sort-data}

La finestra **[!UICONTROL Sorting]** consente di ordinare il contenuto delle colonne. Utilizza le frecce per modificare l’ordine delle colonne:

* La colonna **[!UICONTROL Sorting]** consente un ordinamento semplice e dispone il contenuto delle colonne da A a Z o in ordine crescente.
* **[!UICONTROL Descending sort]** dispone il contenuto da Z ad A e in ordine decrescente. Ciò è utile, ad esempio, per visualizzare le vendite dei record: le cifre più alte vengono visualizzate nella parte superiore dell’elenco.

In questo esempio, i dati vengono ordinati in ordine crescente in base all’età del destinatario.

![](assets/query_editor_nveau_57.png)

## Passaggio 4: filtrare i dati {#step-4---filter-data}

L’editor delle query ti consente di filtrare i dati per limitare i risultati. I filtri disponibili dipendono dalla tabella su cui si sta eseguendo la query.

![](assets/query_editor_nveau_09.png)

Dopo aver selezionato **[!UICONTROL Filtering conditions]**, viene aperta la sezione **[!UICONTROL Target elements]**. Qui puoi definire le regole per filtrare i dati da raccogliere.

* Per creare un nuovo filtro, scegli i campi, gli operatori e i valori necessari per creare la condizione. È inoltre possibile combinare più condizioni, come spiegato [in questa pagina](filter-conditions.md).

* Per riutilizzare un filtro esistente, fare clic sul pulsante **[!UICONTROL Add]**, selezionare **[!UICONTROL Predefined filter]** e scegliere il filtro desiderato.

  ![](assets/query_editor_15.png)

I filtri creati in **[!UICONTROL Generic query editor]** possono essere riutilizzati in altre applicazioni di query e viceversa. Per salvare un filtro per un utilizzo successivo, fare clic sull&#39;icona **[!UICONTROL Save]**.

>[!NOTE]
>
>Per ulteriori informazioni sulla creazione e l&#39;utilizzo dei filtri, consulta [Opzioni di filtro](filter-conditions.md).

Come mostrato nell&#39;esempio seguente, per recuperare tutti i destinatari di lingua inglese, selezionare: &quot;recipient language **equal to** EN&quot;.

![](assets/query_editor_nveau_89.png)

>[!NOTE]
>
>Puoi accedere direttamente a un&#39;opzione digitando la seguente formula nel campo **Valore**: **$(opzioni:OPTION_NAME)**.

Fare clic sulla scheda **[!UICONTROL Preview]** per visualizzare il risultato della condizione di filtro. In questo caso, tutti i destinatari di lingua inglese vengono visualizzati con il loro nome, nome e indirizzo e-mail.

![](assets/query_editor_nveau_98.png)

Gli utenti che hanno familiarità con il linguaggio SQL possono fare clic su **[!UICONTROL Generate SQL query]** per visualizzare la query in SQL.

![](assets/query_editor_nveau_99.png)

## Passaggio 5: formattare i dati {#step-5---format-data}

Dopo aver configurato i filtri di restrizione, viene visualizzata la finestra **[!UICONTROL Data formatting]**. In questa finestra è possibile ridisporre le colonne di output, trasformare i dati e regolare la maiuscola delle etichette di colonna. È inoltre possibile applicare formule al risultato finale creando un campo calcolato.

>[!NOTE]
>
>Per ulteriori informazioni sui tipi di campi calcolati, vedere [Creare campi calcolati](filter-conditions.md#creating-calculated-fields).

Le colonne non selezionate sono nascoste nella finestra di anteprima dati.

![](assets/query_editor_nveau_10.png)

La colonna **[!UICONTROL Transformation]** consente di modificare l&#39;etichetta di una colonna in maiuscolo o minuscolo. Selezionare la colonna e fare clic nella colonna **[!UICONTROL Transformation]**. Puoi scegliere:

* **[!UICONTROL Switch to lower case]**,
* **[!UICONTROL Switch to upper case]**,
* **[!UICONTROL First letter in upper case]**.

![](assets/query_editor_nveau_42.png)

## Passaggio 6: visualizzare l’anteprima dei dati {#step-6---preview-data}

La finestra **[!UICONTROL Data preview]** contrassegna la fase finale del processo di query. Fai clic su **[!UICONTROL Start the preview of the data]** per esaminare i risultati, che possono essere visualizzati in colonne o in formato XML. Per esaminare la query SQL sottostante, aprire la scheda **[!UICONTROL Generated SQL queries]**. Questo passaggio ti consente di verificare che la query si comporti come previsto prima di utilizzarla ulteriormente.

In questo esempio, i dati vengono ordinati in ordine crescente in base all’età del destinatario.

![](assets/query_editor_nveau_11.png)

>[!NOTE]
>
>Come in per tutti gli elenchi disponibili nella console, per impostazione predefinita nella finestra **[!UICONTROL Data preview]** vengono visualizzate solo le prime 200 righe. Per modificare il valore, immettere un numero nella casella **[!UICONTROL Lines to display]** e fare clic su **[!UICONTROL Start the preview of the data]**. [Ulteriori informazioni](../config/ui-settings.md#manage-and-customize-lists)



**Argomenti correlati**

* [Attività query flusso di lavoro](../../automation/workflow/query.md)
* [Eseguire una query sulla tabella dei destinatari](../../automation/workflow/querying-recipient-table.md)
* [Condizioni di filtro](filter-conditions.md)