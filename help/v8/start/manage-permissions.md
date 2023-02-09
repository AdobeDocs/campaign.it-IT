---
title: Concedere autorizzazioni a Campaign v8
description: Scopri come concedere autorizzazioni agli utenti di Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 90154f84-b6a7-407c-93b7-9731dc94d9de
source-git-commit: b96ac3bd2365c548d071e626721d606dd33200b5
workflow-type: tm+mt
source-wordcount: '1632'
ht-degree: 1%

---

# Gestire le autorizzazioni utente{#manage-permissions}

## Aggiungi utenti {#add-users}

In qualità di amministratore di prodotto, puoi aggiungere utenti e concedere l’accesso a Campaign.

Per aggiungere un utente, segui i passaggi seguenti:

1. In [Admin Console](https://adminconsole.adobe.com/enterprise){target="_blank"} home page, seleziona **Aggiungi utenti**.

   ![](assets/add-a-user.png)

1. Immetti l’indirizzo e-mail dell’utente.
1. Utilizza il segno &quot;+&quot; per selezionare i profili di prodotto o i gruppi di utenti da assegnare all’utente.

   ![](assets/add-a-product-profile.png)

   I profili di prodotto incorporati di Campaign sono elencati in [questa sezione](#ootb-productprofiles).

   Scopri come creare gruppi di utenti in [questa sezione](#user-groups)

1. Fai clic su **Salva**. L’utente viene aggiunto e viene visualizzato nell’elenco Utenti. Se assegni un ruolo di amministratore o un profilo di prodotto agli utenti, questi riceveranno una notifica e-mail. Gli utenti devono seguire il collegamento per completare il profilo.

Ulteriori informazioni sulla creazione di utenti nell’Admin Console in [questa pagina](https://helpx.adobe.com/ie/enterprise/using/manage-users-individually.html){target="_blank"}.

Quando nuovi utenti [accedere a Campaign](connect.md) con il loro Adobe ID, vengono aggiunti all’elenco degli operatori Campaign nella console client. Gli operatori di Campaign sono memorizzati nel **[!UICONTROL Administration > Access management > Operators]** cartella di Campaign explorer.

## Utilizzare i profili di prodotto{#product-profiles}

Utilizza i profili di prodotto per assegnare agli utenti le funzionalità incluse nel prodotto.

* Per ogni prodotto dell’Admin Console, puoi creare uno o più profili di prodotto.
* In ciascun profilo di prodotto, assegni utenti e gruppi di utenti (nella tua organizzazione).
* Quando un utente effettua l’accesso con le proprie credenziali come specificato nel profilo di prodotto, gli viene concesso l’accesso alle app e ai servizi del prodotto su cui è basato il profilo di prodotto.

Questi profili di prodotto corrispondono ai gruppi di operatori memorizzati nel **[!UICONTROL Administration > Access management > Operator groups]** cartella di Campaign explorer.

Nell’Admin Console, i profili di prodotto utilizzano la sintassi seguente:

campagna - `<your instance>` - nome interno del gruppo di operatori

Ad esempio, per **Operatore di consegna** nell’istanza &quot;test&quot;, il profilo di prodotto nell’Admin Console è:

campagna - test - consegna

Puoi utilizzare i profili di prodotto predefiniti o crearne di nuovi.

### Creare un profilo di prodotto{#create-product-profile}

Per aggiungere ad Adobe un nuovo profilo di prodotto, devi innanzitutto crearlo nella console del client di Campaign e quindi aggiungerlo nell’Admin Console.

Ad esempio, per creare un profilo di prodotto &quot;revisori&quot;, segui i passaggi seguenti.

#### Creare il gruppo di operatori in Campaign{#create-op-group}

1. Collegati a Campaign, apri Explorer e cerca **[!UICONTROL Administration > Access management > Operator groups]**.
1. Fai clic su **[!UICONTROL New]**, e definisci il nome del gruppo di operatori e imposta il suo nome interno (&quot;revisori&quot;).
   ![](assets/new-op-group.png)
1. Definisci le autorizzazioni associate selezionando i diritti denominati. I diritti denominati sono descritti in dettaglio in [questa sezione](#use-named-rights)
1. Salva il nuovo gruppo di operatori.

#### Crea il profilo di prodotto nell’Admin Console{#create-profile-in-admin-console}

1. Collega a [Admin Console](https://adminconsole.adobe.com/enterprise){target="_blank"}.
1. Da **Prodotti e servizi** apri la sezione prodotto Campaign della home page.
1. Fai clic su **Nuovo profilo** e immetti il nome del profilo di prodotto da creare, con l’esatta sintassi corretta come spiegato [qui](#product-profiles). Per il nostro esempio, immettiamo: campagna - `<your-instance-name>` - revisori

   ![](assets/new-product-profile-ui.png)

1. Salva le modifiche.

Ora puoi aggiungere utenti a questo nuovo profilo di prodotto, come spiegato in [questa sezione](#add-users).

Si consiglia di assegnare profili di prodotto a gruppi di utenti. La gestione delle autorizzazioni per utente non è un modello sostenibile.


### Profili di prodotto e gruppi di operatori predefiniti {#ootb-productprofiles}

Adobe Campaign è dotato di **profili di prodotto** che vengono definiti quando Adobe abilita l’ambiente.

![](assets/ootb-product-profiles.png)

Questi profili di prodotto corrispondono a Campaign **gruppi di operatori**. I gruppi di operatori predefiniti e i relativi [diritti denominati](#use-named-rights) sono elencati di seguito:

1. **[!UICONTROL Administrator]** (admin)

   Gli operatori di questo gruppo hanno pieno accesso all’istanza. Gli amministratori sono utenti che possono accedere alle parti più tecniche dell’interfaccia utente.

   Questo gruppo contiene il seguente diritto denominato:

   * **[!UICONTROL ADMINISTRATION]**: diritto di eseguire/creare/modificare/eliminare qualsiasi oggetto come flusso di lavoro, consegna, script, ecc.

1. **[!UICONTROL Delivery operators]** (consegna)

   Gli operatori di questo gruppo sono responsabili della gestione delle consegne: consentono di accedere alle risorse principali necessarie per creare e preparare le consegne (tipologie di campagne, mappature di consegna, modelli predefiniti, blocchi di personalizzazione, ecc.).

   Questo gruppo contiene i seguenti diritti denominati:

   * **[!UICONTROL PREPARE DELIVERIES]**: diritto di creare, modificare e avviare l’analisi della consegna,
   * **[!UICONTROL START DELIVERIES]**: diritto di approvare le consegne analizzate in precedenza.

1. **[!UICONTROL Campaign managers]** (funzionamento)

   Gli operatori di questo gruppo possono gestire le campagne di marketing: ti consente di accedere agli oggetti collegati alle campagne (piani, programmi, flussi di lavoro, budget, ecc.) nell&#39;ambito **[!UICONTROL Campaign]** (modulo Adobe Campaign facoltativo).

   Questo gruppo contiene i seguenti diritti denominati:

   * **[!UICONTROL INSERT FOLDERS]**: diritto di inserire cartelle nell’albero di Adobe Campaign (purché si disponga dei diritti di modifica per i rami interessati),
   * **[!UICONTROL WORKFLOW]**: diritto di utilizzare i flussi di lavoro.

   >[!NOTE]
   >
   >Questo gruppo non consente agli operatori di avviare le consegne.

1. **[!UICONTROL Content contributors]** (contenuto)

   Gli utenti di questo gruppo possono accedere alle cartelle Contenuto nel contesto **[!UICONTROL Content management]** add-on. Questo gruppo non concede autorizzazioni aggiuntive.

1. **[!UICONTROL Access to reports]** (relazione)

   Questo gruppo è riservato agli operatori esterni per accedere ai rapporti di consegna tramite un [Accesso Web](../start/campaign-ui.md#web-browser).

1. **[!UICONTROL Workflow execution]** (flusso di lavoro)

   La **[!UICONTROL Workflow execution]** consente di controllare l’esecuzione e l’approvazione dei flussi di lavoro di targeting: il WORKFLOW denominato right è mappato sugli operatori di questo gruppo. È richiesto per tutte le azioni sui flussi di lavoro, oltre ad accedere ai diritti ai file di dati. Per impostazione predefinita, la **[!UICONTROL Workflow execution]** gruppo ha accesso in sola lettura ai file di flusso di lavoro di targeting standard e ai modelli di flusso di lavoro. Gli operatori di questo gruppo hanno anche accesso in lettura e scrittura al file di approvazione in sospeso.

1. **[!UICONTROL Workflow supervisors]** (workflowSupervisore)

   Gli utenti di questo gruppo gestiscono le approvazioni del flusso di lavoro e ricevono una notifica e-mail in caso di avvisi relativi ai flussi di lavoro delle campagne.

1. **Gestione locale/centrale** (centrale / locale)

   Gli utenti di questo gruppo possono utilizzare **[!UICONTROL Distributed marketing]** add-on.

1. **[!UICONTROL Offer managers]** (offerta)

   Gli operatori di questo gruppo possono creare e gestire le offerte quando utilizzano il componente aggiuntivo Interaction . [Ulteriori informazioni](../interaction/interaction-operators.md).

   Questo gruppo contiene i seguenti diritti denominati:

   * **[!UICONTROL INSERT FOLDERS]**: Diritto di inserire cartelle nell&#39;albero di Adobe Campaign (purché si disponga dei diritti di modifica per i rami interessati),
   * **[!UICONTROL EDIT FOLDERS]**: Diritto di modificare le proprietà della cartella come nome interno, etichetta, immagine associata, ordine delle sottocartelle, ecc.

   Le autorizzazioni assegnate ai gestori di offerte consentono loro di eseguire le seguenti attività:

   * Modifica **[!UICONTROL Design]** ambienti.
   * Visualizza **[!UICONTROL Live]** ambienti.
   * Configura le funzioni di amministrazione (spazi e filtri predefiniti).
   * Crea e aggiorna le categorie.
   * Crea offerte.
   * Configura l’idoneità delle offerte.
   * Approvare le offerte.

   >[!NOTE]
   >
   >**Gestori di offerte** può approvare un’offerta solo se non è specificato alcun revisore o se è stato impostato come revisore nel modello di offerta.

   La matrice delle autorizzazioni di Offer Manager per ambiente è disponibile in [questa pagina](../interaction/interaction-operators.md#recap-of-rights-according-to-operator).

## Utilizzare i gruppi di utenti{#user-groups}

Puoi utilizzare l’Admin Console per creare gruppi di utenti e assegnare loro gli utenti.

Un gruppo di utenti è una raccolta di utenti diversi a cui deve essere assegnato un set di autorizzazioni condiviso. Scopri come creare gruppi di utenti in [questa sezione](https://helpx.adobe.com/ie/enterprise/using/user-groups.html){target="_blank"}.

Puoi assegnare i profili di prodotto ai gruppi di utenti. Quindi, tutti gli utenti di quel gruppo ricevono lo stesso set di autorizzazioni di prodotto.

## Diritti denominati{#use-named-rights}

Adobe Campaign viene fornito con un set di diritti denominati che ti consentono di definire le autorizzazioni assegnate a utenti e gruppi di utenti. Questi diritti possono essere modificati dalla **[!UICONTROL Administration > Access management > Named rights]** cartella di Campaign explorer.

Autorizzazioni di concessione diritti denominati per:

* Eseguire operazioni Ad esempio, il **Analizza** nell’editor consegne è attivato per i membri del **Operatore di consegna** gruppo che ha **Preparare la consegna** Denominato a destra

* L&#39;accesso alle cartelle L&#39;appartenenza a gruppi di operatori può concedere o limitare i diritti di accesso alle cartelle modificando le impostazioni di protezione nelle cartelle. [Ulteriori informazioni](folder-permissions.md#restrict-access-to-a-folder).

   Ad esempio, può avere un impatto: **Accesso in scrittura** creare nuove entità (come consegne, profili, ecc.), **Accesso in lettura** per utilizzare entità, **Elimina accesso** per eliminare le entità.

I diritti denominati predefiniti in Adobe Campaign sono:

* **[!UICONTROL ADMINISTRATION]**: Operatori con **[!UICONTROL ADMINISTRATION]** il diritto ha pieno accesso all&#39;istanza. Gli utenti amministratori possono eseguire/creare/modificare/eliminare qualsiasi oggetto, ad esempio flusso di lavoro, consegna, script e così via.

* **[!UICONTROL APPROVAL ADMINISTRATION]**: Puoi impostare più passaggi di approvazione all’interno di flussi di lavoro e consegne per garantire che lo stato corrente sia stato approvato da un operatore o gruppo assegnato. Utenti con **[!UICONTROL APPROVAL ADMINISTRATION]** può impostare i passaggi di approvazione e assegnare anche un operatore o un gruppo di operatori che deve approvare tali passaggi.

* **[!UICONTROL CENTRAL]**: Diritto alla gestione centrale (Distributed Marketing).

* **[!UICONTROL DELETE FOLDER]**: Diritto di eliminare le cartelle. Con questo diritto, gli utenti possono eliminare le cartelle dalla visualizzazione Esplora risorse.

* **[!UICONTROL EDIT FOLDERS]**: Diritto di modificare le proprietà della cartella come nome interno, etichetta, immagine associata, ordine delle sottocartelle, ecc.

* **[!UICONTROL EXPORT]**: Gli utenti possono esportare i dati dalle proprie istanze Adobe Campaign in un file su server o computer locale utilizzando **[!UICONTROL EXPORT]** attività del flusso di lavoro.

* **[!UICONTROL FILES ACCESS]**: Diritto di accesso in lettura e scrittura per i file tramite uno script che può essere scritto nel **[!UICONTROL JavaScript]** attività del flusso di lavoro per leggere/scrivere file su un server.

* **[!UICONTROL IMPORT]**: Diritto all’importazione di dati generici. **[!UICONTROL IMPORT]** consente di importare dati in qualsiasi altra tabella, mentre il **[!UICONTROL RECIPIENT IMPORT]** right consente di importare solo nella tabella dei destinatari.

* **[!UICONTROL INSERT FOLDERS]**: Diritto di inserire cartelle. Utenti con **[!UICONTROL INSERT FOLDERS]** a destra è possibile creare nuove cartelle nella struttura delle cartelle in visualizzazione Esplora risorse.

* **[!UICONTROL LOCAL]**: Diritto alla gestione locale (Distributed Marketing).

* **[!UICONTROL MERGE]**: Diritto di unire i record selezionati in un unico record. Se i destinatari esistono come duplicati, la **[!UICONTROL MERGE]** right consente all’utente di selezionare i duplicati e di unirli in un destinatario principale.

* **[!UICONTROL PREPARE DELIVERIES]**: Diritto di creare, modificare e salvare una consegna. Utenti con **[!UICONTROL PREPARE DELIVERIES]** right può anche avviare il processo di analisi della consegna.

* **[!UICONTROL PRIVACY DATA RIGHT]**: Diritto di raccogliere ed eliminare dati sulla privacy. [Ulteriori informazioni](privacy.md).

* **[!UICONTROL PROGRAM EXECUTION]**: Diritto di eseguire comandi in vari linguaggi di programmazione.

* **[!UICONTROL RECIPIENT IMPORT]**: Diritto di importare i destinatari. Utenti con **[!UICONTROL RECIPIENT IMPORT]** right può importare un file locale nella tabella dei destinatari.

* **[!UICONTROL SQL SCRIPT EXECUTION]** Diritto di eseguire qualsiasi comando SQL direttamente sul database.

* **[!UICONTROL START DELIVERIES]**: Diritto di approvare le consegne analizzate in precedenza. Dopo l’analisi della consegna, la consegna verrà messa in pausa a vari passaggi di approvazione e dovrà essere approvata per riprendere. Utenti con **[!UICONTROL START DELIVERIES]** sono autorizzati ad approvare le consegne.

* **[!UICONTROL USE SQL DATA MANAGEMENT ACTIVITY]**: Diritto di scrivere script SQL personalizzati utilizzando l&#39;attività SQL Data Management per creare e popolare tabelle di lavoro. [Ulteriori informazioni](../../automation/workflow/sql-data-management.md).

* **[!UICONTROL WORKFLOW]**: Questo diritto denominato è specifico per i flussi di lavoro: consente di creare, avviare e interrompere i flussi di lavoro. I diritti di lettura sul file del flusso di lavoro sono necessari perché sia applicabile il diritto denominato . Per il targeting dei flussi di lavoro, la lettura a destra **[!UICONTROL Profiles and Targets]** La cartella è necessaria.


* **[!UICONTROL WEBAPP]**: Diritto di utilizzare applicazioni web.

>[!NOTE]
>
>Questo elenco può variare a seconda dei componenti aggiuntivi installati nell&#39;ambiente.



## Risorse aggiuntive{#additional-res}

* [Gestione delle autorizzazioni per i flussi di lavoro](../../automation/workflow/managing-rights.md)
* [Gestione delle autorizzazioni per il marketing distribuito](../../automation/distributed-marketing/about-distributed-marketing.md#operators)
* [Gestisci le autorizzazioni per il modulo di interazione](../interaction/interaction-operators.md)
* [Filtrare l’accesso agli schemi](../dev/filter-schema.md)
* [Limitare la visualizzazione di dati personali](../dev/restrict-pi-view.md)
