---
title: Matrice di compatibilità per Campaign v8
description: Scopri i sistemi e le versioni compatibili con Campaign v8
feature: Release Notes
role: Admin
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
source-git-commit: 329130d716054e5054fc0a5989a77d950c546ec0
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 100%

---

# Matrice di compatibilità per Campaign v8 {#compat-matrix}

Questo documento elenca tutti i sistemi e i componenti supportati dalla build più recente della console client di **Adobe Campaign v8**. Salvo diversa indicazione, sono supportate tutte le versioni minori. I prodotti e le versioni che non fanno parte di questo elenco non sono compatibili con Adobe Campaign.

Quando versioni specifiche di questi sistemi e strumenti di terze parti raggiungono la fine del ciclo di vita (EOL), Adobe Campaign non è più compatibile con tali versioni, che vengono rimosse dalla matrice di compatibilità. Assicurati di disporre delle versioni supportate di tutti i sistemi elencati nella matrice di compatibilità per evitare problemi.

>[!NOTE]
>
>Il server di Adobe Campaign e la console client di Campaign devono avere la stessa versione. [Scopri come controllare la versione](upgrades.md#version).

## Console client {#ClientConsoleoperatingsystems}

Per utilizzare la console client di Campaign sono necessari i seguenti sistemi operativi e browser. [Ulteriori informazioni](connect.md).

### Sistemi operativi {#op-systems}

* **Microsoft Windows Server** 2019, 2016
* **Microsoft Windows** 11, 10

>[!NOTE]
>La versione a 32 bit della console client è obsoleta a partire dalla versione 8.5. A partire dalla versione 8.6, la console client è disponibile solo a 64 bit. Per ulteriori informazioni su come aggiornare il sistema, consulta questa [nota tecnica](../../technotes/upgrades/console.md).

### Browser web {#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**, versione più recente. Scaricala dal [sito per sviluppatori Microsoft](http://www.adobe.com/go/acc-ms-webview2-runtime-download_it){target="_blank"}.

## Connettori CRM {#CRMconnectors}

I sistemi CRM per la gestione delle relazioni con i clienti compatibili con Adobe Campaign sono elencati di seguito. Ulteriori informazioni sui connettori CRM sono disponibili [in questa pagina](../connect/crm.md).

* API connettore **Salesforce** versione 49
* Connettore **Microsoft Dynamics**, API Web: Dynamics 365 on-premise e online

## Federated Data Access (FDA){#FederatedDataAccessFDA}

I database esterni compatibili con il modulo Federated Data Access (FDA) di Adobe Campaign sono elencati di seguito. Ulteriori informazioni sull’FDA sono disponibili [in questa pagina](../connect/fda.md)

* Connettore ODBC **[!DNL Amazon Redshift]**, a partire dalle versioni v8.6.4 / v8.7.1 di Campaign
* **[!DNL Amazon Redshift]** connettore legacy
* **[!DNL Azure Synapse]**, a partire da Campaign v8.5 
* **[!DNL Databricks]**, a partire dalle versioni v8.6.4 / v8.7 di Campaign
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**
* **[!DNL Fabrics]**


>[!AVAILABILITY]
>Inoltre, con il [Componente aggiuntivo di sicurezza avanzato](../config/enhanced-security.md#secure-vpn-tunneling), è possibile accedere ai database on-premise tramite il tunneling VPN sicuro. [Ulteriori informazioni](../config/enhanced-security.md#vpn-callouts)

## SDK per dispositivi mobili {#MobileSDK}

Per inviare [notifiche push](../send/push.md) con Campaign, puoi utilizzare l’SDK di Adobe Experience Platform Mobile configurando l’estensione di Adobe Campaign Classic nell’interfaccia utente di raccolta dati.

Le versioni compatibili per iOS e Android sono descritte in dettagli nella [documentazione di Adobe Developer](https://developer.adobe.com/client-sdks/home/){target="_blank"}.

## Interfaccia utente web {#web-ui}

I seguenti browser sono compatibili con l’interfaccia utente web di Campaign. Ulteriori informazioni sull’interfaccia utente web di Campaign sono disponibili [in questa pagina](campaign-ui.md#ac-web-ui).

* **Microsoft Edge**, **Google Chrome**, **Safari** (versioni più recenti)

## Accesso web {#web-access}

I seguenti browser sono compatibili con Campaign per l’accesso web. Ulteriori informazioni sull’accesso web di Campaign sono disponibili [in questa pagina](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (versioni più recenti)

## Risorse aggiuntive {#support}

* [Aggiornamenti alle versioni di Campaign](upgrades.md)
* [Verificare la versione di Campaign](upgrades.md#version)
* [Installare la console client di Campaign](connect.md)
* [Versioni del Pannello di controllo](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=it){target="_blank"}

Per ricevere informazioni sulle nuove versioni della soluzione Experience Cloud, iscriviti ad [Adobe Priority Product Update](https://www.adobe.com/it/subscription/priority-product-update.html){target="_blank"}.