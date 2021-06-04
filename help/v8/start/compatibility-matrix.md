---
product: Adobe Campaign
title: Matrice di compatibilità per Campaign v8
description: Scopri i sistemi e le versioni compatibili con Campaign v8
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: f7e2581899d965975c129cac530a7edc6a2d55dd
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 75%

---

# Matrice di compatibilità per Campaign v8

Questo documento elenca tutti i sistemi e i componenti supportati dalla build più recente di **Adobe Campaign v8**. I prodotti e le versioni che non fanno parte di questo elenco non sono compatibili con Adobe Campaign.

>[!CAUTION]
>
>* Salvo diversa indicazione, sono supportate tutte le versioni minori.
>* Quando versioni specifiche di questi sistemi e strumenti di terze parti raggiungono la fine del ciclo di vita (EOL), Adobe Campaign non è più compatibile con tali versioni, che vengono rimosse dalla matrice di compatibilità. Assicurati di disporre delle versioni supportate di tutti i sistemi elencati nella matrice di compatibilità per evitare problemi.


## Sistemi compatibili

### Console client{#ClientConsoleoperatingsystems}

:warning: Per utilizzare la console client di Campaign sono necessari i seguenti sistemi operativi e browser.

**Sistemi operativi**

* **Microsoft Windows Server** 2016, 2012
* **Microsoft Windows** 8, 10 (consigliato per le istanze giapponesi))

**Browser**

**Microsoft Internet Explorer** 11

### Connettori CRM{#CRMconnectors}

* API connettore **Salesforce** versione 49
* Connettore **Microsoft Dynamics**, API Web: Dynamics 365 On-premise e online

### Federated Data Access (FDA){#FederatedDataAccessFDA}

* **Amazon Redshift**
* **[!DNL Snowflake]**

### SDK per dispositivi mobili{#MobileSDK}

* **Android** 7.x, 8.x, 9.0 con SDK mobile build 1.0.27.
* **Apple iOS** 9-14 con build 1.0.26 dell’SDK per dispositivi mobili, compatibile con le versioni a 32 e a 64 bit.

### Browser supportati {#Browsers}

I seguenti browser sono compatibili con Campaign per accesso web.

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (versioni più recenti)

* **Internet Explorer** 11

## Controllare la versione di Campaign e costruire

Utilizza il menu **Aiuto > Informazioni su...** per controllare la tua versione.

![](assets/ac-version.png)

Accedi alle seguenti informazioni:

* Numero **versione** della console Client e del server applicazioni. Nell’esempio precedente, la versione è 8.1.5 sia per la console Client che per il server applicazioni.
* Il numero SHA, tra parentesi.
* Un collegamento per contattare l’Assistenza clienti Adobe.
* Collegamenti all’Informativa sulla privacy di Adobe, alle Condizioni d’uso e all’Informativa sui cookie.
