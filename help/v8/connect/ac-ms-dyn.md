---
title: Utilizzare Campaign e Microsoft Dynamics
description: Scopri come utilizzare Campaign e Microsoft Dynamics
feature: Microsoft CRM Integration
role: Admin, User
level: Beginner, Intermediate, Experienced
exl-id: 4f9e8f74-27dc-482c-a83c-25623b53560f
source-git-commit: 290f4e9a0d13ef49caacb7a128ccc266bafd5e69
workflow-type: tm+mt
source-wordcount: '1365'
ht-degree: 3%

---

# Utilizzare Campaign e Microsoft Dynamics 365{#crm-ms-dynamics}

Attiva i dati CRM sulla comunicazione cross-channel: scopri come trasmettere i contatti da **Microsoft Dynamics 365** ad Adobe Campaign e condividere i dati sulle prestazioni della campagna (invii, aperture, clic e mancati recapiti) da Adobe Campaign a Microsoft Dynamics 365.

Al termine della configurazione, la sincronizzazione dei dati tra sistemi viene eseguita tramite un’attività del flusso di lavoro dedicata. [Ulteriori informazioni](crm-data-sync.md).

>[!NOTE]
>
>Le versioni supportate di Microsoft Dynamics sono descritte in dettaglio in Campaign [Matrice di compatibilità](../start/compatibility-matrix.md).

Segui i passaggi seguenti per configurare un account esterno dedicato per importare ed esportare dati di Microsoft Dynamics 365 in Adobe Campaign.

Per ogni sistema, questi passaggi devono essere eseguiti da un amministratore.

>[!CAUTION]
> I passaggi descritti in questa documentazione ti guideranno attraverso la creazione di integrazioni/registrazioni che richiedono l’assegnazione di autorizzazioni e/o accesso amministratore. È tua responsabilità accertarti che questi passaggi siano conformi alle politiche aziendali prima di eseguire e di eseguirli con attenzione.

## Configurare Microsoft Dynamics 365 {#config-crm-microsoft}

Per collegare Microsoft Dynamics 365 per lavorare con Adobe Campaign tramite **API web**, accedi a [Directory di Microsoft Azure](https://portal.azure.com) utilizzando un **Amministratore globale** e seguire i passaggi seguenti:

1. Ottieni l’ID dell’applicazione (client) Dynamics 365. [Ulteriori informazioni](#get-client-id-microsoft)
1. Genera l&#39;identificatore chiave del certificato e l&#39;ID chiave di Microsoft Dynamics. [Ulteriori informazioni](#config-certificate-key-id)
1. Configurare le autorizzazioni. [Ulteriori informazioni](#config-permissions-microsoft)
1. Crea un utente dell’app. [Ulteriori informazioni](#create-app-user-microsoft)
1. Codifica la chiave privata. [Ulteriori informazioni](#configure-acc-for-microsoftt)


### Ottieni ID client Dynamics 365 {#get-client-id-microsoft}

Per ottenere l&#39;ID applicazione (client), è necessario registrare un&#39;app in Azure Active Directory.

1. Sfoglia per **Azure Active Directory > Registrazioni app**, e seleziona **Nuova registrazione**.
1. Inserisci un nome univoco che possa aiutare a identificare un’istanza, ad esempio **adobecampaign`<instance identifier>`**.

Dopo il salvataggio, la directory di Microsoft Azure assegna un valore univoco **ID applicazione (client)** all&#39;app. Questo ID sarà necessario successivamente per configurare Dynamics 365 in Adobe Campaign.

Ulteriori informazioni in [Documentazione di Microsoft Dynamics 365](https://docs.microsoft.com/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory){target="_blank"}.

### Genera ID chiave e identificatore chiave del certificato di Microsoft Dynamics {#config-certificate-key-id}

Per ottenere **Identificatore chiave del certificato (customKeyIdentifier)** e **ID chiave (keyId)**, devi caricare un certificato. I certificati possono essere utilizzati come segreti per dimostrare l’identità dell’applicazione al momento della richiesta di un token. Possono anche essere denominate chiavi pubbliche.

Segui i passaggi seguenti:

1. Sfoglia per **Azure Active Directory > Registrazioni app** e selezionare l&#39;applicazione creata in precedenza.
1. Seleziona il **Certificati e segreto**.
1. Dalla sezione **Certificati** , fare clic su **Carica certificato**
1. Carica il certificato pubblico.
1. Accedi a **Manifesto** collegamento per ottenere **Identificatore chiave del certificato (customKeyIdentifier)** e **ID chiave (keyId)**.

Il **Identificatore chiave del certificato (customKeyIdentifier)** e **ID chiave (keyId)** sono necessarie in Campaign per configurare l’account esterno di gestione delle relazioni con i clienti di Microsoft Dynamics 365 tramite il certificato **[!UICONTROL CRM O-Auth type]**.

+++ Come generare il certificato pubblico

Per generare il certificato, puoi utilizzare openssl.

Ad esempio:

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>Puoi modificare il numero di giorni qui `-days 365`, nel codice di esempio per un periodo di validità del certificato più lungo.

È quindi necessario codificare il certificato in base64. A tale scopo, è possibile utilizzare l&#39;aiuto di un codificatore Base64 o la riga di comando `base64 -w0 private.key` per Linux.

+++

### Configurare le autorizzazioni {#config-permissions-microsoft}

**Passaggio 1**: configura il **Autorizzazioni richieste** per l’app creata.

1. Accedi a **Azure Active Directory > Registrazioni app** e selezionare l&#39;applicazione creata in precedenza.
1. Clic **Impostazioni** in alto a sinistra.
1. On **Autorizzazioni richieste**, fai clic su **Aggiungi** e **Seleziona un’API > Dynamics CRM Online**.
1. Clic **Seleziona**, abilita **Accedere a Dynamics 365 come utenti dell’organizzazione** e fai clic su **Seleziona**.
1. Quindi, dall’app, seleziona la **Manifesto** sotto **Gestisci** menu.
1. Dalla sezione **Manifesto** editor, imposta `allowPublicClient` proprietà da `null` a `true` e fai clic su **Salva**.

**Passaggio 2**: concedi il consenso all’amministratore

1. Accedi a **Azure Active Directory > Applicazioni aziendali**.
1. Seleziona l’applicazione a cui desideri concedere il consenso dell’amministratore a livello di tenant.
1. Dal menu del riquadro a sinistra, seleziona **Autorizzazioni** in **Sicurezza**.
1. Clic **Concedere il consenso dell’amministratore**.

Per ulteriori informazioni, consulta [Documentazione di Azure](https://docs.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent#grant-admin-consent-from-the-azure-portal).

### Creare un utente dell’app {#create-app-user-microsoft}

>[!NOTE]
>
> Questo passaggio è facoltativo con **[!UICONTROL Password credentials]** autenticazione.

L’utente dell’app è l’utente che verrà utilizzato dall’applicazione registrata in precedenza. Eventuali modifiche apportate a Microsoft Dynamics utilizzando l’app registrata in precedenza verranno eseguite tramite questo utente.

**Passaggio 1**: crea un utente non interattivo in Azure Active Directory

1. Clic **Azure Active Directory > Utenti** e fai clic su **Nuovo utente**.
1. Assegna un nome appropriato che desideri utilizzare e il nome utente deve essere in formato e-mail.
1. Scegli **Amministratore Dynamics 365** nel **Ruolo directory**.

**Passaggio 2**: assegna una licenza corretta all’utente creato

1. Da [Microsoft Azure](https://portal.azure.com), fai clic su **App di amministrazione**.
1. Vai a **Utenti > Utenti attivi** e fai clic sul nuovo utente creato.
1. Fai clic su **Modifica licenze prodotto** e seleziona la **Piano di coinvolgimento del cliente Dynamics 365**.
1. Fai clic su **Chiudi**.

**Passaggio 3**: crea un utente dell’applicazione in Dynamics CRM

1. Da [Microsoft Azure](https://portal.azure.com), passa a **Impostazioni > Protezione > Utenti**.
1. Fai clic sull’elenco a discesa, seleziona **Utenti dell’applicazione** e fai clic su **Nuovo**.
1. Utilizzare lo stesso nome utente creato in Active Directory.
1. Assegna la **ID applicazione** per [l&#39;applicazione creata in precedenza](#get-client-id-microsoft).
1. Fai clic su **Gestisci ruoli** e scegli la **Amministratore di sistema** ruolo all&#39;utente.

## Configurare Campaign {#configure-acc-for-microsoft}

### Creare la connessione{#new-ms-dyn-external-account}

Innanzitutto, devi creare l’account esterno di Microsoft Dynamics 365.

1. Sfoglia **[!UICONTROL Administration > Platform > External accounts]** dell’Explorer di Campaign e creare un account esterno.
1. Seleziona **[!UICONTROL Microsoft Dynamics CRM]** account esterno in **Tipo** sezione.
1. Selezionare il metodo di autenticazione in **[!UICONTROL CRM O-Auth type]** elenco a discesa.

   ![](assets/ms-dyn-external-account.png)

   1. Per configurare l&#39;account esterno di Microsoft Dynamics CRM per la connessione ad Adobe Campaign con **Credenziali password**, fornisci i seguenti dettagli:

      * **Server**: URL del server Microsoft CRM in uso. Per trovare l&#39;URL del server di Microsoft CRM, accedere all&#39;account di Microsoft Dynamics CRM, quindi fare clic su Dynamics 365 e selezionare l&#39;app. Puoi quindi trovare l’URL del server nella barra degli indirizzi del browser, ad esempio https://myserver.crm.dynamics.com/.
      * **Account**: account utilizzato per accedere a Microsoft CRM.
      * **Password**: account utilizzato per accedere a Microsoft CRM.
      * **Identificatore client**: ID dell’applicazione (client) accessibile dal portale di gestione di Microsoft Azure nel campo Aggiorna la categoria del codice, ID client.
      * **Versione CRM**: scegli la versione CRM di Dynamics CRM 365.
   1. Per configurare l&#39;account esterno di Microsoft Dynamics CRM per la connessione ad Adobe Campaign con un **Certificato**, fornisci i seguenti dettagli:

      * **Server**: URL del server Microsoft CRM in uso. Per trovare l&#39;URL del server di Microsoft CRM, accedere all&#39;account di Microsoft Dynamics CRM, quindi fare clic su Dynamics 365 e selezionare l&#39;app. Puoi quindi trovare l’URL del server nella barra degli indirizzi del browser, ad esempio https://myserver.crm.dynamics.com/.
      * **Chiave privata**: copia/incolla la chiave privata, codificata base64 come spiegato in [questa sezione](#config-certificate-key-id).
      * **ID chiave**: chiave disponibile nella **Manifesto** della tua applicazione, come spiegato in [questa sezione](#config-certificate-key-id).
      * **Identificatore chiave personalizzato**: identificatore disponibile nella **Manifesto** della tua applicazione, come spiegato in [questa sezione](#config-certificate-key-id).
      * **Identificatore client**: ID dell’applicazione (client) reperibile dal portale di gestione di Microsoft Azure come spiegato in [questa sezione](#get-client-id-microsoft).
      * **Versione CRM**: scegli la versione CRM di Dynamics CRM 365.


1. Seleziona la **Abilita** per attivare l’account in Campaign.

>[!NOTE]
>
>Per approvare la configurazione, disconnettiti e accedi di nuovo alla console client di Adobe Campaign.

### Seleziona tabelle da sincronizzare{#ms-dyn-create-tables}

È ora possibile configurare le tabelle da sincronizzare.

1. Fai clic su **[!UICONTROL Microsoft CRM configuration wizard...]**.
1. Selezionare le tabelle da sincronizzare e avviare il processo.
1. Controlla lo schema generato in Adobe Campaign nel **[!UICONTROL Administration > Configuration > Data schemas]** nodo.

>[!NOTE]
>
>Assicurati di aggiungere all’di inserire nell&#39;elenco Consentiti due URL: l’URL del server e `login.microsoftonline.com`. Per eseguire questa operazione, contatta il rappresentante del tuo Adobe.

## Sincronizzare le enumerazioni{#sfdc-enum-sync}

Una volta creato lo schema, puoi sincronizzare automaticamente le enumerazioni da Dynamics 365 ad Adobe Campaign.

1. Apri l’assistente da  **[!UICONTROL Synchronizing enumerations...]** collegamento.
1. Seleziona l’enumerazione Adobe Campaign che corrisponde all’enumerazione Dynamics 365.
Puoi sostituire tutti i valori di un’enumerazione Adobe Campaign con quelli del CRM: a questo scopo, seleziona **[!UICONTROL Yes]** nel **[!UICONTROL Replace]** colonna.
1. Clic **[!UICONTROL Next]** e poi **[!UICONTROL Start]** per avviare l&#39;importazione delle enumerazioni.
1. Sfoglia **[!UICONTROL Administration > Platform > Enumerations]** per controllare i valori importati.

Adobe Campaign e Microsoft Dynamics 365 sono ora connessi. È possibile impostare la sincronizzazione dei dati tra i due sistemi.

Per sincronizzare i dati tra i dati di Adobe Campaign e Microsoft CRM, crea un flusso di lavoro e utilizza **[!UICONTROL CRM connector]** attività.

Ulteriori informazioni sulla sincronizzazione dei dati [in questa pagina](crm-data-sync.md).

### Tipi di dati dei campi supportati {#ms-dyn-supported-types}

Di seguito sono elencati i tipi di attributo supportati/non supportati per Microsoft Dynamics 365:


| Tipo di attributo | Supportato |
| --------------------------------------------------------------------------------- | --------- |
| Tipi di base : boolean, datetime, decimal, float, double, integer, bigint , string | Sì |
| Denaro (doppio) | Sì |
| memo, entityname , primarykey, uniqueidentifier (come stringhe) | Sì |
| Stato, elenco a discesa (i valori possibili vengono memorizzati nelle enumerazioni), stato (stringa) | Sì |
| proprietario (come stringa) | Sì |
| Ricerca (solo ricerche di riferimento a entità singola) | Sì |
| cliente | No |
| Riguardo | No |
| PartyList | No |
| ManagedProperty | No |
