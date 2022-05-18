---
title: Utilizzare Campaign e Twitter
description: Scopri come integrare l’ambiente Campaign con Twitter
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 4%

---

# Utilizzare Campaign e Twitter{#tw-ac-ovv}

La **Gestione dei social network (Social Marketing)** Il modulo ti consente di interagire con i clienti tramite Twitter. Utilizza questa funzionalità per:

* Invia messaggi - Utilizza Adobe Campaign Social Marketing per inviare messaggi su Twitter. Puoi anche inviare messaggi diretti a tutti i tuoi follower.

* Raccogli nuovi contatti - Adobe Campaign Social Marketing semplifica anche l&#39;acquisizione di nuovi contatti: contatta gli utenti e chiedi loro se desiderano condividere le loro informazioni di profilo. Se accettano, Adobe Campaign recupera automaticamente i dati, consentendo di eseguire campagne di targeting e, quando possibile, di implementare strategie cross-channel.

![](../assets/do-not-localize/speech.png)  Come utente di Cloud Services gestiti, [Adobe di contatto](../start/campaign-faq.md#support) per collegare Campaign a Twitter. La  **Gestione dei social network (Social Marketing)** Il modulo deve essere installato nel tuo ambiente, attraverso il pacchetto dedicato.


Per configurare Adobe Campaign per la pubblicazione dei tweet negli account Twitter, delegare l’accesso in scrittura ad Adobe Campaign per questi account. Per eseguire questa operazione:

1. Creare un account Twitter
1. Creare un account Twitter di prova per l’invio di bozze
1. Creare un&#39;applicazione Twitter (un&#39;app per account Twitter)
1. Crea un nuovo servizio per **[!UICONTROL Twitter]** (un servizio per account Twitter)

## Creare un account di test su Twitter {#tw-test-account}

Oltre all’account Twitter, crea un account Twitter privato che può essere utilizzato per l’invio [bozze di tweet](../send/twitter.md#send-tw-proofs). Per farlo, segui la procedura indicata di seguito:

1. Crea un nuovo account Twitter.
1. Accedere all’account  **Impostazioni**.
1. Sfoglia per **Privacy e sicurezza** e **Pubblico e assegnazione tag** e controlla **Protect i tuoi tweet** opzione . I tuoi Tweet e altre informazioni sull&#39;account sono visibili solo alle persone che ti seguono.

![](assets/social_tw_test_page.png)

## Creare un’applicazione in Twitter {#create-an-app-on-twitter}

Crea un&#39;applicazione Twitter per consentire ad Adobe Campaign di pubblicare tweet sul tuo account Twitter.  Per farlo, segui la procedura indicata di seguito:

1. Accedi al tuo account Twitter.
1. Connetti a [Portale per sviluppatori twitter](https://developer.twitter.com/en/apps).
1. Seleziona **Creare un’app**.
1. Lascia che l’assistente Twitter ti guidi attraverso il processo.

   Per consentire ad Adobe Campaign di inviare tweet al tuo account, modifica il **Autorizzazioni** scheda dell&#39;applicazione e seleziona **Lettura e scrittura** per **Accesso** sezione . In **Impostazioni** , è inoltre necessario uscire dalla **URL di callback** campo vuoto.

   ![](assets/social_tw_app.png)

>[!NOTE]
>
>È necessaria un&#39;applicazione per account Twitter. Di conseguenza, devi creare un’altra applicazione di test per inviare le bozze al tuo account di test.

## Creare un servizio Twitter in Campaign {#create-tw-service}

Per collegare la tua istanza Campaign al tuo account Twitter, crea un **Twitter** accesso in scrittura a Campaign.

Per immettere le impostazioni, devi accedere sia alla console Adobe Campaign che a un account Twitter:

1. Apri **Twitter** e da [la pagina Progetto e app](https://developer.twitter.com/en/portal/projects-and-apps), seleziona l’app creata in precedenza. Accedere al **Autorizzazioni app**.

   ![](assets/social_tw_service.png)

   Modifica le **Tasti e token** per accedere ai dettagli dell’app.

1. In **Adobe Campaign**, sfoglia fino al **[!UICONTROL Profiles and targets]** e seleziona la **[!UICONTROL Services and Subscriptions]** collegamento
1. Crea un nuovo servizio.
1. Seleziona la **[!UICONTROL Twitter]** digitare.

   >[!NOTE]
   >
   >La **[!UICONTROL Synchronize subscriptions]** è attivata per impostazione predefinita: questa opzione recupera automaticamente l&#39;elenco dei follower di Twitter in modo da [inviare loro messaggi diretti](../send/twitter.md#direct-tw-messages). La sincronizzazione viene eseguita da un [flusso di lavoro tecnico dedicato](#synchro-tw-accounts).

1. Immetti l’etichetta e il nome interno del servizio.

   >[!CAUTION]
   >
   >La **[!UICONTROL Internal name]** del servizio deve essere esattamente lo stesso nome del tuo account Twitter.

   Per controllare le impostazioni, puoi:

   * Fai clic sul pulsante **[!UICONTROL Save]**.
   * Nella panoramica dei servizi, seleziona la **Twitter** servizio appena creato.
   * Sfoglia il **[!UICONTROL Twitter page]** scheda: il tuo account Twitter deve essere visualizzato.

1. Per impostazione predefinita, i follower vengono salvati in **[!UICONTROL Visitors]** cartella. Puoi selezionare un’altra posizione dalla **[!UICONTROL Visitor folder]** campo . [Ulteriori informazioni](../send/twitter.md#direct-tw-messages)

1. Dall’app Twitter, copia il contenuto della **[!UICONTROL Consumer Key (API Key)]** e **[!UICONTROL Consumer Secret (API Secret)]** e incollarli nel **[!UICONTROL Consumer key]** e **[!UICONTROL Consumer secret]** campi della campagna **Twitter** servizio.

1. Dall’app Twitter, copia il contenuto della **[!UICONTROL Access Token]** e **[!UICONTROL Access Token Secret]** e incollarli nel **[!UICONTROL Access token]** e **[!UICONTROL Access token secret]** campi della campagna **Twitter** servizio.

1. Nella console del client Campaign, fai clic su **[!UICONTROL Save]**. Hai delegato l’accesso in scrittura ad Adobe Campaign.


>[!NOTE]
>
>Crearne uno **Twitter** servizio per account Twitter. Di conseguenza, devi creare un altro servizio di test per inviare le bozze al tuo account di test.

## Sincronizzazione dell&#39;account Twitter {#synchro-tw-accounts}

La sincronizzazione tra Campaign e Twitter viene gestita tramite flussi di lavoro tecnici dedicati. Questi flussi di lavoro sono memorizzati nella variabile **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** cartella.

Vengono fermati per impostazione predefinita: è necessario avviarli manualmente quando si inizia a utilizzare il **Social marketing** modulo .

La **[!UICONTROL Twitter account synchronization]** il flusso di lavoro tecnico sincronizza gli account Twitter in Adobe Campaign. Questo flusso di lavoro recupera l’elenco dei follower di Twitter in modo da poter inviare loro messaggi diretti. [Ulteriori informazioni](../send/twitter.md#direct-tw-messages)

Per impostazione predefinita, questo flusso di lavoro viene attivato ogni giovedì alle 7:30. È possibile utilizzare **[!UICONTROL Execute pending task(s) now]** per avviare il flusso di lavoro in qualsiasi momento durante l’implementazione di questa integrazione.  Puoi anche modificare la pianificazione per modificare la frequenza di attivazione del flusso di lavoro. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/scheduler.html){target=&quot;_blank&quot;}.

>[!CAUTION]
>
>Per recuperare l&#39;elenco degli abbonati Twitter, la **[!UICONTROL Twitter account synchronization]** deve essere selezionata per il servizio collegato all&#39;account. [Ulteriori informazioni](#create-tw-service)

I seguenti elementi sono memorizzati in una tabella specifica: la tabella dei visitatori. Per visualizzare l’elenco dei follower di Twitter, seleziona **[!UICONTROL Profiles and Targets > Visitors]**.

Per ogni follower, Adobe Campaign memorizza le seguenti informazioni:

* **[!UICONTROL Origin]**: nome del social network (Twitter)
* **[!UICONTROL External ID]**: identificatore utente
* **[!UICONTROL User name]**: nome account dell&#39;utente
* **[!UICONTROL Full name]**: nome dell&#39;utente
* **[!UICONTROL Language]**: lingua utente
* **[!UICONTROL Number of friends]**: numero di follower
* **[!UICONTROL Time zone]**: fuso orario utente
* **[!UICONTROL Verified]**: questo campo indica se l’utente dispone di un account Twitter verificato

Al termine di questa configurazione, puoi pubblicare tweet nei tuoi account Twitter e inviare messaggi diretti ai tuoi follower. [Ulteriori informazioni](../send/twitter.md)
