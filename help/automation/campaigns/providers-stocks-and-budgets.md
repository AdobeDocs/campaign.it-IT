---
product: campaign
title: Fornitori, scorte e budget
description: Fornitori, scorte e budget
feature: Budget Management, Campaigns
role: User
exl-id: 1d4a98e6-af11-4645-864e-29aa5766d9d8
source-git-commit: c3f4ad0b56dd45d19eebaa4d2f06551c8fecac1d
workflow-type: tm+mt
source-wordcount: '1832'
ht-degree: 1%

---

# Fornitori, scorte e budget{#providers-stocks-and-budgets}

Adobe Campaign consente di definire i provider di servizi che saranno coinvolti nei processi eseguiti all’interno delle campagne. Le informazioni relative ai fornitori di servizi e alle relative strutture di costo sono definite dall’amministratore di Adobe Campaign a partire dalla visualizzazione principale. Il fornitore di servizi è indicato dalla consegna e la sua struttura dei costi consente il calcolo dei costi associati a tale consegna e la gestione delle scorte in questione.

## Creazione di provider di servizi e relative strutture di costo {#create-service-providers-and-their-cost-structures}

Ogni provider di servizi viene salvato in un file con i dettagli dei contatti, i modelli di servizio e i processi correlati.

I provider di servizi sono configurati in **[!UICONTROL Administration > Campaign management]** cartella di Campaign explorer.

I lavori svolti durante le consegne sono svolti da fornitori di servizi, in particolare per la direct mailing e i canali mobili. Questi fornitori di servizi possono, ad esempio, essere coinvolti nella stampa o nella distribuzione di messaggi. Questi lavori comportano configurazioni e costi specifici per ciascun fornitore di servizi. La configurazione dei prestatori di servizi prevede quattro fasi:

1. Creazione di un provider di servizi in Adobe Campaign. [Ulteriori informazioni](#add-a-service-provider)

1. Definizione delle categorie di costo e delle strutture dei modelli di servizio associati. [Ulteriori informazioni](#define-cost-categories)

1. Configurazione dei processi. [Ulteriori informazioni](#configure-processes-associated-with-a-service).

1. Riferimento al fornitore di servizi a livello di campagna. [Ulteriori informazioni](#associate-a-service-with-a-campaign).

### Creazione di un provider di servizi e delle relative categorie di costo {#create-a-service-provider-and-its-cost-categories}

#### Aggiungere un provider di servizi {#add-a-service-provider}

Puoi creare tutti i provider di servizi necessari per le consegne. La procedura per aggiungere un fornitore di servizi è la seguente:

1. Fai clic su **[!UICONTROL New]** sopra l&#39;elenco dei fornitori di servizi.
1. Nella sezione inferiore della finestra specificare il nome e i recapiti del provider di servizi.

   ![](assets/add-a-supplier.png)

1. Fai clic su **[!UICONTROL Save]** per aggiungere il provider di servizi all&#39;elenco.

#### Definire le categorie di costo {#define-cost-categories}

È ora possibile associare modelli di servizio a ciascun provider di servizi. In questi modelli, è necessario innanzitutto identificare le categorie di costo e, se necessario, lo stock interessato. È quindi possibile creare le regole di calcolo dei costi per ogni categoria tramite le strutture dei costi. [Ulteriori informazioni](#define-the-cost-structure).

Una categoria di costi è un’entità contenente una serie di costi ammissibili per un tipo di consegna (e-mail, direct mail, SMS, ecc.). Le categorie di costo sono raggruppate nei modelli dei servizi associati ai fornitori di servizi. Ogni provider di servizi può fare riferimento a uno o più modelli di servizio.

Per creare un modello di servizio e definirne il contenuto, effettuare le seguenti operazioni:

1. In **[!UICONTROL Services]** del provider di servizi, fare clic sul pulsante **[!UICONTROL Add]** e immettere il nome del modello di servizio.

   ![](assets/supplier-new-template.png)

1. Crea le categorie di costo per ogni tipo di processo (consegna tramite direct mailing/e-mail/ecc.). o attività). A questo scopo, fai clic su **[!UICONTROL Cost categories]** e quindi la scheda **[!UICONTROL Add]** e inserire i parametri di ciascuna categoria di costo.

   ![](assets/add-cost-categories.png)

   * Immettere un&#39;etichetta per questa categoria di costi e selezionare il tipo di processo interessato: **[!UICONTROL Direct mail]**, **[!UICONTROL Email]**, **[!UICONTROL Mobile]**, ecc.
   * Fai clic su **[!UICONTROL Add]** per definire i tipi di costo associati a questa categoria.
   * Se necessario, associare una linea di magazzino a ciascun tipo di costo in modo che le quantità utilizzate vengano automaticamente correlate alle scorte esistenti.

     >[!NOTE]
     >
     >Le linee delle scorte sono definite nella **[!UICONTROL Stock management]** nodo. [Ulteriori informazioni](#stock-and-order-management).

1. È possibile preselezionare un valore per questa categoria di costo, che è il valore predefinito nelle categorie di costo del fornitore di servizi (anziché uno vuoto). Per eseguire questa operazione, abilita **Sì** opzione in **[!UICONTROL Selected]** colonna relativa al tipo di categoria interessata:

   ![](assets/default-cost-type.png)

   A livello di consegna, il valore viene selezionato per impostazione predefinita.

### Definire la struttura dei costi {#define-the-cost-structure}

Per ogni tipo di costo, la struttura dei costi specifica le regole di calcolo da applicare.

Fai clic su **[!UICONTROL Cost structure]** per configurare il calcolo del costo per ogni categoria e tipo di costo. Clic **[!UICONTROL Add]** e inserire la struttura dei costi.

![](assets/add-cost-structure.png)

* Per creare la struttura dei costi, selezionare il tipo di messaggio e la categoria di costo interessati dagli elenchi a discesa, nonché il tipo di costo a cui verrà applicata la regola di calcolo. Il contenuto di questi elenchi a discesa proviene dalle informazioni immesse tramite **[!UICONTROL Cost categories]** scheda.

  È necessario assegnare un&#39;etichetta alla struttura dei costi. Per impostazione predefinita, presenta la seguente struttura di consegna: **Categoria di costo - Tipo di costo**.

  Tuttavia, puoi rinominarlo: inserisci il valore desiderato direttamente in **[!UICONTROL Label]** campo.

* La formula di calcolo dei costi è definita nella sezione inferiore della finestra.

  Questa formula può essere corretta (per qualsiasi numero di messaggi) o calcolata in base al numero di messaggi.

  Quando dipende dal numero di messaggi, la struttura di calcolo dei costi può essere **[!UICONTROL Linear]**, **[!UICONTROL Linear by threshold]**, o **[!UICONTROL Constant by threshold]**.

#### Struttura lineare {#linear-structure}

Se la quantità di messaggi è sempre la stessa per un messaggio (o un batch di messaggi) indipendentemente dal numero totale di messaggi, seleziona **[!UICONTROL Linear]** e inserisci il costo di ciascun messaggio.

Se questo importo si applica a un batch di messaggi, specificare il numero di messaggi interessati nel campo **[!UICONTROL for]** campo.

![](assets/supplier_cost_structure_calc.png)


#### Struttura lineare per soglia {#linear-structure-by-threshold}

Se l’importo si applica per soglia per ogni messaggio, devi definire un **[!UICONTROL Linear by threshold]** struttura di calcolo. In questo tipo di struttura di costo, ogni messaggio costerà 0,13, ad esempio, se il numero totale di messaggi è compreso tra 1 e 100, e costerà 0,12 da 100 a 1000 messaggi inviati, oppure 0,11 da 1000 messaggi.

La configurazione è la seguente:

![](assets/supplier-cost-structure-linear.png)

Per aggiungere una soglia, fare clic su **[!UICONTROL Add]** a destra dell&#39;elenco.

#### Struttura costante per soglia {#constant-structure-by-threshold}

Infine, puoi configurare un calcolo dei costi in base al numero totale di messaggi. A questo scopo, seleziona una **[!UICONTROL Constant by threshold]** struttura di calcolo. Ad esempio, il costo verrà impostato su un importo fisso di 12.00 per 1-100 messaggi e su 100.00 per una consegna di 101-1000 messaggi e su 500.00 per una consegna superiore a 1000 messaggi, indipendentemente dal numero totale.

![](assets/supplier-cost-structure-constant.png)

### Configurare i processi associati a un servizio {#configure-processes-associated-with-a-service}

È possibile associare informazioni sui processi associati al provider di servizi tramite **[!UICONTROL Jobs]** scheda. Questa sezione consente di configurare l&#39;invio di informazioni al router.

![](assets/cost-supplier-jobs.png)

* Il **[!UICONTROL File extraction]** indica il modello di esportazione utilizzato per la consegna quando viene selezionato questo servizio. È possibile indicare il nome del file di output nel **[!UICONTROL Extraction file]** campo. Il pulsante a destra del campo consente di inserire le variabili.

* Il **[!UICONTROL Notification email]** sezione consente di specificare il modello per la notifica ai provider di servizi dopo l&#39;invio dei file. Selezionare il modello utilizzato per creare il messaggio di avviso e il gruppo di destinatari.

  Per impostazione predefinita, i modelli di consegna per i messaggi di notifica vengono salvati in **[!UICONTROL Administration > Campaign management > Technical delivery templates]** , accessibile dalla vista generale.

* Il **[!UICONTROL Post-processing]** consente di selezionare il flusso di lavoro da avviare dopo l’approvazione della consegna. Se viene immesso un modello di flusso di lavoro, viene creata automaticamente un’istanza di flusso di lavoro e quindi viene avviata non appena l’approvazione diventa effettiva. Questo flusso di lavoro può inviare il file di estrazione a un provider di servizi esterno, ad esempio per l’elaborazione.

### Associare un servizio a una campagna {#associate-a-service-with-a-campaign}

I provider di servizi sono associati alle consegne delle campagne. Sono indicati nei modelli di consegna per offrire i loro servizi nelle consegne create tramite questo modello.

Quando viene selezionato un servizio, le categorie di costo corrispondenti al tipo di consegna (direct mailing, e-mail, ecc.) vengono indicate automaticamente nella tabella centrale insieme alle opzioni di elaborazione definite.

>[!NOTE]
>
>Se quando si seleziona un servizio non viene visualizzata alcuna categoria di costo, significa che per questo tipo di processo non è stata definita alcuna categoria di costo. Ad esempio, per una consegna e-mail, se no **[!UICONTROL Email]** tipo di categoria di costo definita, non verrà visualizzata alcuna categoria e la selezione del servizio non avrà alcun effetto.

* Per una consegna direct mailing, puoi selezionare il servizio dalla finestra di configurazione.

  ![](assets/supplier-mail-delivery-select.png)

* Per le consegne su canali mobili o telefono, si applica la stessa modalità di selezione.
* Per una consegna e-mail, il servizio viene selezionato da **[!UICONTROL Advanced]** nelle proprietà di consegna, come nell’esempio seguente:

  ![](assets/supplier-email-delivery-select.png)

Il **[!UICONTROL Amount to surcharge]** consente di aggiungere un costo per questa categoria nel contesto della consegna o dell’attività interessata.

È possibile definire una selezione obbligatoria di un tipo di costo durante la definizione delle categorie di costo per una consegna. A questo scopo, seleziona **[!UICONTROL A cost type must be selected]**.

![](assets/cost-type-must-be-selected.png)

## Gestione di scorte e ordini {#stock-and-order-management}

I tipi di costo possono essere associati alle linee delle scorte per gestire gli avvisi, tenere traccia delle forniture e avviare gli ordini.

La procedura per impostare la gestione delle scorte e degli ordini in Adobe Campaign e avvisare gli operatori in caso di forniture insufficienti per una consegna è la seguente:

1. Creazione di scorte e riferimento di fornitori di servizi associati. [Ulteriori informazioni](#create-a-stock).

1. Aggiunta di linee di magazzino. [Ulteriori informazioni](#add-stock-lines).

1. Notifica agli operatori in caso di avviso. [Ulteriori informazioni](#alert-operators).

1. Ordini e forniture. [Ulteriori informazioni](#orders).

### Gestione delle scorte {#stock-management}

Adobe Campaign può avvisare un gruppo di operatori se le scorte sono esaurite o hanno raggiunto una soglia minima. I livelli delle scorte sono accessibili tramite **[!UICONTROL Stocks]** collegamento del **[!UICONTROL Campaigns]** tramite la scheda **[!UICONTROL Other choices]** collegamento dell’area di navigazione.

![](assets/stock-dashboard.png)

#### Creare un grezzo {#creating-a-stock}

Per creare un nuovo materiale grezzo, applicate le seguenti operazioni:

1. Fai clic su **[!UICONTROL Create]** sopra l’elenco delle scorte.
1. Immettere l&#39;etichetta del titolo e selezionare dall&#39;elenco a discesa il fornitore di servizi a cui è associato. [Ulteriori informazioni](#create-service-providers-and-their-cost-structures).

#### Aggiungi righe magazzino {#add-stock-lines}

Un magazzino comprende varie linee di magazzino. Una linea magazzino contiene una quantità iniziale di risorse che verranno consumate dalle consegne. Ogni linea magazzino indica la quantità consumata, la quantità in magazzino e la quantità ordinata.

Quando create un grezzo, fate clic su **[!UICONTROL Stock lines]** per aggiungere nuove righe.

![](assets/stock-new-lines.png)

Una volta creato il grezzo, utilizzate il relativo quadro comandi per creare e monitorare le linee del grezzo.

Fai clic su **[!UICONTROL Create]** per aggiungere nuove linee di magazzino.

![](assets/add-stock-lines.png)

* Indicare la quantità inizialmente in giacenza nel **[!UICONTROL Initial stock]** campo. Il **[!UICONTROL Consumed]** e **[!UICONTROL In stock]** I campi vengono calcolati automaticamente e aggiornati in base all’avanzamento delle campagne.

  ![](assets/create-new-stock-line.png)

* Indicare la soglia a partire dalla quale gli operatori devono essere avvisati di ordinare le scorte nella **[!UICONTROL Alert level]** campo. Quando viene raggiunto il livello di avviso, nella finestra di approvazione delle consegne che utilizzano questo stock viene visualizzato un messaggio di avviso.

#### Associare un magazzino alle categorie di costo {#associate-a-stock-with-cost-categories}

Per un determinato fornitore di servizi, in un servizio, una linea di magazzino può essere referenziata da una delle categorie di costo, come segue:

![](assets/select-stock-line-supplier.png)

### Tracciamento magazzino {#stock-tracking}

#### Operatori di avviso {#alert-operators}

Viene visualizzato un avviso quando una scorta a cui si fa riferimento in una consegna è insufficiente. Ad esempio, quando viene approvato un file di estrazione, viene visualizzato il seguente avviso:

![](assets/stock-alert.png)

#### Ordini {#orders}

Il **[!UICONTROL Orders]** scheda secondaria consente di visualizzare gli ordini correnti e salvare i nuovi ordini.

Per salvare un ordine, modificare la linea del magazzino di destinazione, fare clic su **[!UICONTROL Add]** e specificare la data di consegna e la quantità ordinata.

![](assets/order-stocks.png)

>[!NOTE]
>
>Una volta raggiunta la data di consegna, la linea delle scorte ordinate scompare automaticamente e la quantità inserita nella **[!UICONTROL Volume on order]** è stato aggiunto al **[!UICONTROL Tracking]** scheda. Questa quantità viene aggiunta automaticamente al volume delle scorte.

Il **[!UICONTROL Consumptions]** contiene il volume utilizzato per campagna. Le informazioni di questa scheda vengono immesse automaticamente in base alle consegne eseguite. Fai clic su **[!UICONTROL Edit]** per aprire la campagna in questione.

## Calcola budget {#calculate-budgets}

### Principio {#principle}

I costi vengono gestiti per consegne e campagne. In funzione dei progressi compiuti, tali costi sono imputati ai bilanci.

I costi di consegna di una campagna sono consolidati a livello di campagna e i costi di tutte le campagne di un programma vengono trasferiti al programma a cui sono associati. I rapporti dedicati consentono di tenere traccia dei budget per l’intera piattaforma o per ciascun piano e programma.

### Implementazione {#implementation}

In una campagna, quando selezioni il budget devi inserire l&#39;importo iniziale. I costi calcolati vengono aggiornati automaticamente in base al livello di impegno degli importi inseriti (spese effettuate, previste, impegnate, impegnate).


<!--
See [Calculating amounts](../../mrm/using/controlling-costs.md#calculating-amounts).

>[!NOTE]
>
>The procedure for creating budgets is presented in [Creating a budget](../../mrm/using/controlling-costs.md#creating-a-budget).
-->
