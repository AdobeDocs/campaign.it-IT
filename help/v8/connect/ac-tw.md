---
title: Utilizzare Campaign e X (Twitter)
description: Scopri come integrare l’ambiente Campaign con X (precedentemente noto come Twitter)
role: User, Admin
feature: Social Marketing
level: Beginner, Intermediate
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 42241364c1a23ae75d8f0aaf18a2cb1c04ce5b0c
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 2%

---

# Utilizzare Campaign e X (Twitter) {#tw-ac-ovv}

Il modulo **Gestione dei social network (Social Marketing)** consente di interagire con i clienti tramite X (precedentemente noto come Twitter). Utilizza questa funzionalità per:

* Pubblica messaggi e invia messaggi DM: utilizza Adobe Campaign Social Marketing per pubblicare messaggi su X. Puoi anche inviare messaggi diretti a tutti i tuoi follower.

* Raccogliere nuovi contatti: Adobe Campaign Social Marketing semplifica anche l’acquisizione di nuovi contatti: contatta gli utenti e chiedi loro se desiderano condividere le informazioni del loro profilo. Se accettano, Adobe Campaign recupera automaticamente i dati, consentendo di eseguire campagne di targeting e, quando possibile, di implementare strategie cross-channel.


>[!NOTE]
>
>In qualità di utente di Managed Cloud Services, [contatta Adobe](../start/campaign-faq.md#support) per connettere Campaign a X. Il componente aggiuntivo **Gestione dei social network (Social Marketing)** deve essere installato nel tuo ambiente tramite il pacchetto dedicato e l&#39;account esterno Twitter deve essere configurato.


Per configurare Adobe Campaign per la pubblicazione di tweet sui tuoi account X, delega l’accesso in scrittura ad Adobe Campaign per questi account. A questo scopo, devi:

1. Crea un account X e registrati per un account sviluppatore. [Ulteriori informazioni](#dev-account)
1. (facoltativo) Crea un account di test X per l’invio delle bozze. [Ulteriori informazioni](#tw-test-account)
1. Crea un’applicazione X (un’app per ogni account X). [Ulteriori informazioni](#create-an-app-on-twitter)
1. Crea un nuovo servizio per **[!UICONTROL Twitter]** (un servizio per ogni account X). [Ulteriori informazioni](#create-tw-service)
1. Sincronizza il tuo account X con Campaign. [Ulteriori informazioni](#synchro-tw-accounts)

## X account sviluppatore {#dev-account}

Per iniziare con questa integrazione, devi iscriverti a un account sviluppatore [X](https://developer.twitter.com){target="_blank"}.

Campaign utilizza la versione 1.1 dell’API X. Per utilizzarlo, devi richiedere l’accesso con privilegi elevati tramite il portale per sviluppatori. Ulteriori informazioni su X Elevated Access [sono disponibili in questa pagina](https://developer.twitter.com/en/portal/products/elevated){target="_blank"}.

## Creare un’applicazione su X {#create-an-app-on-twitter}

Dopo aver ricevuto l’approvazione con accesso privilegiato, crea un’applicazione X per consentire ad Adobe Campaign di creare post sul tuo account X. A questo scopo, segui la procedura indicata di seguito:

1. Accedi al tuo account X.
1. Connetti al [X portale per sviluppatori](https://developer.twitter.com/en/apps){target="_blank"}.
1. Selezionare **Crea un&#39;app**.
1. Lascia che l’assistente X ti guidi attraverso il processo.
1. Per consentire ad Adobe Campaign di creare post sul tuo account, modifica le **autorizzazioni app** dalla sezione Configurazione autenticazione utente dell&#39;app. Selezionare **Messaggi diretti, di lettura e scrittura**.

   ![](assets/tw-permissions.png)

1. Nella sezione **Tipo di app**, selezionare **App Web, App automatizzata o Bot**. Puoi lasciare vuoto il campo **URL richiamata** e salvare la configurazione.

   ![](assets/tw-app-type.png)

1. Torna al dashboard dell&#39;app, seleziona l&#39;app e passa alla scheda **Tasti e token**. In **Token di accesso e segreto**, se l&#39;autorizzazione **Messaggi diretti, di lettura e scrittura** non è menzionata, è necessario rigenerare il token e il segreto dell&#39;app. Tieni presente che tutte le chiavi e i token devono essere salvati al momento della creazione. Saranno necessarie per configurare il servizio Campaign Twitter.

   ![](assets/tw-permissions-check.png)


>[!NOTE]
>
>È necessaria un&#39;applicazione per ogni account X. Di conseguenza, devi creare un’altra applicazione di test per inviare le bozze al tuo account di test.
>

## Creare un servizio Twitter in Campaign {#create-tw-service}

Per collegare la tua istanza di Campaign all&#39;account X, crea un servizio **Twitter** e delega l&#39;accesso in scrittura a Campaign.

>[!CAUTION]
>
>Crea un servizio **Twitter** per ogni account X. Di conseguenza, devi creare un altro servizio di test per inviare le bozze al tuo [account di test](#tw-test-account).
>
>Ogni servizio **Twitter** deve essere creato anche da Adobe nell&#39;istanza MID (mid-sourcing). Contatta il rappresentante Adobe per configurare l’ambiente.
>

Per immettere le impostazioni, devi accedere sia alla console client di Adobe Campaign che alle autorizzazioni della tua app X.

1. In **Adobe Campaign**, passare alla scheda **[!UICONTROL Profiles and targets]** e selezionare il collegamento **[!UICONTROL Services and Subscriptions]**
1. Crea un nuovo servizio.
1. Selezionare il tipo **[!UICONTROL Twitter]**.
1. Inserisci l’etichetta e il nome interno del servizio.

   >[!CAUTION]
   >
   >**[!UICONTROL Internal name]** del servizio deve avere lo stesso nome dell&#39;account X.
   >

1. Per impostazione predefinita, i follower vengono salvati nella cartella **[!UICONTROL Visitors]**. È possibile selezionare un altro percorso dal campo **[!UICONTROL Visitor folder]**. [Ulteriori informazioni](../send/twitter.md#direct-tw-messages)

   ![](assets/tw-service-in-ac.png)

   >[!NOTE]
   >
   >L&#39;opzione **[!UICONTROL Synchronize subscriptions]** è attivata per impostazione predefinita: questa opzione ripristina automaticamente l&#39;elenco degli X follower in modo che tu possa [inviare loro messaggi diretti](../send/twitter.md#direct-tw-messages). La sincronizzazione viene eseguita da un [flusso di lavoro tecnico dedicato](#synchro-tw-accounts).

1. Dall&#39;app X, copia il contenuto dei campi **Chiave API** e **[Segreto chiave API]** e incollali nei campi **[!UICONTROL Consumer key]** e **[!UICONTROL Consumer secret]** del servizio **Twitter** della campagna.

1. Dall&#39;app X, copia il contenuto dei campi **Token di accesso** e **Segreto token di accesso** e incollali nei campi **[!UICONTROL Access token]** e **[!UICONTROL Access token secret]** del servizio **Twitter** della campagna.

1. Nella console del client di Campaign, fai clic su **[!UICONTROL Save]**. Ora hai delegato l’accesso in scrittura ad Adobe Campaign.

Per verificare le impostazioni, è possibile:

* Modifica il servizio **Twitter** appena creato.
* Sfoglia la scheda **[!UICONTROL Twitter page]**: dovrebbe essere visualizzato il tuo account Twitter.
  ![](assets/tw-page.png)

## Sincronizza il tuo account X {#synchro-tw-accounts}

La sincronizzazione tra Campaign e X viene gestita tramite flussi di lavoro tecnici dedicati. Questi flussi di lavoro sono archiviati nella cartella **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]**.

Per impostazione predefinita sono interrotti. Devi avviarli manualmente quando inizi a utilizzare il modulo **Social Marketing**.

Il flusso di lavoro tecnico **[!UICONTROL Synchronization of Twitter accounts]** sincronizza gli account X in Adobe Campaign. Questo flusso di lavoro recupera l’elenco degli X follower in modo da poter inviare loro messaggi diretti. [Ulteriori informazioni](../send/twitter.md#direct-tw-messages)

Per impostazione predefinita, questo flusso di lavoro viene attivato ogni giovedì alle 07:30. È possibile utilizzare l&#39;opzione **[!UICONTROL Execute pending task(s) now]** per avviare il flusso di lavoro in qualsiasi momento durante l&#39;implementazione di questa integrazione.  Puoi anche modificare la pianificazione per cambiare la frequenza di attivazione del flusso di lavoro. Per ulteriori informazioni, consulta [questa pagina](../../automation/workflow/scheduler.md).

>[!CAUTION]
>
>Per ripristinare l&#39;elenco degli abbonati X, è necessario controllare l&#39;opzione **[!UICONTROL Twitter account synchronization]** per il servizio collegato all&#39;account. [Ulteriori informazioni](#create-tw-service)

I follower sono memorizzati in una tabella specifica: la tabella dei visitatori. Per visualizzare l&#39;elenco degli X follower, passa a **[!UICONTROL Profiles and Targets > Visitors]**.

Per ogni follower, Adobe Campaign memorizza le seguenti informazioni:

* **[!UICONTROL Origin]**: Twitter
* **[!UICONTROL External ID]**: identificatore utente
* **[!UICONTROL Username]**: nome account dell&#39;utente
* **[!UICONTROL Full name]**: nome dell&#39;utente
* **[!UICONTROL Number of friends]**: numero di follower
* **[!UICONTROL Checked]**: questo campo indica se l&#39;utente dispone di un account Twitter verificato

Al termine della configurazione, puoi creare post sui tuoi account X e inviare messaggi diretti ai tuoi follower. [Ulteriori informazioni](../send/twitter.md)

## Crea un account di test su X {#tw-test-account}

Oltre all&#39;account X, crea un account X privato che può essere utilizzato per inviare [bozze tweet](../send/twitter.md#send-tw-proofs). A questo scopo, segui la procedura indicata di seguito:

1. Crea un nuovo account X.
1. Accedi all&#39;account **Impostazioni**.
1. Passa a **Privacy e sicurezza** e **Pubblico e assegnazione tag** e seleziona l&#39;opzione **Proteggi i tuoi post**. I tuoi post e altre informazioni sull&#39;account sono visibili solo alle persone che ti seguono.

![](assets/do-not-localize/social_tw_test_page.png)

Configura l’app X e il servizio Campaign affinché funzionino con questo account di test, come descritto in precedenza.
