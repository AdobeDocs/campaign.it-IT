---
title: Account esterni di Campaign
description: Account esterni di Campaign
feature: Application Settings
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: c46eaa73deed643a4e92928b6ce2b1beb1596d73
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 4%

---


# Configurare gli account esterni

Adobe Campaign è dotato di un set di account esterni predefiniti. Per impostare connessioni con sistemi esterni, puoi creare nuovi account esterni.

Gli account esterni sono utilizzati da processi tecnici quali flussi di lavoro tecnici o flussi di lavoro per campagne. Ad esempio, quando imposti un trasferimento di file in un flusso di lavoro o uno scambio di dati con un’altra applicazione (Adobe Target, Experience Manager, ecc.), devi selezionare un account esterno.

Puoi accedere ad account esterni da Adobe Campaign **[!UICONTROL Explorer]**: passa a **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>* In qualità di utente di Managed Cloud Services, gli account esterni sono configurati per la tua istanza da Adobe e non devono essere modificati.
>
>* Nell&#39;ambito di una [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), uno specifico **[!UICONTROL Full FDA]** (ffda) un account esterno gestisce la connessione tra il database locale di Campaign e il database cloud ([!DNL Snowflake]).
>


## Account esterni specifici per la campagna

I seguenti account tecnici vengono utilizzati da Adobe Campaign per abilitare ed eseguire processi specifici.

### Messaggi non recapitati {#bounce-mails-external-account}

>[!NOTE]
>
>A partire da Campaign v8.3, è disponibile l’autenticazione OAuth 2.0 di Microsoft Exchange Online per la funzionalità POP3. Per verificare la versione, consulta [questa sezione](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).

Il **Messaggi non recapitati** account esterno specifica l&#39;account POP3 esterno da utilizzare per la connessione al servizio e-mail. Tutti i server configurati per l&#39;accesso POP3 possono essere utilizzati per ricevere la posta di ritorno.

Ulteriori informazioni sulle e-mail in entrata in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html).

![](assets/bounce_external_1.png)

Per configurare **[!UICONTROL Bounce mails (defaultPopAccount)]** account esterno:

* **[!UICONTROL Server]** - URL del server POP3.

* **[!UICONTROL Port]** - Numero porta di connessione POP3. La porta predefinita è 110.

* **[!UICONTROL Account]** - Nome dell&#39;utente.

* **[!UICONTROL Password]** - Password dell&#39;account utente.

* **[!UICONTROL Encryption]** - Tipo di crittografia scelta tra **[!UICONTROL By default]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** o **[!UICONTROL POP3S]**.

   Il **Messaggi non recapitati** account esterno specifica l&#39;account POP3 esterno da utilizzare per la connessione al servizio e-mail. Tutti i server configurati per l&#39;accesso POP3 possono essere utilizzati per ricevere la posta di ritorno.

* **[!UICONTROL Function]** - E-mail in entrata o router SOAP

![](assets/bounce_external_2.png)

>[!CAUTION]
>
>Prima di configurare l’account esterno POP3 utilizzando Microsoft OAuth 2.0, è necessario registrare l’applicazione nel portale di Azure. Per ulteriori informazioni, consulta questa [pagina](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

Per configurare un POP3 esterno tramite Microsoft OAuth 2.0, seleziona la **[!UICONTROL Microsoft OAuth 2.0]** e compilare i campi seguenti:

* **[!UICONTROL Azure tenant]** : l’ID di Azure (o l’ID di directory (tenant)) si trova nella **Elementi di base** della panoramica dell’applicazione nel portale di Azure.

* **[!UICONTROL Azure Client ID]** - L’ID client (o l’ID applicazione (client) ) si trova nella **Elementi di base** della panoramica dell’applicazione nel portale di Azure.

* **[!UICONTROL Azure Client secret]** - L’ID del segreto client si trova nella **Segreti client** colonna da **Certificati e segreti** dell’applicazione nel portale di Azure.

* **[!UICONTROL Azure Redirect URL]** - L’URL di reindirizzamento si trova nella sezione **Autenticazione** dell’applicazione nel portale di Azure. Deve terminare con la seguente sintassi `nl/jsp/oauth.jsp`, ad es. `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

   Dopo aver immesso le diverse credenziali, puoi fare clic su **[!UICONTROL Setup the connection]** per completare la configurazione dell’account esterno.

### Indirizzamento {#routing}

Il **[!UICONTROL Routing]** l’account esterno ti consente di configurare ogni canale disponibile in Adobe Campaign in base ai pacchetti installati.

>[!CAUTION]
>
>Il **[!UICONTROL Internal email delivery routing]** (defaultEmailBulk) account esterno **non deve** essere abilitato in Adobe Campaign v8.

### Istanza di esecuzione {#execution-instance}

Nel contesto della messaggistica transazionale, le istanze di esecuzione sono collegate all’istanza di controllo e le connettono. I modelli di messaggi transazionali vengono distribuiti nell’istanza di esecuzione. Ulteriori informazioni sull’architettura del Centro messaggi in [questa pagina](../architecture/architecture.md#transac-msg-archi).

## Accesso a account esterni di sistemi esterni

* **Database esterno (FDA)** - Il **Database esterno** tipo di account esterno utilizzato per connettersi a un database esterno tramite Federated Data Access (FDA). Ulteriori informazioni sull’opzione Federated Data Access (FDA) in [questa sezione](../connect/fda.md).

   I database esterni compatibili con Adobe Campaign v8 sono elencati nella [Matrice di compatibilità](../start/compatibility-matrix.md)

* **Twitter** - Il **Twitter** digita account esterno per collegare Campaign al tuo account twitter e pubblicare messaggi per tuo conto. Ulteriori informazioni sull’integrazione di Twitter in [questa sezione](../connect/ac-tw.md).

## Account esterni di Adobe Solution Integration

* **Adobe Experience Cloud** - Il **[!UICONTROL Adobe Experience Cloud]** viene utilizzato un account esterno per implementare Adobe Identity Management Service (IMS) e connettersi a Adobe Campaign. Ulteriori informazioni sul servizio Identity Management (IMS) di Adobe in [questa sezione](../start/connect.md#logon-to-ac).

* **Web Analytics** - Il **[!UICONTROL Web Analytics (Adobe Analytics)]** l’account esterno viene utilizzato per configurare il trasferimento di dati da Adobe Analytics ad Adobe Campaign. Ulteriori informazioni sull’integrazione Adobe Campaign - Adobe Analytics in [questa pagina](../connect/ac-aa.md).

* **Adobe Experience Manager** - Il **[!UICONTROL AEM]** l’account esterno consente di gestire il contenuto delle consegne e-mail e dei moduli direttamente in Adobe Experience Manager. Ulteriori informazioni sull’integrazione Adobe Campaign - Adobe Analytics in [questa pagina](../connect/ac-aem.md).


## Account esterni del connettore CRM

* **Microsoft Dynamics CRM** - Il **[!UICONTROL Microsoft Dynamics CRM]** l’account esterno ti consente di importare ed esportare dati di Microsoft Dynamics in Adobe Campaign. Ulteriori informazioni sull’integrazione di Adobe Campaign con Microsoft Dynamics CRM in [questa pagina](../connect/ac-ms-dyn.md).

* **Salesforce.com** - Il **[!UICONTROL Salesforce CRM]** l’account esterno ti consente di importare ed esportare i dati di Salesforce in Adobe Campaign. Ulteriori informazioni sull’integrazione di Adobe Campaign con il sistema CRM Salesforce.com in [questa pagina](../connect/ac-sfdc.md).

## Trasferisci dati account esterni

Questi account esterni possono essere utilizzati per importare o esportare dati in Adobe Campaign utilizzando un **[!UICONTROL Transfer file]** attività del flusso di lavoro. Ulteriori informazioni su **Trasferimento file** nei flussi di lavoro in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html).

* **FTP e SFTP** - Il **FTP** l’account esterno consente di configurare e testare l’accesso a un server esterno a Adobe Campaign. Per configurare le connessioni con sistemi esterni, come i server SFTP o FTP 898 utilizzati per i trasferimenti di file, puoi creare account esterni.

   Per farlo, specifica in questo account esterno l’indirizzo e le credenziali utilizzati per stabilire la connessione al server SFTP o FTP.

* **Servizio Amazon Simple Storage (S3)** - Il **AWS S3** il connettore può essere utilizzato per importare o esportare dati in Adobe Campaign utilizzando un **[!UICONTROL Transfer file]** attività del flusso di lavoro. Quando imposti questo nuovo account esterno, dovrai fornire i seguenti dettagli:

   * **[!UICONTROL AWS S3 Account Server]**: URL del server, compilato come segue:   `<S3bucket name>.s3.amazonaws.com/<s3object path>`

   * **[!UICONTROL AWS access key ID]**: scopri come trovare il tuo ID chiave di accesso ad AWS in [Documentazione di Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

   * **[!UICONTROL Secret access key to AWS]**: scopri come trovare la tua chiave di accesso segreta ad AWS in [Documentazione di Amazon](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}.

   * **[!UICONTROL AWS Region]**: ulteriori informazioni sulle aree geografiche di AWS in [Documentazione di Amazon](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}.

   * Il **[!UICONTROL Use server side encryption]** casella di controllo consente di memorizzare il file in modalità crittografata S3. Scopri come trovare l’ID della chiave di accesso e la chiave di accesso segreta in [Documentazione di Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

* **Archiviazione BLOB di Azure** - Il **Azure** l’account esterno può essere utilizzato per importare o esportare dati in Adobe Campaign utilizzando un **[!UICONTROL Transfer file]** attività del flusso di lavoro. Per configurare **Azure** account esterno per lavorare con Adobe Campaign, è necessario fornire i seguenti dettagli:

   * **[!UICONTROL Server]**: URL del server di archiviazione BLOB di Azure.

   * **[!UICONTROL Encryption]**: tipo di crittografia tra **[!UICONTROL None]** o **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: scopri come trovare il tuo **[!UICONTROL Access key]** in [Documentazione di Microsoft](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}.
