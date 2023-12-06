---
title: Utilizzare Campaign e X (Twitter)
description: Scopri come integrare l’ambiente Campaign con X (precedentemente noto come Twitter)
role: User, Admin
feature: Social Marketing
level: Beginner, Intermediate
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 8f58db2b00f2fc98afd737f20411f829dd24c78a
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 2%

---

# Utilizzare Campaign e X (Twitter) {#tw-ac-ovv}

Il **Gestione dei social network (Social Marketing)** consente di interagire con i clienti tramite X (precedentemente noto come Twitter). Utilizza questa funzionalità per:

* Pubblica messaggi e invia messaggi DM: utilizza Adobe Campaign Social Marketing per pubblicare messaggi su X. Puoi anche inviare messaggi diretti a tutti i tuoi follower.

* Raccogliere nuovi contatti: Adobe Campaign Social Marketing semplifica anche l’acquisizione di nuovi contatti: contatta gli utenti e chiedi loro se desiderano condividere le informazioni del loro profilo. Se accettano, Adobe Campaign recupera automaticamente i dati, consentendo di eseguire campagne di targeting e, quando possibile, di implementare strategie cross-channel.

![](../assets/do-not-localize/speech.png) In qualità di utente di Managed Cloud Service, [Adobe di contatto](../start/campaign-faq.md#support) per collegare Campaign a X. Il  **Gestione dei social network (Social Marketing)** il componente aggiuntivo deve essere installato nell’ambiente tramite il pacchetto dedicato e l’account esterno del Twitter deve essere configurato.


Per configurare Adobe Campaign per la pubblicazione di tweet sui tuoi account X, delega l’accesso in scrittura ad Adobe Campaign per questi account. A questo scopo, devi:

1. Crea un account X e registrati per un account sviluppatore. [Ulteriori informazioni](#dev-account)
1. (facoltativo) Crea un account di test X per l’invio delle bozze. [Ulteriori informazioni](#tw-test-account)
1. Crea un’applicazione X (un’app per ogni account X). [Ulteriori informazioni](#create-an-app-on-twitter)
1. Crea un nuovo servizio per **[!UICONTROL Twitter]** (un servizio per ogni account X). [Ulteriori informazioni](#create-tw-service)
1. Sincronizza il tuo account X con Campaign. [Ulteriori informazioni](#synchro-tw-accounts)

## X account sviluppatore {#dev-account}

Per iniziare con questa integrazione, devi iscriverti a [X account sviluppatore](https://developer.twitter.com){target="_blank"}.

Campaign utilizza la versione 1.1 dell’API X. Per utilizzarlo, devi richiedere l’accesso con privilegi elevati tramite il portale per sviluppatori. Ulteriori informazioni su X Elevated Access [in questa pagina](https://developer.twitter.com/en/portal/products/elevated){target="_blank"}.

## Creare un’applicazione su X {#create-an-app-on-twitter}

Dopo aver ricevuto l’approvazione con accesso privilegiato, crea un’applicazione X per consentire ad Adobe Campaign di creare post sul tuo account X. A questo scopo, segui la procedura indicata di seguito:

1. Accedi al tuo account X.
1. Connetti a [X portale per sviluppatori](https://developer.twitter.com/en/apps).
1. Seleziona **Creare un’app**.
1. Lascia che l’assistente X ti guidi attraverso il processo.
1. Per consentire ad Adobe Campaign di creare post sul tuo account, modifica in **Autorizzazioni app** dalla sezione Configurazione dell’autenticazione utente nell’app. Seleziona **Lettura, scrittura e messaggi diretti**.

   ![](assets/tw-permissions.png)

1. In **Tipo di app** sezione, seleziona **App web, app automatizzata o bot**. È possibile lasciare **URL callback** e salva la configurazione.

   ![](assets/tw-app-type.png)

1. Torna al dashboard dell’app, seleziona l’app e passa alla sezione **Tasti e token** scheda. Sotto **Token di accesso e segreto**, se **Lettura, scrittura e messaggi diretti** L&#39;autorizzazione non è menzionata, devi rigenerare il token e il segreto dell&#39;app. Tieni presente che tutte le chiavi e i token devono essere salvati al momento della creazione. Saranno necessarie per configurare il servizio di Twitter Campaign.

   ![](assets/tw-permissions-check.png)


>[!NOTE]
>
>È necessaria un&#39;applicazione per ogni account X. Di conseguenza, devi creare un’altra applicazione di test per inviare le bozze al tuo account di test.
>

## Creazione di un servizio di Twitter in Campaign {#create-tw-service}

Per collegare la tua istanza di Campaign all’account X, crea un’ **Twitter** accesso in scrittura a Campaign tramite servizio e delegato.

>[!CAUTION]
>
>Crea un elemento **Twitter** servizio per account X. Di conseguenza, devi creare un altro servizio di test per inviare le bozze al tuo [account di prova](#tw-test-account).
>
>Ogni **Twitter** deve essere creato anche da Adobe sull’istanza MID. Contatta il rappresentante del tuo Adobe per configurare l’ambiente.
>

Per immettere le impostazioni, devi accedere sia alla console client di Adobe Campaign che alle autorizzazioni della tua app X.

1. In entrata **Adobe Campaign**, passare alla **[!UICONTROL Profiles and targets]** e seleziona la scheda **[!UICONTROL Services and Subscriptions]** link
1. Crea un nuovo servizio.
1. Seleziona la **[!UICONTROL Twitter]** tipo.
1. Inserisci l’etichetta e il nome interno del servizio.

   >[!CAUTION]
   >
   >Il **[!UICONTROL Internal name]** del servizio deve corrispondere esattamente allo stesso nome del tuo account X.
   >

1. Per impostazione predefinita, i follower vengono salvati in **[!UICONTROL Visitors]** cartella. È possibile selezionare un&#39;altra posizione dal **[!UICONTROL Visitor folder]** campo. [Ulteriori informazioni](../send/twitter.md#direct-tw-messages)

   ![](assets/tw-service-in-ac.png)

   >[!NOTE]
   >
   >Il **[!UICONTROL Synchronize subscriptions]** è attivata per impostazione predefinita: questa opzione recupera automaticamente l’elenco degli X follower in modo che sia possibile [inviare loro messaggi diretti](../send/twitter.md#direct-tw-messages). La sincronizzazione viene eseguita da un [flusso di lavoro tecnico dedicato](#synchro-tw-accounts).

1. Dall’app X, copia il contenuto della **Chiave API** e **[Segreto chiave API]** e incollarli nel **[!UICONTROL Consumer key]** e **[!UICONTROL Consumer secret]** campi della campagna **Twitter** servizio.

1. Dall’app X, copia il contenuto della **Token di accesso** e **Segreto token di accesso** e incollarli nel **[!UICONTROL Access token]** e **[!UICONTROL Access token secret]** campi della campagna **Twitter** servizio.

1. Nella console client di Campaign, fai clic su **[!UICONTROL Save]**. Ora hai delegato l’accesso in scrittura ad Adobe Campaign.

Per verificare le impostazioni, è possibile:

* Modifica il **Twitter** servizio appena creato.
* Sfoglia **[!UICONTROL Twitter page]** scheda: viene visualizzato l’account di Twitter.
  ![](assets/tw-page.png)

## Sincronizza il tuo account X {#synchro-tw-accounts}

La sincronizzazione tra Campaign e X viene gestita tramite flussi di lavoro tecnici dedicati. Questi flussi di lavoro sono memorizzati nel **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** cartella.

Per impostazione predefinita vengono arrestati: è necessario avviarli manualmente quando si inizia a utilizzare **Social marketing** modulo.

Il **[!UICONTROL Synchronization of Twitter accounts]** il flusso di lavoro tecnico sincronizza gli account X in Adobe Campaign. Questo flusso di lavoro recupera l’elenco degli X follower in modo da poter inviare loro messaggi diretti. [Ulteriori informazioni](../send/twitter.md#direct-tw-messages)

Per impostazione predefinita, questo flusso di lavoro viene attivato ogni giovedì alle 07:30. È possibile utilizzare **[!UICONTROL Execute pending task(s) now]** per avviare il flusso di lavoro in qualsiasi momento durante l’implementazione di questa integrazione.  Puoi anche modificare la pianificazione per cambiare la frequenza di attivazione del flusso di lavoro. Per ulteriori informazioni, consulta [questa pagina](../../automation/workflow/scheduler.md).

>[!CAUTION]
>
>Per recuperare l’elenco degli abbonati X, utilizza **[!UICONTROL Twitter account synchronization]** deve essere selezionata l’opzione per il servizio collegato all’account. [Ulteriori informazioni](#create-tw-service)

I follower sono memorizzati in una tabella specifica: la tabella dei visitatori. Per visualizzare l&#39;elenco degli X follower, selezionare **[!UICONTROL Profiles and Targets > Visitors]**.

Per ogni follower, Adobe Campaign memorizza le seguenti informazioni:

* **[!UICONTROL Origin]**: TWITTER
* **[!UICONTROL External ID]**: identificatore utente
* **[!UICONTROL Username]**: nome account dell’utente
* **[!UICONTROL Full name]**: nome dell’utente
* **[!UICONTROL Number of friends]**: numero di follower
* **[!UICONTROL Checked]**: questo campo indica se l’utente dispone di un account di Twitter verificato

Al termine della configurazione, puoi creare post sui tuoi account X e inviare messaggi diretti ai tuoi follower. [Ulteriori informazioni](../send/twitter.md)

## Crea un account di test su X {#tw-test-account}

Oltre all’account X, crea un account X privato da utilizzare per l’invio [bozze tweet](../send/twitter.md#send-tw-proofs). A questo scopo, segui la procedura indicata di seguito:

1. Crea un nuovo account X.
1. Accedere all’account  **Impostazioni**.
1. Sfoglia per **Privacy e sicurezza** e **Pubblico e assegnazione tag** e controlla **Protect post** opzione. I tuoi post e altre informazioni sull&#39;account sono visibili solo alle persone che ti seguono.

![](assets/do-not-localize/social_tw_test_page.png)

Configura l’app X e il servizio Campaign affinché funzionino con questo account di test, come descritto in precedenza.
