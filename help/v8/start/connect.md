---
title: Connessione a Campaign v8
description: Scopri come connetterti ad Adobe Campaign v8 e installare la console sul computer per un accesso più semplice.
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 24ecf598d3d01f7fb59c70e1c8c81e9c086e653e
workflow-type: ht
source-wordcount: '1006'
ht-degree: 100%

---

# Connessione ad Adobe Campaign v8{#gs-ac-connect}

Per iniziare a utilizzare Campaign, devi installare e configurare la console client.

La console client è un’applicazione nativa che comunica con il server applicazioni di Adobe Campaign tramite protocolli Internet standard, quali SOAP e HTTP. La console client di Campaign centralizza tutte le funzionalità e le impostazioni e richiede una larghezza di banda minima in quanto si basa su una cache locale. Progettata per una semplice implementazione, la console client di Campaign può essere distribuita da un browser Internet, può essere aggiornata automaticamente e non richiede alcuna configurazione di rete specifica perché genera solo traffico HTTP(S).

Prima di iniziare, è necessario:

* Verificare la compatibilità del sistema e degli strumenti con Adobe Campaign nella [Matrice di compatibilità](compatibility-matrix.md)
* Ottenere l’URL del server di Campaign
* Creare il proprio Adobe ID o ottenere le credenziali utente dall’azienda
* Installare Microsoft Edge Webview2 Runtime sul sistema. [Ulteriori informazioni](#webview)

## Installare la console client{#download-ac-console}

### Microsoft Edge WebView2 Runtime {#webview}

A partire dalla versione della build di Campaign Classic 8.4, è necessaria l’installazione di Microsoft Edge Webview2 Runtime per qualsiasi installazione della console client.

WebView è installato per impostazione predefinita come parte del sistema operativo Windows 11. Se non è già presente nel sistema, il programma di installazione della console client di Campaign ti richiederà di scaricarla dal [sito web per sviluppatori Microsoft](http://www.adobe.com/go/acc-ms-webview2-runtime-download_it){target="_blank"}. Il collegamento di download non funziona nel browser Internet Explorer 11 in quanto Microsoft ne ha dichiarato obsoleto il supporto. Accertati di utilizzare un browser diverso per accedere al collegamento.

### Scaricare la console{#install-ac-console}

Quando utilizzi Campaign per la prima volta, devi scaricare la console client e installarla.

Per scaricare la console client sono disponibili due opzioni:

1. In qualità di amministratore di Campaign, connettiti alla [Distribuzione di software](https://experience.adobe.com/#/downloads/content/software-distribution/it/campaign.html){target="_blank"} di Adobe.

1. In qualità di utente finale, l’amministratore di Campaign implementa la console client e la rende disponibile tramite un URL dedicato.

Una volta scaricato il programma di installazione della console client, installalo sul computer locale.

Tieni presente che puoi modificare la lingua della console client dopo l’installazione.

## Creare la connessione{#create-your-connection}

Dopo aver installato la console client, segui i passaggi seguenti per creare la connessione al server applicazioni:

1. Avvia la console e sfoglia il collegamento nell’angolo a destra per accedere alla schermata di configurazione della connessione.

1. Fai clic su **[!UICONTROL Add > Connection]** e immetti l’etichetta e l’URL del server applicazioni di Adobe Campaign.

1. Specifica una connessione al server applicazioni di Adobe Campaign tramite un URL. Utilizza un DNS o un alias del computer oppure il tuo indirizzo IP.

   Ad esempio, puoi utilizzare l’URL di tipo `https://<machine>.<domain>.com`.

1. Seleziona l’opzione **[!UICONTROL Connect with an Adobe ID]**.

1. Fai clic su **[!UICONTROL Ok]** per salvare le impostazioni.

Puoi aggiungere tutte le connessioni necessarie per connetterti, ad esempio, agli ambienti di test, stage e produzione.

>[!NOTE]
>
>Il pulsante **[!UICONTROL Add]** consente di creare **[!UICONTROL folders]** per organizzare tutte le connessioni. È sufficiente trascinare ogni connessione in una cartella.

## Accedere ad Adobe Campaign {#logon-to-ac}

Gli utenti di Campaign si connettono alla console di Adobe Campaign utilizzando il proprio Adobe ID, tramite Adobe Identity Management System (IMS). Possono utilizzare lo stesso ID per tutte le soluzioni Adobe. Quando si utilizza Adobe Campaign con altre soluzioni la connessione viene salvata. Ulteriori informazioni su Adobe IMS sono disponibili in [questa pagina](https://helpx.adobe.com/it/enterprise/using/identity.html){target="_blank"}.

Per accedere a un’istanza, segui i seguenti passaggi:

1. Avvia la console e sfoglia il collegamento nell’angolo a destra per accedere alla schermata di configurazione della connessione.

   ![](assets/connectToCampaign.png)

1. Seleziona l’istanza di Campaign a cui devi accedere.

1. Fai clic su **[!UICONTROL Ok]**.

Puoi quindi accedere a Campaign con il tuo Adobe ID.

![](assets/adobeID.png)

>[!NOTE]
>
>Poiché Microsoft Edge Webview2 non salva le credenziali proxy, la console potrebbe richiedere l’autenticazione due volte alla prima connessione.

## Aggiornare la console client{#upgrade-ac-console}

Quando il sistema viene aggiornato a una versione più recente, devi aggiornare la console client alla stessa versione. Questa è una best practice e per alcune versioni questo aggiornamento è obbligatorio. In tal caso, viene menzionato nelle [Note sulla versione](release-notes.md).

In qualità di utente di Managed Cloud Services, Adobe distribuisce la console client per te. Quando ti connetti all’ambiente aggiornato, ti viene richiesto di scaricare l’ultima versione della console client in una finestra a comparsa. Devi accettare questo aggiornamento e aggiornare la console client come richiesto.

>[!CAUTION]
>
>Adobe consiglia di lasciare deselezionata l’opzione **[!UICONTROL No longer ask this question]** per assicurarti di ricevere un avviso quando è disponibile una nuova versione della console. Se questa opzione è selezionata, l’utente non viene informato che è necessario un aggiornamento della console.
>



## Concedere l’accesso agli utenti{#grant-access}

Adobe Campaign consente di definire e gestire i diritti assegnati ai vari operatori.

In qualità di amministratore di Campaign, sei responsabile della creazione degli operatori e della condivisione delle relative credenziali con gli utenti.

Ulteriori informazioni sugli utenti e su come definire le relative autorizzazioni sono disponibili in [questa sezione](gs-permissions.md).


## Accedere a Campaign con un browser web {#connect-web-ac}

### Interfaccia utente web {#connect-web-ui}

A partire dalla versione di Campaign v8.6, potrai accedere alla nuova **interfaccia utente web di Campaign**, disponibile nell’ambiente Adobe Experience Cloud centrale. Experience Cloud è un insieme integrato di applicazioni, prodotti e servizi per il marketing digitale di Adobe. Grazie alla sua interfaccia intuitiva, puoi accedere rapidamente alle applicazioni cloud, alle funzionalità dei prodotti e ai servizi.

>[!AVAILABILITY]
>
>L’interfaccia utente di Campaign Web è disponibile solo per gli utenti che si connettono ad Adobe Campaign con il proprio Adobe ID. Ulteriori informazioni su [Adobe Identity Management System (IMS)](https://helpx.adobe.com/it/enterprise/using/identity.html){target="_blank"}.
>

Scopri come connetterti ad Adobe Experience Cloud e come accedere all’interfaccia di Adobe Campaign Web [in questa pagina](campaign-ui.md#ac-web-ui).

Ulteriori informazioni nella [documentazione dell’interfaccia utente di Adobe Campaign Web](https://experienceleague.adobe.com/it/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

### Accesso web {#web-access}

Alcune parti dell’applicazione sono accessibili tramite un browser web che utilizza un’interfaccia utente HTML: reporting, approvazione della consegna, monitoraggio dell’istanza e altro ancora.

L’accesso web fornisce un’interfaccia simile alla console ma con un set ridotto di funzionalità.

Ad esempio, per un dato operatore, viene visualizzata una campagna con le seguenti opzioni nella console:

![](assets/campaign-from-console.png)

Con l’accesso web, invece, le opzioni consentiranno principalmente la visualizzazione di:

![](assets/campaign-from-web.png)

L’accesso web viene utilizzato anche nel processo di convalida: gli operatori possono fare clic sull’e-mail di richiesta di approvazione e connettersi a Campaign tramite il proprio browser web per convalidare o rifiutare il contenuto o il budget di una consegna.

Per accedere all’istanza Campaign dal web, l’URL è: `https://<your adobe campaign server>:<port number>/view/home`.
