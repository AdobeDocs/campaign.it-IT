---
title: Progettare le query in Campaign v8
description: Scopri come creare le query
feature: Query Editor, Data Management
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: 46f97303adf21e88aaa3417c6596dcb62e453c9e
workflow-type: tm+mt
source-wordcount: '1038'
ht-degree: 11%

---

# Query database Campaign

Lo strumento di query di Adobe Campaign si trova su più livelli del software: per creare una popolazione target, segmentare i clienti, estrarre e filtrare i log di tracking, creare filtri, ecc.

Lo strumento di query Adobe Campaign consente di eseguire query in un database utilizzando un assistente dedicato: l’editor di query generico. È accessibile tramite il menu **[!UICONTROL Tools > Generic query editor...]**. Ti consente di estrarre le informazioni archiviate in un database e organizzarle, raggrupparle, ordinarle, eccetera. Ad esempio, l’utente può recuperare i destinatari che hanno fatto clic più di “n” volte sul collegamento di una newsletter in un determinato periodo di tempo. Questo strumento ti consente di raccogliere, ordinare e visualizzare i risultati in base alle tue esigenze.

Questo strumento combina tutte possibilità di query di Adobe Campaign. Ad esempio, ti consente di creare e salvare filtri con restrizioni. Ciò significa che un filtro utente creato nell’editor di query generico può essere utilizzato nella casella di query di un flusso di lavoro di targeting, ecc.

Le query vengono create utilizzando i campi della tabella selezionata o utilizzando una formula.

I passaggi per la creazione di una query in Adobe Campaign sono i seguenti:

1. Selezionare la tabella di lavoro. Fare riferimento a [Passaggio 1 - Scegliere una tabella](#step-1---choose-a-table).
1. Seleziona i dati da estrarre. Consulta [Passaggio 2 - Scegliere i dati da estrarre](#step-2---choose-data-to-extract).
1. Definire la sequenza di ordinamento dei dati. Consulta [Passaggio 3 - Ordinare i dati](#step-3---sort-data).
1. Filtrare i dati. Consulta [Passaggio 4 - Filtrare i dati](#step-4---filter-data).
1. Formattare i dati. Consulta [Passaggio 5 - Formattare i dati](#step-5---format-data).
1. Visualizzare il risultato. Consulta [Passaggio 6 - Anteprima dati](#step-6---preview-data).


>[!NOTE]
>
>* Tutti questi passaggi sono disponibili nell’editor di query generico. Quando una query viene creata in un altro contesto, alcuni passaggi possono essere esclusi.
>
>* Per ulteriori informazioni sulle query e su come crearle, consulta la [documentazione del flusso di lavoro di Campaign](../../automation/workflow/query.md).

Per eseguire una query sul database di Campaign, apri l&#39;**editor di query generico** e segui questi passaggi:

## Passaggio 1: scegliere una tabella {#step-1---choose-a-table}

Selezionare la tabella contenente i dati da interrogare nella finestra **[!UICONTROL Document type]**. Se necessario, filtrare i dati utilizzando il campo filtro o il pulsante **[!UICONTROL Filters]**.

![](assets/query_editor_nveau_21.png)

## Passaggio 2: scegliere i dati da estrarre {#step-2---choose-data-to-extract}

Nella finestra **[!UICONTROL Data to extract]**, selezionare i dati da visualizzare: questi campi costituiranno le colonne di output.

Selezionare ad esempio **[!UICONTROL Age]**, **[!UICONTROL Primary key]**, **[!UICONTROL Email domain]** e **[!UICONTROL City]**. I risultati saranno organizzati in base a questa selezione. Utilizzare le frecce blu a destra della finestra per modificare l&#39;ordine delle colonne.

![](assets/query_editor_nveau_01.png)

È possibile modificare un&#39;espressione inserendovi una formula o eseguendo un processo su una funzione di aggregazione. A tale scopo, fare clic sul campo colonna **[!UICONTROL Expression]**, quindi selezionare **[!UICONTROL Edit expression]**.

![](assets/query_editor_nveau_97.png)

È possibile raggruppare i dati della colonna di output: a tale scopo, selezionare **[!UICONTROL Yes]** nella colonna **[!UICONTROL Group]** della finestra **[!UICONTROL Data to extract]**. Questa funzione genera un risultato attorno all’asse di raggruppamento selezionato. Un esempio di query con raggruppamento è disponibile in [questa sezione](../../automation/workflow/query-delivery-info.md).

![](assets/query_editor_nveau_56.png)

* La funzione **[!UICONTROL Handle groupings (GROUP BY + HAVING)]** consente di &quot;raggruppare&quot; e selezionare ciò che è stato raggruppato (&quot;avere&quot;). Questa funzione si applica a tutti i campi nella colonna di output. Ad esempio, questa opzione consente di raggruppare tutte le scelte di una colonna di output e di recuperare un tipo specifico di informazioni, ad esempio i destinatari compresi tra 35 e 50.

  Per ulteriori informazioni al riguardo, consulta [questa sezione](../../automation/workflow/query-grouping-management.md).

* La funzione **[!UICONTROL Remove duplicate rows (DISTINCT)]** consente di deduplicare risultati identici ottenuti nella colonna di output. Ad esempio, se esegui un censimento selezionando i campi Cognome, Nome ed E-mail nella colonna di output, quelli con dati identici verranno eliminati, in quanto significa che lo stesso contatto è stato immesso più volte nel database: verrà preso in considerazione un solo risultato.

## Passaggio 3: ordinare i dati {#step-3---sort-data}

La finestra **[!UICONTROL Sorting]** consente di ordinare il contenuto delle colonne. Utilizza le frecce per modificare l’ordine delle colonne:

* La colonna **[!UICONTROL Sorting]** consente un ordinamento semplice e dispone il contenuto delle colonne da A a Z o in ordine crescente.
* **[!UICONTROL Descending sort]** dispone il contenuto da Z ad A e in ordine decrescente. Ciò è utile, ad esempio, per visualizzare le vendite dei record: le cifre più alte vengono visualizzate nella parte superiore dell’elenco.

In questo esempio, i dati vengono ordinati in ordine crescente in base all’età del destinatario.

![](assets/query_editor_nveau_57.png)

## Passaggio 4: filtrare i dati {#step-4---filter-data}

L’editor delle query ti consente di filtrare i dati per perfezionare la ricerca.

I filtri offerti dipendono dalla tabella interessata dalla query.

![](assets/query_editor_nveau_09.png)

Dopo aver selezionato **[!UICONTROL Filtering conditions]**, potrai accedere alla sezione **[!UICONTROL Target elements]**: questo ti consente di definire come filtrare i dati da raccogliere.

* Per creare un nuovo filtro, selezionare i campi, gli operatori e i valori necessari per la creazione della formula da verificare per la selezione dei dati. Puoi anche combinare diverse condizioni come [dettagliato in questa pagina](filter-conditions.md).
* Per utilizzare i filtri salvati in precedenza, aprire l&#39;elenco a discesa facendo clic sul pulsante **[!UICONTROL Add]**, fare clic su **[!UICONTROL Predefined filter]** e selezionare quello desiderato.

  ![](assets/query_editor_15.png)

* I filtri creati in **[!UICONTROL Generic query editor]** sono disponibili in altre applicazioni di query e viceversa. Per salvare un filtro, fare clic sull&#39;icona **[!UICONTROL Save]**.

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

Dopo aver configurato i filtri di restrizione, si accede alla finestra **[!UICONTROL Data formatting]**. Questa finestra consente di ridisporre le colonne di output, trasformare i dati e modificare le lettere maiuscole e minuscole delle etichette di colonna. Consente inoltre di applicare una formula al risultato finale utilizzando un campo calcolato.

>[!NOTE]
>
>Per ulteriori informazioni sui tipi di campi calcolati, vedere [Creare campi calcolati](filter-conditions.md#creating-calculated-fields).

Le colonne non selezionate non vengono visualizzate nella finestra di anteprima dati.

![](assets/query_editor_nveau_10.png)

La colonna **[!UICONTROL Transformation]** consente di modificare l&#39;etichetta di una colonna in maiuscolo o minuscolo. Selezionare la colonna e fare clic nella colonna **[!UICONTROL Transformation]**. Puoi scegliere:

* **[!UICONTROL Switch to lower case]**,
* **[!UICONTROL Switch to upper case]**,
* **[!UICONTROL First letter in upper case]**.

![](assets/query_editor_nveau_42.png)

## Passaggio 6: visualizzare l’anteprima dei dati {#step-6---preview-data}

La finestra **[!UICONTROL Data preview]** è l&#39;ultima fase. Fai clic su **[!UICONTROL Start the preview of the data]** per ottenere i risultati della query. È disponibile in colonne o in formato XML. Fare clic sulla scheda **[!UICONTROL Generated SQL queries]** per visualizzare la query in formato SQL.

In questo esempio, i dati vengono ordinati in ordine crescente in base all’età del destinatario.

![](assets/query_editor_nveau_11.png)

>[!NOTE]
>
>Per impostazione predefinita, nella finestra **[!UICONTROL Data preview]** vengono visualizzate solo le prime 200 righe. Per modificare il valore, immettere un numero nella casella **[!UICONTROL Lines to display]** e fare clic su **[!UICONTROL Start the preview of the data]**.



**Argomenti correlati**

* [Attività query flusso di lavoro](../../automation/workflow/query.md)
* [Eseguire una query sulla tabella dei destinatari](../../automation/workflow/querying-recipient-table.md)
* [Condizioni di filtro](filter-conditions.md)