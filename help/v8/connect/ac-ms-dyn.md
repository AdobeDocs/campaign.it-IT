---
title: Utilizzare Campaign e Microsoft Dynamics
description: Scopri come utilizzare Campaign e Microsoft Dynamics
feature: Microsoft CRM Integration
role: Admin, User
level: Beginner, Intermediate
exl-id: 4f9e8f74-27dc-482c-a83c-25623b53560f
source-git-commit: d80a39d7f0df939d0e9e3f782d5d9aef3d459a32
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 2%

---

# Utilizzare Campaign e Microsoft Dynamics 365{#crm-ms-dynamics}

Attiva i dati CRM sulla comunicazione cross-channel: scopri come trasferire i contatti da **Microsoft Dynamics 365** ad Adobe Campaign e condividere i dati sulle prestazioni della campagna (invii, aperture, clic e mancati recapiti) da Adobe Campaign a Microsoft Dynamics 365.

Al termine della configurazione, la sincronizzazione dei dati tra sistemi viene eseguita tramite un’attività del flusso di lavoro dedicata. [Ulteriori informazioni](crm-data-sync.md).

>[!NOTE]
>
>Le versioni di Microsoft Dynamics supportate sono descritte in dettaglio nella [Matrice di compatibilità](../start/compatibility-matrix.md) di Campaign.

Segui i passaggi seguenti per configurare un account esterno dedicato per importare ed esportare dati Microsoft Dynamics 365 in Adobe Campaign.

Per ogni sistema, questi passaggi devono essere eseguiti da un amministratore.

>[!CAUTION]
> I passaggi descritti in questa documentazione ti guideranno attraverso la creazione di integrazioni/registrazioni che richiedono l’assegnazione di autorizzazioni e/o l’accesso come amministratore. È tua responsabilità accertarti che questi passaggi siano conformi alle politiche aziendali prima di eseguire e di eseguirli con attenzione.

## Configurare Microsoft Dynamics 365 {#config-crm-microsoft}

Per connettere Microsoft Dynamics 365 per l&#39;utilizzo con Adobe Campaign tramite **API Web**, accedere alla [directory di Microsoft Azure](https://portal.azure.com) utilizzando una credenziale **Global administrator**, quindi eseguire la procedura seguente:

1. Ottieni l’ID dell’applicazione (client) Dynamics 365. [Ulteriori informazioni](#get-client-id-microsoft)
1. Genera l’identificatore e l’ID della chiave del certificato di Microsoft Dynamics. [Ulteriori informazioni](#config-certificate-key-id)
1. Configurare le autorizzazioni. [Ulteriori informazioni](#config-permissions-microsoft)
1. Crea un utente dell’app. [Ulteriori informazioni](#create-app-user-microsoft)
1. Codifica la chiave privata. [Ulteriori informazioni](#configure-acc-for-microsoftt)


### Ottieni ID client Dynamics 365 {#get-client-id-microsoft}

Per ottenere l&#39;ID applicazione (client), è necessario registrare un&#39;app in Azure Active Directory.

1. Selezionare **Azure Active Directory > Registrazioni app** e selezionare **Nuova registrazione**.
1. Immettere un nome univoco che consenta di identificare un&#39;istanza, ad esempio **adobecampaign`<instance identifier>`**.

Dopo il salvataggio, la directory di Microsoft Azure assegna un ID **applicazione (client) univoco** all&#39;app. Questo ID sarà necessario successivamente per configurare Dynamics 365 in Adobe Campaign.

Ulteriori informazioni sono disponibili nella [documentazione di Microsoft Dynamics 365](https://docs.microsoft.com/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory){target="_blank"}.

### Genera ID chiave e identificatore chiave del certificato di Microsoft Dynamics {#config-certificate-key-id}

Per ottenere l&#39;**identificatore chiave del certificato (customKeyIdentifier)** e l&#39;**ID chiave (keyId)**, è necessario caricare un certificato. I certificati possono essere utilizzati come segreti per dimostrare l’identità dell’applicazione al momento della richiesta di un token. Possono anche essere denominate chiavi pubbliche.

Segui i passaggi seguenti:

1. Selezionare **Azure Active Directory > Registrazioni app** e quindi l&#39;applicazione creata in precedenza.
1. Seleziona **Certificati e segreto**.
1. Dalla scheda **Certificati**, fai clic su **Carica certificato**
1. Carica il certificato pubblico.
1. Passare al collegamento **Manifesto** per ottenere l&#39;**identificatore chiave del certificato (customKeyIdentifier)** e l&#39;**ID chiave (keyId)**.

L&#39;identificatore della chiave del certificato **(customKeyIdentifier)** e l&#39;ID della chiave **(keyId)** sono necessari in Campaign per configurare l&#39;account esterno di Microsoft Dynamics 365 CRM utilizzando il certificato **[!UICONTROL CRM O-Auth type]**.

+++ Come generare il certificato pubblico

Per generare il certificato, puoi utilizzare openssl.

Ad esempio:

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>È possibile modificare il numero di giorni, qui `-days 365`, nell&#39;esempio di codice per un periodo di validità del certificato più lungo.

È quindi necessario codificare il certificato in base64. A tale scopo, è possibile utilizzare l&#39;aiuto di un codificatore Base64 o la riga di comando `base64 -w0 private.key` per Linux.

+++

### Configurare le autorizzazioni {#config-permissions-microsoft}

**Passaggio 1**: configurare le **autorizzazioni richieste** per l&#39;app creata.

1. Passare a **Azure Active Directory > Registrazioni app** e selezionare l&#39;applicazione creata in precedenza.
1. Fai clic su **Impostazioni** in alto a sinistra.
1. In **Autorizzazioni richieste**, fare clic su **Aggiungi** e **Seleziona un&#39;API > Dynamics CRM Online**.
1. Fai clic su **Seleziona**, abilita **Access Dynamics 365 come utenti dell&#39;organizzazione**, seleziona la casella di controllo e fai clic su **Seleziona**.
1. Quindi, dall&#39;app, seleziona **Manifesto** nel menu **Gestisci**.
1. Dall&#39;editor **Manifest**, impostare la proprietà `allowPublicClient` da `null` a `true` e fare clic su **Salva**.

**Passaggio 2**: concedere il consenso dell&#39;amministratore

1. Passare a **Azure Active Directory > Applicazioni aziendali**.
1. Seleziona l’applicazione a cui desideri concedere il consenso dell’amministratore a livello di tenant.
1. Dal menu del riquadro a sinistra, selezionare **Autorizzazioni** in **Sicurezza**.
1. Fai clic su **Concedi il consenso dell&#39;amministratore**.

Per ulteriori informazioni, consulta [Documentazione di Azure](https://docs.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent#grant-admin-consent-from-the-azure-portal).

### Creare un utente dell’app {#create-app-user-microsoft}

>[!NOTE]
>
> Questo passaggio è facoltativo con autenticazione **[!UICONTROL Password credentials]**.

L’utente dell’app è l’utente che verrà utilizzato dall’applicazione registrata in precedenza. Eventuali modifiche apportate a Microsoft Dynamics utilizzando l’app registrata in precedenza verranno eseguite tramite questo utente.

**Passaggio 1**: creare un utente non interattivo in Azure Active Directory

1. Fare clic su **Azure Active Directory > Utenti** e quindi su **Nuovo utente**.
1. Assegna un nome appropriato che desideri utilizzare e il nome utente deve essere in formato e-mail.
1. Scegliere **Amministratore Dynamics 365** in **Ruolo directory**.

**Passaggio 2**: assegna una licenza corretta all&#39;utente creato

1. Da [Microsoft Azure](https://portal.azure.com), fare clic su **App amministratore**.
1. Vai a **Utenti > Utenti attivi** e fai clic sull&#39;utente appena creato.
1. Fai clic su **Modifica licenze prodotto** e seleziona il **Piano di coinvolgimento del cliente Dynamics 365**.
1. Fai clic su **Chiudi**.

**Passaggio 3**: creare un utente dell&#39;applicazione in Dynamics CRM

1. Da [Microsoft Azure](https://portal.azure.com), passare a **Impostazioni > Protezione > Utenti**.
1. Fare clic sull&#39;elenco a discesa, selezionare **Utenti applicazioni** e fare clic su **Nuovo**.
1. Utilizzare lo stesso nome utente creato in Active Directory.
1. Assegna **ID applicazione** per [l&#39;applicazione creata in precedenza](#get-client-id-microsoft).
1. Fai clic su **Gestisci ruoli** e scegli il ruolo **Amministratore di sistema** per l&#39;utente.

## Configurare Campaign {#configure-acc-for-microsoft}

### Creare la connessione{#new-ms-dyn-external-account}

Innanzitutto, devi creare l’account esterno Microsoft Dynamics 365.

1. Sfoglia il nodo **[!UICONTROL Administration > Platform > External accounts]** di Esplora campagne e crea un account esterno.
1. Selezionare l&#39;account esterno **[!UICONTROL Microsoft Dynamics CRM]** nella sezione **Tipo**.
1. Selezionare il metodo di autenticazione nell&#39;elenco a discesa **[!UICONTROL CRM O-Auth type]**.

   ![](assets/ms-dyn-external-account.png)

   1. Per configurare l&#39;account esterno di Microsoft Dynamics CRM per la connessione ad Adobe Campaign con **credenziali password**, specificare i dettagli seguenti:

      * **Server**: URL del server Microsoft CRM. Per trovare l&#39;URL del server di Microsoft CRM, accedere all&#39;account di Microsoft Dynamics CRM, quindi fare clic su Dynamics 365 e selezionare l&#39;app. Puoi quindi trovare l’URL del server nella barra degli indirizzi del browser, ad esempio https://myserver.crm.dynamics.com/.
      * **Account**: account utilizzato per accedere a Microsoft CRM.
      * **Password**: account utilizzato per accedere a Microsoft CRM.
      * **Identificatore client**: ID applicazione (client) che è possibile trovare dal portale di gestione di Microsoft Azure nel campo Aggiorna categoria codice, ID client.
      * **Versione CRM**: scegliere la versione CRM 365 di Dynamics CRM.

   1. Per configurare l&#39;account esterno di Microsoft Dynamics CRM per la connessione ad Adobe Campaign con un **certificato**, specificare i dettagli seguenti:

      * **Server**: URL del server Microsoft CRM. Per trovare l&#39;URL del server di Microsoft CRM, accedere all&#39;account di Microsoft Dynamics CRM, quindi fare clic su Dynamics 365 e selezionare l&#39;app. Puoi quindi trovare l’URL del server nella barra degli indirizzi del browser, ad esempio https://myserver.crm.dynamics.com/.
      * **Chiave privata**: copia/incolla la chiave privata, codificata base64 come spiegato in [questa sezione](#config-certificate-key-id).
      * **ID chiave**: chiave disponibile nella scheda **Manifesto** dell&#39;applicazione, come spiegato in [questa sezione](#config-certificate-key-id).
      * **Identificatore chiave personalizzato**: identificatore disponibile nella scheda **Manifesto** dell&#39;applicazione, come spiegato in [questa sezione](#config-certificate-key-id).
      * **Identificatore client**: ID dell&#39;applicazione (client) che è possibile trovare dal portale di gestione di Microsoft Azure come spiegato in [questa sezione](#get-client-id-microsoft).
      * **Versione CRM**: scegliere la versione CRM 365 di Dynamics CRM.

1. Seleziona l&#39;opzione **Abilita** per attivare l&#39;account in Campaign.

>[!NOTE]
>
>Per approvare la configurazione, disconnettiti e accedi di nuovo alla console client di Adobe Campaign.

### Seleziona tabelle da sincronizzare{#ms-dyn-create-tables}

È ora possibile configurare le tabelle da sincronizzare.

1. Fare clic su **[!UICONTROL Microsoft CRM configuration wizard...]**.
1. Selezionare le tabelle da sincronizzare e avviare il processo.
1. Controllare lo schema generato in Adobe Campaign nel nodo **[!UICONTROL Administration > Configuration > Data schemas]**.

>[!NOTE]
>
>Assicurarsi di aggiungere al elenco Consentiti di due URL: l&#39;URL del server e `login.microsoftonline.com`. Per eseguire l’operazione, contatta il rappresentante Adobe.

## Sincronizzare le enumerazioni{#sfdc-enum-sync}

Una volta creato lo schema, puoi sincronizzare automaticamente le enumerazioni da Dynamics 365 ad Adobe Campaign.

1. Apri l&#39;assistente dal collegamento **[!UICONTROL Synchronizing enumerations...]**.
1. Seleziona l’enumerazione Adobe Campaign che corrisponde all’enumerazione Dynamics 365.
È possibile sostituire tutti i valori di un&#39;enumerazione Adobe Campaign con quelli del CRM: a questo scopo, selezionare **[!UICONTROL Yes]** nella colonna **[!UICONTROL Replace]**.
1. Fare clic su **[!UICONTROL Next]** e quindi su **[!UICONTROL Start]** per avviare l&#39;importazione delle enumerazioni.
1. Sfoglia il nodo **[!UICONTROL Administration > Platform > Enumerations]** per controllare i valori importati.

Adobe Campaign e Microsoft Dynamics 365 sono ora connessi. È possibile impostare la sincronizzazione dei dati tra i due sistemi.

Per sincronizzare i dati tra i dati di Adobe Campaign e Microsoft CRM, creare un workflow e utilizzare l&#39;attività **[!UICONTROL CRM connector]**.

Ulteriori informazioni sulla sincronizzazione dei dati [sono disponibili in questa pagina](crm-data-sync.md).

### Tipi di dati dei campi supportati {#ms-dyn-supported-types}

Di seguito sono elencati i tipi di attributo supportati/non supportati da Microsoft Dynamics 365:


| Tipo di attributo | Supportato |
| --------------------------------------------------------------------------------- | --------- |
| Tipi di base: boolean, datetime, decimal, float, double, integer, bigint , string | Sì |
| Denaro (doppio) | Sì |
| memo, entityname , primarykey, uniqueidentifier (come stringhe) | Sì |
| Stato, elenco a discesa (i valori possibili vengono memorizzati nelle enumerazioni), stato (stringa) | Sì |
| proprietario (come stringa) | Sì |
| Ricerca (solo ricerche di riferimento a entità singola) | Sì |
| cliente | No |
| Riguardo | No |
| PartyList | No |
| ManagedProperty | No |
