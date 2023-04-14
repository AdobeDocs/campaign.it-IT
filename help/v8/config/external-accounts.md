---
title: Account esterni per Campaign
description: Account esterni per Campaign
feature: Application Settings
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 2d10a8f4349b9e2405847fc6a3db1ed568c60387
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 5%

---

# Configurare gli account esterni

Adobe Campaign è dotato di un set di account esterni predefiniti. Per impostare connessioni con sistemi esterni, puoi creare nuovi account esterni.

Gli account esterni sono utilizzati da processi tecnici quali flussi di lavoro tecnici o flussi di lavoro per campagne. Ad esempio, quando imposti un trasferimento di file in un flusso di lavoro o uno scambio di dati con un’altra applicazione (Adobe Target, Experience Manager, ecc.), devi selezionare un account esterno.

Puoi accedere agli account esterni da Adobe Campaign **[!UICONTROL Explorer]**: naviga a **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>* In qualità di utente di Cloud Services gestiti, gli account esterni sono configurati per la tua istanza per Adobe e non devono essere modificati.

>
>* >Nel contesto di un [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), un **[!UICONTROL Full FDA]** (ffda) l’account esterno gestisce la connessione tra il database locale di Campaign e il database Cloud ([!DNL Snowflake]).
>


## Account esterni specifici per la campagna

I seguenti account tecnici vengono utilizzati da Adobe Campaign per abilitare ed eseguire processi specifici.

![](../assets/do-not-localize/speech.png)  In qualità di utente di Cloud Services gestiti, ad Adobe, configura per te tutti gli account esterni specifici di Campaign.

### Messaggi non recapitati {#bounce-mails-external-account}

>[!NOTE]
L’autenticazione di Microsoft Exchange Online OAuth 2.0 per la funzionalità POP3 è disponibile a partire da Campaign v8.3. Per verificare la versione, fai riferimento a [questa sezione](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

La **Messaggi non recapitati** account esterno specifica l’account POP3 esterno da utilizzare per connettersi al servizio e-mail. Tutti i server configurati per l&#39;accesso POP3 possono essere utilizzati per ricevere la posta di ritorno.

Ulteriori informazioni sulle e-mail in entrata in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html)

![](assets/bounce_external_1.png)

Per configurare le **[!UICONTROL Bounce mails (defaultPopAccount)]** account esterno:

* **[!UICONTROL Server]**

   URL del server POP3.

* **[!UICONTROL Port]**

   Numero della porta di connessione POP3. La porta predefinita è 110.

* **[!UICONTROL Account]**

   Nome dell&#39;utente.

* **[!UICONTROL Password]**

   Password dell&#39;account utente.

* **[!UICONTROL Encryption]**

   Tipo di crittografia scelto tra **[!UICONTROL By default]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** o **[!UICONTROL POP3S]**.
La **Messaggi non recapitati** account esterno specifica l’account POP3 esterno da utilizzare per connettersi al servizio e-mail. Tutti i server configurati per l&#39;accesso POP3 possono essere utilizzati per ricevere la posta di ritorno.

* **[!UICONTROL Function]**

   Router e-mail o SOAP in entrata

![](assets/bounce_external_2.png)

>[!IMPORTANT]
Prima di configurare l’account esterno POP3 utilizzando Microsoft OAuth 2.0, è necessario registrare l’applicazione nel portale di Azure. Per ulteriori informazioni, consulta questa [pagina](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

Per configurare un POP3 esterno utilizzando Microsoft OAuth 2.0, controlla il **[!UICONTROL Microsoft OAuth 2.0]** e compila i campi seguenti:

* **[!UICONTROL Azure tenant]**

   L&#39;ID di Azure (o ID di directory (tenant)) si trova nella **Elementi essenziali** panoramica dell’applicazione nel portale di Azure.

* **[!UICONTROL Azure Client ID]**

   L&#39;ID client (o l&#39;ID applicazione (client)) si trova nella **Elementi essenziali** panoramica dell’applicazione nel portale di Azure.

* **[!UICONTROL Azure Client secret]**:

   L&#39;ID segreto client si trova nella **Segmenti client** dalla colonna **Certificati e segreti** menu dell’applicazione nel portale di Azure.

* **[!UICONTROL Azure Redirect URL]**:

   L’URL di reindirizzamento si trova nella sezione **Autenticazione** menu dell’applicazione nel portale di Azure. Deve terminare con la seguente sintassi `nl/jsp/oauth.jsp`ad esempio `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

Dopo aver immesso le diverse credenziali, puoi fare clic su **[!UICONTROL Setup the connection]** per completare la configurazione dell’account esterno.

### Indirizzamento {#routing}

La **[!UICONTROL Routing]** l’account esterno ti consente di configurare ogni canale disponibile in Adobe Campaign in base ai pacchetti installati.

>[!CAUTION]
La **[!UICONTROL Internal email delivery routing]** Account esterno (defaultEmailBulk) **non deve** in Adobe Campaign v8.

### Istanza di esecuzione {#execution-instance}

Nel contesto della messaggistica transazionale, le istanze di esecuzione sono collegate all’istanza di controllo e le collegano. I modelli di messaggi transazionali vengono distribuiti nell’istanza di esecuzione.

![](../assets/do-not-localize/glass.png) Ulteriori informazioni sull&#39;architettura del Centro messaggi in [questa pagina](../architecture/architecture.md#transac-msg-archi).

## Accesso agli account esterni dei sistemi esterni

* **Database esterno (FDA)** - **Database esterno** Il tipo di account esterno viene utilizzato per connettersi a un database esterno tramite Federated Data Access (FDA). Ulteriori informazioni sull’opzione Federated Data Access (FDA) in [questa sezione](../connect/fda.md).

   I database esterni compatibili con Adobe Campaign v8 sono elencati nel [Matrice di compatibilità](../start/compatibility-matrix.md)

* **Twitter** - **Twitter** Il tipo di account esterno viene utilizzato per collegare Campaign al tuo account twitter e per inviare messaggi per tuo conto. Ulteriori informazioni sull’integrazione di Twitter in [questa sezione](../connect/ac-tw.md).

## Account esterni per l’integrazione di soluzioni Adobe

* **Adobe Experience Cloud** - **[!UICONTROL Adobe Experience Cloud]** l’account esterno viene utilizzato per implementare Adobe Identity Management Service (IMS) per connettersi ad Adobe Campaign. Ulteriori informazioni su Adobe Identity Management Service (IMS) in [questa sezione](../start/connect.md#connect-ims).

* **Analisi web** - **[!UICONTROL Web Analytics (Adobe Analytics)]** l’account esterno viene utilizzato per configurare il trasferimento di dati da Adobe Analytics ad Adobe Campaign. Ulteriori informazioni sull’integrazione Adobe Campaign - Adobe Analytics in [questa pagina](../connect/ac-aa.md).

* **Adobe Experience Manager** - **[!UICONTROL AEM]** l’account esterno ti consente di gestire il contenuto delle consegne e-mail e dei moduli direttamente in Adobe Experience Manager. Ulteriori informazioni sull’integrazione Adobe Campaign - Adobe Analytics in [questa pagina](../connect/ac-aem.md).


## Account esterni del connettore di gestione delle relazioni con i clienti

* **Microsoft Dynamics CRM** - **[!UICONTROL Microsoft Dynamics CRM]** l’account esterno ti consente di importare ed esportare dati di Microsoft Dynamics in Adobe Campaign. Ulteriori informazioni sull’integrazione di Adobe Campaign - Microsoft Dynamics CRM in [questa pagina](../connect/ac-ms-dyn.md).

* **Salesforce.com** - **[!UICONTROL Salesforce CRM]** l’account esterno ti consente di importare ed esportare dati Salesforce in Adobe Campaign. Ulteriori informazioni sull&#39;integrazione di Adobe Campaign - Salesforce.com CRM in [questa pagina](../connect/ac-sfdc.md).

## Trasferisci account esterni dati

Questi account esterni possono essere utilizzati per importare o esportare dati in Adobe Campaign utilizzando un **[!UICONTROL Transfer file]** attività del flusso di lavoro. Ulteriori informazioni sul trasferimento di file nei flussi di lavoro in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html)

* **FTP e SFTP**

   La **FTP** l’account esterno ti consente di configurare e testare l’accesso a un server al di fuori di Adobe Campaign. Per impostare connessioni con sistemi esterni come server SFTP o FTP 898 utilizzati per i trasferimenti di file, puoi creare account esterni.
Per farlo, specifica in questo account esterno l’indirizzo e le credenziali utilizzati per stabilire la connessione al server SFTP o FTP.

* **Servizio di archiviazione semplice Amazon (S3)**

   La **AWS S3** può essere utilizzato per importare o esportare dati in Adobe Campaign utilizzando un **[!UICONTROL Transfer file]** attività del flusso di lavoro. Quando imposti questo nuovo account esterno, dovrai fornire i seguenti dettagli:

   * **[!UICONTROL AWS S3 Account Server]**: URL del server, compilato come segue:   ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL AWS access key ID]**: Scopri come trovare il tuo ID chiave di accesso AWS in [Documentazione di Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

   * **[!UICONTROL Secret access key to AWS]**: Scopri come trovare la chiave di accesso segreta in AWS in [Documentazione di Amazon](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}.

   * **[!UICONTROL AWS Region]**: Ulteriori informazioni sulle aree geografiche di AWS in [Documentazione di Amazon](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}.

   * La **[!UICONTROL Use server side encryption]** casella di controllo consente di memorizzare il file in modalità crittografata S3. Scopri come trovare l’ID chiave di accesso e la chiave di accesso segreto in [Documentazione di Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

* **Archiviazione BLOB di Azure**

   La **Azure** l’account esterno può essere utilizzato per importare o esportare dati in Adobe Campaign utilizzando un **[!UICONTROL Transfer file]** attività del flusso di lavoro. Per configurare le **Azure** per lavorare con Adobe Campaign, devi fornire i seguenti dettagli:

   * **[!UICONTROL Server]**: URL del server di archiviazione BLOB di Azure.

   * **[!UICONTROL Encryption]**: Tipo di cifratura tra **[!UICONTROL None]** o **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: Scopri come trovare il tuo **[!UICONTROL Access key]** in [Documentazione di Microsoft](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}.
