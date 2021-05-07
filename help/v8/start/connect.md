---
solution: Campaign
product: Adobe Campaign
title: Scopri come connettersi a Campaign v8
description: Connetti a Campaign v8
feature: Pubblici
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 4%

---

# Connetti ad Adobe Campaign v8{#gs-ac-connect}

Campaign Client Console è un client avanzato che ti consente di connettersi ai server delle applicazioni Campaign.

>[!CAUTION]
>
>Prima di iniziare, devi controllare l’ [Matrice di compatibilità](compatibility-matrix.md) di Campaign, ottenere l’URL del server Campaign e le credenziali utente.

## Scaricare e installare la console client

Quando utilizzi Campaign per la prima volta o se hai bisogno di eseguire l’aggiornamento a una versione più recente, devi scaricare la console Client e installarla.

Sono disponibili due opzioni:

1. In qualità di amministratore di Campaign, collegati ad Adobe [Distribuzione di software](https://experience.adobe.com/#/downloads/content/software-distribution/encampaign.html) e scarica il programma di installazione della console client. È quindi possibile installarlo nel computer locale.

1. In qualità di utente finale, Adobe può distribuire la console per: una volta aggiornata la console, ti verrà richiesto di scaricare la versione più recente della console client in una finestra pop-up.

>[!CAUTION]
>
>Adobe consiglia di lasciare l’opzione **[!UICONTROL No longer ask this question]** deselezionata per fare in modo che tutti gli utenti vengano avvisati quando è disponibile una nuova versione della console.  Se questa opzione è selezionata, l’utente non verrà informato delle nuove versioni disponibili.

## Creare la connessione

Una volta che la Console client è stata appena installata, segui i passaggi seguenti per creare la connessione al server applicazioni:

1. Avviare la console dal menu Windows **[!UICONTROL Start]**, nel gruppo di programmi **Adobe Campaign**.

1. Fai clic sul collegamento nell’angolo in alto a destra dei campi delle credenziali per accedere alla finestra di configurazione della connessione.

1. Fai clic su **[!UICONTROL Add > Connection]** e immetti l’etichetta e l’URL del server dell’applicazione Adobe Campaign.

1. Specifica una connessione al server dell’applicazione Adobe Campaign tramite un URL. Utilizzare un DNS o un alias del computer o l&#39;indirizzo IP.

   Ad esempio, puoi utilizzare l&#39;URL del tipo [`https://<machine>.<domain>.com`](https://myserver.adobe.com).

1. Se Adobe Identity Management System (IMS) è configurato per la tua organizzazione, seleziona l’opzione **[!UICONTROL Connect with an Adobe ID]** .

1. Fai clic su **[!UICONTROL Ok]** per salvare le impostazioni.

Puoi aggiungere tutte le connessioni necessarie per connettersi, ad esempio, agli ambienti di test, stage e produzione.

>[!NOTE]
>
>Il pulsante **[!UICONTROL Add]** consente di creare **[!UICONTROL folders]** per organizzare tutte le connessioni. Trascina e rilascia ciascuna connessione in una cartella.

## Accedere ad Adobe Campaign

Per accedere a un&#39;istanza esistente, segui i passaggi seguenti:

1. Avviare la console dal menu Windows **[!UICONTROL Start]**, nel gruppo di programmi **Adobe Campaign**.

1. Fai clic sul collegamento nell’angolo in alto a destra dei campi delle credenziali per accedere alla finestra di configurazione della connessione.

1. Seleziona l’istanza Campaign a cui devi accedere.

1. Fai clic su **[!UICONTROL Ok]**.

1. Immetti le credenziali di accesso dell’utente e fai clic su **[!UICONTROL LOG IN]**.

   ![](assets/sign-in-v8.png)

A seconda della configurazione, le credenziali possono essere:

* fornito dall’amministratore di Campaign che ti ha concesso l’accesso
* il tuo Adobe ID

## Concedere l’accesso agli utenti

Adobe Campaign ti consente di definire e gestire i diritti assegnati ai vari operatori. Si tratta di una serie di diritti e restrizioni che autorizzano o negano:

* Accesso a determinate funzionalità (tramite i diritti denominati),
* Accesso a determinati elementi,
* Crea, modifica e/o elimina elementi (consegna, contatti, campagne, gruppi, ecc.).

Ulteriori informazioni sugli utenti e su come definirne le autorizzazioni in [questa sezione](permissions.md).

In qualità di amministratore di Campaign, sei responsabile della creazione degli operatori e della condivisione delle loro credenziali con gli utenti.


## Connettiti a Campaign con il tuo Adobe ID{#connect-ims}

Gli utenti di Campaign possono connettersi alla console Adobe Campaign utilizzando il proprio Adobe ID, tramite Adobe Identity Management System (IMS). Questa implementazione offre i seguenti vantaggi:

* Lo stesso ID può essere utilizzato per tutte le soluzioni Experience Cloud.
* Il collegamento viene memorizzato quando si utilizza Adobe Campaign con diverse integrazioni.
* Criteri di gestione password più rigidi.
* Utilizzo di account Federated ID (provider di ID esterno).

:speech_balloon: In qualità di utente di Cloud Services gestiti, [contatta Adobe](support.md#support) per implementare Adobe IMS con Campaign.

## Connettiti a Campaign con il tuo accesso LDAP

Adobe Campaign può essere configurato in modo che l&#39;utente possa accedere alla piattaforma tramite la propria autenticazione LDAP.

:speech_balloon: In qualità di utente di Cloud Services gestiti, [contatta Adobe](support.md#support) per configurare l’integrazione LDAP con Campaign.


## Accesso Web

Alcune parti dell&#39;applicazione sono accessibili tramite un semplice browser web che utilizza un&#39;interfaccia utente HTML: reporting, approvazione della consegna, monitoraggio delle istanze e altro ancora.
