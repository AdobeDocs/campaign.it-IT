---
product: campaign
title: Creare campagne di marketing
description: Scopri come creare ed eseguire campagne di marketing
feature: Campaigns, Cross Channel Orchestration, Programs
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 90dd2dad-1380-490e-b958-4a28a7d930ed
source-git-commit: a5f7cf6e21b263f8a7fb4fa19a88bebb78390c3d
workflow-type: tm+mt
source-wordcount: '1327'
ht-degree: 4%

---

# Creare programmi e campagne{#create-programs-and-campaigns}

I componenti di orchestrazione delle campagne si trovano nella scheda **[!UICONTROL Campaigns]**: qui puoi vedere una panoramica dei programmi e delle campagne di marketing e dei relativi elementi associati.

Un programma di marketing è costituito da campagne, che sono costituite da consegne, risorse, ecc. Tutte le informazioni relative a consegne, budget, revisori e documenti collegati sono raggruppate nella campagna.

![](assets/campaigns-create-from-home.png)

![](assets/do-not-localize/how-to-video.png) [Scopri programmi e campagne nel video](#video)

## Utilizzare programmi e piani{#work-with-plan-and-program}

### Creare la gerarchia di piani e programmi {#create-plan-and-program}

Ogni campagna appartiene a un programma che a sua volta appartiene a un piano. Tutti i piani, i programmi e le campagne sono disponibili tramite il menu **[!UICONTROL Campaign calendar]** nella scheda **Campagne**.

Prima di iniziare a creare campagne e consegne, configura la gerarchia di cartelle per i piani e i programmi di marketing.

1. Fai clic sull&#39;icona **Explorer** nella home page.
1. Fare clic con il pulsante destro del mouse sulla cartella in cui si desidera creare il piano.
1. Selezionare **Aggiungi nuova cartella > Gestione campagne > Piano**.

   ![](assets/create-new-plan-folder.png)

1. Rinominare il piano.
1. Fare clic con il pulsante destro del mouse sul piano appena creato e selezionare **Proprietà...**.
1. Nella scheda **Generale**, modifica **Nome interno** per evitare duplicati durante le esportazioni del pacchetto.

   ![](assets/plan-properties.png)

1. Fai clic su **Salva**.
1. Fare clic con il pulsante destro del mouse sul piano appena creato e selezionare **Crea una nuova cartella &#39;Programma&#39;**.

   ![](assets/program-folder.png)

1. Ripetere i passaggi precedenti per rinominare la nuova cartella del programma e il relativo nome interno.


### Configurare un programma {#edit-a-program}

Durante la modifica di un programma, utilizza le schede descritte di seguito per sfogliarlo e configurarlo.

* Nella scheda **Pianificazione** viene visualizzato il calendario dei programmi per un mese, una settimana o un giorno, a seconda della scheda su cui si fa clic nell&#39;intestazione del calendario. Da questa pagina è possibile creare una campagna, un programma o un’attività. [Ulteriori informazioni](#campaign-calendar)

* La scheda **Modifica** ti consente di personalizzare il programma: nome, date di inizio e fine, budget, documenti collegati, ecc.

  ![](assets/new-program-edit-tab.png)

## Utilizzare le campagne{#work-with-campaigns}

### Creare una campagna {#create-a-campaign}

Puoi creare una campagna tramite l’elenco delle campagne. Per visualizzare questa visualizzazione, selezionare il menu **[!UICONTROL Campaigns]** nel dashboard **[!UICONTROL Campaigns]** e fare clic su **[!UICONTROL Create]**.

Il campo **[!UICONTROL Program]** consente di selezionare il programma a cui allegare la campagna. Queste informazioni sono obbligatorie.

![](assets/new-campaign-settings.png)

Le campagne possono essere create anche tramite dal calendario della campagna o del programma. [Ulteriori informazioni](#campaign-calendar)

Nella finestra di creazione della campagna, seleziona il modello della campagna e aggiungi un nome e una descrizione della campagna. Puoi anche specificare le date di inizio e di fine della campagna.

Fare clic su **[!UICONTROL OK]** per creare la campagna. Viene aggiunta alla pianificazione del programma e all’elenco delle campagne.

Puoi quindi modificare la campagna appena creata e definirne i parametri. Per aprire e configurare questa campagna, puoi:

1. Sfogliare il calendario della campagna e selezionare la campagna da visualizzare, quindi fare clic sul collegamento **[!UICONTROL Open]**.
1. Sfoglia la scheda **[!UICONTROL Schedule]** del programma, seleziona la campagna e aprila.
1. Sfoglia l’elenco delle campagne e fai clic sul nome della campagna da modificare.

Tutte queste azioni ti portano al dashboard della campagna.

![](assets/campaigns-dashboard-approve.png)

Accedi alle sezioni seguenti per scoprire come configurare la campagna:

* [Aggiungere consegne](marketing-campaign-deliveries.md)
* [Gestire risorse e documenti](marketing-campaign-assets.md)
* [Creare il pubblico di destinazione](marketing-campaign-target.md)
* [Impostare il processo di approvazione](marketing-campaign-approval.md)
* [Gestire scorte e budget](providers-stocks-and-budgets.md)


### Modificare le impostazioni della campagna {#campaign-settings}

Le campagne vengono create tramite modelli di campagna. Puoi configurare modelli riutilizzabili per i quali sono selezionate alcune opzioni e altre impostazioni sono già salvate.

Per ogni campagna sono disponibili le seguenti funzionalità:

* Documentazione e risorse di riferimento: è possibile associare documenti alla campagna (breve, rapporto, immagini, ecc.). Sono supportati tutti i formati di documento. [Ulteriori informazioni](marketing-campaign-deliveries.md#manage-associated-documents).
* Definire i costi: per ogni campagna, Adobe Campaign consente di definire le voci di costo e le strutture di calcolo dei costi che possono essere utilizzate durante la creazione della campagna di marketing. Ad esempio: spese di stampa, ricorso ad agenzie esterne, affitto di stanze, ecc. [Ulteriori informazioni](providers-stocks-and-budgets.md#defining-cost-categories).
* Definire gli obiettivi: puoi definire obiettivi quantificabili per una campagna, ad esempio numero di abbonati, volume di business, ecc. Queste informazioni vengono successivamente utilizzate nei rapporti delle campagne.
* Gestisce gli indirizzi seed e i gruppi di controllo. [Ulteriori informazioni](marketing-campaign-deliveries.md#defining-a-control-group).
* Gestisci approvazioni: puoi selezionare i trattamenti da approvare e, se necessario, selezionare gli operatori o i gruppi di operatori per la revisione. [Ulteriori informazioni](marketing-campaign-approval.md#checking-and-approving-deliveries).

>[!NOTE]
>
>Per accedere e aggiornare le impostazioni della campagna, sfogliare il collegamento **[!UICONTROL Advanced campaign parameters...]** nella scheda **[!UICONTROL Edit]**.

### Monitorare una campagna {#monitor-a-campaign}

Per ogni campagna, i processi, le risorse e le consegne sono centralizzati in un dashboard. Questa interfaccia consente di gestire e orchestrare azioni di marketing.

Con Adobe Campaign puoi impostare processi collaborativi per la creazione e l’approvazione dei vari passaggi delle campagne: approvazione del budget, target, contenuto, ecc. Questa orchestrazione è descritta in [questa sezione](marketing-campaign-approval.md).

![](assets/campaigns-dashboard-approval-tab.png)

>[!NOTE]
>
>I componenti disponibili in una campagna dipendono dal relativo modello. La configurazione del modello di campagna è presentata in [questa sezione](marketing-campaign-templates.md#campaign-templates).

Una volta ottenuta la campagna, utilizza il collegamento **[!UICONTROL Reports]** per accedere ai rapporti della campagna.

![](assets/campaigns-reports-dashboard.png)

## Calendario della campagna {#campaign-calendar}

Il calendario della campagna mostra tutti i programmi, i piani, le campagne e le consegne.

Per modificare un piano, un programma, una campagna o una consegna, individuarne il nome nel calendario e quindi utilizzare il collegamento **[!UICONTROL Open]**. Viene quindi visualizzato in una nuova scheda, come illustrato di seguito:

![](assets/campaign-calendar.png)

Puoi filtrare le informazioni visualizzate nel calendario della campagna. A tale scopo, fare clic sul collegamento **[!UICONTROL Filter]** e selezionare i criteri di filtro.

![](assets/campaign_planning_filter.png)

>[!NOTE]
>
>Quando si applica un filtro in base a una data, vengono visualizzate tutte le campagne con una data di inizio successiva alla data specificata e/o con una data di fine precedente alla data specificata. Le date vengono selezionate utilizzando i calendari a destra di ciascun campo.

È inoltre possibile utilizzare il campo **[!UICONTROL Search]** per filtrare gli elementi visualizzati.

Le icone collegate a ciascun elemento ti consentono di visualizzarne lo stato: completato, in corso, in corso di modifica, ecc.

Per filtrare le campagne da visualizzare, fare clic sul collegamento **[!UICONTROL Filter]** e selezionare lo stato delle campagne da visualizzare.

![](assets/calendar-filter-options.png)

Durante l’esplorazione del calendario, puoi anche creare un programma o una campagna.

![](assets/campaign-create-from-calendar.png)

Quando si crea una campagna tramite la scheda **[!UICONTROL Schedule]** di un programma, la campagna viene automaticamente collegata al programma interessato. In questo caso, il campo **[!UICONTROL Program]** è nascosto.


## Accedere a Campaign con un browser web {#use-the-web-interface}


>[!AVAILABILITY]
>
>A partire dalla versione 8.6 di Campaign, Campaign è disponibile in un’interfaccia utente web. La maggior parte delle azioni di marketing può essere eseguita da questa nuova interfaccia. [Ulteriori informazioni](../../v8/start/campaign-ui.md#discover-the-user-interface).

Puoi accedere ad alcune delle schermate della console client di Adobe Campaign tramite un browser Internet per visualizzare tutte le campagne e le consegne, nonché i rapporti e le informazioni sui profili nel database. Non è possibile creare componenti da questo accesso Web ma, a seconda dei diritti di accesso, è possibile visualizzare e/o agire sui dati nel database. In genere, puoi approvare il contenuto della campagna e il targeting, riavviare o interrompere una consegna, ecc.

1. Accedi come di consueto tramite https://`<your instance>:<port>/view/home`.
1. Utilizza i menu per accedere alle panoramiche.

   ![](assets/web-access-campaigns.png)

Oltre a navigare tra le campagne e visualizzarle, puoi eseguire i seguenti tipi di attività:

* Monitorare l’attività su un’istanza
* Partecipa ai processi di convalida, ad esempio approva o rifiuta un contenuto di consegna
* Eseguire altre azioni rapide, ad esempio sospendere un flusso di lavoro
* Accedere a tutte le funzioni di reporting
* Partecipa alle discussioni del forum

Questa tabella fornisce un riepilogo delle azioni che è possibile eseguire sulle campagne da un browser:

| Pagina  | Azione |
| --- | --- |
| Elenco di campagne, consegne, offerte, ecc. | Eliminare una voce di elenco |
| Campaign | Annullare una campagna |
| Consegna | Approva il contenuto e la destinazione della consegna<br/>Invia il contenuto della consegna<br/>Conferma una consegna<br/>Sospendi e interrompi una consegna |
| Applicazione web | Crea un&#39;applicazione Web<br/>Modifica il contenuto e le proprietà dell&#39;applicazione<br/>Salva il contenuto dell&#39;applicazione come modello<br/>Pubblica l&#39;applicazione |
| Offerta | Approva il contenuto e l&#39;idoneità dell&#39;offerta<br/>Disattiva un&#39;offerta online |
| Attività Task | Termina un&#39;attività<br/>Annulla un&#39;attività |
| Risorse di marketing | Approva una risorsa<br/>Blocca e sblocca una risorsa |
| Pacchetto campagna | Invia un pacchetto per l&#39;approvazione<br/>Approva o rifiuta un pacchetto<br/>Annulla un pacchetto |
| Ordine delle campagne | Crea un ordine<br/>Accetta o rifiuta un ordine |
| Magazzino | Eliminare una linea di magazzino |
| Simulazione di offerta | Avviare e interrompere una simulazione |
| Flusso di lavoro di destinazione | Avviare, mettere in pausa e interrompere un flusso di lavoro |
| Report | Salva i dati correnti nella cronologia del rapporto |
| Forum | Aggiungi una discussione<br/>Rispondi a un messaggio in una discussione<br/>Segui una discussione e annulla l&#39;iscrizione |

### Gestire le approvazioni

Le approvazioni di un target o di un contenuto di consegna possono essere eseguite tramite accesso web.

![](assets/web-access-approval.png)

Puoi anche utilizzare il collegamento contenuto nei messaggi di notifica. Per ulteriori informazioni al riguardo, consulta [questa sezione](marketing-campaign-approval.md#checking-and-approving-deliveries).


## Video tutorial {#video}

Questo video mostra come creare un piano di marketing, programmi e campagne.

>[!VIDEO](https://video.tv.adobe.com/v/333810?quality=12)
