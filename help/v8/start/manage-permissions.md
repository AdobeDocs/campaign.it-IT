---
title: Concedere le autorizzazioni per Campaign v8
description: Scopri come concedere autorizzazioni agli utenti di Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 90154f84-b6a7-407c-93b7-9731dc94d9de
source-git-commit: 09db0cc1a14bffefe8d1b8d0d5a06d5b6517a5bb
workflow-type: tm+mt
source-wordcount: '1618'
ht-degree: 1%

---

# Gestire le autorizzazioni utente{#manage-permissions}

## Aggiungi utenti {#add-users}

In qualità di amministratore di prodotto, puoi aggiungere utenti e concedere l’accesso a Campaign.

Per aggiungere un utente, effettua le seguenti operazioni:

1. In [Admin Console](https://adminconsole.adobe.com/enterprise){target="_blank"} home page, seleziona **Aggiungi utenti**.

   ![](assets/add-a-user.png)

1. Inserisci l’indirizzo e-mail dell’utente.
1. Utilizza il segno &quot;+&quot; per selezionare i profili di prodotto o i gruppi di utenti da assegnare all’utente.

   ![](assets/add-a-product-profile.png)

   I profili di prodotto incorporati di Campaign sono elencati in [questa sezione](#ootb-productprofiles).

   Scopri come creare gruppi di utenti in [questa sezione](#user-groups)

1. Clic **Salva**. L’utente viene aggiunto e viene visualizzato nell’elenco Utenti. Se assegni un ruolo di amministratore o un profilo di prodotto agli utenti, questi riceveranno una notifica e-mail. Gli utenti devono seguire il link per completare il loro profilo.

Per ulteriori informazioni sulla creazione di utenti, consulta l’Admin Console in [questa pagina](https://helpx.adobe.com/ie/enterprise/using/manage-users-individually.html){target="_blank"}.

Quando nuovi utenti [accedere a Campaign](connect.md) con il rispettivo Adobe ID, vengono aggiunti all’elenco degli operatori Campaign nella console client. Gli operatori di Campaign sono memorizzati in **[!UICONTROL Administration > Access management > Operators]** cartella di Campaign explorer.

## Utilizzare i profili di prodotto{#product-profiles}

Utilizza i profili di prodotto per autorizzare gli utenti a utilizzare le funzionalità incluse nel prodotto.

* Per ogni prodotto nell’Admin Console, puoi creare uno o più profili di prodotto.
* In ciascun profilo di prodotto, puoi assegnare utenti e gruppi di utenti (nella tua organizzazione).
* Quando un utente effettua l’accesso con le proprie credenziali come specificato nel profilo di prodotto, gli viene concesso l’accesso alle app e ai servizi del prodotto su cui è basato il profilo di prodotto.

Questi profili di prodotto corrispondono ai gruppi di operatori memorizzati nella **[!UICONTROL Administration > Access management > Operator groups]** cartella di Campaign explorer.

Nell’Admin Console, i profili di prodotto utilizzano la sintassi seguente:

campagna - `<your instance>` - nome interno del gruppo di operatori

Ad esempio, per **Operatore di consegna** nell’istanza &quot;test&quot;, il profilo di prodotto nell’Admin Console è:

campaign - test - delivery

Puoi utilizzare profili di prodotto predefiniti o crearne di nuovi.

### Creare un profilo di prodotto{#create-product-profile}

Per aggiungere un nuovo profilo di prodotto ad Adobe, devi innanzitutto crearlo nella console client di Campaign, quindi aggiungerlo nell’Admin Console.

Ad esempio, per creare un profilo di prodotto &quot;revisori&quot;, segui i passaggi seguenti.

#### Creare il gruppo di operatori in Campaign{#create-op-group}

1. Connettiti a Campaign, apri Explorer e passa a **[!UICONTROL Administration > Access management > Operator groups]**.
1. Clic **[!UICONTROL New]**e definiscono il nome del gruppo di operatori e ne impostano il nome interno (&quot;revisori&quot;).
   ![](assets/new-op-group.png)
1. Definisci le autorizzazioni associate selezionando i diritti denominati. I diritti denominati sono descritti in [questa sezione](#use-named-rights)
1. Salva il nuovo gruppo di operatori.

#### Creare il profilo di prodotto nell’Admin Console{#create-profile-in-admin-console}

1. Connetti a [Admin Console](https://adminconsole.adobe.com/enterprise){target="_blank"}.
1. Dalla sezione **Prodotti e servizi** nella pagina principale, apri il prodotto Campaign.
1. Clic **Nuovo profilo** e inserisci il nome del profilo di prodotto da creare, con la sintassi esatta e corretta come spiegato [qui](#product-profiles). Nel nostro esempio, immettiamo: campaign - `<your-instance-name>` - revisori

   ![](assets/new-product-profile-ui.png)

1. Salva le modifiche.

Ora puoi aggiungere utenti a questo nuovo profilo di prodotto, come spiegato in [questa sezione](#add-users).

Si consiglia di assegnare profili di prodotto a gruppi di utenti. La gestione delle autorizzazioni da parte dell’utente non è un modello sostenibile.


### Profili di prodotto e gruppi di operatori predefiniti {#ootb-productprofiles}

Adobe Campaign viene fornito con **profili di prodotto** che vengono definiti quando Adobe abilita l’ambiente.

![](assets/ootb-product-profiles.png)

Questi profili di prodotto corrispondono a Campaign **gruppi di operatori**. I gruppi di operatori predefiniti e i relativi [diritti denominati](#use-named-rights) sono elencati di seguito:

1. **[!UICONTROL Administrator]** (amministratore)

   Gli operatori di questo gruppo hanno accesso completo all’istanza. Gli amministratori sono utenti che possono accedere alle parti più tecniche dell’interfaccia utente.

   Questo gruppo contiene i seguenti diritti denominati:

   * **[!UICONTROL ADMINISTRATION]**: diritto di eseguire/creare/modificare/eliminare qualsiasi oggetto, ad esempio flusso di lavoro, consegna, script e così via.

1. **[!UICONTROL Delivery operators]** (consegna)

   Gli operatori di questo gruppo sono responsabili della gestione delle consegne: consentono l’accesso alle risorse principali necessarie per la creazione e la preparazione delle consegne (tipologie di campagne, mappature di consegna, modelli predefiniti, blocchi di personalizzazione, ecc.).

   Questo gruppo contiene i seguenti diritti denominati:

   * **[!UICONTROL PREPARE DELIVERIES]**: diritto di creare, modificare e avviare l’analisi della consegna,
   * **[!UICONTROL START DELIVERIES]**: diritto di approvare le consegne analizzate in precedenza.

1. **[!UICONTROL Campaign managers]** (funzionamento)

   Gli operatori di questo gruppo possono gestire le campagne di marketing: ti consente di accedere agli oggetti collegati alle campagne (piani, programmi, flussi di lavoro, budget, ecc.) nell&#39;ambito del **[!UICONTROL Campaign]** (modulo Adobe Campaign opzionale).

   Questo gruppo contiene i seguenti diritti denominati:

   * **[!UICONTROL INSERT FOLDERS]**: diritto di inserire cartelle nella struttura Adobe Campaign (purché si disponga dei diritti di modifica per i rami interessati),
   * **[!UICONTROL WORKFLOW]**: diritto di utilizzare i flussi di lavoro.

   >[!NOTE]
   >
   >Questo gruppo non consente agli operatori di avviare le consegne.

1. **[!UICONTROL Content contributors]** (contenuto)

   Gli utenti di questo gruppo possono accedere alle cartelle di contenuto nel contesto del **[!UICONTROL Content management]** componente aggiuntivo. Questo gruppo non concede autorizzazioni aggiuntive.

1. **[!UICONTROL Access to reports]** (rapporto)

   Questo gruppo è riservato agli operatori esterni, per accedere ai rapporti di consegna tramite un [Accesso web](../start/campaign-ui.md#web-browser).

1. **[!UICONTROL Workflow execution]** (flusso di lavoro)

   Il **[!UICONTROL Workflow execution]** Il gruppo consente di controllare l’esecuzione e l’approvazione dei flussi di lavoro di targeting: il FLUSSO DI LAVORO denominato right è mappato agli operatori di questo gruppo. È richiesto per tutte le azioni sui flussi di lavoro, oltre ai diritti di accesso ai file di dati. Per impostazione predefinita, il **[!UICONTROL Workflow execution]** Il gruppo ha accesso in sola lettura ai file di flusso di lavoro di targeting standard e ai modelli di flusso di lavoro. Gli operatori di questo gruppo dispongono inoltre dell&#39;accesso in lettura e scrittura al file di approvazione in sospeso.

1. **[!UICONTROL Workflow supervisors]** (workflowSupervisor)

   Gli utenti di questo gruppo gestiscono le approvazioni dei flussi di lavoro e ricevono una notifica e-mail in caso di avvisi relativi ai flussi di lavoro delle campagne.

1. **Gestione locale/centrale** (centrale / locale)

   Gli utenti di questo gruppo possono utilizzare **[!UICONTROL Distributed marketing]** componente aggiuntivo.

1. **[!UICONTROL Offer managers]** (offerta)

   Gli operatori di questo gruppo possono creare e gestire le offerte quando utilizzano il componente aggiuntivo Interazione. [Ulteriori informazioni](../interaction/interaction-operators.md).

   Questo gruppo contiene i seguenti diritti denominati:

   * **[!UICONTROL INSERT FOLDERS]**: diritto di inserire cartelle nella struttura Adobe Campaign (purché si disponga dei diritti di modifica per i rami interessati),
   * **[!UICONTROL EDIT FOLDERS]**: diritto di modificare le proprietà della cartella come nome interno, etichetta, immagine associata, ordine delle sottocartelle e così via.

   Le autorizzazioni assegnate ai gestori delle offerte consentono loro di eseguire le seguenti attività:

   * Modifica **[!UICONTROL Design]** ambienti.
   * Visualizza **[!UICONTROL Live]** ambienti.
   * Configurare le funzioni di amministrazione (spazi e filtri predefiniti).
   * Crea e aggiorna le categorie.
   * Creare le offerte.
   * Configurare l’idoneità per le offerte.
   * Approvare le offerte.

   >[!NOTE]
   >
   >**Manager offerta** può approvare un’offerta solo se non è specificato alcun revisore o se questi sono stati impostati come revisori nel modello di offerta.

   La matrice delle autorizzazioni di Offer Manager per ambiente è disponibile in [questa pagina](../interaction/interaction-operators.md#recap-of-rights-according-to-operator).

## Utilizzare i gruppi di utenti{#user-groups}

Puoi utilizzare l’Admin Console per creare gruppi di utenti e assegnarvi utenti.

Un gruppo di utenti è una raccolta di utenti diversi a cui deve essere assegnato un set condiviso di autorizzazioni. Scopri come creare gruppi di utenti in [questa sezione](https://helpx.adobe.com/ie/enterprise/using/user-groups.html){target="_blank"}.

Puoi assegnare profili di prodotto a gruppi di utenti. In questo modo, tutti gli utenti del gruppo riceveranno lo stesso set di autorizzazioni per il prodotto.

## Diritti denominati{#use-named-rights}

Adobe Campaign viene fornito con un set di diritti denominati che ti consentono di definire le autorizzazioni assegnate a utenti e gruppi di utenti. Questi diritti possono essere modificati da **[!UICONTROL Administration > Access management > Named rights]** cartella di Campaign explorer.

I diritti denominati concedono le autorizzazioni a:

* Eseguire operazioni Ad esempio, il **Analizza** nell’editor di consegna sia attivato per i membri del gruppo **Operatore di consegna** gruppo che dispone di **Prepara consegna** Denominato a destra

* Accesso alle cartelle L&#39;appartenenza ai gruppi di operatori può concedere o limitare i diritti di accesso alle cartelle modificando le impostazioni di protezione delle cartelle. [Ulteriori informazioni](folder-permissions.md#restrict-access-to-a-folder).

  Ad esempio, può avere un impatto su: **Accesso in scrittura** creare nuove entità (come consegne, profili, ecc.), **Accesso in lettura** per utilizzare le entità, **Elimina accesso** per eliminare le entità.

I diritti denominati predefiniti in Adobe Campaign sono:

* **[!UICONTROL ADMINISTRATION]**: operatori con **[!UICONTROL ADMINISTRATION]** right dispone dell’accesso completo all’istanza. Gli utenti amministratori possono eseguire/creare/modificare/eliminare qualsiasi oggetto, ad esempio flusso di lavoro, consegna, script e così via.

* **[!UICONTROL APPROVAL ADMINISTRATION]**: puoi impostare più passaggi di approvazione all’interno di flussi di lavoro e consegne per garantire che lo stato corrente sia stato approvato da un operatore o un gruppo assegnato. Utenti con **[!UICONTROL APPROVAL ADMINISTRATION]** L&#39;autorizzazione può impostare le fasi di approvazione e assegnare un operatore o un gruppo di operatori che deve approvarle.

* **[!UICONTROL CENTRAL]**: diritto alla gestione centrale (Marketing distribuito).

* **[!UICONTROL DELETE FOLDER]**: diritto di eliminare le cartelle. Con questo diritto, gli utenti possono eliminare cartelle dalla visualizzazione Esplora risorse.

* **[!UICONTROL EDIT FOLDERS]**: diritto di modificare le proprietà della cartella come nome interno, etichetta, immagine associata, ordine delle sottocartelle e così via.

* **[!UICONTROL EXPORT]**: gli utenti possono esportare i dati dalle istanze Adobe Campaign in un file sul server o sul computer locale utilizzando **[!UICONTROL EXPORT]** attività del flusso di lavoro.

* **[!UICONTROL FILES ACCESS]**: diritto di accesso in lettura e scrittura per i file tramite uno script che può essere scritto nel **[!UICONTROL JavaScript]** attività del flusso di lavoro per la lettura/scrittura di file su un server.

* **[!UICONTROL IMPORT]**: diritto per l’importazione di dati generici. **[!UICONTROL IMPORT]** consente di importare dati in qualsiasi altra tabella, mentre **[!UICONTROL RECIPIENT IMPORT]** right consente di importare solo nella tabella dei destinatari.

* **[!UICONTROL INSERT FOLDERS]**: diritto di inserire cartelle. Utenti con **[!UICONTROL INSERT FOLDERS]** con il pulsante destro del mouse è possibile creare nuove cartelle nella struttura cartelle in visualizzazione esplora risorse.

* **[!UICONTROL LOCAL]**: diritto alla gestione locale (Marketing distribuito).

* **[!UICONTROL MERGE]**: diritto di unire i record selezionati in uno. Se i destinatari esistono come duplicati, il **[!UICONTROL MERGE]** L’opzione a destra consente all’utente di selezionare i duplicati e unirli in un destinatario primario.

* **[!UICONTROL PREPARE DELIVERIES]**: diritto di creare, modificare e salvare una consegna. Utenti con **[!UICONTROL PREPARE DELIVERIES]** right può anche avviare il processo di analisi della consegna.

* **[!UICONTROL PRIVACY DATA RIGHT]**: diritto di raccogliere ed eliminare dati sulla privacy. [Ulteriori informazioni](privacy.md).

* **[!UICONTROL PROGRAM EXECUTION]**: diritto di eseguire comandi in vari linguaggi di programmazione.

* **[!UICONTROL RECIPIENT IMPORT]**: diritto di importare i destinatari. Utenti con **[!UICONTROL RECIPIENT IMPORT]** right può importare un file locale nella tabella dei destinatari.

* **[!UICONTROL SQL SCRIPT EXECUTION]** Diritto di eseguire qualsiasi comando SQL direttamente sul database.

* **[!UICONTROL START DELIVERIES]**: diritto di approvare le consegne analizzate in precedenza. Dopo l’analisi della consegna, la consegna viene sospesa in vari passaggi di approvazione e deve essere approvata per riprendere. Utenti con **[!UICONTROL START DELIVERIES]** I diritti di possono approvare le consegne.

* **[!UICONTROL USE SQL DATA MANAGEMENT ACTIVITY]**: diritto di scrivere script SQL personalizzati utilizzando l’attività Gestione dati SQL per creare e popolare tabelle di lavoro. [Ulteriori informazioni](../../automation/workflow/sql-data-management.md).

* **[!UICONTROL WORKFLOW]**: questo diritto denominato è specifico per i flussi di lavoro e consente di creare, avviare e interrompere i flussi di lavoro. Affinché il diritto denominato sia applicabile, è necessario disporre dei diritti di lettura per il file del flusso di lavoro. Per i flussi di lavoro di targeting, la lettura a destra nella **[!UICONTROL Profiles and Targets]** è necessaria.


* **[!UICONTROL WEBAPP]**: diritto di utilizzare le applicazioni web.

>[!NOTE]
>
>Questo elenco può variare a seconda dei componenti aggiuntivi installati nell&#39;ambiente.



## Risorse aggiuntive{#additional-res}

* [Gestire le autorizzazioni per i flussi di lavoro](../../automation/workflow/managing-rights.md)
* [Gestire le autorizzazioni per il marketing distribuito](../../automation/distributed-marketing/about-distributed-marketing.md#operators)
* [Gestire le autorizzazioni per il modulo di interazione](../interaction/interaction-operators.md)
* [Filtrare l’accesso agli schemi](../dev/filter-schema.md)
* [Limitare la visualizzazione di dati personali](../dev/restrict-pi-view.md)
