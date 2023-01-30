---
product: campaign
title: Creare una campagna locale
description: Creare una campagna locale
feature: Distributed Marketing
exl-id: b46530b5-cb81-40d7-b596-c7685359782a
source-git-commit: 7e5ffbec959785971280c394c416cebe83590897
workflow-type: tm+mt
source-wordcount: '1554'
ht-degree: 1%

---

# Creare una campagna locale{#creating-a-local-campaign}



Una campagna locale è un&#39;istanza creata da un modello a cui si fa riferimento nell&#39;elenco di **[!UICONTROL campaign packages]** con **programma di esecuzione specifico**. Il suo obiettivo è soddisfare un&#39;esigenza di comunicazione locale utilizzando un modello di campagna configurato e configurato dall&#39;entità centrale. Le fasi principali per l&#39;attuazione di un&#39;operazione locale sono le seguenti:

**Per l&#39;entità centrale**

1. Creazione di un modello di campagna locale.
1. Creazione di un pacchetto della campagna da un modello.
1. Pubblicazione di un pacchetto della campagna.
1. Approvazione degli ordini.

**Per l&#39;entità locale**

1. Ordinamento della campagna.
1. Esecuzione di campagne.

## Creazione di un modello di campagna locale {#creating-a-local-campaign-template}

Per creare un pacchetto della campagna, devi innanzitutto creare il **modello di campagna** tramite **[!UICONTROL Resources > Templates]** nodo.

Per creare un nuovo modello locale, duplica il modello predefinito **[!UICONTROL Local campaign (opLocal)]** modello.

![](assets/mkg_dist_local_op_creation.png)

Denomina il modello di campagna e completa i campi disponibili.

![](assets/mkg_dist_local_op_creation1.png)

Nella finestra della campagna, fai clic su **[!UICONTROL Edit]** , quindi fai clic sul pulsante **[!UICONTROL Advanced campaign parameters...]** link.

![](assets/mkt_distr_4.png)

### Interfaccia Web {#web-interface}

In **Marketing distribuito** È possibile scegliere il tipo di interfaccia Web e specificare i valori e i parametri predefiniti da immettere quando un&#39;entità locale inserisce un ordine.

L’interfaccia web corrisponde a un modulo che deve essere compilato dall’entità locale durante l’ordinamento della campagna.

Seleziona il tipo di interfaccia web da applicare alle campagne create dal modello:

![](assets/mkt_distr_1.png)

Sono disponibili quattro tipi di interfacce web:

* **[!UICONTROL By brief]** : l’entità locale deve fornire una descrizione in cui descrive le configurazioni della campagna. Una volta approvato l’ordine, l’entità centrale configura ed esegue la campagna nel suo insieme.

   ![](assets/mkt_distr_6.png)

* **[!UICONTROL By form]** : l’entità locale ha accesso a un modulo web in cui, a seconda del modello utilizzato, può modificare il contenuto, il target, le dimensioni massime, nonché le date di creazione ed estrazione utilizzando i campi di personalizzazione. L’entità locale può valutare il target e visualizzare in anteprima il contenuto da questo modulo web.

   ![](assets/mkt_distr_8.png)

   Il modulo offerto è specificato in un&#39;applicazione Web che deve essere selezionata in un elenco a discesa dal **[!UICONTROL web Interface]** nel campo del modello **[!UICONTROL Advanced campaign parameters...]** link. Fai riferimento a [Creazione di una campagna locale (tramite modulo)](examples.md#creating-a-local-campaign--by-form-).

   >[!NOTE]
   >
   >L&#39;applicazione Web utilizzata in questo esempio è un esempio. Per poter utilizzare un modulo è necessario creare un’app Web specifica.

   ![](assets/mkt_distr_7.png)

* **[!UICONTROL By external form]** : l&#39;entità locale ha accesso ai parametri della campagna nella sua extranet (non Adobe Campaign). Questi parametri sono identici a quelli di un **campagna locale (per modulo)**.
* **[!UICONTROL Pre-set]** : campagna di ordini di entità locale utilizzando il modulo predefinito, senza localizzarlo.

   ![](assets/mkt_distr_5.png)

### Valori predefiniti {#default-values}


Seleziona la **[!UICONTROL Default values]** da completare da parte di enti locali. Ad esempio:

* date di contatto ed estrazione,
* caratteristiche del target (segmento di età, ecc.).

![](assets/mkg_dist_local_op_creation2.png)

Completa il **[!UICONTROL Parent marketing program]** e **[!UICONTROL Charge]** campi.

![](assets/mkg_dist_local_op_creation3.png)

### Approvazioni {#approvals}

Da **[!UICONTROL Advanced parameters for campaign entry]** Puoi specificare il numero massimo di revisori.

![](assets/s_advuser_mkg_dist_add_valid_op1.png)

I revisori verranno inseriti dall&#39;entità locale al momento dell&#39;ordine della campagna.

![](assets/mkt_distr_5.png)

Se non desiderate assegnare un nome ai revisori per una campagna, immettete 0.

### Documenti {#documents}

È possibile consentire agli operatori di entità locali di collegare documenti (file di testo, fogli di calcolo, immagini, descrizioni di campagne, ecc.) nella campagna locale durante la creazione dell’ordine. La **[!UICONTROL Advanced parameters for campaign entry...]** link ti consente di limitare il numero di documenti. A questo scopo, inserisci semplicemente il numero massimo consentito nel **[!UICONTROL Number of documents]** campo .

![](assets/s_advuser_mkg_dist_local_docs.png)

Quando si ordina un pacchetto della campagna, il modulo suggerisce di collegare tutti i documenti indicati nel campo corrispondente nel modello.

![](assets/s_advuser_mkg_dist_add_docs.png)

Se non si desidera visualizzare un campo di caricamento del documento, immettere **[!UICONTROL 0]** in **[!UICONTROL Number of documents]** campo .

>[!NOTE]
>
>La **[!UICONTROL Advanced parameters for campaign entry]** può essere disattivato controllando **[!UICONTROL Do not display the page used to enter the campaign parameters]**.

![](assets/s_advuser_mkg_dist_disable_op_parameters.png)

### Flusso di lavoro {#workflow}

In **[!UICONTROL Targeting and workflows]** , crea il flusso di lavoro della campagna che raccoglie i **[!UICONTROL Default values]** specificato nel **[!UICONTROL Advanced campaign parameters...]** e crea le consegne.

![](assets/mkg_dist_local_op_creation4b.png)

Fai doppio clic sul pulsante **[!UICONTROL Query]** per configurarlo in base al **[!UICONTROL Default values]**.

![](assets/mkt_dist_local_campaign_localize_query.png)

### Consegna {#delivery}

In **[!UICONTROL Audit]** fai clic sulla scheda **[!UICONTROL Detail...]** per visualizzare l&#39;icona **[!UICONTROL Scheduling]** per la consegna selezionata.

![](assets/mkg_dist_local_op_creation4c.png)

La **[!UICONTROL Scheduling]** L’icona ti consente di configurare il contatto e la data di esecuzione della consegna.

![](assets/mkg_dist_local_op_creation4d.png)

Se necessario, configura la dimensione massima della consegna:

![](assets/mkg_dist_local_op_creation4e.png)

Individua il HTML della consegna. Ad esempio, in **[!UICONTROL Delivery > Current order > Additional fields]**, utilizza **[!UICONTROL Age segment]** per individuare la consegna in base all’età del target.

![](assets/mkt_dist_local_campaign_localize_html.png)

Salva il modello della campagna. È ora possibile utilizzarlo dal **[!UICONTROL Campaign packages]** visualizza in **[!UICONTROL Campaigns]** facendo clic sulla scheda **[!UICONTROL Create]** pulsante .

![](assets/mkt_distr_9.png)

>[!NOTE]
>
>I modelli di campagna e la relativa configurazione generale sono descritti in [questa pagina](../campaigns/marketing-campaign-templates.md).

## Creazione del pacchetto della campagna {#creating-the-campaign-package}

Affinché il modello di campagna possa essere disponibile per le entità locali, deve essere aggiunto all’elenco. Per fare questo, l&#39;agenzia centrale deve creare un nuovo pacchetto.

Applica i seguenti passaggi:

1. In **[!UICONTROL Navigation]** sezione **Campagne** fai clic su **[!UICONTROL Campaign packages]** link.
1. Fai clic sul pulsante **[!UICONTROL Create]**.

   ![](assets/mkg_dist_add_an_entry.png)

1. La sezione sopra la finestra ti consente di selezionare la [precedente](#creating-a-local-campaign-template) modello di pacchetto della campagna specificato.

   Per impostazione predefinita, la **[!UICONTROL New local campaign package (localEmpty)]** viene utilizzato per le campagne locali.

1. Specifica l’etichetta, la cartella e la pianificazione di esecuzione per il pacchetto della campagna.

### Date {#dates}

Le date di inizio e di fine definiscono il periodo di visibilità della campagna nell’elenco dei pacchetti della campagna.

La data di disponibilità è la data in cui la campagna diventerà disponibile per le entità locali (su ordine).

>[!CAUTION]
>
>Se un&#39;entità locale non riserva la campagna prima della scadenza, non sarà in grado di utilizzarla.

Queste informazioni si trovano nel messaggio di notifica inviato alle agenzie locali, come mostrato di seguito:

![](assets/s_advuser_mkg_dist_local_notif.png)

### Pubblico {#audience}

Per una campagna locale, l’entità centrale può specificare le entità locali coinvolte controllando il **[!UICONTROL Limit the package to a set of local entities]**.

![](assets/s_advuser_mkg_dist_create_mutual_entry3.png)

### Impostazioni aggiuntive {#additional-settings}

Una volta salvato il pacchetto, l’entità centrale può modificarlo dalla **[!UICONTROL Edit]** scheda .

![](assets/mkg_dist_edit_kit.png)

Da **[!UICONTROL General]** , l’entità centrale può:

* configura i revisori dei pacchetti della campagna dalla **[!UICONTROL Approval parameters...]** collegamento,
* rivedere il programma di esecuzione,
* aggiungere o eliminare entità locali.

>[!NOTE]
>
>Per impostazione predefinita, ogni entità può ordinare un **campagna locale** una sola volta.
>   
>Controlla la **[!UICONTROL Enable multiple creation]** per consentire la creazione di più campagne locali dal pacchetto della campagna.

![](assets/mkg_dist_local_op_multi_crea.png)

### Notifiche {#notifications}

Quando una campagna diventa disponibile o quando viene raggiunta la scadenza della registrazione, viene inviato un messaggio agli operatori del gruppo di notifica locale. Per ulteriori informazioni, consulta [Entità organizzative](about-distributed-marketing.md#organizational-entities).

## Ordinamento di una campagna {#ordering-a-campaign}

I pacchetti Campaign diventano accessibili alle entità locali dopo che sono stati approvati e il loro periodo di implementazione è iniziato. Le entità locali ricevono un’e-mail che informa la disponibilità di un nuovo pacchetto della campagna (non appena viene raggiunta la data di disponibilità).

>[!NOTE]
>
>Se durante la creazione del pacchetto della campagna sono state specificate alcune entità locali, queste saranno le uniche a ricevere una notifica. Se non è stata specificata alcuna entità locale, tutte le entità locali riceveranno una notifica.

![](assets/mkg_dist_local_op_notification.png)

Per utilizzare una campagna offerta dall&#39;entità centrale, l&#39;entità locale deve ordinarla.

Per ordinare una campagna:

1. Fai clic su **[!UICONTROL Order campaign]** nel messaggio di notifica o nel pulsante corrispondente in Adobe Campaign.

   Immetti il tuo ID e password per ordinare la campagna. L’interfaccia è composta da un set di pagine definite in un’applicazione web.

1. Immetti le informazioni necessarie nella prima pagina (etichetta dell’ordine e commento) e fai clic su **[!UICONTROL Next]**.

   ![](assets/mkg_dist_subscribe_step1.png)

1. Completa i parametri disponibili e approva l’ordine.

1. Viene inviata una notifica al responsabile dell&#39;entità organizzativa a cui appartiene l&#39;entità locale per approvare questo ordine.

   ![](assets/mkg_dist_subscribe_step3.png)

1. Le informazioni vengono restituite alle entità locali e centrali. Mentre gli enti locali possono visualizzare solo i propri ordini, l&#39;entità centrale può visualizzare tutti gli ordini da qualsiasi entità locale, come mostrato di seguito:

   ![](assets/mkg_dist_subscribe_central_view.png)

   Gli operatori possono visualizzare i dettagli dell&#39;ordine:

   ![](assets/mkg_dist_local_op_catalog_detail_1.png)

   La **[!UICONTROL Edit]** La scheda contiene informazioni immesse dall’entità locale durante l’ordinamento della campagna.

   ![](assets/mkg_dist_local_op_catalog_detail_1b.png)

1. L&#39;ordine deve essere approvato dall&#39;ente centrale per essere finalizzato.

   ![](assets/mkg_dist_local_op_catalog_detail_3.png)

   Per ulteriori informazioni, consulta la sezione [Processo di approvazione](#approval-process) sezione .

1. L’operatore locale viene quindi informato della disponibilità della campagna: la disponibilità della campagna si trova nell’elenco dei pacchetti della campagna **Campagne** scheda . La campagna può quindi essere utilizzata. Per ulteriori informazioni, consulta [Accesso alle campagne](accessing-campaigns.md).

   La **[!UICONTROL Start targeting with order approval]** consente all’entità locale di eseguire la campagna non appena l’ordine è stato approvato.

   ![](assets/mkg_dist_local_op_catalog_use.png)

## Approvazione di un ordine {#approving-an-order}

Per confermare l’ordine di una campagna, l’entità centrale deve approvarlo.

La **[!UICONTROL Campaign orders]** panoramica, accessibile tramite **Campagne** La scheda ti consente di visualizzare lo stato degli ordini delle campagne e di approvarli.

>[!NOTE]
>
>Le entità locali possono apportare modifiche all&#39;ordine finché non viene approvato.

### Processo di approvazione {#approval-process}

#### Notifica e-mail {#email-notification}

Quando una campagna viene ordinata da un’entità locale, i relativi revisori ricevono una notifica tramite e-mail, come illustrato di seguito:

![](assets/mkg_dist_valid_notif_email.png)

>[!NOTE]
>
>La selezione dei revisori viene presentata nella sezione [Revisori](#reviewers) sezione . Possono accettare o rifiutare l&#39;ordine.

![](assets/mkg_dist_command_valid_web.png)

#### Approvazione tramite la console Adobe Campaign {#approving-via-the-adobe-campaign-console}

L’ordine può anche essere approvato tramite la console, nella panoramica dell’ordine della campagna. Per approvare un ordine, selezionalo e fai clic su **[!UICONTROL Approve the order]**.

![](assets/mkg_dist_local_order_valid.png)

>[!NOTE]
>
>La campagna può ancora essere modificata e riconfigurata fino alla data di disponibilità della campagna. Le entità locali possono inoltre rifiutare la campagna facendo clic sul pulsante **[!UICONTROL Cancel]** pulsante .

#### Creazione di una campagna {#creating-a-campaign}

Una volta approvato, l’ordine della campagna può essere configurato ed eseguito dall’entità locale.

![](assets/mkg_dist_mutual_op_created.png)

Per ulteriori informazioni, consulta [Accesso alle campagne](accessing-campaigns.md).

### Rifiuto di un&#39;approvazione {#rejecting-an-approval}

L&#39;operatore incaricato dell&#39;approvazione può rifiutare un ordine o un pacchetto di campagna.

![](assets/mkg_dist_do_not_valid.png)

Se il revisore rifiuta un ordine, la notifica pertinente viene inviata automaticamente agli enti locali interessati: visualizza il commento immesso dall’operatore che ha rifiutato l’approvazione.

Le informazioni vengono visualizzate nella pagina dell’elenco dei pacchetti della campagna o nella pagina dell’ordine della campagna. Se hanno accesso alla console Adobe Campaign, le entità locali vengono informate di questo rifiuto.

![](assets/mkg_dist_do_not_valid_view.png)

Possono visualizzare il relativo commento nel pacchetto della campagna **[!UICONTROL Edit]** scheda .

![](assets/mkg_dist_do_not_valid_tab.png)

### Revisori {#reviewers}

Ogni volta che viene richiesta un’approvazione, i revisori ricevono una notifica via e-mail.

Per ogni entità locale, i revisori vengono selezionati per l&#39;approvazione dell&#39;ordine della campagna e per l&#39;approvazione della campagna. Per ulteriori informazioni sulla selezione dei revisori locali, consulta [Entità organizzative](about-distributed-marketing.md#organizational-entities).

>[!NOTE]
>
>Affinché questa selezione sia possibile, l&#39;approvazione dell&#39;ordine non deve ancora essere efficace.

### Annullamento di un ordine {#canceling-an-order}

L&#39;agenzia centrale può annullare un ordine utilizzando **[!UICONTROL Delete]** sul dashboard dell&#39;ordine.

![](assets/mkg_dist_local_op_cancel.png)

In questo modo la campagna viene annullata nel **[!UICONTROL Campaign orders]** visualizza.
