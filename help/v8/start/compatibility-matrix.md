---
title: Matrice di compatibilità per Campaign v8
description: Scopri i sistemi e le versioni compatibili con Campaign v8
feature: Overview
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: dcb12339d891c61f308cf7b7e518784f3ba1ff31
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 81%

---

# Matrice di compatibilità per Campaign v8

Questo documento elenca tutti i sistemi e i componenti supportati dalla build più recente di **Adobe Campaign v8**. Salvo diversa indicazione, sono supportate tutte le versioni minori. I prodotti e le versioni che non fanno parte di questo elenco non sono compatibili con Adobe Campaign.

Quando versioni specifiche di questi sistemi e strumenti di terze parti raggiungono la fine del ciclo di vita (EOL), Adobe Campaign non è più compatibile con tali versioni, che vengono rimosse dalla matrice di compatibilità. Assicurati di disporre delle versioni supportate di tutti i sistemi elencati nella matrice di compatibilità per evitare problemi.

>[!NOTE]
>
>Il server Adobe Campaign e la console client devono avere la stessa versione. [Scopri come controllare la versione](#version).

## Console client{#ClientConsoleoperatingsystems}

Per utilizzare la console client di Campaign sono necessari i seguenti sistemi operativi e browser. [Ulteriori informazioni](connect.md).

>[!NOTE]
>
>La versione a 32 bit della console client diventerà obsoleta nella versione 8.5. A partire dalla versione 8.6, la console client sarà disponibile solo a 64 bit. Per ulteriori informazioni su come aggiornare il sistema operativo, consulta [nota tecnica](https://experienceleague.corp.adobe.com/docs/campaign/technotes-ac/tn-new/console.html).

### Sistemi operativi{#op-systems}

* **Microsoft Windows Server** 2019, 2016, 2012
* **Microsoft Windows** 11, 10, 8

### Browser web{#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**, versione più recente. Scarica dal [sito web per sviluppatori Microsoft](http://www.adobe.com/go/acc-ms-webview2-runtime-download_it){target="_blank"}.

## Connettori CRM{#CRMconnectors}

I sistemi CRM compatibili con Adobe Campaign sono elencati di seguito. [Ulteriori informazioni](../connect/crm.md).

* API connettore **Salesforce** versione 49
* Connettore **Microsoft Dynamics**, API Web: Dynamics 365 on-premise e online

## Federated Data Access (FDA){#FederatedDataAccessFDA}

I database esterni compatibili con il modulo Federated Data Access (FDA) di Adobe Campaign sono elencati di seguito. [Ulteriori informazioni](../connect/fda.md).

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## SDK per dispositivi mobili{#MobileSDK}

Per inviare [notifiche push](../send/push.md) con Campaign, utilizza l’SDK di Adobe Experience Platform Mobile configurando l’estensione Adobe Campaign Classic nell’interfaccia utente di raccolta dati.


## Accesso web{#web-access}

I seguenti browser sono compatibili con Campaign per l’[accesso web](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (versioni più recenti)

## Come selezionare la versione di Campaign{#version}

Utilizza il menu **Aiuto > Informazioni su** per controllare la versione in uso.

![](assets/ac-version.png)

Accedi alle seguenti informazioni:

* Il numero di **versione** della tua Client Console e del server applicazioni. Nell’esempio precedente, la versione è 8.1.5 sia per Client Console che per il server applicazioni.
* Il numero SHA, tra parentesi.
* Un collegamento per contattare l’Assistenza clienti di Adobe.
* Collegamenti alla Policy per i cookie, alle Condizioni d’uso e all’Informativa sulla privacy di Adobe.
