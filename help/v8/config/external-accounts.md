---
title: Account esterni di Campaign
description: Configura account esterni per collegare Campaign a sistemi esterni come POP3, database FDA, CRM, archiviazione e soluzioni Adobe.
feature: Application Settings, External Account
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 776a0e5eead9161b7e2c9d7746c72cba42ea42cb
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 4%

---


# Configurare gli account esterni {#config-external-accounts}

Adobe Campaign è dotato di un set di account esterni predefiniti. Per impostare connessioni con sistemi esterni, puoi creare nuovi account esterni.

Gli account esterni sono utilizzati da processi tecnici quali flussi di lavoro tecnici o flussi di lavoro per campagne. Ad esempio, quando imposti un trasferimento di file in un flusso di lavoro o uno scambio di dati con un’altra applicazione (Adobe Target, Experience Manager, ecc.), devi selezionare un account esterno.

È possibile accedere ad account esterni da Adobe Campaign **[!UICONTROL Explorer]**: passare a **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>* In qualità di utente di Managed Cloud Services, gli account esterni vengono configurati per la tua istanza da Adobe e non devono essere modificati.
>
>* Nel contesto di una distribuzione [Enterprise (FFDA)](../architecture/enterprise-deployment.md), un account esterno **[!UICONTROL Full FDA]** (ffda) specifico gestisce la connessione tra il database locale di Campaign e il database cloud ([!DNL Snowflake]).
>

## Account esterni specifici per la campagna {#ac-external-accounts}

I seguenti account tecnici vengono utilizzati da Adobe Campaign per abilitare ed eseguire processi specifici.

### E-mail non recapitate {#bounce-mails-external-account}

>[!NOTE]
>
>A partire da Campaign v8.3, è disponibile l’autenticazione OAuth 2.0 di Microsoft Exchange Online per la funzionalità POP3. Per verificare la versione, consultare [questa sezione](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).
>

L&#39;account esterno **Messaggi non recapitati** specifica l&#39;account POP3 esterno da utilizzare per connettersi al servizio e-mail. Tutti i server configurati per l&#39;accesso POP3 possono essere utilizzati per ricevere la posta di ritorno.

Ulteriori informazioni sulle e-mail in entrata in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html?lang=it){target="_blank"}.

![](assets/bounce_external_1.png)

Per configurare l&#39;account esterno **[!UICONTROL Bounce mails (defaultPopAccount)]**:

* **[!UICONTROL Server]** - URL del server POP3.

* **[!UICONTROL Port]** - Numero porta di connessione POP3. La porta predefinita è 110.

* **[!UICONTROL Account]** - Nome dell&#39;utente.

* **[!UICONTROL Password]** - Password account utente.

* **[!UICONTROL Encryption]** - Tipo di crittografia scelta tra **[!UICONTROL By default]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** o **[!UICONTROL POP3S]**.

* **[!UICONTROL Function]** - E-mail in entrata o router SOAP.

![](assets/bounce_external_2.png)

>[!CAUTION]
>
>Prima di configurare l’account esterno POP3 utilizzando Microsoft OAuth 2.0, è necessario registrare l’applicazione nel portale Azure. Per ulteriori informazioni, consulta questa [pagina](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.
>

Per configurare un POP3 esterno tramite Microsoft OAuth 2.0, seleziona l’opzione **[!UICONTROL Microsoft OAuth 2.0]** e compila i campi seguenti:

* **[!UICONTROL Azure tenant]** - Azure ID (o ID directory (tenant)) si trova nel menu a discesa **Essentials** della panoramica dell&#39;applicazione nel portale Azure.

* **[!UICONTROL Azure Client ID]** - L&#39;ID client (o l&#39;ID applicazione (client)) si trova nel menu a discesa **Essentials** della panoramica dell&#39;applicazione nel portale Azure.

* **[!UICONTROL Azure Client secret]** - L&#39;ID del segreto client si trova nella colonna **Segreti client** dal menu **Certificati e segreti** dell&#39;applicazione nel portale Azure.

* **[!UICONTROL Azure Redirect URL]** - L&#39;URL di reindirizzamento si trova nel menu **Autenticazione** dell&#39;applicazione nel portale Azure. Deve terminare con la seguente sintassi `nl/jsp/oauth.jsp`, ad esempio `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

Dopo aver immesso le credenziali, fai clic su **[!UICONTROL Setup the connection]** per completare la configurazione dell&#39;account esterno.

### Indirizzamento {#routing}

L&#39;account esterno **[!UICONTROL Routing]** consente di configurare ogni canale disponibile in Adobe Campaign in base ai pacchetti installati.

Ulteriori informazioni sulla gestione degli account esterni e sull&#39;esecuzione della consegna in [questa sezione](../architecture/architecture.md#split).

### Istanza di esecuzione {#execution-instance}

Nel contesto dei messaggi transazionali, l’istanza di esecuzione è collegata all’istanza di controllo e le connette. I modelli di messaggi transazionali vengono distribuiti nell’istanza di esecuzione. Ulteriori informazioni sull&#39;architettura del Centro messaggi in [questa pagina](../architecture/architecture.md#transac-msg-archi).

## Accesso a account esterni di sistemi esterni {#external-syst-external-accounts}

### Federated Data Access (FDA) {#fda-external-accounts}

L&#39;account esterno di tipo **Database esterno** viene utilizzato per connettersi a un database esterno tramite Federated Data Access (FDA). Ulteriori informazioni sull&#39;opzione Federated Data Access (FDA) in [questa sezione](../connect/fda.md).

>[!NOTE]
>
>I database esterni compatibili con Adobe Campaign v8 sono elencati nella [Matrice di compatibilità](../start/compatibility-matrix.md). Le connessioni FDA utilizzano driver ODBC; con Adobe Campaign Managed Cloud Services, la configurazione del driver ODBC e dell&#39;account esterno è impostata da Adobe.

Le impostazioni di configurazione dell&#39;account esterno dipendono dal motore del database. Con Adobe Campaign Managed Cloud Services, la configurazione degli account esterni viene eseguita da Adobe. Ulteriori informazioni su questa configurazione sono disponibili nella [documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/it/docs/campaign-classic/using/installing-campaign-classic/accessing-external-database/external-accounts){target="_blank"}.

#### Account esterno database {#databricks-external-accounts}

La connessione FDA Databricks utilizza il driver ODBC Databricks. A partire dalla versione 8.9.1 di Campaign, gli account esterni Databricks supportano l’autenticazione OAuth2 tramite l’entità principale del servizio (flusso di credenziali client non interattive), fornendo un’autenticazione sicura per l’accesso ai dati federati.

Ulteriori informazioni sulle entità servizio nella [documentazione di Microsoft](https://learn.microsoft.com/en-us/azure/databricks/admin/users-groups/service-principals){target="_blank"}.

Per configurare l’autenticazione OAuth2 tramite l’entità servizio in Campaign:

1. L&#39;amministratore dell&#39;area di lavoro Database abilita le entità servizio nell&#39;area di lavoro Database e genera le credenziali. Per autorizzare l’accesso alle risorse del database Azure con OAuth, crea un segreto OAuth (utilizzato per generare token di accesso OAuth per l’autenticazione).
2. In Adobe Campaign, crea o modifica un account esterno Databricks e apri la scheda **OAuth**.
3. Incolla le credenziali nei campi della scheda OAuth dell’account esterno Database.
4. Utilizza **[!UICONTROL Test the connection]** per convalidare la configurazione.

### X (precedentemente noto come Twitter) {#twitter-external-account}

L&#39;account esterno di tipo **Twitter** viene utilizzato per connettere Campaign al tuo account X e per pubblicare messaggi per tuo conto. Ulteriori informazioni sull&#39;integrazione X in [questa sezione](../connect/ac-tw.md).

## Account esterni per l’integrazione delle soluzioni Adobe {#adobe-integration-external-accounts}

* **Adobe Experience Cloud** - L&#39;account esterno **[!UICONTROL Adobe Experience Cloud]** viene utilizzato per implementare Adobe Identity Management Service (IMS) per la connessione ad Adobe Campaign. Ulteriori informazioni su Adobe Identity Management Service (IMS) sono disponibili in [questa sezione](../start/connect.md#logon-to-ac).

* **Web Analytics** - L&#39;account esterno **[!UICONTROL Web Analytics (Adobe Analytics)]** viene utilizzato per configurare il trasferimento di dati da Adobe Analytics ad Adobe Campaign. Ulteriori informazioni sull&#39;integrazione Adobe Campaign - Adobe Analytics in [questa pagina](../connect/ac-aa.md).

* **Adobe Experience Manager** - L&#39;account esterno **[!UICONTROL AEM]** consente di gestire il contenuto delle consegne e-mail e dei moduli direttamente in Adobe Experience Manager. Ulteriori informazioni sull&#39;integrazione Adobe Campaign - Adobe Experience Manager in [questa pagina](../connect/ac-aem.md).


## Account esterni del connettore CRM {#crm-external-accounts}

* **Microsoft Dynamics CRM** - L&#39;account esterno **[!UICONTROL Microsoft Dynamics CRM]** ti consente di importare ed esportare dati Microsoft Dynamics in Adobe Campaign. Ulteriori informazioni sull&#39;integrazione tra Adobe Campaign e Microsoft Dynamics CRM in [questa pagina](../connect/ac-ms-dyn.md).

* **Salesforce.com** - L&#39;account esterno **[!UICONTROL Salesforce CRM]** consente di importare ed esportare dati Salesforce in Adobe Campaign. Ulteriori informazioni sull&#39;integrazione di Adobe Campaign - Salesforce.com CRM in [questa pagina](../connect/ac-sfdc.md).

## Trasferisci dati account esterni {#transfer-data-external-accounts}

Questi account esterni possono essere utilizzati per importare o esportare dati in Adobe Campaign utilizzando un&#39;attività del flusso di lavoro **[!UICONTROL Transfer file]**. Ulteriori informazioni su **Trasferimento file** nei flussi di lavoro in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html?lang=it){target="_blank"}.

* **FTP e SFTP** - L&#39;account esterno **FTP** consente di configurare e testare l&#39;accesso a un server esterno a Adobe Campaign. Per impostare le connessioni con i sistemi esterni, ad esempio i server SFTP o FTP utilizzati per i trasferimenti di file, puoi creare account esterni.

  Per farlo, specifica in questo account esterno l’indirizzo e le credenziali utilizzati per stabilire la connessione al server SFTP o FTP.

  >[!NOTE]
  >
  >A partire dalla versione 8.5, ora puoi eseguire l’autenticazione in modo sicuro utilizzando una chiave privata durante la configurazione dell’account esterno SFTP. [Ulteriori informazioni sulla gestione delle chiavi](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=it){target="_blank"}.

* **Servizio Amazon Simple Storage (S3)** - Il connettore **AWS S3** può essere utilizzato per importare o esportare dati in Adobe Campaign utilizzando un&#39;attività del flusso di lavoro **[!UICONTROL Transfer file]**. Quando imposti questo nuovo account esterno, dovrai fornire i seguenti dettagli:

   * **[!UICONTROL AWS S3 Account Server]**: URL del server, nel formato `<S3bucket name>.s3.amazonaws.com/<s3object path>`.

   * **[!UICONTROL AWS access key ID]**: scopri come trovare il tuo ID chiave di accesso AWS nella [documentazione di Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

   * **[!UICONTROL Secret access key to AWS]**: scopri come trovare la tua chiave di accesso segreta ad AWS nella [documentazione di Amazon](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}.

   * **[!UICONTROL AWS Region]**: ulteriori informazioni sulle aree geografiche di AWS sono disponibili nella [documentazione di Amazon](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}.

   * La casella di controllo **[!UICONTROL Use server side encryption]** consente di archiviare il file in modalità crittografata S3. Scopri come trovare l&#39;ID della chiave di accesso e la chiave di accesso segreta nella [documentazione di Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

* **Archiviazione BLOB di Azure** - L&#39;account esterno **Azure** può essere utilizzato per importare o esportare dati in Adobe Campaign utilizzando un&#39;attività del flusso di lavoro **[!UICONTROL Transfer file]**. Per configurare l&#39;account esterno **Azure** per l&#39;utilizzo con Adobe Campaign, è necessario fornire i dettagli seguenti:

   * **[!UICONTROL Server]**: URL del server di archiviazione BLOB di Azure.

   * **[!UICONTROL Encryption]**: tipo di crittografia: **[!UICONTROL None]** o **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: scopri come trovare **[!UICONTROL Access key]** nella [documentazione di Microsoft](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}.

* **Microsoft Fabric** - L&#39;account esterno **Microsoft Fabric** consente di importare ed esportare dati tra Microsoft Fabric e Adobe Campaign utilizzando l&#39;attività del flusso di lavoro **[!UICONTROL Transfer file]**. Per configurare questa integrazione, fornisci i seguenti dettagli:

   * **[!UICONTROL Server]**: URL del server di archiviazione Microsoft Fabric.

   * **[!UICONTROL Application ID]**: identificatore univoco dell&#39;applicazione utilizzata per l&#39;autenticazione e l&#39;accesso alle risorse di Microsoft Fabric.

   * **[!UICONTROL Client secret]**: la chiave o la password di autenticazione associata all&#39;applicazione, necessaria per connettersi in modo sicuro a Microsoft Fabric.
