---
product: Adobe Campaign
title: Account esterni per Campaign
description: Account esterni per Campaign
feature: Panoramica
role: Data Engineer
level: Beginner
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '1001'
ht-degree: 4%

---


# Configurare gli account esterni

Adobe Campaign è dotato di un set di account esterni predefiniti. Per impostare connessioni con sistemi esterni, puoi creare nuovi account esterni.

Gli account esterni sono utilizzati da processi tecnici quali flussi di lavoro tecnici o flussi di lavoro per campagne. Ad esempio, quando imposti un trasferimento di file in un flusso di lavoro o uno scambio di dati con un’altra applicazione (Adobe Target, Experience Manager, ecc.), devi selezionare un account esterno.

Puoi accedere agli account esterni da Adobe Campaign **[!UICONTROL Explorer]**: vai a **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>Un account esterno **[!UICONTROL Full FDA]** (ffda) specifico gestisce la connessione tra il database locale di Campaign e il database Cloud ([!DNL Snowflake]).
>
>In qualità di utente di Cloud Services gestiti, questo account esterno viene configurato per la tua istanza per Adobe. Non deve essere modificato.


## Account esterni specifici per la campagna

I seguenti account tecnici vengono utilizzati da Adobe Campaign per abilitare ed eseguire processi specifici.

? In qualità di utente di Cloud Services gestiti, ad Adobe, configura per te tutti gli account esterni specifici di Campaign.

* **Messaggi non recapitati (POP3)**

   L&#39;account esterno **Bounce mails** specifica l&#39;account POP3 esterno da utilizzare per la connessione al servizio e-mail. Tutti i server configurati per l&#39;accesso POP3 possono essere utilizzati per ricevere la posta di ritorno.

   ↗️ Ulteriori informazioni sulle e-mail in entrata nella documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html){target=&quot;_blank&quot;}[

* **Indirizzamento**

   L’account esterno **[!UICONTROL Routing]** ti consente di configurare ogni canale disponibile in Adobe Campaign in base ai pacchetti installati.

   >[!CAUTION]
   >
   >L&#39;account esterno **[!UICONTROL Internal email delivery routing]** (defaultEmailBulk) **non deve essere abilitato** in Adobe Campaign v8.

* **Istanza di esecuzione**

   Nel contesto della messaggistica transazionale, le istanze di esecuzione sono collegate all’istanza di controllo e le collegano. I modelli di messaggi transazionali vengono distribuiti nell’istanza di esecuzione.

   ? Ulteriori informazioni sull&#39;architettura del Centro messaggi in [questa pagina](../dev/architecture.md#transac-msg-archi).

## Accesso agli account esterni dei sistemi esterni

* **Database esterno (FDA)**

   Utilizza il tipo di account esterno **Database esterno** per connettersi a un database esterno tramite FDA.

   I database esterni compatibili con Adobe Campaign v8 sono elencati nella [Matrice di compatibilità](../start/compatibility-matrix.md)

   ? Ulteriori informazioni sull&#39;opzione Federated Data Access (FDA) in [questa sezione](../connect/fda.md).

## Account esterni per l’integrazione di soluzioni Adobe

* **Adobe Experience Cloud**

   L’ account esterno **[!UICONTROL Adobe Experience Cloud]** viene utilizzato per implementare Adobe IMS per connettersi alla console Adobe Campaign utilizzando un Adobe ID.

   ? Per ulteriori informazioni su Adobe Identity Management Service (IMS), consulta [questa sezione](../start/connect.md#connect-ims).

* **Analisi web**

   Utilizza l’ account esterno **[!UICONTROL Web Analytics (Adobe Analytics)]** per configurare il trasferimento di dati da Adobe Analytics ad Adobe Campaign.

   ? Ulteriori informazioni sull&#39;integrazione Adobe Campaign - Adobe Analytics in [questa pagina](../connect/ac-aa.md).

   ? In qualità di utente di Cloud Services gestiti, [contatta Adobe](../start/campaign-faq.md#support) per integrare Adobe Analytics con Campaign.

   * **Adobe Experience Manager**
   L’ account esterno **[!UICONTROL AEM]** ti consente di gestire il contenuto delle consegne e-mail e dei moduli direttamente in Adobe Experience Manager.

   ? Ulteriori informazioni sull&#39;integrazione Adobe Campaign - Adobe Analytics in [questa pagina](../connect/ac-aem.md).

   ? In qualità di utente di Cloud Services gestiti, [contatta Adobe](../start/campaign-faq.md#support) per integrare Adobe Experience Manager con Adobe Campaign.


## Account esterni del connettore di gestione delle relazioni con i clienti

* **Microsoft Dynamics CRM**

   L’account esterno **[!UICONTROL Microsoft Dynamics CRM]** ti consente di importare ed esportare dati di Microsoft Dynamics in Adobe Campaign.

   ? Ulteriori informazioni sull&#39;integrazione Adobe Campaign - Microsoft Dynamics CRM in [questa pagina](../connect/crm.md).

   Con il tipo di distribuzione **[!UICONTROL Web API]** e l&#39;autenticazione **[!UICONTROL Password credentials]**, devi fornire i seguenti dettagli:

   * **[!UICONTROL Account]**: Account utilizzato per accedere a Microsoft CRM.

   * **[!UICONTROL Server]**: URL del server Microsoft CRM in uso.

   * **[!UICONTROL Client identifier]**: ID client che si trova dal portale di gestione di Microsoft Azure nel  **[!UICONTROL Update your code]** campo  **[!UICONTROL Client ID]** categoria.

   * **[!UICONTROL CRM version]**: Versione del CRM tra  **[!UICONTROL Dynamics CRM 2007]**,  **[!UICONTROL Dynamics CRM 2015]** o  **[!UICONTROL Dynamics CRM 2016]**.
   Con il tipo di distribuzione **[!UICONTROL Web API]** e l&#39;autenticazione **[!UICONTROL Certificate]**, devi fornire i seguenti dettagli:

   * **[!UICONTROL Server]**: URL del server Microsoft CRM in uso.

   * **[!UICONTROL Private Key (Base64 encoded)]**: Chiave privata codificata in Base64

   * **[!UICONTROL Custom Key identifier]**

   * **[!UICONTROL Key ID]**

   * **[!UICONTROL Client identifier]**: ID client che si trova dal portale di gestione di Microsoft Azure nel  **[!UICONTROL Update your code]** campo  **[!UICONTROL Client ID]** categoria.

   * **[!UICONTROL CRM version]**: Versione del CRM tra  **[!UICONTROL Dynamics CRM 2007]**,  **[!UICONTROL Dynamics CRM 2015]** o  **[!UICONTROL Dynamics CRM 2016]**.


* **Salesforce.com**

   L’account esterno **[!UICONTROL Salesforce CRM]** ti consente di importare ed esportare dati Salesforce in Adobe Campaign.

   Per configurare l&#39;account esterno di gestione delle relazioni con i clienti Salesforce affinché funzioni con Adobe Campaign, devi fornire i seguenti dettagli:

   * **[!UICONTROL Account]**: Account utilizzato per accedere a CRM Salesforce.

   * **[!UICONTROL Password]**: Password utilizzata per accedere a CRM Salesforce.

   * **[!UICONTROL Client identifier]**: Scopri come trovare l’identificatore client in  [questa pagina](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL Security token]**: Scopri come trovare il token di sicurezza in  [questa pagina](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL API version]**: Seleziona la versione dell’API. Per questo account esterno, devi configurare il tuo CRM Salesforce con la procedura guidata di configurazione.

## Trasferisci account esterni dati

Questi account esterni possono essere utilizzati per importare o esportare dati in Adobe Campaign utilizzando un’attività di flusso di lavoro **[!UICONTROL Transfer file]** .

↗️ Ulteriori informazioni sul trasferimento dei file nei flussi di lavoro nella documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html){target=&quot;_blank&quot;}[

* **FTP e SFTP**

   L&#39;account esterno **FTP** ti consente di configurare e testare l&#39;accesso a un server esterno ad Adobe Campaign. Per impostare connessioni con sistemi esterni come server SFTP o FTP 898 utilizzati per i trasferimenti di file, puoi creare account esterni.
Per farlo, specifica in questo account esterno l’indirizzo e le credenziali utilizzati per stabilire la connessione al server SFTP o FTP.

* **Servizio di archiviazione semplice Amazon (S3)**

   Il connettore **AWS S3** può essere utilizzato per importare o esportare dati in Adobe Campaign utilizzando un’attività del flusso di lavoro **[!UICONTROL Transfer file]**. Quando imposti questo nuovo account esterno, dovrai fornire i seguenti dettagli:

   * **[!UICONTROL AWS S3 Account Server]**: URL del server, compilato come segue:    ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL AWS access key ID]**: Scopri come trovare il tuo ID chiave di accesso AWS nella documentazione di  [Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) .

   * **[!UICONTROL Secret access key to AWS]**: Scopri come trovare la chiave di accesso segreto ad AWS nella documentazione di  [Amazon](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/).

   * **[!UICONTROL AWS Region]**: Ulteriori informazioni sulle aree AWS nella documentazione di  [Amazon](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/).

   * La casella di controllo **[!UICONTROL Use server side encryption]** consente di memorizzare il file in modalità crittografata S3. Scopri come trovare l’ID chiave di accesso e la chiave di accesso segreto nella [documentazione di Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys).

* **Archiviazione BLOB di Azure**

   L’account esterno **Azure** può essere utilizzato per importare o esportare dati in Adobe Campaign utilizzando un’attività del flusso di lavoro **[!UICONTROL Transfer file]**. Per configurare l&#39;account esterno **Azure** in modo che funzioni con Adobe Campaign, devi fornire i seguenti dettagli:

   * **[!UICONTROL Server]**: URL del server di archiviazione BLOB di Azure.

   * **[!UICONTROL Encryption]**: Tipo di crittografia tra  **[!UICONTROL None]** o  **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: Scopri come trovare il tuo  **[!UICONTROL Access key]** nella documentazione  [Microsoft](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal).

