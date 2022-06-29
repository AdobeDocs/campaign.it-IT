---
title: Utilizzare Campaign e Microsoft Dynamics
description: Scopri come utilizzare Campaign e Microsoft Dynamics
feature: Microsoft CRM Integration
role: Data Engineer
level: Beginner
exl-id: 4f9e8f74-27dc-482c-a83c-25623b53560f
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Utilizzo di Campaign e Microsoft Dynamics 365{#crm-ms-dynamics}

Attiva i dati CRM sulla comunicazione cross-channel: scopri come trasmettere i contatti da **Microsoft Dynamics 365** ad Adobe Campaign e condividi i dati sulle prestazioni delle campagne (invii, aperture, clic e mancati recapiti) da Adobe Campaign a Microsoft Dynamics 365.

Al termine della configurazione, la sincronizzazione dei dati tra i sistemi viene eseguita tramite un’attività di flusso di lavoro dedicata. [Ulteriori informazioni](crm-data-sync.md).

>[!NOTE]
>
>Le versioni supportate di Microsoft Dynamics sono descritte in dettaglio in Campaign [Matrice di compatibilità](../start/compatibility-matrix.md).

Per configurare un account esterno dedicato per l’importazione e l’esportazione di dati Microsoft Dynamics 365 in Adobe Campaign, effettua le seguenti operazioni.

Per ogni sistema, questi passaggi devono essere eseguiti da un amministratore.

>[!CAUTION]
> I passaggi di questa documentazione ti guideranno attraverso la creazione di integrazioni/registrazioni che richiedono l’assegnazione di autorizzazioni e/o l’accesso dell’amministratore. È tua responsabilità assicurarsi che questi passaggi siano conformi alle politiche aziendali prima di eseguire e eseguirli con attenzione.

## Configurare Microsoft Dynamics 365 {#config-crm-microsoft}

Per collegare Microsoft Dynamics 365 e lavorare con Adobe Campaign tramite **API web**, accedere a [Directory di Microsoft Azure](https://portal.azure.com) utilizzando **Amministratore globale** credenziale e segui i passaggi seguenti:

1. Ottieni l’ID dell’applicazione Dynamics 365 (client). [Ulteriori informazioni](#get-client-id-microsoft)
1. Genera l’identificatore della chiave del certificato Microsoft Dynamics e l’ID della chiave. [Ulteriori informazioni](#config-certificate-key-id)
1. Configura le autorizzazioni. [Ulteriori informazioni](#config-permissions-microsoft)
1. Crea un utente dell’app. [Ulteriori informazioni](#create-app-user-microsoft)
1. Codifica la chiave privata. [Ulteriori informazioni](#configure-acc-for-microsoftt)


### Ottieni ID client Dynamics 365 {#get-client-id-microsoft}

Per ottenere l’ID applicazione (client), è necessario registrare un’app in Azure Active Directory.

1. Sfoglia per **Azure Active Directory > Registrazioni app**, quindi seleziona **Nuova registrazione**.
1. Immettere un nome univoco che consenta di identificare un&#39;istanza, ad esempio **adobecamcampaign`<instance identifier>`**.

Dopo il salvataggio, la directory di Microsoft Azure assegna un univoco **ID applicazione (client)** all’app. Questo ID sarà necessario in seguito per configurare Dynamics 365 in Adobe Campaign.

Ulteriori informazioni in [Documentazione di Microsoft Dynamics 365](https://docs.microsoft.com/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory){target=&quot;_blank&quot;}.

### Genera l’identificatore della chiave di certificato e l’ID della chiave di Microsoft Dynamics {#config-certificate-key-id}

Per ottenere **Identificatore della chiave del certificato (customKeyIdentifier)** e **ID chiave (keyId)**, devi caricare un certificato. I certificati possono essere utilizzati come segreti per dimostrare l’identità dell’applicazione durante la richiesta di un token. Può anche essere indicato come chiave pubblica.

Segui i passaggi seguenti:

1. Sfoglia per **Azure Active Directory > Registrazioni app** e selezionare l&#39;applicazione creata in precedenza.
1. Seleziona su **Certificati e segreti**.
1. Da **Certificati** scheda , fai clic su **Carica certificato**
1. Carica il certificato pubblico.
1. Sfoglia il **Manifesto** collegamento per ottenere **Identificatore della chiave del certificato (customKeyIdentifier)** e **ID chiave (keyId)**.

La **Identificatore della chiave del certificato (customKeyIdentifier)** e **ID chiave (keyId)** sono necessarie in Campaign per configurare l’account esterno di gestione delle relazioni con i clienti Microsoft Dynamics 365 utilizzando il certificato **[!UICONTROL CRM O-Auth type]**.

+++ Come generare il certificato pubblico

Per generare il certificato, puoi utilizzare openssl.

Ad esempio:

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>È possibile modificare il numero di giorni, qui `-days 365`, nell’esempio di codice per un periodo di validità del certificato più lungo.

Devi quindi codificare il certificato in base64. Per farlo, puoi utilizzare l&#39;aiuto di un encoder Base64 o la riga di comando `base64 -w0 private.key` per Linux.

+++

### Configurare le autorizzazioni {#config-permissions-microsoft}

**Passaggio 1**: Configura le **Autorizzazioni necessarie** per l’app creata.

1. Passa a **Azure Active Directory > Registrazioni app** e selezionare l&#39;applicazione creata in precedenza.
1. Fai clic su **Impostazioni** in alto a sinistra.
1. On **Autorizzazioni necessarie**, fai clic su **Aggiungi** e **Seleziona un’API > Dynamics CRM Online**.
1. Fai clic su **Seleziona**, abilita **Accesso a Dynamics 365 come utenti dell’organizzazione** seleziona e fai clic su **Seleziona**.
1. Quindi, dall’app, seleziona la **Manifesto** in **Gestisci** menu.
1. Da **Manifesto** editor, imposta `allowPublicClient` proprietà da `null` a `true` e fai clic su **Salva**.

**Passaggio 2**: Concedere il consenso dell’amministratore

1. Passa a **Azure Active Directory > Applicazioni Enterprise**.
1. Seleziona l’applicazione a cui desideri concedere il consenso dell’amministratore a livello di tenant.
1. Dal menu del riquadro a sinistra, seleziona **Autorizzazioni** sotto **Sicurezza**.
1. Fai clic su **Concedere il consenso dell’amministratore**.

Per ulteriori informazioni, consulta [Documentazione di Azure](https://docs.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent#grant-admin-consent-from-the-azure-portal).

### Creare un utente di app {#create-app-user-microsoft}

>[!NOTE]
>
> Questo passaggio è facoltativo con **[!UICONTROL Password credentials]** autenticazione.

L&#39;utente dell&#39;app è l&#39;utente che verrà utilizzato dall&#39;applicazione registrata in precedenza. Tutte le modifiche apportate a Microsoft Dynamics utilizzando l’app registrata sopra verranno effettuate tramite questo utente.

**Passaggio 1**: Crea un utente non interattivo nella directory attiva azure

1. Fai clic su **Azure Active Directory > Utenti** e fai clic su **Nuovo utente**.
1. Assegna un nome appropriato da utilizzare e il nome utente deve essere un formato e-mail.
1. Scegli **Amministratore di Dynamics 365** in **Ruolo directory**.

**Passaggio 2**: Assegnare una licenza corretta all&#39;utente creato

1. Da [Microsoft Azure](https://portal.azure.com), fai clic su **App amministratore**.
1. Vai a **Utenti > Utenti attivi** e fai clic sull’utente appena creato.
1. Fai clic su **Modifica licenze prodotto** e seleziona la **Piano di coinvolgimento dei clienti di Dynamics 365**.
1. Fai clic su **Chiudi**.

**Passaggio 3**: Creare un utente dell’applicazione in Dynamics CRM

1. Da [Microsoft Azure](https://portal.azure.com), passa a **Impostazioni > Sicurezza > Utenti**.
1. Fai clic sull’elenco a discesa, seleziona **Utenti applicazioni** e fai clic su **Nuovo**.
1. Utilizza lo stesso nome utente dell&#39;utente creato nella directory attiva qui sopra.
1. Assegna **ID applicazione** per [applicazione creata in precedenza](#get-client-id-microsoft).
1. Fai clic su **Gestisci ruoli** e scegli la **Amministratore di sistema** ruolo per l&#39;utente.

## Configurare Campaign {#configure-acc-for-microsoft}

### Creare la connessione{#new-ms-dyn-external-account}

Innanzitutto, devi creare l’account esterno Microsoft Dynamics 365.

1. Sfoglia il **[!UICONTROL Administration > Platform > External accounts]** nodo di Campaign explorer e crea un account esterno.
1. Seleziona **[!UICONTROL Microsoft Dynamics CRM]** account esterno nel **Tipo** sezione .
1. Seleziona il metodo di autenticazione nel **[!UICONTROL CRM O-Auth type]** elenco a discesa.

   ![](assets/ms-dyn-external-account.png)

   1. Per configurare l’account esterno di Microsoft Dynamics CRM per la connessione con Adobe Campaign **Credenziali password**, fornisce i seguenti dettagli:

      * **Server**: URL del server Microsoft CRM. Per trovare l’URL del server Microsoft CRM, accedi al tuo account Microsoft Dynamics CRM, quindi fai clic su Dynamics 365 e seleziona la tua app. Puoi quindi trovare l’URL del server nella barra degli indirizzi del browser, ad esempio https://myserver.crm.dynamics.com/.
      * **Account**: Account utilizzato per accedere a Microsoft CRM.
      * **Password**: Account utilizzato per accedere a Microsoft CRM.
      * **Identificatore client**: ID applicazione (client) che si trova dal portale di gestione di Microsoft Azure nel campo Aggiorna la categoria di codice , ID client .
      * **Versione CRM**: Scegli la versione CRM Dynamics CRM 365.
   1. Per configurare l’account esterno Microsoft Dynamics CRM per la connessione con Adobe Campaign con un **Certificato**, fornisce i seguenti dettagli:

      * **Server**: URL del server Microsoft CRM. Per trovare l’URL del server Microsoft CRM, accedi al tuo account Microsoft Dynamics CRM, quindi fai clic su Dynamics 365 e seleziona la tua app. Puoi quindi trovare l’URL del server nella barra degli indirizzi del browser, ad esempio https://myserver.crm.dynamics.com/.
      * **Chiave privata**: Copia/Incolla la chiave privata, codifica base64 come spiegato in [questa sezione](#config-certificate-key-id).
      * **ID chiave**: Chiave disponibile in **Manifesto** scheda dell&#39;applicazione, come spiegato in [questa sezione](#config-certificate-key-id).
      * **Identificatore chiave personalizzato**: Identificatore disponibile nel **Manifesto** scheda dell&#39;applicazione, come spiegato in [questa sezione](#config-certificate-key-id).
      * **Identificatore client**: ID applicazione (client) che si trova dal portale di gestione di Microsoft Azure come spiegato in [questa sezione](#get-client-id-microsoft).
      * **Versione CRM**: Scegli la versione CRM Dynamics CRM 365.


1. Seleziona la **Abilita** per attivare l’account in Campaign.

>[!NOTE]
>
>Per approvare la configurazione, disconnettiti e accedi nuovamente alla console Adobe Campaign.

### Selezionare le tabelle da sincronizzare{#ms-dyn-create-tables}

È ora possibile configurare le tabelle da sincronizzare.

1. Fai clic sul pulsante **[!UICONTROL Microsoft CRM configuration wizard...]**.
1. Selezionare le tabelle da sincronizzare e avviare il processo.
1. Controlla lo schema generato in Adobe Campaign nel **[!UICONTROL Administration > Configuration > Data schemas]** nodo.

>[!NOTE]
>
>Assicurati di aggiungere all’inserire nell&#39;elenco Consentiti due URL: l&#39;URL del server e `login.microsoftonline.com`. Per eseguire questa operazione, contatta il tuo rappresentante Adobe.

## Sincronizza enumerazioni{#sfdc-enum-sync}

Una volta creato lo schema, puoi sincronizzare automaticamente le enumerazioni da Dynamics 365 ad Adobe Campaign.

1. Apri l&#39;assistente dal  **[!UICONTROL Synchronizing enumerations...]** link.
1. Seleziona l’enumerazione Adobe Campaign che corrisponde all’enumerazione Dynamics 365.
Puoi sostituire tutti i valori di un&#39;enumerazione Adobe Campaign con quelli del CRM: a questo scopo, seleziona **[!UICONTROL Yes]** in **[!UICONTROL Replace]** colonna.
1. Fai clic su **[!UICONTROL Next]** e poi **[!UICONTROL Start]** per iniziare a importare le enumerazioni.
1. Sfoglia il **[!UICONTROL Administration > Platform > Enumerations]** nodo per controllare i valori importati.

Adobe Campaign e Microsoft Dynamics 365 sono ora connessi. È possibile impostare la sincronizzazione dei dati tra i due sistemi.

Per sincronizzare i dati tra i dati di Adobe Campaign e Microsoft CRM, crea un flusso di lavoro e utilizza il **[!UICONTROL CRM connector]** attività.

Ulteriori informazioni sulla sincronizzazione dei dati [in questa pagina](crm-data-sync.md).

### Tipi di dati campo supportati {#ms-dyn-supported-types}

Per i tipi di attributi supportati o non supportati da Microsoft Dynamics 365, consulta l’elenco seguente:


| Tipo di attributo | Supportato |
| --------------------------------------------------------------------------------- | --------- |
| Tipi di base : booleano, datetime, decimal, float, double, integer, bigint, string | Sì |
| Denaro (come doppio) | Sì |
| promemoria, entity yname , primarykey, uniqueidentifier (come stringhe) | Sì |
| Stato, elenco a discesa (memorizziamo i valori possibili nelle enumerazioni), stato (stringa) | Sì |
| proprietario (come stringa) | Sì |
| Ricerca (solo ricerche di riferimento a entità singola) | Sì |
| cliente | No |
| Riguardo | No |
| PartyList | No |
| ManagedProperty | No |
