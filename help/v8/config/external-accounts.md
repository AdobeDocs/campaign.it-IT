---
title: Account esterni per Campaign
description: Account esterni per Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 4%

---

# Configurare gli account esterni

Adobe Campaign è dotato di un set di account esterni predefiniti. Per impostare connessioni con sistemi esterni, puoi creare nuovi account esterni.

Gli account esterni sono utilizzati da processi tecnici quali flussi di lavoro tecnici o flussi di lavoro per campagne. Ad esempio, quando imposti un trasferimento di file in un flusso di lavoro o uno scambio di dati con un’altra applicazione (Adobe Target, Experience Manager, ecc.), devi selezionare un account esterno.

Puoi accedere agli account esterni da Adobe Campaign **[!UICONTROL Explorer]**: naviga a **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>Una specifica **[!UICONTROL Full FDA]** (ffda) l’account esterno gestisce la connessione tra il database locale di Campaign e il database Cloud ([!DNL Snowflake]).
>
>In qualità di utente di Cloud Services gestiti, questo account esterno viene configurato per la tua istanza per Adobe. Non deve essere modificato.


## Account esterni specifici per la campagna

I seguenti account tecnici vengono utilizzati da Adobe Campaign per abilitare ed eseguire processi specifici.

![](../assets/do-not-localize/speech.png)  In qualità di utente di Cloud Services gestiti, ad Adobe, configura per te tutti gli account esterni specifici di Campaign.

* **Messaggi non recapitati (POP3)**

   La **Messaggi non recapitati** account esterno specifica l’account POP3 esterno da utilizzare per connettersi al servizio e-mail. Tutti i server configurati per l&#39;accesso POP3 possono essere utilizzati per ricevere la posta di ritorno.

   ![](../assets/do-not-localize/book.png) Ulteriori informazioni sulle e-mail in entrata in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html){target=&quot;_blank&quot;}

* **Indirizzamento**

   La **[!UICONTROL Routing]** l’account esterno ti consente di configurare ogni canale disponibile in Adobe Campaign in base ai pacchetti installati.

   >[!CAUTION]
   >
   >La **[!UICONTROL Internal email delivery routing]** Account esterno (defaultEmailBulk) **non deve** in Adobe Campaign v8.

* **Istanza di esecuzione**

   Nel contesto della messaggistica transazionale, le istanze di esecuzione sono collegate all’istanza di controllo e le collegano. I modelli di messaggi transazionali vengono distribuiti nell’istanza di esecuzione.

   ![](../assets/do-not-localize/glass.png) Ulteriori informazioni sull&#39;architettura del Centro messaggi in [questa pagina](../dev/architecture.md#transac-msg-archi).

## Accesso agli account esterni dei sistemi esterni

* **Database esterno (FDA)**

   Utilizza la **Database esterno** digitare account esterno per connettersi a un database esterno tramite FDA.

   I database esterni compatibili con Adobe Campaign v8 sono elencati nel [Matrice di compatibilità](../start/compatibility-matrix.md)

   ![](../assets/do-not-localize/glass.png) Ulteriori informazioni sull’opzione Federated Data Access (FDA) in [questa sezione](../connect/fda.md).

## Account esterni per l’integrazione di soluzioni Adobe

* **Adobe Experience Cloud**

   La **[!UICONTROL Adobe Experience Cloud]** l’account esterno viene utilizzato per implementare Adobe IMS per connettersi alla console Adobe Campaign utilizzando un Adobe ID.

   ![](../assets/do-not-localize/glass.png) Ulteriori informazioni su Adobe Identity Management Service (IMS) in [questa sezione](../start/connect.md#connect-ims).

* **Analisi web**

   Utilizza la **[!UICONTROL Web Analytics (Adobe Analytics)]** account esterno per configurare il trasferimento di dati da Adobe Analytics ad Adobe Campaign.

   ![](../assets/do-not-localize/glass.png) Ulteriori informazioni sull’integrazione Adobe Campaign - Adobe Analytics in [questa pagina](../connect/ac-aa.md).

   ![](../assets/do-not-localize/speech.png)  Come utente di Cloud Services gestiti, [Adobe di contatto](../start/campaign-faq.md#support) per integrare Adobe Analytics con Campaign.

   * **Adobe Experience Manager**
   La **[!UICONTROL AEM]** l’account esterno ti consente di gestire il contenuto delle consegne e-mail e dei moduli direttamente in Adobe Experience Manager.

   ![](../assets/do-not-localize/glass.png) Ulteriori informazioni sull’integrazione Adobe Campaign - Adobe Analytics in [questa pagina](../connect/ac-aem.md).

   ![](../assets/do-not-localize/speech.png)  Come utente di Cloud Services gestiti, [Adobe di contatto](../start/campaign-faq.md#support) per integrare Adobe Experience Manager con Adobe Campaign.


## Account esterni del connettore di gestione delle relazioni con i clienti

* **Microsoft Dynamics CRM**

   La **[!UICONTROL Microsoft Dynamics CRM]** l’account esterno ti consente di importare ed esportare dati di Microsoft Dynamics in Adobe Campaign.

   ![](../assets/do-not-localize/glass.png) Ulteriori informazioni sull’integrazione di Adobe Campaign - Microsoft Dynamics CRM in [questa pagina](../connect/crm.md).

   Con **[!UICONTROL Web API]** tipo di distribuzione e **[!UICONTROL Password credentials]** autenticazione, devi fornire i seguenti dettagli:

   * **[!UICONTROL Account]**: Account utilizzato per accedere a Microsoft CRM.

   * **[!UICONTROL Server]**: URL del server Microsoft CRM.

   * **[!UICONTROL Client identifier]**: ID client che è possibile trovare dal portale di gestione di Microsoft Azure in **[!UICONTROL Update your code]** categoria, **[!UICONTROL Client ID]** campo .

   * **[!UICONTROL CRM version]**: Versione del CRM tra **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** o **[!UICONTROL Dynamics CRM 2016]**.
   Con **[!UICONTROL Web API]** tipo di distribuzione e **[!UICONTROL Certificate]** autenticazione, devi fornire i seguenti dettagli:

   * **[!UICONTROL Server]**: URL del server Microsoft CRM.

   * **[!UICONTROL Private Key (Base64 encoded)]**: Chiave privata codificata in Base64

   * **[!UICONTROL Custom Key identifier]**

   * **[!UICONTROL Key ID]**

   * **[!UICONTROL Client identifier]**: ID client che è possibile trovare dal portale di gestione di Microsoft Azure in **[!UICONTROL Update your code]** categoria, **[!UICONTROL Client ID]** campo .

   * **[!UICONTROL CRM version]**: Versione del CRM tra **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** o **[!UICONTROL Dynamics CRM 2016]**.


* **Salesforce.com**

   La **[!UICONTROL Salesforce CRM]** l’account esterno ti consente di importare ed esportare dati Salesforce in Adobe Campaign.

   Per configurare l&#39;account esterno di gestione delle relazioni con i clienti Salesforce affinché funzioni con Adobe Campaign, devi fornire i seguenti dettagli:

   * **[!UICONTROL Account]**: Account utilizzato per accedere a CRM Salesforce.

   * **[!UICONTROL Password]**: Password utilizzata per accedere a CRM Salesforce.

   * **[!UICONTROL Client identifier]**: Scopri come trovare l’identificatore client in [questa pagina](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL Security token]**: Scopri come trovare il token di sicurezza in [questa pagina](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL API version]**: Seleziona la versione dell’API. Per questo account esterno, devi configurare il tuo CRM Salesforce con la procedura guidata di configurazione.

## Trasferisci account esterni dati

Questi account esterni possono essere utilizzati per importare o esportare dati in Adobe Campaign utilizzando un **[!UICONTROL Transfer file]** attività del flusso di lavoro.

![](../assets/do-not-localize/book.png) Ulteriori informazioni sul trasferimento di file nei flussi di lavoro in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html){target=&quot;_blank&quot;}

* **FTP e SFTP**

   La **FTP** l’account esterno ti consente di configurare e testare l’accesso a un server al di fuori di Adobe Campaign. Per impostare connessioni con sistemi esterni come server SFTP o FTP 898 utilizzati per i trasferimenti di file, puoi creare account esterni.
Per farlo, specifica in questo account esterno l’indirizzo e le credenziali utilizzati per stabilire la connessione al server SFTP o FTP.

* **Servizio di archiviazione semplice Amazon (S3)**

   La **AWS S3** può essere utilizzato per importare o esportare dati in Adobe Campaign utilizzando un **[!UICONTROL Transfer file]** attività del flusso di lavoro. Quando imposti questo nuovo account esterno, dovrai fornire i seguenti dettagli:

   * **[!UICONTROL AWS S3 Account Server]**: URL del server, compilato come segue:   ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL AWS access key ID]**: Scopri come trovare il tuo ID chiave di accesso AWS in [Documentazione di Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) .

   * **[!UICONTROL Secret access key to AWS]**: Scopri come trovare la chiave di accesso segreta in AWS in [Documentazione di Amazon](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/).

   * **[!UICONTROL AWS Region]**: Ulteriori informazioni sulle aree geografiche di AWS in [Documentazione di Amazon](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/).

   * La **[!UICONTROL Use server side encryption]** casella di controllo consente di memorizzare il file in modalità crittografata S3. Scopri come trovare l’ID chiave di accesso e la chiave di accesso segreto in [Documentazione di Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys).

* **Archiviazione BLOB di Azure**

   La **Azure** l’account esterno può essere utilizzato per importare o esportare dati in Adobe Campaign utilizzando un **[!UICONTROL Transfer file]** attività del flusso di lavoro. Per configurare le **Azure** per lavorare con Adobe Campaign, devi fornire i seguenti dettagli:

   * **[!UICONTROL Server]**: URL del server di archiviazione BLOB di Azure.

   * **[!UICONTROL Encryption]**: Tipo di cifratura tra **[!UICONTROL None]** o **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: Scopri come trovare il tuo **[!UICONTROL Access key]** in [Documentazione di Microsoft](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal).
