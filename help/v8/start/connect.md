---
title: Connettersi a Campaign v8
description: Scopri come connetterti ad Adobe Campaign v8 e installare la console sul computer per un accesso più semplice.
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 3%

---

# Connettersi ad Adobe Campaign v8{#gs-ac-connect}

Per iniziare a utilizzare Campaign, devi installare e configurare la console client.

Client Console è un’applicazione nativa che comunica con il server applicazioni Adobe Campaign tramite protocolli Internet standard, come SOAP e HTTP. La console client di Campaign centralizza tutte le funzionalità e le impostazioni e richiede una larghezza di banda minima in quanto si basa su una cache locale. Progettata per una facile distribuzione, la console client di Campaign può essere distribuita da un browser Internet, aggiornata automaticamente e non richiede alcuna configurazione di rete specifica in quanto genera solo traffico HTTP(S).

Prima di iniziare, è necessario:

* Verifica la compatibilità del sistema e degli strumenti con Adobe Campaign nella [Matrice di compatibilità](compatibility-matrix.md)
* Ottenere l’URL del server Campaign
* Crea il tuo Adobe ID o ottieni le credenziali utente dalla tua azienda
* Installare Microsoft Edge Webview2 Runtime sul sistema. [Ulteriori informazioni](#webview)

## Installare la console client{#download-ac-console}

### Microsoft Edge WebView2 Runtime {#webview}

A partire dalla versione della build Campaign Classic 8.4, l’installazione di Microsoft Edge Webview 2 Runtime è necessaria per qualsiasi installazione della console client.

La visualizzazione Web è installata per impostazione predefinita come parte del sistema operativo Windows 11. Se non è già presente nel sistema, il programma di installazione della console client di Campaign ti chiederà di scaricarla da [Sito Web Microsoft Developer](http://www.adobe.com/go/acc-ms-webview2-runtime-download_it){target="_blank"}. Il collegamento di download non funziona nel browser Internet Explorer 11 in quanto Microsoft ne ha dichiarato obsoleto il supporto. Utilizza un browser diverso per accedere al collegamento.

### Scarica la console{#install-ac-console}

Quando utilizzi Campaign per la prima volta, devi scaricare la console client e installarla.

Per scaricare Client Console sono disponibili due opzioni:

1. In qualità di amministratore di Campaign, accedi ad Adobe [Distribuzione di software](https://experience.adobe.com/#/downloads/content/software-distribution/it/campaign.html){target="_blank"}.

1. In qualità di utente finale, l’amministratore di Campaign implementa la console client e la rende disponibile tramite un URL dedicato.

Una volta scaricato il programma di installazione della console client, installarlo nel computer locale.

Una volta installata, non è possibile modificare la lingua della console client.

## Creare la connessione{#create-your-connection}

Dopo aver installato Client Console, attenersi alla procedura descritta di seguito per creare la connessione al server applicazioni:

1. Avvia la Console e sfoglia il collegamento nell’angolo a destra per accedere alla schermata di configurazione della connessione.

1. Clic **[!UICONTROL Add > Connection]** e immetti l’etichetta e l’URL del server applicazioni Adobe Campaign.

1. Specifica una connessione al server applicazioni Adobe Campaign tramite un URL. Utilizza un DNS o un alias del computer oppure il tuo indirizzo IP.

   Ad esempio, puoi utilizzare [`https://<machine>.<domain>.com`](https://myserver.adobe.com) digita URL.

1. Seleziona l’opzione **[!UICONTROL Connect with an Adobe ID]**.

1. Clic **[!UICONTROL Ok]** per salvare le impostazioni.

Puoi aggiungere tutte le connessioni necessarie per connettersi, ad esempio, agli ambienti di test, stage e produzione.

>[!NOTE]
>
>Il **[!UICONTROL Add]** consente di creare **[!UICONTROL folders]** per organizzare tutte le connessioni. È sufficiente trascinare ogni connessione in una cartella.

## Accedere ad Adobe Campaign {#logon-to-ac}

Gli utenti di Campaign si connettono alla console Adobe Campaign utilizzando il proprio Adobe ID, tramite Adobe Identity Management System (IMS). Possono utilizzare lo stesso ID per tutte le soluzioni di Adobe. La connessione viene salvata quando si utilizza Adobe Campaign con altre soluzioni. Ulteriori informazioni su Adobe IMS in [questa pagina](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"}.

Per accedere a un’istanza, effettua le seguenti operazioni:

1. Avvia la Console e sfoglia il collegamento nell’angolo a destra per accedere alla schermata di configurazione della connessione.

   ![](assets/connectToCampaign.png)

1. Seleziona l’istanza di Campaign a cui devi accedere.

1. Fai clic su **[!UICONTROL Ok]**.

Puoi quindi accedere a Campaign con il tuo Adobe ID.

![](assets/adobeID.png)

>[!NOTE]
>
>Poiché Microsoft Edge Webview2 non salva le credenziali proxy, la console potrebbe richiedere l&#39;autenticazione due volte alla prima connessione.

## Aggiornare la console client{#upgrade-ac-console}

Quando il sistema viene aggiornato a una versione più recente, è necessario aggiornare la console client alla stessa versione. Questa è una best practice e per alcune versioni questo aggiornamento è obbligatorio. In tal caso, è menzionato nella [Note sulla versione](release-notes.md).

In qualità di utente di Managed Cloud Service, Adobe distribuisce la Client Console al posto tuo. Quando ci si connette all’ambiente aggiornato, viene richiesto di scaricare l’ultima versione della console client in una finestra pop-up. Devi accettare questo aggiornamento e aggiornare la console client come richiesto.

>[!CAUTION]
>
>Adobe consiglia di lasciare l’opzione **[!UICONTROL No longer ask this question]** deselezionato per essere sicuri di ricevere un avviso quando è disponibile una nuova versione della console. Se questa opzione è selezionata, l’utente non viene informato che è necessario un aggiornamento della console.
>



## Concedere l’accesso agli utenti{#grant-access}

Adobe Campaign ti consente di definire e gestire i diritti assegnati ai vari operatori.

In qualità di amministratore di Campaign, sei responsabile della creazione degli operatori e della condivisione delle relative credenziali con gli utenti.

Ulteriori informazioni sugli utenti e su come definire le relative autorizzazioni in [questa sezione](gs-permissions.md).


## Accesso web{#web-access}

Alcune parti dell’applicazione sono accessibili tramite un browser web che utilizza un’interfaccia utente HTML: reporting, approvazione della consegna, monitoraggio delle istanze e altro ancora.

L’accesso web fornisce un’interfaccia simile alla console ma con un set ridotto di funzionalità.

Ad esempio, per un dato operatore, viene visualizzata una campagna con le seguenti opzioni nella console:

![](assets/campaign-from-console.png)

Con l’accesso web, invece, le opzioni consentono principalmente la visualizzazione di:

![](assets/campaign-from-web.png)

L’accesso web viene utilizzato anche per nel processo di convalida: gli operatori possono fare clic sull’e-mail della richiesta di approvazione e connettersi a Campaign tramite il proprio browser web per convalidare o rifiutare un contenuto o un budget di consegna.

Per accedere alla tua istanza di Campaign dal web, l’URL è:  `https://<your adobe campaign server>:<port number>/view/home`.
