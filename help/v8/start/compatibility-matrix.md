---
title: Matrice di compatibilità per Campaign v8
description: Scopri i sistemi e le versioni compatibili con Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: 83874f4d124d7892f99e973684b1e8ee571f31e0
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 78%

---

# Matrice di compatibilità per Campaign v8

Questo documento elenca tutti i sistemi e i componenti supportati dalla build più recente di **Adobe Campaign v8**. Salvo diversa indicazione, sono supportate tutte le versioni minori. I prodotti e le versioni che non fanno parte di questo elenco non sono compatibili con Adobe Campaign.

Quando versioni specifiche di questi sistemi e strumenti di terze parti raggiungono la fine del ciclo di vita (EOL), Adobe Campaign non è più compatibile con tali versioni, che vengono rimosse dalla matrice di compatibilità. Assicurati di disporre delle versioni supportate di tutti i sistemi elencati nella matrice di compatibilità per evitare problemi.

## Console client{#ClientConsoleoperatingsystems}

Per utilizzare la console client di Campaign sono necessari i seguenti sistemi operativi e browser. [Ulteriori informazioni](connect.md).

### Sistemi operativi

* **Microsoft Windows Server** 2016, 2012
* **Microsoft Windows** 8, 10 (consigliato per le istanze giapponesi))

### Browser

**Microsoft Internet Explorer** 11

>[!NOTE]
>
>Il server Adobe Campaign e la console client devono avere la stessa versione. [Scopri come controllare la tua versione](#version).

## Connettori CRM{#CRMconnectors}

I sistemi di gestione delle relazioni con i clienti (CRM) compatibili con Adobe Campaign sono elencati di seguito. [Ulteriori informazioni](../connect/crm.md).

* API connettore **Salesforce** versione 49
* Connettore **Microsoft Dynamics**, API Web: Dynamics 365 On-premise e online

## Federated Data Access (FDA){#FederatedDataAccessFDA}

I database esterni compatibili con il modulo Adobe Campaign Federated Data Access (FDA) sono elencati di seguito. [Ulteriori informazioni](../connect/fda.md).

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## SDK per dispositivi mobili{#MobileSDK}

Puoi utilizzare Campaign per inviare [notifiche push](../send/push.md) sui sistemi operativi elencati di seguito, utilizzando l’SDK mobile associato.

* **Android** 7.x, 8.x, 9.0 con SDK Campaign Android versione 1.1.1.
* **Apple iOS** 9-14 con SDK Campaign iOS versione 1.0.26, compatibile con le versioni a 32 e a 64 bit.

## Accesso web

I seguenti browser sono compatibili con Campaign per [Web Access](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (versioni più recenti)

* **Internet Explorer** 11

## Controllare la versione di Campaign e la build{#version}

Utilizza il menu **Aiuto > Informazioni su** per controllare la versione in uso.

![](assets/ac-version.png)

Accedi alle seguenti informazioni:

* Il numero di **versione** della tua Client Console e del server applicazioni. Nell’esempio precedente, la versione è 8.1.5 sia per Client Console che per il server applicazioni.
* Il numero SHA, tra parentesi.
* Un collegamento per contattare l’Assistenza clienti di Adobe.
* Collegamenti alla Policy per i cookie, alle Condizioni d’uso e all’Informativa sulla privacy di Adobe.
