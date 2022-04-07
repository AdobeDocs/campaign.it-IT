---
title: Connetti a Campaign v8
description: Scopri come connettersi a Campaign v8
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: c3beb735f54606537bcc977f2f0539767d15b2d9
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 2%

---

# Connessione ad Adobe Campaign v8{#gs-ac-connect}

Campaign Client Console è un client avanzato che ti consente di connettersi ai server delle applicazioni Campaign.

Prima di iniziare, è necessario:

* Verifica la compatibilità di sistema e strumenti con Adobe Campaign nella [Matrice di compatibilità](compatibility-matrix.md)
* Ottieni l’URL del server Campaign
* Crea il tuo Adobe ID o ottieni le tue credenziali utente dalla tua azienda

## Scaricare e installare la console client{#download-ac-console}

Quando utilizzi Campaign per la prima volta o se hai bisogno di eseguire l’aggiornamento a una versione più recente, devi scaricare la console Client e installarla.

Sono disponibili due opzioni:

1. In qualità di amministratore di Campaign, collegati ad Adobe [Distribuzione di software](https://experience.adobe.com/#/downloads/content/software-distribution/it/campaign.html) e scaricare il programma di installazione della console client. È quindi possibile installarlo nel computer locale.

1. In qualità di utente finale, Adobe può distribuire la console per: una volta aggiornata la console, ti verrà richiesto di scaricare la versione più recente della console client in una finestra pop-up.

>[!CAUTION]
>
>L’Adobe consiglia di lasciare l’opzione **[!UICONTROL No longer ask this question]** deselezionata per fare in modo che tutti gli utenti ricevano avvisi quando è disponibile una nuova versione della console.  Se questa opzione è selezionata, l’utente non verrà informato delle nuove versioni disponibili.

## Creare la connessione{#create-your-connection}

Una volta che la Console client è stata appena installata, segui i passaggi seguenti per creare la connessione al server applicazioni:

1. Avvia la console da Windows **[!UICONTROL Start]** nel menu **Adobe Campaign** gruppo di programmi.

1. Fai clic sul collegamento nell’angolo in alto a destra dei campi delle credenziali per accedere alla finestra di configurazione della connessione.

1. Fai clic su **[!UICONTROL Add > Connection]** e immetti l’etichetta e l’URL dell’application server di Adobe Campaign.

1. Specifica una connessione al server dell’applicazione Adobe Campaign tramite un URL. Utilizzare un DNS o un alias del computer o l&#39;indirizzo IP.

   Ad esempio, puoi utilizzare il [`https://<machine>.<domain>.com`](https://myserver.adobe.com) digitare URL.

1. Controlla l’opzione **[!UICONTROL Connect with an Adobe ID]**.

1. Fai clic su **[!UICONTROL Ok]** per salvare le impostazioni.

Puoi aggiungere tutte le connessioni necessarie per connettersi, ad esempio, agli ambienti di test, stage e produzione.

>[!NOTE]
>
>La **[!UICONTROL Add]** pulsante consente di creare **[!UICONTROL folders]** per organizzare tutte le connessioni. Trascina e rilascia ciascuna connessione in una cartella.

## Accedere ad Adobe Campaign {#logon-to-ac}

Per accedere a un&#39;istanza esistente, segui i passaggi seguenti:

1. Avvia la console da Windows **[!UICONTROL Start]** nel menu **Adobe Campaign** gruppo di programmi.

1. Fai clic sul collegamento nell’angolo in alto a destra dei campi delle credenziali per accedere alla finestra di configurazione della connessione.

   ![](assets/connectToCampaign.png)

1. Seleziona l’istanza Campaign a cui devi accedere.

1. Fai clic su **[!UICONTROL Ok]**.

1. Puoi quindi accedere a Campaign con [il tuo Adobe ID](#connect-ims).

   ![](assets/adobeID.png)

## Concedere l’accesso agli utenti{#grant-access}

Adobe Campaign ti consente di definire e gestire i diritti assegnati ai vari operatori. Si tratta di una serie di diritti e restrizioni che autorizzano o negano:

* Accesso a determinate funzionalità (tramite i diritti denominati),
* Accesso a determinati elementi,
* Crea, modifica e/o elimina elementi (consegna, contatti, campagne, gruppi, ecc.).

Ulteriori informazioni sugli utenti e su come definirne le autorizzazioni in [questa sezione](permissions.md).

In qualità di amministratore di Campaign, sei responsabile della creazione degli operatori e della condivisione delle loro credenziali con gli utenti.

## Connettiti a Campaign con il tuo Adobe ID{#connect-ims}

Gli utenti di Campaign si collegano alla console Adobe Campaign utilizzando il proprio Adobe ID, tramite Adobe Identity Management System (IMS). Possono utilizzare lo stesso ID per tutte le soluzioni Adobe. La connessione viene salvata quando si utilizza Adobe Campaign con altre soluzioni.

Ulteriori informazioni su Adobe IMS in [questa pagina](https://helpx.adobe.com/enterprise/using/identity.html).

## Accesso web{#web-access}

È possibile accedere ad alcune parti dell’applicazione tramite un browser web utilizzando un’interfaccia utente di HTML: reporting, approvazione della consegna, monitoraggio delle istanze e altro ancora.

L’accesso Web fornisce un’interfaccia simile alla console ma con un set ridotto di funzionalità.

Ad esempio, per un determinato operatore, nella console verrà visualizzata una campagna con le seguenti opzioni:

![](assets/campaign-from-console.png)

Mentre con l&#39;accesso Web, le opzioni consentono principalmente la visualizzazione:

![](assets/campaign-from-web.png)

Nel processo di convalida viene utilizzato anche l’accesso Web: gli operatori possono fare clic sull’e-mail di richiesta di approvazione e connettersi a Campaign tramite il proprio browser web per convalidare o rifiutare un contenuto o un budget di consegna.

Per accedere all’istanza Campaign dal web, l’URL è:  `https://<your adobe campaign server>:<port number>/view/home`.
